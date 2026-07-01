# -Flexbox
Quyida so'ralgan papkalar tuzilmasi va fayllarning bir-biri bilan qanday bog'lanishi to'liq ko'rsatilgan.

1. Loyiha Tuzilmasi (Folder Structure)
Loyiha papkalari va fayllari quyidagicha joylashishi kerak:

Plaintext
scss/
│
├── abstracts/
│   ├── _variables.scss
│   ├── _mixins.scss
│   ├── _functions.scss
│   └── _index.scss
│
├── base/
│   └── _reset.scss
│
├── components/
│   └── _buttons.scss
│
├── layouts/
│   └── _navbar.scss
│
├── pages/
│   └── _home.scss
│
└── main.scss
2. Abstracts (Abstrakt) Fayllar
abstracts/ papkasidagi fayllar brauzer uchun to'g'ridan-to'g'ri CSS kod ishlab chiqarmaydi, ular faqat boshqa fayllarda ishlatiladigan vositalardir.

abstracts/_variables.scss
SCSS
$color-primary: #3b82f6;
$color-secondary: #64748b;
$space-md: 16px;
abstracts/_mixins.scss
SCSS
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}
abstracts/_functions.scss
SCSS
// Pikselni REM ga o'giruvchi funksiya
@function px-to-rem($px) {
    @return ($px / 16) * 1rem;
}
3. @forward bilan abstracts/_index.scss yaratish
abstracts/ ichidagi barcha vositalarni bitta joyga to'plab, tashqariga uzatish (forward qilish) uchun shu papka ichida _index.scss ochiladi. Bu tashqi fayllarga abstracts papkasini bitta yo'l bilan chaqirish imkonini beradi.

abstracts/_index.scss
SCSS
@forward 'variables';
@forward 'mixins';
@forward 'functions';
4. Komponentlarda Namespace (Nomlar fazosi) ishlatish
Endi components/_buttons.scss faylida abstracts ichidagi o'zgaruvchi va mixinlarni zamonaviy Namespace orqali chaqiramiz.

components/_buttons.scss
SCSS
// abstracts papkasidagi _index.scss ni yuklaymiz. 
// Avtomatik ravishda unga 'abstracts' nomi (namespace) beriladi.
@use '../abstracts';

.btn-primary {
    // Namespace yordamida o'zgaruvchi va funksiyani ishlatish
    background-color: abstracts.$color-primary;
    padding: abstracts.$space-md;
    font-size: abstracts.px-to-rem(18); 
    
    // Mixinni ishlatish
    @include abstracts.flex-center;
}
5. main.scss da barcha fayllarni yig'ish
main.scss — bu loyihaning markaziy fayli bo'lib, u barcha qismlarni @use orqali tartib bilan birlashtiradi va yakuniy bitta CSS fayliga kompilyatsiya qiladi.

main.scss
SCSS
// 1. Strukturasiz (Abstracts) vositalarni yuklash (ixtiyoriy, agar main.scss da ham kerak bo'lsa)
@use 'abstracts';

// 2. Bazaviy stillar
@use 'base/reset';

// 3. Maketlar (Layouts)
@use 'layouts/navbar';

// 4. Komponentlar
@use 'components/buttons';

// 5. Sahifalar (Pages)
@use 'pages/home';
💡 Zamonaviy Sass qoidasi:
Eski @import o'rniga @use va @forward ishlatishning asosiy sababi — global to'qnashuvlarning oldini olishdir. @use yordamida har bir fayl o'z o'zgaruvchilarini shaxsiy "g'aladonda" (Namespace) saqlaydi va kodlar bir-biriga aralashib ketmaydi.
