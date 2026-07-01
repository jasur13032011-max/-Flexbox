# -Flexbox
1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To'liq Ekran Overlay</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="sahifa-kontent">
        <h1>Asosiy Sahifa</h1>
        <p>Ushbu tugmani bossangiz, to'liq ekranli modal oyna ochiladi.</p>
        <button id="ochish-btn" class="ochish-tugma">Overlayni Ochish</button>
    </div>

    <div id="overlay" class="overlay">
        <button id="yopish-btn" class="yopish-tugma">&times;</button>
        
        <div class="modal-kontent">
            <h2>Modal Oyna</h2>
            <p>Bu <code>position: fixed</code> yordamida qilingan to'liq ekranli overlay. U sahifadagi barcha elementlarning ustida turadi.</p>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
2. CSS Fayl (style.css)
CSS
/* Umumiy stillar */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, sans-serif;
}

body {
    background-color: #f1f5f9;
    padding: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

.ochish-tugma {
    padding: 12px 24px;
    font-size: 16px;
    background-color: #3b82f6;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 600;
}

/* --- TO'LIQ EKRAN OVERLAY (`position: fixed`) --- */
.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(15, 23, 42, 0.95); /* To'q shaffof fon */
    
    /* Boshqa barcha elementlardan ustun turishi uchun yuqori z-index */
    z-index: 9999; 
    
    /* Ichidagi kontentni markazlash */
    display: flex;
    justify-content: center;
    align-items: center;
    
    /* Standart holatda yashirin bo'ladi */
    display: none; 
}

/* Overlay ochilganda JS orqali qo'shiladigan klass */
.overlay.active {
    display: flex;
}

/* --- MODAL ICHIDAGI KONTENT --- */
.modal-kontent {
    color: white;
    text-align: center;
    max-width: 500px;
    padding: 20px;
}

.modal-kontent h2 {
    font-size: 32px;
    margin-bottom: 15px;
}

.modal-kontent p {
    color: #cbd5e1;
    font-size: 18px;
    line-height: 1.6;
}

/* --- YOPISH (X) TUGMASI (`position: absolute`) --- */
.yopish-tugma {
    position: absolute;
    top: 25px;
    right: 35px;
    
    background: transparent;
    border: none;
    color: #94a3b8;
    font-size: 45px;
    line-height: 1;
    cursor: pointer;
    transition: color 0.2s;
}

.yopish-tugma:hover {
    color: #ffffff;
}
3. JavaScript Fayl (script.js)
JavaScript
// Elementlarni tanlab olamiz
const ochishBtn = document.getElementById('ochish-btn');
const yopishBtn = document.getElementById('yopish-btn');
const overlay = document.getElementById('overlay');

// Overlayni ochish hodisasi
ochishBtn.addEventListener('click', () => {
    overlay.classList.add('active');
    // Sahifa orqasidagi scrollni to'xtatib turish (ixtiyoriy)
    document.body.style.overflow = 'hidden'; 
});

// Overlayni yopish hodisasi
yopishBtn.addEventListener('click', () => {
    overlay.classList.remove('active');
    // Scrollni qayta tiklash
    document.body.style.overflow = 'auto'; 
});
Qo'llanilgan texnikalar tahlili:
position: fixed (Overlay): Oynani brauzer oynasiga (viewport) nisbatan qotiradi. Sahifa pastga varaqlansa ham (scroll), overlay to'liq ekranni qoplab turaveradi.

z-index: 9999: Yangi yuqori darajali stek kontekstini yaratib, ushbu modal oynani saytdagi boshqa har qanday element (rasmlar, menyular, matnlar) ustiga chiqishini kafolatlaydi.

position: absolute (Yopish tugmasi): × tugmasini faqat o'zining ota-onasi bo'lgan .overlay konteyneriga nisbatan joylashtiradi.
