# -Flexbox
1. Global O'zgaruvchilar Fayli (_variables.scss)
SCSS
// ==========================================
// 1. RANG O'ZGARUVCHILARI (Kamida 8 ta)
// ==========================================
$color-primary:       #3b82f6; // Asosiy ko'k rang
$color-primary-hover: #1d4ed8; // Asosiy rang ustiga borgandagi holat
$color-secondary:     #64748b; // Ikkinchi darajali kulrang
$color-success:       #10b981; // Muvaffaqiyat (yashil)
$color-danger:        #ef4444; // Xatolik/O'chirish (qizil)
$color-bg-main:       #f8fafc; // Sahifaning asosiy foni
$color-bg-card:       #ffffff; // Bloklar va kartalar foni
$color-text-dark:     #0f172a; // To'q matnlar uchun
$color-text-light:    #ffffff; // Yoritilgan matnlar uchun
$color-border:        #e2e8f0; // Chegaralar uchun rang

// ==========================================
// 2. TIPOGRAFIYA O'ZGARUVCHILARI
// ==========================================
$font-size-sm:        0.875rem; // Kichik matnlar (14px)
$font-size-md:        1rem;     // Oddiy matnlar (16px)
$font-size-lg:        1.25rem;  // Katta matnlar (20px)
$font-heading:        2rem;     // Sarlavhalar uchun (32px)
$font-family-base:    'Inter', system-ui, sans-serif;

// ==========================================
// 3. BO'SHLIQ SISTEMI (Spacing System)
// ==========================================
$space-xs:            0.25rem; // 4px
$space-sm:            0.5rem;  // 8px
$space-md:            1rem;    // 16px
$space-lg:            1.5rem;  // 24px
$space-xl:            2rem;    // 32px
$space-2xl:           3rem;    // 48px

// ==========================================
// 4. BORDER-RADIUS VA BOX-SHADOW
// ==========================================
$radius-sm:           4px;
$radius-md:           8px;
$radius-lg:           12px;
$radius-circle:       50%;

$shadow-sm:           0 1px 2px 0 rgba(0, 0, 0, 0.05);
$shadow-md:           0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
$shadow-lg:           0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
2. Navigatsiya Komponenti Fayli (_nav.scss)
SCSS
// O'zgaruvchilarni ulash (Agar alohida faylda bo'lsa)
@import 'variables';

// ==========================================
// 5. SCSS NESTING BILAN NAV KOMPONENTI
// ==========================================
.main-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    
    // O'zgaruvchilardan foydalanish
    background-color: $color-bg-card;
    padding: $space-md $space-lg;
    border-bottom: 1px solid $color-border;
    box-shadow: $shadow-sm;
    font-family: $font-family-base;

    .nav-logo {
        font-size: $font-size-lg;
        font-weight: 700;
        color: $color-text-dark;
        text-decoration: none;
        
        &:hover {
            color: $color-primary;
        }
    }

    .nav-list {
        display: flex;
        gap: $space-md;
        list-style: none;
        margin: 0;
        padding: 0;
    }

    .nav-item {
        // Element ichidagi elementlar (Nesting)
        .nav-link {
            display: inline-block;
            font-size: $font-size-md;
            color: $color-secondary;
            text-decoration: none;
            padding: $space-sm $space-md;
            border-radius: $radius-sm;
            transition: all 0.2s ease-in-out;

            // Uchun :hover holati
            &:hover {
                color: $color-primary-hover;
                background-color: lighten($color-primary, 35%); // SCSS o'rnatilgan funksiyasi
            }

            // Uchun .active holati (Joriy sahifa)
            &.active {
                color: $color-text-light;
                background-color: $color-primary;
                box-shadow: $shadow-md;
                font-weight: 600;
                
                &:hover {
                    background-color: $color-primary-hover;
                }
            }
        }
    }
}
3. Namuna HTML Tuzilishi (index.html)
Ushbu SCSS kodlari brauzerda to'g'ri ko'rinishi uchun HTML quyidagi klaslar ierarxiyasida bo'lishi kerak:

HTML
<nav class="main-nav">
    <a href="#" class="nav-logo">BrendLogo</a>
    
    <ul class="nav-list">
        <li class="nav-item">
            <a href="#" class="nav-link active">Bosh sahifa</a>
        </li>
        <li class="nav-item">
            <a href="#" class="nav-link">Xizmatlar</a>
        </li>
        <li class="nav-item">
            <a href="#" class="nav-link">Loyihalar</a>
        </li>
        <li class="nav-item">
            <a href="#" class="nav-link">Aloqa</a>
        </li>
    </ul>
</nav>
Kodning afzalliklari va tahlili:
Sizga moslashuvchanlik: Dizayn rangini o'zgartirish uchun faqat $color-primary o'zgartirilsa kifoya, .nav-link:hover va .nav-link.active avtomatik ravishda yangi rangga moslashadi.

Toza Nesting: .nav-link ichida yozilgan &:hover brauzerda .main-nav .nav-item .nav-link:hover ko'rinishida CSS ga kompilyatsiya bo'ladi,
