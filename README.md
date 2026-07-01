# -Flexbox
1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tema Almashinuvi</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="konteyner">
        <header class="header">
            <h1 class="sarlavha">Tema Almashish Tizimi</h1>
            <button id="tema-toggle" class="tugma">Rejimni o'zgartirish</button>
        </header>

        <main class="kontent">
            <div class="karta">
                <h2 class="karta-sarlavha">CSS O'zgaruvchilari</h2>
                <p class="matn">
                    Ushbu sahifada birorta ham rang to'g'ridan-to'g'ri yozilmagan. 
                    Barcha ranglar va o'lchamlar <code>:root</code> ichidagi o'zgaruvchilardan olinadi.
                </p>
            </div>
        </main>
    </div>

    <script src="script.js"></script>
</body>
</html>
2. CSS Fayl (style.css)
CSS
/* --- CSS O'ZGARUVCHILARI (:root) --- */
:root {
    /* O'lchamlar (Padding, Margin, Radius) */
    --padding-asosiy: 20px;
    --padding-karta: 25px;
    --radius-burchak: 12px;
    --shrift-katta: clamp(1.8rem, 3vw, 2.5rem);
    --shrift-normal: 1rem;
    --shrift-orta: 1.4rem;

    /* Standart yorug' (light) tema ranglari */
    --rang-fon: #f8fafc;
    --rang-blok: #ffffff;
    --rang-matn-asosiy: #0f172a;
    --rang-matn-tizimli: #475569;
    --rang-asosiy: #3b82f6;
    --rang-asosiy-hover: #1d4ed8;
    --rang-tugma-matn: #ffffff;
    --rang-soya: rgba(0, 0, 0, 0.05);
}

/* --- QORONG'U (DARK) TEMA RANGLARI --- */
[data-theme="dark"] {
    --rang-fon: #0f172a;
    --rang-blok: #1e293b;
    --rang-matn-asosiy: #f8fafc;
    --rang-matn-tizimli: #94a3b8;
    --rang-asosiy: #38bdf8;
    --rang-asosiy-hover: #7dd3fc;
    --rang-tugma-matn: #0f172a;
    --rang-soya: rgba(0, 0, 0, 0.3);
}

/* --- SAHIFA STILLARI (Faqat o'zgaruvchilar bilan) --- */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, sans-serif;
    /* Tema almashganda ranglar silliq o'zgarishi uchun transition */
    transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
}

body {
    background-color: var(--rang-fon);
    color: var(--rang-matn-asosiy);
    padding: var(--padding-asosiy);
}

.konteyner {
    max-width: 800px;
    margin: 0 auto;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: var(--padding-asosiy);
    padding: var(--padding-asosiy) 0;
}

.sarlavha {
    font-size: var(--shrift-katta);
}

/* Tugma stili */
.tugma {
    background-color: var(--rang-asosiy);
    color: var(--rang-tugma-matn);
    padding: 10px 20px;
    border: none;
    border-radius: var(--radius-burchak);
    font-weight: 600;
    font-size: var(--shrift-normal);
    cursor: pointer;
}

.tugma:hover {
    background-color: var(--rang-asosiy-hover);
}

/* Karta stili */
.karta {
    background-color: var(--rang-blok);
    padding: var(--padding-karta);
    border-radius: var(--radius-burchak);
    box-shadow: 0 4px 6px -1px var(--rang-soya);
}

.karta-sarlavha {
    font-size: var(--shrift-orta);
    margin-bottom: 10px;
}

.matn {
    color: var(--rang-matn-tizimli);
    font-size: var(--shrift-normal);
    line-height: 1.6;
}
3. JavaScript Fayl (script.js)
JavaScript
// Tugmani tanlab olamiz
const temaToggleBtn = document.getElementById('tema-toggle');

// HTML elementini tanlab olamiz (data-theme atributini o'zgartirish uchun)
const htmlElement = document.documentElement;

// Tugma bosilganda ishlaydigan funksiya
temaToggleBtn.addEventListener('click', () => {
    // Hozirgi temani tekshiramiz
    const joriyTema = htmlElement.getAttribute('data-theme');
    
    // Agar light bo'lsa dark ga, aks holda light ga o'tkazamiz
    if (joriyTema === 'light') {
        htmlElement.setAttribute('data-theme', 'dark');
    } else {
        htmlElement.setAttribute('data-theme', 'light');
    }
});
Bu tizimning ishlash mexanizmi:
Hech qanday rang CSS ichida to'g'ridan-to'g'ri yozilmadi: Barcha rang beruvchi xossalar (masalan: background-color, color) var(--o'zgaruvchi-nom) ko'rinishida yozildi.

Atribut orqali boshqarish: JavaScript tugma bosilganda HTML tegining data-theme atributini light yoki dark ga o'zgartiradi.

CSS-ning kuchi: [data-theme="dark"] selektori ishga tushganda, barcha o'zgaruvchilar yangi (qorong'u) rang qiymatlarini oladi va butun sahifa avtomatik ravishda yangi ranglarga moslashadi.
