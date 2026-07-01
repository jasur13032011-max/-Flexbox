# -Flexbox
1. Placeholderlar va Komponentlar Fayli (_components.scss)
SCSS
// ==========================================
// 1 & 2. PLACEHOLDERLAR (Sass % Placeholders)
// ==========================================
// %-placeholderlar CSS faylga to'g'ridan-to'g'ri kompilyatsiya bo'lmaydi.
// Ular faqat boshqa klasslar ichida @extend qilingandagina kodni birlashtiradi.

%base-card {
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    background-color: #ffffff;
    border: 1px solid transparent;
}

%flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

// ==========================================
// 3. .ALERT KOMPONENTI (@extend bilan)
// ==========================================
.alert {
    // Baza xususiyatlarini placeholderdan meros qilib olamiz
    @extend %base-card;
    margin-bottom: 15px;
    font-weight: 500;

    // Variantlar
    &--success {
        background-color: #d1fae5;
        color: #065f46;
        border-color: #a7f3d0;
    }

    &--warning {
        background-color: #fef3c7;
        color: #92400e;
        border-color: #fde68a;
    }

    &--error {
        background-color: #fee2e2;
        color: #991b1b;
        border-color: #fca5a5;
    }
}

// ==========================================
// 4. .BADGE KOMPONENTI (4 ta variant)
// ==========================================
.badge {
    // Matnni o'rtalash uchun tayyor placeholderdan foydalanamiz
    @extend %flex-center;
    display: inline-flex; // Badge odatda inline-blok bo'ladi
    padding: 4px 12px;
    font-size: 12px;
    font-weight: 600;
    border-radius: 9999px; // To'liq yumaloq shakl (pill)
    text-transform: uppercase;

    // Variantlar
    &--primary {
        background-color: #3b82f6;
        color: #ffffff;
    }

    &--secondary {
        background-color: #64748b;
        color: #ffffff;
    }

    &--info {
        background-color: #06b6d4;
        color: #ffffff;
    }

    &--dark {
        background-color: #0f172a;
        color: #ffffff;
    }
}

// ==========================================
// 5. @EXTEND VA MIXIN FARQI (IZOH)
// ==========================================
/*
  ========================================================================
  📌 @EXTEND va @MIXIN O'RTASIDAGI ASOSIY FARQLAR:
  
  1. Kodning kompilyatsiya bo'lishi (CSS shakli):
     - @mixin: Uni chaqirgan har bir klass ichiga kodni NUSXALAB (copy-paste) joylashtiradi.
       CSS hajmi kattalashishi mumkin, lekin selektorlar alohida qoladi.
     - @extend: Bir xil kodni ishlatuvchi klasslarni CSS-da vergul bilan BIRLASHTIRADI.
       Masalan, .alert--success, .alert--warning { padding: 20px; ... } shakliga keladi.
       Bu CSS fayl hajmini sezilarli darajada kichraytiradi (DRY prinsipi).

  2. Parametrlar (Argumentlar):
     - @mixin: Dinamik parametrlar qabul qila oladi (masalan: @mixin tugma($rang) ).
     - @extend / Placeholder: Hech qanday parametr qabul qilmaydi, faqat statik kodlarni
       meros qilib beradi.

  💡 Qachon qaysi biri ishlatiladi?
     - Agar elementlaringiz mutqloq bir xil bazaviy stillarga ega bo'lsa (masalan, barcha alertlar),
       @extend (%placeholder) ishlating.
     - Agar stil o'lchamlari yoki ranglari vaziyatga qarab o'zgarishi kerak bo'lsa (dinamik bo'lsa),
       @mixin ishlating.
  ========================================================================
*/
2. Namunaviy HTML Tuzilishi (index.html)
Ushbu komponentlarni brauzerda sinab ko'rish uchun quyidagi HTML klasslaridan foydalanishingiz mumkin:

HTML
<div class="container">
    <div class="alert alert--success">Muvaffaqiyatli bajarildi!</div>
    <div class="alert alert--warning">Diqqat! Tizimda yangilanish kutilmoqda.</div>
    <div class="alert alert--error">Xatolik yuz berdi. Qayta urinib ko'ring.</div>

    <br>

    <span class="badge badge--primary">Yangi</span>
    <span class="badge badge--secondary">Eski</span>
    <span class="badge badge--info">Ma'lumot</span>
    <span class="badge badge--dark">Yopiq</span>
</div>
