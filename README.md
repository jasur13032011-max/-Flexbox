# -Flexbox
HTML va CSS kodlari alohida fayllarga ajratilgan.

1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Grid Maket</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="grid-container">
        <header class="header">
            <h1>Mening Veb-sahifam</h1>
        </header>

        <section class="card card-large">
            <h2>Karta 1 (Kattalashtirilgan)</h2>
            <p>Bu karta <code>grid-column: span 2;</code> xossasi yordamida ikkita ustun kengligini egallab turibdi. Bu muhim yangiliklar yoki katta kontentlar uchun juda qulay.</p>
        </section>

        <section class="card">
            <h2>Karta 2</h2>
            <p>Bu oddiy ustun o'lchamidagi karta. Grid tarmog'ida o'ziga ajratilgan 1 ta ustun joyini egallaydi.</p>
        </section>

        <section class="card">
            <h2>Karta 3</h2>
            <p>Uchinchi karta. CSS Grid avtomatik ravishda elementlarni bo'sh joylarga tartib bilan joylashtiradi.</p>
        </section>

        <section class="card">
            <h2>Karta 4</h2>
            <p>To'rtinchi karta. Elementlar soni ko'paysa, ular keyingi qatorlardan joy olishda davom etadi.</p>
        </section>

        <section class="card">
            <h2>Karta 5</h2>
            <p>Beshinchi karta. Barcha kartalar bir xil tartibda va chiroyli to'r shaklida joylashgan.</p>
        </section>

        <footer class="footer">
            <p>&copy; 2026 Barcha huquqlar himoyalangan.</p>
        </footer>
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
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #f0f2f5;
    padding: 20px;
}

/* --- GRID KONTEYNERI --- */
.grid-container {
    display: grid;
    /* 3 ta teng ustunli to'r yaratish */
    grid-template-columns: repeat(3, 1fr); 
    /* Qatorlar va ustunlar orasidagi masofa */
    gap: 20px; 
    max-width: 1200px;
    margin: 0 auto;
}

/* --- SARLAVHA VA FOOTER --- */
.header, .footer {
    /* 1-chiziqdan boshlab oxirgi chiziqqacha (to'liq kenglik) */
    grid-column: 1 / -1; 
    background-color: #1e293b;
    color: #ffffff;
    padding: 20px;
    text-align: center;
    border-radius: 8px;
}

.header h1 {
    font-size: 24px;
}

/* --- KARTALAR STILI --- */
.card {
    background-color: #ffffff;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.card h2 {
    color: #334155;
    margin-bottom: 10px;
    font-size: 20px;
}

.card p {
    color: #64748b;
    line-height: 1.5;
}

/* --- MAXSUS KARTALAR (Kengaytirilgan) --- */
.card-large {
    /* 2 ta ustun kengligini egallash */
    grid-column: span 2; 
    background-color: #eff6ff; /* Ajralib turishi uchun boshqa rang */
    border-left: 5px solid #3b82f6;
}

/* --- RESPONSIVE (Mobil qurilmalar uchun moslashuvchanlik) --- */
@media (max-width: 768px) {
    .grid-container {
        /* Ekran kichrayganda barcha elementlar 1 ta ustunga aylanadi */
        grid-template-columns: 1fr;
    }
    
    .card-large {
        /* Mobil ekranda katta karta ham 1 ta ustun joy oladi */
        grid-column: auto;
    }
}
Kodning asosiy tushuntirishlari:
grid-template-columns: repeat(3, 1fr);: Konteyner ichida 3 ta teng (1fr yoki fractional unit) ustun hosil qiladi.

grid-column: 1 / -1;: Sarlavha (header) va footer elementlariga birinchi grid chizig'idan boshlab eng oxirgi chiziqqacha cho'zilishni buyuradi. Bu ularning to'liq ekran kengligini egallashini ta'minlaydi.

grid-column: span 2;: Birinchi kartaga odatdagi 1 ta ustun o'rniga, yonidagi qo'shni ustunni ham qo'shib, jami 2 ta ustun kengligida joylashish imkonini beradi.

@media (max-width: 768px): Telefon yoki planshetlarda 3 ta ustun siqilib qolmasligi uchun maketni avtomat ravishda bitta ustunli tartibga (
