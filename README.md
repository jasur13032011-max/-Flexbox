# -Flexbox     
Mana Bootstrap frameworki yordamida so'ralgan barcha komponentlarni (yig'iluvchi navbar, mahsulot kartalari, badgeler, pagination va alert xabari) o'z ichiga olgan to'liq va tayyor andoza (template).

Bunda komponentlarning barchasi Bootstrap 5 ning tayyor klasslari orqali responsive (mobilbop) qilib sozlangan.

1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Do'kon Sahifasi</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <nav class="navbar navbar-expand-lg navbar-dark bg-dark sticky-top">
        <div class="container">
            <a class="navbar-brand fw-bold" href="#">E-Do'kon</a>
            <button class="navbar-toggler" type="text/gradient" data-bs-toggle="collapse" data-bs-target="#mainNavbar">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="mainNavbar">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                    <li class="nav-item"><a class="nav-link active" href="#">Bosh sahifa</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Mahsulotlar</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Chegirmalar</a></li>
                    <li class="nav-item"><a class="nav-link" href="#">Aloqa</a></li>
                </ul>
            </div>
        </div>
    </nav>

    <div class="container my-4">
        <div class="alert alert-success alert-dismissible fade show shadow-sm" role="alert">
            <strong>Aksiya!</strong> Barcha mahsulotlar uchun bugun 20% lik maxsus chegirmalar mavjud!
            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
        </div>

        <h2 class="my-4 fw-bold text-secondary">Yangi Mahsulotlar</h2>

        <div class="row g-4">
            
            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm position-relative product-card">
                    <span class="badge bg-danger position-absolute top-0 start-0 m-3 fs-6">Yangi</span>
                    <div class="card-img-top bg-light text-center py-5 text-muted">Rasm Joyi</div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-bold">Smartfon X10</h5>
                        <p class="card-text text-muted flex-grow-1">Zamonaviy dizayn va yuqori unumdorlikka ega yangi avlod smartfoni.</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold text-primary fs-5">3 500 000 so'm</span>
                            <button class="btn btn-outline-primary btn-sm px-3">Sotib olish</button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm position-relative product-card">
                    <span class="badge bg-warning text-dark position-absolute top-0 start-0 m-3 fs-6">-15%</span>
                    <div class="card-img-top bg-light text-center py-5 text-muted">Rasm Joyi</div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-bold">Simsiz Quloqchin</h5>
                        <p class="card-text text-muted flex-grow-1">Toza ovoz va uzoq muddatga yetuvchi batareya quvvati.</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold text-primary fs-5">450 000 so'm</span>
                            <button class="btn btn-outline-primary btn-sm px-3">Sotib olish</button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm position-relative product-card">
                    <span class="badge bg-success position-absolute top-0 start-0 m-3 fs-6">Top</span>
                    <div class="card-img-top bg-light text-center py-5 text-muted">Rasm Joyi</div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-bold">Aqlli Soat Pro</h5>
                        <p class="card-text text-muted flex-grow-1">Salomatlik ko'rsatkichlari va bildirishnomalarni kuzatish tizimi.</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold text-primary fs-5">1 200 000 so'm</span>
                            <button class="btn btn-outline-primary btn-sm px-3">Sotib olish</button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm position-relative product-card">
                    <span class="badge bg-danger position-absolute top-0 start-0 m-3 fs-6">Yangi</span>
                    <div class="card-img-top bg-light text-center py-5 text-muted">Rasm Joyi</div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-bold">Noutbuk Ultra</h5>
                        <p class="card-text text-muted flex-grow-1">O'qish va ofis ishlari uchun juda yengil va tezkor noutbuk.</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold text-primary fs-5">7 800 000 so'm</span>
                            <button class="btn btn-outline-primary btn-sm px-3">Sotib olish</button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm position-relative product-card">
                    <span class="badge bg-info text-dark position-absolute top-0 start-0 m-3 fs-6">Tavsiya</span>
                    <div class="card-img-top bg-light text-center py-5 text-muted">Rasm Joyi</div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-bold">Powerbank 20K</h5>
                        <p class="card-text text-muted flex-grow-1">Qurilmalaringizni tezkor quvvatlovchi ixcham tashqi akkumulyator.</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold text-primary fs-5">300 000 so'm</span>
                            <button class="btn btn-outline-primary btn-sm px-3">Sotib olish</button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6 col-lg-4">
                <div class="card h-100 shadow-sm position-relative product-card">
                    <span class="badge bg-warning text-dark position-absolute top-0 start-0 m-3 fs-6">-30%</span>
                    <div class="card-img-top bg-light text-center py-5 text-muted">Rasm Joyi</div>
                    <div class="card-body d-flex flex-column">
                        <h5 class="card-title fw-bold">O'yin Sichqonchasi</h5>
                        <p class="card-text text-muted flex-grow-1">RGB yoritgichli va yuqori aniqlikda ishlovchi sensorli sichqoncha.</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold text-primary fs-5">250 000 so'm</span>
                            <button class="btn btn-outline-primary btn-sm px-3">Sotib olish</button>
                        </div>
                    </div>
                </div>
            </div>

        </div> <nav class="my-5">
            <ul class="pagination justify-content-center">
                <li class="page-item disabled"><a class="page-link" href="#">Orqaga</a></li>
                <li class="page-item active"><a class="page-link" href="#">1</a></li>
                <li class="page-item"><a class="page-link" href="#">2</a></li>
                <li class="page-item"><a class="page-link" href="#">3</a></li>
                <li class="page-item"><a class="page-link" href="#">Keyingi</a></li>
            </ul>
        </nav>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
2. CSS Fayl (style.css)
Bootstrap stillarini yanada jozibador ko'rinishga keltirish uchun qo'shimcha maxsus stillar fayli:

CSS
/* Umumiy sahifa foni */
body {
    background-color: #f8fafc;
    font-family: system-ui, -apple-system, sans-serif;
}

/* Mahsulot kartalari uchun animatsiya effekti */
.product-card {
    border: none;
    border-radius: 12px;
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.product-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1) !important;
}

/* Rasm joylashadigan fiktiv blokni bezash */
.card-img-top {
    font-weight: 500;
    font-size: 1.1rem;
    letter-spacing: 1px;
    border-bottom: 1px solid #f1f5f9;
}

/* Badgelarning burchaklarini chiroyli qilish */
.card .badge {
    border-radius: 6px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Pagination dizaynini yumaloqroq qilish */
.page-link {
    border-radius: 6px;
    margin: 0 3px;
    color: #4b5563;
}

.page-item.active .page-link {
    background-color: #3b82f6;
    border-color: #3b82f6;
}
Muhim Bootstrap Klasslari Tahlili:
navbar-expand-lg va collapse navbar-collapse: Bu klaslar navigatsiya menyusining katta ekranlarda to'liq gorizontal, planshet va mobil telefonlarda esa o'ng tomondagi "hamburger" tugmasi ichiga yashirinishini ta'minlaydi.

position-relative va position-absolute: Badgelarni rasm ustiga, aniq yuqori chap burchakka joylashtirish uchun foydalanildi.

d-flex flex-column va flex-grow-1: Har xil matn hajmidan qat'iy nazar, kartalar ichidagi narxlar va "Sotib olish" tugmalarining har doim bir xil chiziqda (karta tubida teppa-teng) turishini kafolatlaydi.

alert-dismissible: Alert xabari chetida uni yopib yuboruvchi × (btn-close) tugmasini ishlatish imkonini beradi.
