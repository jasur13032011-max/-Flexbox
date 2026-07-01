# -Flexbox
1. Mixinlar Fayli (_mixins.scss)
SCSS
// ==========================================
// 1. FLEX-CENTER MIXIN
// ==========================================
// Standart holatda elementlarni to'liq markazlaydi ($justify va $align o'zgartirilishi ham mumkin)
@mixin flex-center($justify: center, $align: center) {
    display: flex;
    justify-content: $justify;
    align-items: $align;
}

// ==========================================
// 2. RESPOND-TO MIXIN (Media Queries)
// ==========================================
// Breakpoint qiymatlarini o'zgaruvchida saqlaymiz
$breakpoints: (
    'sm': 576px,
    'md': 768px,
    'lg': 992px,
    'xl': 1200px
);

@mixin respond-to($breakpoint) {
    // Berilgan breakpoint xaritada borligini tekshiramiz
    @if map-has-key($breakpoints, $breakpoint) {
        $value: map-get($breakpoints, $breakpoint);
        
        @media (max-width: $value) {
            @content;
        }
    } @else {
        @warn "Kechirasiz, bunday breakpoint topilmadi: #{$breakpoint}.";
    }
}

// ==========================================
// 3. BUTTON-VARIANT MIXIN
// ==========================================
// Ranglarni qabul qilib, tugma va uning :hover holatini avtomatlashtiradi
@mixin button-variant($bg, $color) {
    background-color: $bg;
    color: $color;
    border: 1px solid transparent;
    transition: background-color 0.2s ease, transform 0.1s ease;

    &:hover {
        // Rangni avtomatik 10% to'q qilib beradi
        background-color: darken($bg, 10%);
    }

    &:active {
        transform: scale(0.98);
    }
}

// ==========================================
// 4. TRUNCATE MIXIN (Matnni qisqartirish)
// ==========================================
// Berilgan qatorlar sonidan oshganda matn oxiriga uchta nuqta (...) qo'yadi
@mixin truncate($lines: 1) {
    @if $lines == 1 {
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    } @else {
        display: -webkit-box;
        -webkit-line-clamp: $lines;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
}
2. Komponentlar Fayli (_components.scss)
Yuqoridagi barcha mixinlarni haqiqiy hayotiy komponentlarda (Karta va Tugmalar) ishlatib ko'ramiz:

SCSS
@import 'mixins';

// ==========================================
// 5. MIXINLARNING KOMPONENTLARDA ISHLATILISHI
// ==========================================

// --- A) Tugmalar Komponenti (button-variant ishlatilishi) ---
.btn {
    padding: 10px 20px;
    font-size: 1rem;
    font-weight: 600;
    border-radius: 6px;
    cursor: pointer;

    // Mixin yordamida har xil variantlarni yaratamiz
    &--primary {
        @include button-variant(#3b82f6, #ffffff);
    }

    &--success {
        @include button-variant(#10b981, #ffffff);
    }

    &--danger {
        @include button-variant(#ef4444, #ffffff);
    }
}

// --- B) Profil Kartasi Komponenti (Barcha mixinlar jamlanmasi) ---
.profile-card {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 12px;
    padding: 24px;
    max-width: 350px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);

    // 1. flex-center mixin: Avatar va ma'lumotlarni vertikal tekislaydi
    &__header {
        @include flex-center(flex-start, center);
        gap: 16px;
        margin-bottom: 16px;
    }

    &__avatar {
        width: 50px;
        height: 50px;
        border-radius: 50%;
        background-color: #cbd5e1;
        // Ichidagi ikonkani markazlash uchun yana flex-center
        @include flex-center(); 
    }

    // 4. truncate mixin: Karta sarlavhasi va matnlarini jilovlash
    &__title {
        font-size: 1.25rem;
        font-weight: 700;
        margin-bottom: 4px;
        @include truncate(1); // Ism juda uzun bo'lsa 1 qatorda kesiladi
    }

    &__bio {
        font-size: 0.9rem;
        color: #64748b;
        line-height: 1.5;
        margin-bottom: 20px;
        @include truncate(3); // Bioografiya 3 qatordan oshsa ... bo'ladi
    }

    // 2. respond-to mixin: Kichik (Mobil) ekranda kartani moslashtirish
    @include respond-to('md') {
        max-width: 100%; // Mobil ekranda to'liq kenglikni oladi
        padding: 16px;

        &__header {
            flex-direction: column; // Rasmni tepaga, matnni pastga tushiradi
            text-align: center;
            @include flex-center(center, center);
        }
    }
}
Kodlar Tahlili:
@include flex-center(): Kodni qayta yozishdan asraydi, display: flex, justify-content kabilarni bir qatorda hal qiladi.

@include respond-to('md'): CSS ichida chalkash media-query yozishni yo'qotadi va komponentga tegishli responsiv kodni komponentning o'z ichida saqlashga yordam beradi.

@include truncate(3): CSS-ning eski va murakkab
