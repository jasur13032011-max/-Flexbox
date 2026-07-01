# -Flexbox
Sass (SCSS) tilidagi sikllar (@each, @for) va shart operatorlari (@if, @else) yordamida loyihalar uchun juda qisqa kod bilan yuzlab utility (yordamchi) klasslarni avtomatik generatsiya qilish mumkin.

Quyida Tailwind CSS yoki Bootstrap uslubidagi utility klasslarni generatsiya qiluvchi to'liq SCSS kodi keltirilgan. Bu kod jami 50 tadan ko'p foydali klasslarni tayyorlab beradi.

Utility Generator SCSS Kodi
SCSS
// ==========================================
// 1. MAP'LAR (Ma'lumotlar ombori)
// ==========================================

// Ranglar xaritasi (8 ta rang variantlari)
$colors: (
    "primary":   #3b82f6,
    "secondary": #64748b,
    "success":   #10b981,
    "danger":    #ef4444,
    "warning":   #f59e0b,
    "info":      #06b6d4,
    "dark":      #0f172a,
    "light":     #f8fafc
);

// Bo'shliqlar xaritasi (6 ta o'lcham variantlari)
$spacings: (
    "0": 0,
    "1": 4px,
    "2": 8px,
    "3": 16px,
    "4": 24px,
    "5": 32px
);

// ==========================================
// 2. @EACH BILAN RANGLAR UTILITY (16 ta klass)
// ==========================================
// .text-{color} va .bg-{color} klasslarini yaratadi
@each $name, $value in $colors {
    .text-#{$name} {
        color: $value;
    }
    .bg-#{$name} {
        background-color: $value;
    }
}

// ==========================================
// 3. @EACH BILAN SPACING UTILITY (18 ta klass)
// ==========================================
// .mt-{n}, .mb-{n} va .p-{n} klasslarini yaratadi
@each $key, $val in $spacings {
    .mt-#{$key} {
        margin-top: $val;
    }
    .mb-#{$key} {
        margin-bottom: $val;
    }
    .p-#{$key} {
        padding: $val;
    }
}

// ==========================================
// 4. @FOR BILAN GRID COLUMNS (12 ta klass)
// ==========================================
// .col-1 dan .col-12 gacha kenglik klasslarini yaratadi
@for $i from 1 through 12 {
    .col-#{$i} {
        width: ($i / 12) * 100%;
        box-sizing: border-box;
    }
}

// ==========================================
// 5. @IF / @ELSE BILAN TEMA UTILITY (4 ta klass)
// ==========================================
// Loyihada qaysi tema yoqilganiga qarab maxsus yordamchi klasslar beradi
$theme-mode: "dark"; // "light" qilib o'zgartirish mumkin

@if $theme-mode == "dark" {
    .theme-panel {
        background-color: map-get($colors, "dark");
        color: map-get($colors, "light");
    }
    .theme-border {
        border-color: map-get($colors, "secondary");
    }
} @else {
    .theme-panel {
        background-color: map-get($colors, "light");
        color: map-get($colors, "dark");
    }
    .theme-border {
        border-color: map-get($colors, "light");
    }
}
Kompilyatsiyadan keyingi yakuniy CSS ko'rinishi (Guvoh bo'ling):
Sass ushbu kodni oddiy CSS-ga o'gorganda, avtomatik ravishda 50 ta klass hosil bo'ladi:

Ranglar (16 ta): .text-primary, .bg-primary, .text-secondary, .bg-secondary ... va h.k.

Bo'shliqlar (18 ta): * .mt-0, .mt-1, .mt-2, .mt-3, .mt-4, .mt-5 (6 ta)

.mb-0, .mb-1, .mb-2, .mb-3, .mb-4, .mb-5 (6 ta)

.p-0, .p-1, .p-2, .p-3, .p-4, .p-5 (6 ta)

Grid ustunlari (12 ta): .col-1 (width: 8.33%), .col-2 (width: 16.66%) ... .col-12 (width: 100%).

Tema (2 ta): .theme-panel va .theme-border.

Jami: 16 + 18 + 12 + 2 = 48 ta asosiy klass. Agar xaritaga yana 1 tadan qiymat qo'shsangiz, klasslar soni darrov 60 tadan oshib ketadi.

HTML-da ishlatish namunasi:
HTML
<div class="theme-panel p-3 mb-4 col-6">
    <h2 class="text-primary">Klasslar avtomatlashgan!</h2>
    <p class="text-secondary mt-2">Bu juda qulay tizim.</p>
    <button class="bg-success text-light p-2 mt-3">Tasdiqlash</button>
</div>
