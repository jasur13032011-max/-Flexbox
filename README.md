# -Flexbox     
1. HTML Fayl (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Panel Dashboard</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.0/font/bootstrap-icons.css" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="d-flex">
        <aside class="sidebar bg-dark text-white p-3 min-vh-100 d-none d-md-block" id="sidebarMenu">
            <div class="fs-4 fw-bold text-center py-3 border-bottom border-secondary mb-4">
                <i class="bi bi-speedometer2"></i> AdminPanel
            </div>
            <ul class="nav nav-pills flex-column mb-auto gap-2">
                <li class="nav-item">
                    <a href="#" class="nav-link active text-white"><i class="bi bi-house-door me-2"></i> Bosh sahifa</a>
                </li>
                <li>
                    <a href="#" class="nav-link text-secondary"><i class="bi bi-people me-2"></i> Mijozlar</a>
                </li>
                <li>
                    <a href="#" class="nav-link text-secondary"><i class="bi bi-graph-up me-2"></i> Analitika</a>
                </li>
                <li>
                    <a href="#" class="nav-link text-secondary"><i class="bi bi-gear me-2"></i> Sozlamalar</a>
                </li>
            </ul>
        </aside>

        <div class="flex-grow-1 bg-light min-vh-100">
            
            <nav class="navbar navbar-expand navbar-white bg-white shadow-sm px-4 py-3">
                <div class="container-fluid p-0 d-flex justify-content-between align-items-center">
                    <button class="btn btn-outline-dark d-md-none me-2" type="button" data-bs-toggle="collapse" data-bs-target="#mobileSidebar">
                        <i class="bi bi-list"></i>
                    </button>
                    
                    <h5 class="m-0 fw-bold d-none d-sm-block">Asosiy Oyna</h5>
                    
                    <div class="dropdown">
                        <a href="#" class="d-flex align-items-center text-decoration-none dropdown-toggle text-dark" data-bs-toggle="dropdown">
                            <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=50&auto=format&fit=crop&q=80" alt="avatar" width="32" height="32" class="rounded-circle me-2">
                            <span class="d-none d-sm-inline">Malika A.</span>
                        </a>
                        <ul class="dropdown-menu dropdown-menu-end shadow">
                            <li><a class="dropdown-menu-item p-2 px-3 text-dark d-block text-decoration-none" href="#">Profil</a></li>
                            <li><hr class="dropdown-divider"></li>
                            <li><a class="dropdown-menu-item p-2 px-3 text-danger d-block text-decoration-none" href="#">Chiqish</a></li>
                        </ul>
                    </div>
                </div>
            </nav>

            <div class="collapse d-md-none bg-dark text-white p-3" id="mobileSidebar">
                <ul class="nav nav-pills flex-column gap-2">
                    <li><a href="#" class="nav-link active text-white">Bosh sahifa</a></li>
                    <li><a href="#" class="nav-link text-secondary">Mijozlar</a></li>
                    <li><a href="#" class="nav-link text-secondary">Analitika</a></li>
                </ul>
            </div>

            <main class="p-4">
                
                <div class="row g-3 mb-4">
                    <div class="col-12 col-sm-6 col-xl-3">
                        <div class="card stat-card bg-primary text-white border-0 p-3 shadow-sm">
                            <div class="d-flex justify-content-between align-items-center">
                                <div><h6 class="text-white-50">Jami Daromad</h6><h3>$24,500</h3></div>
                                <i class="bi bi-wallet2 fs-1 text-white-50"></i>
                            </div>
                        </div>
                    </div>
                    <div class="col-12 col-sm-6 col-xl-3">
                        <div class="card stat-card bg-success text-white border-0 p-3 shadow-sm">
                            <div class="d-flex justify-content-between align-items-center">
                                <div><h6 class="text-white-50">Yangi Mijozlar</h6><h3>+1,240</h3></div>
                                <i class="bi bi-people-fill fs-1 text-white-50"></i>
                            </div>
                        </div>
                    </div>
                    <div class="col-12 col-sm-6 col-xl-3">
                        <div class="card stat-card bg-warning text-dark border-0 p-3 shadow-sm">
                            <div class="d-flex justify-content-between align-items-center">
                                <div><h6 class="text-dark-50">Faol Buyurtmalar</h6><h3>458 ta</h3></div>
                                <i class="bi bi-cart-check-fill fs-1 text-dark-50"></i>
                            </div>
                        </div>
                    </div>
                    <div class="col-12 col-sm-6 col-xl-3">
                        <div class="card stat-card bg-danger text-white border-0 p-3 shadow-sm">
                            <div class="d-flex justify-content-between align-items-center">
                                <div><h6 class="text-white-50">Bekor qilingan</h6><h3>12 ta</h3></div>
                                <i class="bi bi-x-circle-fill fs-1 text-white-50"></i>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="card border-0 shadow-sm rounded-3 p-4 mb-4">
                    <div class="d-flex justify-content-between align-items-center mb-4 flex-wrap gap-2">
                        <h5 class="fw-bold m-0">Oxirgi tranzaksiyalar</h5>
                        <button class="btn btn-dark btn-sm px-3" data-bs-toggle="modal" data-bs-target="#addTransactionModal">
                            <i class="bi bi-plus-lg me-1"></i> Qo'shish
                        </button>
                    </div>

                    <div class="table-responsive">
                        <table class="table table-hover align-middle m-0">
                            <thead class="table-light text-muted">
                                <tr>
                                    <th>ID</th>
                                    <th>Mijoz</th>
                                    <th>Sana</th>
                                    <th>Summa</th>
                                    <th>Status</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td>#1024</td>
                                    <td class="fw-semibold">Anvar Alimov</td>
                                    <td>01.07.2026</td>
                                    <td>1,200,000 so'm</td>
                                    <td><span class="badge bg-success-subtle text-success px-2 py-1">Yakunlandi</span></td>
                                </tr>
                                <tr>
                                    <td>#1023</td>
                                    <td class="fw-semibold">Zilola Umarova</td>
                                    <td>30.06.2026</td>
                                    <td>450,000 so'm</td>
                                    <td><span class="badge bg-warning-subtle text-warning px-2 py-1">Kutilmoqda</span></td>
                                </tr>
                                <tr>
                                    <td>#1022</td>
                                    <td class="fw-semibold">Jasur Karimov</td>
                                    <td>28.06.2026</td>
                                    <td>3,100,000 so'm</td>
                                    <td><span class="badge bg-success-subtle text-success px-2 py-1">Yakunlandi</span></td>
                                </tr>
                                <tr>
                                    <td>#1021</td>
                                    <td class="fw-semibold">Nodira Tolipova</td>
                                    <td>25.06.2026</td>
                                    <td>150,000 so'm</td>
                                    <td><span class="badge bg-danger-subtle text-danger px-2 py-1">Rad etildi</span></td>
                                </tr>
                                <tr>
                                    <td>#1020</td>
                                    <td class="fw-semibold">Farruh Toshmatov</td>
                                    <td>24.06.2026</td>
                                    <td>890,000 so'm</td>
                                    <td><span class="badge bg-success-subtle text-success px-2 py-1">Yakunlandi</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

            </main>
        </div>
    </div>

    <div class="modal fade" id="addTransactionModal" tabindex="-1" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content border-0 shadow">
                <div class="modal-header">
                    <h5 class="modal-title fw-bold">Yangi ma'lumot qo'shish</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <form id="modalForm" class="needs-validation" novalidate>
                    <div class="modal-body text-start">
                        <div class="mb-3">
                            <label class="form-label">Mijoz Ismi</label>
                            <input type="text" class="form-control" required>
                            <div class="invalid-feedback">Ismni kiriting.</div>
                        </div>
                        <div class="mb-3">
                            <label class="form-label">Summa</label>
                            <div class="input-group">
                                <input type="number" class="form-control" required>
                                <span class="input-group-text">so'm</span>
                            </div>
                        </div>
                        <div class="mb-3">
                            <label class="form-label">Status</label>
                            <select class="form-select" required>
                                <option value="" selected disabled>Tanlang...</option>
                                <option value="1">Yakunlandi</option>
                                <option value="2">Kutilmoqda</option>
                            </select>
                        </div>
                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Bekor qilish</button>
                        <button type="submit" class="btn btn-primary">Saqlash</button>
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
CSS
/* Sidebar uchun o'lcham belgilash */
.sidebar {
    width: 260px;
    flex-shrink: 0;
}

/* Statitik kartalarni yanada chiroyli qilish */
.stat-card {
    border-radius: 12px;
    transition: transform 0.2s ease;
}

.stat-card:hover {
    transform: translateY(-3px);
}

/* Kichik shaffof matnlar moslashuvi */
.text-white-50 { color: rgba(255, 255, 255, 0.7) !important; }
.text-dark-50 { color: rgba(15, 23, 42, 0.6) !important; }

/* Jadval stillari */
.table th {
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.table-responsive {
    border-radius: 8px;
    overflow: hidden;
}

/* Dropdown menyu foni effekti */
.dropdown-menu-item:hover {
    background-color: #f8fafc;
}
3. JavaScript Fayl (script.js)
JavaScript
document.addEventListener('DOMContentLoaded', () => {
    const form = document.getElementById('modalForm');

    form.addEventListener('submit', (event) => {
        // Bootstrap validatsiyasini tekshirish
        if (!form.checkValidity()) {
            event.preventDefault();
            event.stopPropagation();
        } else {
            alert("Ma'lumot muvaffaqiyatli qo'shildi!");
        }
        
        form.classList.add('was-validated');
    }, false);
});
📱 Responsivlik qanday ta'minlangan?
Sidebar: Katta ekranlarda ko'rinadi (d-none d-md-block), mobil qurilmalarda esa yashirinib, Top Navbar ichidagi "hamburger" tugmasi bosilganda pastga chiroyli yig'iluvchi ko'rinishda ochiladi (d-md-none va collapse).

Stat Kartalar: col-12 col-sm-6 col-xl-3 kombinatsiyasi yordamida mobilda 1 qatorda 1 tadan, planshetda 2 tadan, kompyuterda esa 4 tasi yonma-yon joylashadi.

Jadval: .table-responsive klassi tufayli kichik ekranlarda jadval ekranni buzib yubormaydi, uning ichida gorizontal scroll paydo bo'ladi.
