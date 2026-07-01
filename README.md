# -Flexbox     
Faqatgina Bootstrap 5 ning tayyor klasslaridan (hech qanday shaxsiy CSS kodlarsiz) foydalanib tayyorlangan, ichida rounded-circle avatar, rol ko'rsatilgan badge, flex utilitilari va Bootstrap ikonkalari mavjud bo'lgan profil kartasi (User Profile Card) komponenti.

HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Profil Kartasi</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.0/font/bootstrap-icons.css" rel="stylesheet">
</head>
<body class="bg-light d-flex justify-content-center align-items-center min-vh-100">

    <div class="card shadow-sm border-0 p-4 text-center" style="max-width: 350px; border-radius: 16px;">
        
        <div class="text-end mb-2">
            <span class="badge bg-primary-subtle text-primary px-3 py-2 rounded-pill fw-semibold">
                Admin
            </span>
        </div>

        <div class="d-flex justify-content-center mb-3">
            <div class="position-relative">
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=150&auto=format&fit=crop&q=80" 
                     alt="Avatar" 
                     class="rounded-circle border border-4 border-white shadow-sm"
                     style="width: 100px; height: 100px; object-fit: cover;">
                <span class="position-absolute bottom-0 end-0 p-2 bg-success border border-2 border-white rounded-circle"></span>
            </div>
        </div>

        <h5 class="fw-bold text-dark mb-1">Malika Axmedova</h5>
        <p class="text-muted small mb-3">Senior UI/UX Designer</p>

        <div class="d-flex justify-content-center gap-3 mb-4">
            <a href="#" class="btn btn-light rounded-circle p-2 d-flex align-items-center justify-content-center text-secondary" style="width: 40px; height: 40px;">
                <i class="bi bi-envelope-fill fs-5"></i>
            </a>
            <a href="#" class="btn btn-light rounded-circle p-2 d-flex align-items-center justify-content-center text-secondary" style="width: 40px; height: 40px;">
                <i class="bi bi-telegram fs-5"></i>
            </a>
            <a href="#" class="btn btn-light rounded-circle p-2 d-flex align-items-center justify-content-center text-secondary" style="width: 40px; height: 40px;">
                <i class="bi bi-linkedin fs-5"></i>
            </a>
        </div>

        <div class="d-grid">
            <button class="btn btn-primary fw-medium py-2 rounded-3 d-flex align-items-center justify-content-center gap-2">
                <i class="bi bi-person-plus-fill"></i> Profilni ko'rish
            </button>
        </div>

    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
Ishlatilgan Bootstrap Utilitilari Tahlili:
rounded-circle: Rasm burchaklarini to'liq yumaloq qilib, mukammal avatar shakliga keltirish uchun ishlatildi.

badge bg-primary-subtle text-primary: Rolni (Admin) chiroyli, yumshoq ko'k fonda va to'q ko'k matnda ko'rsatish uchun xizmat qiladi.

d-flex justify-content-center align-items-center: Elementlarni (ham markaziy kartani, ham karta ichidagi tugma va belgilarni) mukammal darajada o'rtalash va tartiblash uchun qo'llanilgan flex xossalari.

bi bi-...: Bootstrap Icons kutubxonasidan aloqa tugmalari va asosiy tugma ichidagi ikonkalarni (envelope-fill, telegram, linkedin, person-plus-fill) chiqarish uchun foydalanildi.

shadow-sm border-0: Kartaga custom CSS yozmasdan, nafis soya berish va uning standart qora chegaralarini olib tashlash imkonini berdi.
