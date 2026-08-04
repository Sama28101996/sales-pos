<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>نظام إدارة المبيعات</title>
  <link rel="manifest" href="manifest.json" />
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body { font-family: 'Segoe UI', Tahoma, sans-serif; background: #f1f5f9; color: #1e293b; }
    .app { min-height: 100vh; display: flex; flex-direction: column; }
    .header { background: linear-gradient(135deg, #2563eb 0%, #1e40af 100%); color: white; padding: 1rem; text-align: center; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }
    .header h1 { font-size: 1.5rem; }
    .main { flex: 1; padding: 1rem; max-width: 1200px; margin: 0 auto; width: 100%; }
    .card { background: white; border-radius: 12px; padding: 1.5rem; margin-bottom: 1rem; box-shadow: 0 1px 3px rgba(0,0,0,0.1); }
    .card h2 { color: #2563eb; margin-bottom: 1rem; font-size: 1.2rem; }
    .btn { background: #2563eb; color: white; border: none; padding: 0.75rem 1.5rem; border-radius: 8px; cursor: pointer; font-size: 1rem; font-weight: 600; transition: all 0.2s; }
    .btn:hover { background: #1e40af; }
    .btn-block { width: 100%; }
    .btn-secondary { background: #64748b; }
    .btn-danger { background: #dc2626; }
    .form-group { margin-bottom: 1rem; }
    .form-group label { display: block; margin-bottom: 0.5rem; font-weight: 600; }
    .form-group input, .form-group select, .form-group textarea { width: 100%; padding: 0.75rem; border: 1px solid #cbd5e1; border-radius: 8px; font-size: 1rem; font-family: inherit; }
    .form-group input:focus, .form-group select:focus, .form-group textarea:focus { outline: none; border-color: #2563eb; }
    .grid { display: grid; gap: 1rem; }
    .grid-2 { grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); }
    .grid-3 { grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); }
    .list { list-style: none; }
    .list-item { background: #f8fafc; padding: 1rem; border-radius: 8px; margin-bottom: 0.5rem; display: flex; justify-content: space-between; align-items: center; }
    .badge { background: #2563eb; color: white; padding: 0.25rem 0.75rem; border-radius: 12px; font-size: 0.85rem; }
    .badge-success { background: #16a34a; }
    .badge-danger { background: #dc2626; }
    .badge-warning { background: #ea580c; }
    .empty { text-align: center; padding: 2rem; color: #64748b; }
    .toast { position: fixed; bottom: 1rem; right: 1rem; background: #1e293b; color: white; padding: 1rem 1.5rem; border-radius: 8px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); z-index: 1000; animation: slideIn 0.3s; }
    .toast.success { background: #16a34a; }
    .toast.error { background: #dc2626; }
    @keyframes slideIn { from { transform: translateX(100%); } to { transform: translateX(0); } }
    .nav { display: flex; gap: 0.5rem; margin-bottom: 1rem; overflow-x: auto; padding-bottom: 0.5rem; }
    .nav button { white-space: nowrap; }
    .nav button.active { background: #1e40af; }
    .stats { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; margin-bottom: 1rem; }
    .stat { background: white; padding: 1.5rem; border-radius: 12px; text-align: center; box-shadow: 0 1px 3px rgba(0,0,0,0.1); }
    .stat-value { font-size: 2rem; font-weight: bold; color: #2563eb; }
    .stat-label { color: #64748b; margin-top: 0.5rem; }
    .modal { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.5); display: flex; align-items: center; justify-content: center; z-index: 100; padding: 1rem; }
    .modal-content { background: white; border-radius: 12px; padding: 1.5rem; max-width: 500px; width: 100%; max-height: 90vh; overflow-y: auto; }
    .login-page { min-height: 100vh; display: flex; align-items: center; justify-content: center; background: linear-gradient(135deg, #2563eb 0%, #1e40af 100%); }
    .login-box { background: white; padding: 2rem; border-radius: 16px; box-shadow: 0 10px 25px rgba(0,0,0,0.2); width: 100%; max-width: 400px; }
    .login-box h1 { text-align: center; color: #2563eb; margin-bottom: 0.5rem; }
    .login-box p { text-align: center; color: #64748b; margin-bottom: 1.5rem; }
    .hidden { display: none !important; }
  </style>
</head>
<body>
  <div id="app"></div>
  <script>
    // ====== بيانات التطبيق ======
    const DB_KEYS = {
      PRODUCTS: 'pos_products',
      CUSTOMERS: 'pos_customers',
      SALES: 'pos_sales',
      USERS: 'pos_users',
      SUPPLIERS: 'pos_suppliers',
      PURCHASES: 'pos_purchases',
      DEBTS: 'pos_debts',
      SETTINGS: 'pos_settings',
      CURRENT_USER: 'pos_current_user'
    };
    const PERMISSIONS = {
      ALL: '*', SELL: 'sell', PURCHASE: 'purchase',
      INVENTORY_VIEW: 'inventory_view', INVENTORY_EDIT: 'inventory_edit',
      CUSTOMERS_VIEW: 'customers_view', CUSTOMERS_EDIT: 'customers_edit',
      DEBTS_VIEW: 'debts_view', DEBTS_MANAGE: 'debts_manage',
      REPORTS_VIEW: 'reports_view', TEAM_MANAGE: 'team_manage',
      SETTINGS_MANAGE: 'settings_manage'
    };
    const ROLES = {
      admin: { name: 'مشرف', permissions: ['*'] },
      seller: { name: 'بائع', permissions: ['sell', 'inventory_view', 'customers_view', 'customers_edit', 'debts_view'] }
    };
    function dbGet(k, d) { try { const v = localStorage.getItem(k); return v ? JSON.parse(v) : d; } catch(e) { return d; } }
    function dbSet(k, v) { try { localStorage.setItem(k, JSON.stringify(v)); return true; } catch(e) { return false; } }
    function uuid() { return 'id-' + Date.now() + '-' + Math.random().toString(36).substr(2, 9); }
    function toast(msg, type) { const t = document.createElement('div'); t.className = 'toast ' + (type || ''); t.textContent = msg; document.body.appendChild(t); setTimeout(() => t.remove(), 3000); }
    function escapeHtml(s) { if (s == null) return ''; return String(s).replace(/[&<>"']/g, c => ({ '&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;' }[c])); }

    // ====== المصادقة ======
    function initUsers() {
      let users = dbGet(DB_KEYS.USERS, []);
      if (users.length === 0) {
        users = [{
          id: 'admin-001', username: 'admin', password: 'admin123',
          name: 'المشرف', role: 'admin', permissions: ['*'], disabled: false
        }];
        dbSet(DB_KEYS.USERS, users);
      }
    }
    function login(username, password) {
      const users = dbGet(DB_KEYS.USERS, []);
      const user = users.find(u => u.username === username && u.password === password);
      if (!user) return { ok: false, error: 'اسم المستخدم أو كلمة المرور غير صحيحة' };
      if (user.disabled) return { ok: false, error: 'الحساب معطل' };
      dbSet(DB_KEYS.CURRENT_USER, { id: user.id, loginAt: new Date().toISOString() });
      return { ok: true, user };
    }
    function logout() { localStorage.removeItem(DB_KEYS.CURRENT_USER); }
    function currentUser() {
      const s = dbGet(DB_KEYS.CURRENT_USER, null);
      if (!s) return null;
      const users = dbGet(DB_KEYS.USERS, []);
      return users.find(u => u.id === s.id) || null;
    }
    function hasPermission(user, perm) {
      if (!user) return false;
      if (user.permissions && user.permissions.includes('*')) return true;
      if (user.permissions && user.permissions.includes(perm)) return true;
      const role = ROLES[user.role];
      if (role && role.permissions.includes('*')) return true;
      if (role && role.permissions.includes(perm)) return true;
      return false;
    }

    // ====== صفحة الدخول ======
    function renderLogin() {
      return `
        <div class="login-page">
          <div class="login-box">
            <h1>📦 نظام إدارة المبيعات</h1>
            <p>سجّل دخولك للمتابعة</p>
            <form id="loginForm">
              <div class="form-group">
                <label>اسم المستخدم</label>
                <input type="text" id="username" required autocomplete="username" />
              </div>
              <div class="form-group">
                <label>كلمة المرور</label>
                <input type="password" id="password" required autocomplete="current-password" />
              </div>
              <button type="submit" class="btn btn-block">دخول</button>
            </form>
            <p style="margin-top:1rem;font-size:0.85rem;color:#64748b;">
              الحساب الافتراضي: <b>admin / admin123</b>
            </p>
          </div>
        </div>
      `;
    }

    // ====== التطبيق ======
    function renderApp() {
      const user = currentUser();
      if (!user) return renderLogin();
      return `
        <div class="app">
          <div class="header">
            <h1>📦 نظام إدارة المبيعات</h1>
            <p style="margin-top:0.5rem;opacity:0.9;">مرحباً ${escapeHtml(user.name)} (${escapeHtml(ROLES[user.role]?.name || user.role)})</p>
          </div>
          <div class="main">
            <div class="nav">
              <button class="btn active" data-page="dashboard">🏠 الرئيسية</button>
              <button class="btn btn-secondary" data-page="inventory">📦 المخزون</button>
              <button class="btn btn-secondary" data-page="sales">🛒 المبيعات</button>
              <button class="btn btn-secondary" data-page="customers">👥 العملاء</button>
              ${hasPermission(user, 'debts_view') ? '<button class="btn btn-secondary" data-page="debts">💰 الديون</button>' : ''}
              ${hasPermission(user, 'reports_view') ? '<button class="btn btn-secondary" data-page="reports">📊 التقارير</button>' : ''}
              ${user.role === 'admin' ? '<button class="btn btn-secondary" data-page="team">👨‍👩‍👧‍👦 الفريق</button>' : ''}
              <button class="btn btn-danger" id="logoutBtn">🚪 خروج</button>
            </div>
            <div id="pageContent"></div>
          </div>
        </div>
      `;
    }

    // ====== الصفحات ======
    function renderDashboard() {
      const products = dbGet(DB_KEYS.PRODUCTS, []);
      const customers = dbGet(DB_KEYS.CUSTOMERS, []);
      const sales = dbGet(DB_KEYS.SALES, []);
      const today = new Date().toISOString().split('T')[0];
      const todaySales = sales.filter(s => s.date && s.date.startsWith(today));
      const todayRevenue = todaySales.reduce((sum, s) => sum + (s.total || 0), 0);
      const totalStock = products.reduce((sum, p) => sum + (p.stock || 0), 0);
      return `
        <div class="stats">
          <div class="stat"><div class="stat-value">${products.length}</div><div class="stat-label">المنتجات</div></div>
          <div class="stat"><div class="stat-value">${customers.length}</div><div class="stat-label">العملاء</div></div>
          <div class="stat"><div class="stat-value">${sales.length}</div><div class="stat-label">إجمالي المبيعات</div></div>
          <div class="stat"><div class="stat-value">${totalStock}</div><div class="stat-label">الكمية بالمخزون</div></div>
          <div class="stat" style="background:#16a34a;color:white;"><div class="stat-value" style="color:white;">${todayRevenue.toFixed(2)}</div><div class="stat-label" style="color:white;">مبيعات اليوم</div></div>
        </div>
        <div class="card">
          <h2>🕐 آخر المبيعات</h2>
          ${sales.length === 0 ? '<p class="empty">لا توجد مبيعات بعد</p>' : `
            <ul class="list">
              ${sales.slice(-5).reverse().map(s => `
                <li class="list-item">
                  <span>${escapeHtml(s.customerName || 'بدون اسم')}</span>
                  <span class="badge badge-success">${(s.total || 0).toFixed(2)}</span>
                </li>
              `).join('')}
            </ul>
          `}
        </div>
      `;
    }
    function renderInventory() {
      const user = currentUser();
      const products = dbGet(DB_KEYS.PRODUCTS, []);
      const canEdit = hasPermission(user, 'inventory_edit');
      return `
        <div class="card">
          <h2>📦 المخزون ${canEdit ? '<button class="btn" onclick="showAddProduct()" style="float:left;">+ إضافة</button>' : ''}</h2>
          ${products.length === 0 ? '<p class="empty">لا توجد منتجات</p>' : `
            <ul class="list">
              ${products.map(p => `
                <li class="list-item">
                  <div>
                    <b>${escapeHtml(p.name)}</b><br>
                    <small>السعر: ${(p.price || 0).toFixed(2)} | الكمية: ${p.stock || 0}</small>
                  </div>
                  ${canEdit ? `<button class="btn btn-danger" onclick="deleteProduct('${p.id}')">حذف</button>` : ''}
                </li>
              `).join('')}
            </ul>
          `}
        </div>
      `;
    }
    function renderSales() {
      const user = currentUser();
      if (!hasPermission(user, 'sell')) return '<div class="card"><p class="empty">ليس لديك صلاحية للبيع</p></div>';
      const products = dbGet(DB_KEYS.PRODUCTS, []);
      const customers = dbGet(DB_KEYS.CUSTOMERS, []);
      return `
        <div class="card">
          <h2>🛒 بيع جديد</h2>
          <form id="saleForm">
            <div class="form-group">
              <label>المنتج</label>
              <select id="saleProduct" required>
                <option value="">اختر منتج</option>
                ${products.map(p => `<option value="${p.id}" data-price="${p.price || 0}">${escapeHtml(p.name)} - ${(p.price || 0).toFixed(2)}</option>`).join('')}
              </select>
            </div>
            <div class="grid grid-2">
              <div class="form-group">
                <label>الكمية</label>
                <input type="number" id="saleQty" min="1" value="1" required />
              </div>
              <div class="form-group">
                <label>العميل (اختياري)</label>
                <select id="saleCustomer">
                  <option value="">بدون عميل</option>
                  ${customers.map(c => `<option value="${c.id}">${escapeHtml(c.name)}</option>`).join('')}
                </select>
              </div>
            </div>
            <button type="submit" class="btn btn-block">💰 إتمام البيع</button>
          </form>
        </div>
      `;
    }
    function renderCustomers() {
      const user = currentUser();
      const customers = dbGet(DB_KEYS.CUSTOMERS, []);
      const canEdit = hasPermission(user, 'customers_edit');
      return `
        <div class="card">
          <h2>👥 العملاء ${canEdit ? '<button class="btn" onclick="showAddCustomer()" style="float:left;">+ إضافة</button>' : ''}</h2>
          ${customers.length === 0 ? '<p class="empty">لا يوجد عملاء</p>' : `
            <ul class="list">
              ${customers.map(c => `
                <li class="list-item">
                  <div>
                    <b>${escapeHtml(c.name)}</b> ${c.phone ? `<br><small>${escapeHtml(c.phone)}</small>` : ''}
                  </div>
                  ${canEdit ? `<button class="btn btn-danger" onclick="deleteCustomer('${c.id}')">حذف</button>` : ''}
                </li>
              `).join('')}
            </ul>
          `}
        </div>
      `;
    }
    function renderDebts() {
      const sales = dbGet(DB_KEYS.SALES, []);
      const debts = sales.filter(s => s.debt && s.debt > 0);
      return `
        <div class="card">
          <h2>💰 الديون</h2>
          ${debts.length === 0 ? '<p class="empty">لا توجد ديون</p>' : `
            <ul class="list">
              ${debts.map(s => `
                <li class="list-item">
                  <div>
                    <b>${escapeHtml(s.customerName || 'بدون اسم')}</b><br>
                    <small>التاريخ: ${s.date ? s.date.split('T')[0] : ''}</small>
                  </div>
                  <span class="badge badge-danger">${(s.debt || 0).toFixed(2)}</span>
                </li>
              `).join('')}
            </ul>
          `}
        </div>
      `;
    }
    function renderReports() {
      const sales = dbGet(DB_KEYS.SALES, []);
      const totalRevenue = sales.reduce((sum, s) => sum + (s.total || 0), 0);
      return `
        <div class="card">
          <h2>📊 التقارير</h2>
          <div class="stats">
            <div class="stat"><div class="stat-value">${sales.length}</div><div class="stat-label">عدد المبيعات</div></div>
            <div class="stat"><div class="stat-value">${totalRevenue.toFixed(2)}</div><div class="stat-label">إجمالي الإيرادات</div></div>
          </div>
        </div>
      `;
    }
    function renderTeam() {
      const users = dbGet(DB_KEYS.USERS, []);
      return `
        <div class="card">
          <h2>👨‍👩‍👧‍👦 الفريق <button class="btn" onclick="showAddUser()" style="float:left;">+ إضافة عضو</button></h2>
          <ul class="list">
            ${users.map(u => `
              <li class="list-item">
                <div>
                  <b>${escapeHtml(u.name)}</b> <span class="badge">${escapeHtml(ROLES[u.role]?.name || u.role)}</span><br>
                  <small>@${escapeHtml(u.username)}</small>
                </div>
                ${u.id !== 'admin-001' ? `<button class="btn btn-danger" onclick="deleteUser('${u.id}')">حذف</button>` : '<span class="badge badge-success">أنت</span>'}
              </li>
            `).join('')}
          </ul>
        </div>
      `;
    }

    // ====== العمليات ======
    function showAddProduct() {
      const html = `
        <div class="modal" id="modal">
          <div class="modal-content">
            <h2>منتج جديد</h2>
            <form id="addProductForm">
              <div class="form-group"><label>الاسم</label><input type="text" id="pName" required /></div>
              <div class="form-group"><label>السعر</label><input type="number" id="pPrice" min="0" step="0.01" required /></div>
              <div class="form-group"><label>الكمية</label><input type="number" id="pStock" min="0" value="0" required /></div>
              <button type="submit" class="btn btn-block">حفظ</button>
              <button type="button" class="btn btn-secondary btn-block" onclick="closeModal()" style="margin-top:0.5rem;">إلغاء</button>
            </form>
          </div>
        </div>
      `;
      document.body.insertAdjacentHTML('beforeend', html);
      document.getElementById('addProductForm').onsubmit = (e) => {
        e.preventDefault();
        const products = dbGet(DB_KEYS.PRODUCTS, []);
        products.push({ id: uuid(), name: document.getElementById('pName').value, price: parseFloat(document.getElementById('pPrice').value), stock: parseInt(document.getElementById('pStock').value) });
        dbSet(DB_KEYS.PRODUCTS, products);
        closeModal();
        toast('تم إضافة المنتج ✓', 'success');
        navigate('inventory');
      };
    }
    function deleteProduct(id) {
      if (!confirm('حذف هذا المنتج؟')) return;
      const products = dbGet(DB_KEYS.PRODUCTS, []).filter(p => p.id !== id);
      dbSet(DB_KEYS.PRODUCTS, products);
      toast('تم الحذف', 'success');
      navigate('inventory');
    }
    function showAddCustomer() {
      const html = `
        <div class="modal" id="modal">
          <div class="modal-content">
            <h2>عميل جديد</h2>
            <form id="addCustomerForm">
              <div class="form-group"><label>الاسم</label><input type="text" id="cName" required /></div>
              <div class="form-group"><label>الهاتف (اختياري)</label><input type="tel" id="cPhone" /></div>
              <button type="submit" class="btn btn-block">حفظ</button>
              <button type="button" class="btn btn-secondary btn-block" onclick="closeModal()" style="margin-top:0.5rem;">إلغاء</button>
            </form>
          </div>
        </div>
      `;
      document.body.insertAdjacentHTML('beforeend', html);
      document.getElementById('addCustomerForm').onsubmit = (e) => {
        e.preventDefault();
        const customers = dbGet(DB_KEYS.CUSTOMERS, []);
        customers.push({ id: uuid(), name: document.getElementById('cName').value, phone: document.getElementById('cPhone').value });
        dbSet(DB_KEYS.CUSTOMERS, customers);
        closeModal();
        toast('تم إضافة العميل ✓', 'success');
        navigate('customers');
      };
    }
    function deleteCustomer(id) {
      if (!confirm('حذف هذا العميل؟')) return;
      const customers = dbGet(DB_KEYS.CUSTOMERS, []).filter(c => c.id !== id);
      dbSet(DB_KEYS.CUSTOMERS, customers);
      navigate('customers');
    }
    function showAddUser() {
      const html = `
        <div class="modal" id="modal">
          <div class="modal-content">
            <h2>عضو جديد</h2>
            <form id="addUserForm">
              <div class="form-group"><label>الاسم</label><input type="text" id="uName" required /></div>
              <div class="form-group"><label>اسم المستخدم</label><input type="text" id="uUsername" required /></div>
              <div class="form-group"><label>كلمة المرور</label><input type="password" id="uPassword" required /></div>
              <div class="form-group"><label>الدور</label>
                <select id="uRole"><option value="seller">بائع</option><option value="admin">مشرف</option></select>
              </div>
              <button type="submit" class="btn btn-block">حفظ</button>
              <button type="button" class="btn btn-secondary btn-block" onclick="closeModal()" style="margin-top:0.5rem;">إلغاء</button>
            </form>
          </div>
        </div>
      `;
      document.body.insertAdjacentHTML('beforeend', html);
      document.getElementById('addUserForm').onsubmit = (e) => {
        e.preventDefault();
        const users = dbGet(DB_KEYS.USERS, []);
        users.push({ id: uuid(), name: document.getElementById('uName').value, username: document.getElementById('uUsername').value, password: document.getElementById('uPassword').value, role: document.getElementById('uRole').value, permissions: ROLES[document.getElementById('uRole').value].permissions, disabled: false });
        dbSet(DB_KEYS.USERS, users);
        closeModal();
        toast('تم إضافة العضو ✓', 'success');
        navigate('team');
      };
    }
    function deleteUser(id) {
      if (!confirm('حذف هذا العضو؟')) return;
      const users = dbGet(DB_KEYS.USERS, []).filter(u => u.id !== id);
      dbSet(DB_KEYS.USERS, users);
      navigate('team');
    }
    function closeModal() { const m = document.getElementById('modal'); if (m) m.remove(); }

    // ====== التنقل ======
    function navigate(page) {
      const content = document.getElementById('pageContent');
      const pages = {
        dashboard: renderDashboard, inventory: renderInventory, sales: renderSales,
        customers: renderCustomers, debts: renderDebts, reports: renderReports, team: renderTeam
      };
      content.innerHTML = pages[page] ? pages[page]() : '<p class="empty">صفحة غير موجودة</p>';
      document.querySelectorAll('.nav button[data-page]').forEach(b => b.classList.toggle('active', b.dataset.page === page));
      window.scrollTo(0, 0);
    }

    // ====== التشغيل ======
    function init() {
      initUsers();
      document.getElementById('app').innerHTML = renderApp();
      const loginForm = document.getElementById('loginForm');
      if (loginForm) {
        loginForm.onsubmit = (e) => {
          e.preventDefault();
          const result = login(document.getElementById('username').value, document.getElementById('password').value);
          if (result.ok) { init(); toast('مرحباً ' + result.user.name, 'success'); }
          else { toast(result.error, 'error'); }
        };
        return;
      }
      navigate('dashboard');
      document.querySelectorAll('.nav button[data-page]').forEach(btn => {
        btn.onclick = () => navigate(btn.dataset.page);
      });
      const logoutBtn = document.getElementById('logoutBtn');
      if (logoutBtn) logoutBtn.onclick = () => { logout(); init(); };
      const saleForm = document.getElementById('saleForm');
      if (saleForm) {
        saleForm.onsubmit = (e) => {
          e.preventDefault();
          const productId = document.getElementById('saleProduct').value;
          const qty = parseInt(document.getElementById('saleQty').value);
          const customerId = document.getElementById('saleCustomer').value;
          const products = dbGet(DB_KEYS.PRODUCTS, []);
          const customers = dbGet(DB_KEYS.CUSTOMERS, []);
          const product = products.find(p => p.id === productId);
          if (!product) return toast('منتج غير موجود', 'error');
          if ((product.stock || 0) < qty) return toast('الكمية غير كافية', 'error');
          const customer = customers.find(c => c.id === customerId);
          product.stock -= qty;
          dbSet(DB_KEYS.PRODUCTS, products);
          const sales = dbGet(DB_KEYS.SALES, []);
          const total = (product.price || 0) * qty;
          sales.push({ id: uuid(), productId, productName: product.name, qty, price: product.price, total, customerId: customerId || null, customerName: customer?.name || '', date: new Date().toISOString() });
          dbSet(DB_KEYS.SALES, sales);
          toast('تم البيع بنجاح ✓', 'success');
          navigate('dashboard');
        };
      }
    }
    document.addEventListener('DOMContentLoaded', init);
  </script>
</body>
</html>
