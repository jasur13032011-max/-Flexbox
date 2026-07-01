# -Flexbox
Bootstrap yoki maxsus yaratilgan CSS framework uslubida 6 ta kartadan iborat to'liq responsiv maket (layout). Bu yerda container, row, col-* sinflari va kartalarning har xil ekranlarda qanday joylashishi aniq ko'rsatilgan.

1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Grid Maketi</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container my-5">
        
        <div class="row g-4">
            
            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm border-0">
                    <div class="card-body">
                        <h5 class="card-title">Karta 1</h5>
                        <p class="card-text">Bu birinchi karta. Katta ekranda u 3 ta ustundan birini egallaydi.</p>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm border-0">
                    <div class="card-body">
                        <h5 class="card-title">Karta 2</h5>
                        <p class="card-text">Bu ikkinchi karta. Planshet ekranida u yonma-yon joylashishni boshlaydi.</p>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm border-0">
                    <div class="card-body">
                        <h5 class="card-title">Karta 3</h5>
                        <p class="card-text">Bu uchinchi karta. shadow-sm yordamida yengil soya berilgan.</p>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm border-0">
                    <div class="card-body">
                        <h5 class="card-title">Karta 4</h5>
                        <p class="card-text">To'rtinchi karta. g-4 orqali qatorlar orasida ham masofa saqlanadi.</p>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm border-0">
                    <div class="card-body">
                        <h5 class="card-title">Karta 5</h5>
                        <p class="card-text">Beshinchi karta. h-100 klassi hamma kartalar bo'yini tenglashtiradi.</p>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm border-0">
                    <div class="card-body">
                        <h5 class="card-title">Karta 6</h5>
                        <p class="card-text">Oltinchi karta. Ekran torayganda bu karta ham to'liq kenglikka o'tadi.</p>
                    </div>
                </div>
            </div>

        </div> </div> </body>
</html>
2. CSS Fayl (style.css)
Bootstrap o'zining tayyor stillariga ega bo'lsa-da, dizaynni yanada chiroyli qilish uchun qo'shimcha CSS fayli:

CSS
/* Qo'shimcha shaxsiy stillar */
body {
    background-color: #f4f6f9;
    font-family: system-ui, -apple-system, sans-serif;
}

/* Kartalarni vizual bezash */
.card {
    background-color: #ffffff;
    border-radius: 10px;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

/* Sichqoncha karta ustiga kelganda effekt (ixtiyoriy) */
.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1) !important;
}

.card-title {
    color: #1e293b;
    font-weight: 600;
}

.card-text {
    color: #64748b;
    line-height: 1.6;
}
Ustunlar kombinatsiyasi qanday ishlaydi?
col-12: Mobil ekranlarda (kengligi 576px gacha bo'lgan qurilmalarda) har bir karta butun qatorni egallaydi (1 qatorda 1 tadan karta).

col-sm-6: Kichik ekranlarda (planshetlarda, 576px va undan katta) har bir karta yarim kenglikni oladi (12/6=2, ya'ni 1 qatorda 2 tadan karta).

col-lg-4: Katta ekranlarda (kompyuterlarda, 992px va undan katta) har bir karta uchdan bir qismni oladi (12/4=3, ya'ni 1 qatorda 3 tadan karta). Natijada 6 ta karta chiroyli bo'lib 2 qatorga taxlanadi.

g-4: Kartalar orasida gorizontal va vertikal ravishda 1.5rem (24px) bo'shliq (gap) hosil qiladi.

shadow-sm: Kartalarga nafis, ko'zga og'irlik qilmaydigan kichik soya beradi.
