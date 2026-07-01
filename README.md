# -Flexbox     
1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap Modal va Forma Validatsiyasi</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.0/font/bootstrap-icons.css" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container text-center my-5">
        <h1>Ro'yxatdan o'tish tizimi</h1>
        <p>Formani to'ldirish uchun quyidagi tugmani bosing.</p>
        <button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#registrationModal">
            Anketani to'ldirish
        </button>
    </div>

    <div class="modal fade" id="registrationModal" tabindex="-1" aria-labelledby="modalTitle" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content">
                
                <div class="modal-header">
                    <h5 class="modal-title fw-bold" id="modalTitle">Yangi foydalanuvchi anketasi</h5>
                    <button type="button" class="btn-close" data-bs-shadow="none" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>

                <form id="regForm" class="needs-validation" novalidate>
                    <div class="modal-body text-start">
                        
                        <div class="mb-3">
                            <label for="fullName" class="form-label">To'liq ismingiz</label>
                            <input type="text" class="form-control" id="fullName" required minlength="3">
                            <div class="invalid-feedback">Iltimos, ismingizni kiriting (kamida 3 ta harf).</div>
                            <div class="valid-feedback">Ajoyib!</div>
                        </div>

                        <div class="mb-3">
                            <label for="username" class="form-label">Foydalanuvchi nomi (Username)</label>
                            <div class="input-group has-validation">
                                <span class="input-group-text" id="addon-wrapping">@</span>
                                <input type="text" class="form-control" id="username" aria-describedby="addon-wrapping" required>
                                <div class="invalid-feedback">Yagona foydalanuvchi nomini kiritish majburiy.</div>
                            </div>
                        </div>

                        <div class="mb-3">
                            <label for="email" class="form-label">Elektron pochta</label>
                            <div class="input-group">
                                <span class="input-group-text"><i class="bi bi-envelope"></i></span>
                                <input type="email" class="form-control" id="email" placeholder="example@mail.com" required>
                                <div class="invalid-feedback">To'g'ri email manzilini kiriting.</div>
                            </div>
                        </div>

                        <div class="mb-3">
                            <label for="phone" class="form-label">Telefon raqam</label>
                            <div class="input-group">
                                <span class="input-group-text">+998</span>
                                <input type="tel" class="form-control" id="phone" placeholder="901234567" pattern="[0-9]{9}" required>
                                <div class="invalid-feedback">9 xonali telefon raqamini kiriting (Masalan: 901234567).</div>
                            </div>
                        </div>

                        <div class="mb-3">
                            <label for="course" class="form-label">Yo'nalishni tanlang</label>
                            <select class="form-select" id="course" required>
                                <option selected disabled value="">Tanlang...</option>
                                <option value="frontend">Frontend Dasturlash</option>
                                <option value="backend">Backend Dasturlash</option>
                                <option value="design">UI/UX Dizayn</option>
                            </select>
                            <div class="invalid-feedback">Iltimos, yo'nalishlardan birini tanlang.</div>
                        </div>

                    </div>

                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Yopish</button>
                        <button type="submit" class="btn btn-success">Ma'lumotlarni yuborish</button>
                    </div>
                </form>

            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script src="script.js"></script>
</body>
</html>
2. CSS Fayl (style.css)
Forma va modalning ko'rinishini yanada mukammallashtirish uchun qo'shimcha stillar:

CSS
body {
    background-color: #f3f4f6;
    font-family: system-ui, -apple-system, sans-serif;
}

/* Modalning chetlarini yumaloq qilish */
.modal-content {
    border: none;
    border-radius: 16px;
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
}

.modal-header {
    border-bottom: 1px solid #f1f5f9;
    background-color: #fafafa;
    border-top-left-radius: 16px;
    border-top-right-radius: 16px;
}

.modal-footer {
    border-top: 1px solid #f1f5f9;
    background-color: #fafafa;
    border-bottom-left-radius: 16px;
    border-bottom-right-radius: 16px;
}

/* Fokus bo'lganda input guruhlarining chiroyli ko'rinishi */
.form-control:focus, .form-select:focus {
    border-color: #3b82f6;
    box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.25);
}
3. JavaScript Fayl (script.js)
Bootstrap-ning rasmiy shakl (form) validatsiyasini faollashtiruvchi va xatoliklarni tekshiruvchi skript:

JavaScript
document.addEventListener('DOMContentLoaded', () => {
    // Sahifadagi barcha validatsiya kerak bo'lgan formalarni olamiz
    const forms = document.querySelectorAll('.needs-validation');

    // Formalar bo'ylab tsikl aylantiramiz va yuborishni (submit) tekshiramiz
    Array.from(forms).forEach(form => {
        form.addEventListener('submit', event => {
            
            // Agar forma to'g'ri to'ldirilmagan bo'lsa, yuborishni to'xtatadi
            if (!form.checkValidity()) {
                event.preventDefault();
                event.stopPropagation();
            } else {
                // Agar hammasi to'g'ri bo'lsa, xabar chiqaradi (Real loyihada bu yerda API ga yuboriladi)
                alert("Tabriklaymiz! Anketa muvaffaqiyatli yuborildi.");
            }

            // Bootstrap-ning validatsiya klasini qo'shadi (yashil/qizil ranglarni ko'rsatish uchun)
            form.classList.add('was-validated');
            
        }, false);
    });
});
Amaldagi texnikalar tahlili:
Modal ishlashi (data-bs-toggle="modal"): JS kod yozmasdan, faqat HTML atributlar orqali modal ochiladi va data-bs-dismiss="modal" yordamida yopiladi hamda footer tugmalari to'g'ri ishlaydi.

4+ Maydonlar (Fields): Formada jami 5 ta turli xil maydon bor (Ism, Username, Email, Telefon, Kurs select-opsiyasi).

Input Group: @, pochta ikonka va +998 kabi elementlar input-group va input-group-text klaslari orqali inputlar bilan birlashtirilgan.

Validatsiya holatlari: Inputlardagi required, minlength, pattern atributlari xatoliklarni aniqlaydi. .invalid-feedback va
