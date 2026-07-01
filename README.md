# -Flexbox
Mana Flexbox yordamida so'ralgan talablar asosida tayyorlangan kodlar to'plami. HTML va CSS alohida fayllarga ajratilgan.

1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox Maket</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header class="navbar">
        <div class="logo">MeningLogo</div>
        <nav class="nav-menu">
            <a href="#">Bosh sahifa</a>
            <a href="#">Xizmatlar</a>
            <a href="#">Biz haqimizda</a>
            <a href="#">Aloqa</a>
        </nav>
    </header>

    <main class="card-container">
        <div class="card">
            <h3>Karta 1</h3>
            <p>Bu birinchi karta uchun matn. Flexbox yordamida barcha kartalar teng kenglikda joylashadi.</p>
        </div>
        <div class="card">
            <h3>Karta 2</h3>
            <p>Bu ikkinchi karta uchun matn. Ekran kichrayganda bu kartalar pastga tartib bilan tushadi.</p>
        </div>
        <div class="card">
            <h3>Karta 3</h3>
            <p>Bu uchinchi karta uchun matn. flex-wrap xossasi aynan shu moslashuvchanlikni ta'minlaydi.</p>
        </div>
    </main>

</body>
</html>
2. CSS Fayl (style.css)
CSS
/* Umumiy stillar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #f4f6f9;
    padding: 20px;
}

/* --- NAVIGATSIYA (Flexbox) --- */
.navbar {
    display: flex;
    justify-content: space-between; /* Logotip chapda, menu o'ngda */
    align-items: center;           /* Vertikal bo'yicha markazlash */
    background-color: #ffffff;
    padding: 15px 30px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    margin-bottom: 30px;
}

.logo {
    font-size: 24px;
    font-weight: bold;
    color: #333;
}

.nav-menu a {
    text-decoration: none;
    color: #555;
    margin-left: 20px;
    font-weight: 500;
    transition: color 0.3s;
}

.nav-menu a:hover {
    color: #007bff;
}

/* --- KARTALAR (Flexbox & Wrap) --- */
.card-container {
    display: flex;
    flex-wrap: wrap;       /* Kichik ekranda kartalarni pastga tushiradi */
    gap: 20px;             /* Kartalar orasidagi masofa */
}

.card {
    /* flex: grow shrink basis */
    /* 1 (teng o'sadi), 1 (teng kichrayadi), calc(...) -> 3 ta karta orasidagi 2 ta gap (20px * 2 = 40px) ayirib tashlanadi */
    flex: 1 1 calc((100% - 40px) / 3); 
    
    background-color: #ffffff;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    border-top: 4px solid #007bff;
    
    /* Mobil qurilmalarda karta juda kichrayib ketmasligi uchun minimal kenglik */
    min-width: 280px; 
}

.card h3 {
    margin-bottom: 12px;
    color: #222;
}

.card p {
    color: #666;
    line-height: 1.6;
}
Kodning asosiy qismlari:
justify-content: space-between;: Navigatsiya panelida logotipni eng chapga, menyuni esa eng o'ngga surib beradi.

flex-wrap: wrap;: Agarda ekran kengligi 3 ta kartani bir qatorga sig'dira olmasa (masalan, telefonda), kartalarni avtomatik ravishda keyingi qatorga o'tkazadi.

flex: 1 1 calc(...): Kartalarning kengligi har doim bir xil (teng) bo'lishini va umumiy joyni 3 ga teng bo'lishini ta'minlaydi.
