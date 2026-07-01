# -Flexbox
Mana so'ralgan barcha talablar (CSS Grid maketi, @media so'rovi va matnlar uchun clamp() funksiyasi) asosida tayyorlangan kodlar.

1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsiv Maket (Clamp)</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="sahifa-konteyner">
        <aside class="sidebar">
            <h2 class="kichik-sarlavha">Navigatsiya</h2>
            <ul>
                <li><a href="#">Bosh sahifa</a></li>
                <li><a href="#">Ma'lumotlar</a></li>
                <li><a href="#">Sozlamalar</a></li>
            </ul>
        </aside>

        <main class="kontent">
            <h1 class="katta-sarlavha">Responsiv Matn va Grid Maketi</h1>
            <p class="matn">
                Ushbu sahifadagi sarlavhalar va matn o'lchami <code>clamp()</code> funksiyasi yordamida qilingan. 
                Ekran o'lchamiga qarab matnlar hech qanday uzilishlarsiz, silliq ravishda kattalashadi yoki kichrayadi.
            </p>
            <p class="matn">
                Katta ekranda chap tomonda sidebar va o'ng tomonda kontent ko'rinadi. 
                Ekran kengligi 768px dan kichrayganda esa, ular avtomatik ravishda bitta ustunga tartiblanadi.
            </p>
        </main>
    </div>

</body>
</html>
2. CSS Fayl (style.css)
CSS
/* Umumiy stillar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', system-ui, sans-serif;
}

body {
    background-color: #f8fafc;
    color: #334155;
    padding: 20px;
}

/* --- CLAMP() BILAN RESPONSIV MATNLAR --- */
/* clamp(minimal_o'lcham, o'rtacha_o'lcham, maksimal_o'lcham) */
.katta-sarlavha {
    font-size: clamp(1.8rem, 4vw + 1rem, 3rem);
    line-height: 1.2;
    margin-bottom: 15px;
    color: #0f172a;
}

.kichik-sarlavha {
    font-size: clamp(1.3rem, 2vw + 1rem, 1.8rem);
    margin-bottom: 10px;
}

.matn {
    font-size: clamp(1rem, 0.5vw + 0.9rem, 1.2rem);
    line-height: 1.6;
    margin-bottom: 15px;
}

/* --- GRID MAKETI (Katta ekran uchun) --- */
.sahifa-konteyner {
    display: grid;
    /* Chapda 250px li sidebar, o'ngda qolgan barcha joyni oluvchi kontent */
    grid-template-columns: 250px 1fr; 
    gap: 20px;
    max-width: 1200px;
    margin: 0 auto;
}

.sidebar {
    background-color: #0f172a;
    color: #ffffff;
    padding: 25px;
    border-radius: 12px;
}

.sidebar ul {
    list-style: none;
}

.sidebar ul li {
    margin-bottom: 12px;
}

.sidebar ul li a {
    color: #cbd5e1;
    text-decoration: none;
    transition: color 0.2s;
}

.sidebar ul li a:hover {
    color: #38bdf8;
}

.kontent {
    background-color: #ffffff;
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

/* --- MEDIA SO'ROVI (Kichik ekranlar uchun) --- */
@media (max-width: 768px) {
    .sahifa-konteyner {
        /* Kichik ekranda 2 ta ustun 1 ta ustunga aylanadi */
        grid-template-columns: 1fr;
    }
}
Texnologiyalar tushuntirishi:
clamp() funksiyasi: Matn o'lchamini dinamik boshqaradi. Masalan, clamp(1.8rem, 4vw + 1rem, 3rem) sarlavha o'lchami eng kichik ekranda 1.8rem dan kamayib ketmasligini, eng katta ekranda 3rem dan oshmasligini va ular orasida ekranning kengligiga (4vw) qarab silliq o'zgarishini ta'minlaydi.

grid-template-columns: 250px 1fr;: Katta ekranlarda yon panelni aniq 250 piksel, asosiy qismni esa qolgan hamma bo'sh joyni egallaydigan qiladi.

@media (max-width: 768px): Ekran kengligi 768px yoki undan kichik bo'lganda gridni 1fr (ya'ni 1 ta ustun) holatiga o'tkazadi va natijada sidebar kontentning tepasiga chiqib qoladi.
