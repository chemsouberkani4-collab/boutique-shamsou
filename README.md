<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>شمسو شوب — النسخة المتقدمة</title>
  <style>
    /* ==========================
       تصميم عام — CSS متقدم
       ========================== */
    :root{
      --accent:#ff6b6b;
      --muted:#6b7280;
      --bg:#f5f5f7;
      --card:#ffffff;
      --radius:12px;
      --shadow: 0 6px 18px rgba(16,24,40,0.06);
      --max-width:1200px;
      --transition:200ms ease;
      --font-family: "Noto Sans", "Segoe UI", Tahoma, Arial, sans-serif;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:var(--font-family);
      background:var(--bg);
      color:#111827;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.4;
    }
    a{color:inherit}
    /* ======= Header ======= */
    header{
      background:linear-gradient(90deg,#0f172a,#111827);
      color:white;
      padding:0.6rem 1rem;
      position:sticky;
      top:0;
      z-index:50;
      box-shadow:0 2px 8px rgba(2,6,23,0.3);
    }
    .topbar{
      max-width:var(--max-width);
      margin:0 auto;
      display:flex;
      align-items:center;
      gap:1rem;
      padding:0.4rem;
    }
    .logo{
      display:flex;align-items:center;gap:.6rem;font-weight:700;font-size:1.1rem
    }
    .logo .mark{width:44px;height:44px;border-radius:10px;background:linear-gradient(45deg,var(--accent),#f59e0b);display:flex;align-items:center;justify-content:center;color:white;font-weight:800}
    .searchbar{flex:1;display:flex;align-items:center;gap:.6rem}
    .searchbar input{flex:1;padding:.6rem .8rem;border-radius:10px;border:0;outline:none;box-shadow:var(--shadow)}
    .controls{display:flex;align-items:center;gap:.6rem}
    .lang-select, .cart-btn{background:transparent;border:0;color:white;padding:.4rem .6rem;border-radius:8px;cursor:pointer}
    .cart-badge{background:var(--accent);color:white;padding:2px 7px;border-radius:999px;font-size:0.8rem;margin-inline-start:6px}/* ======= Main layout ======= */
.layout{max-width:var(--max-width);margin:1.2rem auto;display:grid;grid-template-columns:260px 1fr;gap:1rem;padding:0 1rem}

/* Sidebar filters */
.sidebar{background:var(--card);padding:1rem;border-radius:var(--radius);box-shadow:var(--shadow);height:fit-content}
.sidebar h3{margin:0 0 .6rem}
.categories{display:flex;flex-direction:column;gap:.4rem}
.cat-btn{background:transparent;border:1px solid #e6e7eb;padding:.5rem .6rem;border-radius:8px;cursor:pointer;text-align:right}
.cat-btn.active{background:linear-gradient(90deg,#fff4f4,#fff);border-color:var(--accent)}
.filter-section{margin-top:1rem}
.range{display:flex;gap:.5rem;align-items:center}

/* Products grid */
.products-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:1rem}
.card{background:var(--card);border-radius:12px;overflow:hidden;box-shadow:var(--shadow);transition:transform var(--transition);display:flex;flex-direction:column}
.card:hover{transform:translateY(-6px)}
.card-media{position:relative;padding-top:125%;overflow:hidden}
.card-media img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover}
.card-body{padding:0.8rem;display:flex;flex-direction:column;gap:.4rem}
.title{font-weight:700}
.meta{color:var(--muted);font-size:0.9rem}
.price-row{display:flex;align-items:center;justify-content:space-between;gap:.6rem}
.price{font-weight:800}
.actions{display:flex;gap:.5rem}
.btn{padding:.45rem .6rem;border-radius:8px;border:0;cursor:pointer}
.btn-ghost{background:transparent;border:1px solid #e6e7eb}
.btn-primary{background:var(--accent);color:white}

/* Cart panel */
.cart-panel{position:fixed;top:0;right:0;height:100vh;width:420px;transform:translateX(110%);transition:transform .28s ease;z-index:60;display:flex;flex-direction:column}
.cart-panel.open{transform:translateX(0)}
.cart-panel .inner{background:var(--card);padding:1rem;height:100%;box-shadow:var(--shadow);overflow:auto}
.cart-item{display:flex;gap:.6rem;padding:.6rem;border-bottom:1px dashed #eee;align-items:center}
.cart-item img{width:64px;height:64px;object-fit:cover;border-radius:8px}
.cart-actions{margin-top:1rem;display:flex;flex-direction:column;gap:.5rem}

/* Modal (product quick view & checkout) */
.modal-backdrop{position:fixed;inset:0;background:rgba(2,6,23,0.45);display:none;align-items:center;justify-content:center;z-index:80}
.modal-backdrop.open{display:flex}
.modal{background:var(--card);width:92%;max-width:940px;border-radius:12px;overflow:auto;max-height:92vh}
.modal .modal-body{display:grid;grid-template-columns:1fr 1fr;gap:1rem;padding:1rem}
.modal img{width:100%;height:100%;object-fit:cover;border-radius:8px}

/* Footer */
footer{max-width:var(--max-width);margin:1rem auto;padding:1rem;color:var(--muted);text-align:center}

/* Responsive */
@media(max-width:900px){
  .layout{grid-template-columns:1fr;}
  .sidebar{order:2}
  .cart-panel{width:100%;}
  .modal .modal-body{grid-template-columns:1fr}
}

/* Small helpers */
.small{font-size:.9rem;color:var(--muted)}
.center{display:flex;align-items:center;justify-content:center}
.text-muted{color:var(--muted)}

  </style>
</head>
<body>
  <header>
    <div class="topbar">
      <div class="logo" title="شمسو شوب">
        <div class="mark">ش</div>
        <div>
          <div>شمسو شوب</div>
          <div style="font-size:.8rem;color:#cbd5e1">بوتيك على الانترنت</div>
        </div>
      </div><div class="searchbar">
    <input id="searchInput" placeholder="ابحث عن المنتجات، الأقسام، أو المواصفات..." />
    <button class="btn btn-ghost" id="clearBtn">مسح</button>
  </div>

  <div class="controls">
    <select id="langSelect" class="lang-select" title="اختر اللغة">
      <option value="ar">العربية</option>
      <option value="fr">Français</option>
      <option value="en">English</option>
    </select>
    <button class="cart-btn" id="openCartBtn" title="عرض السلة">عربة <span id="cartCount" class="cart-badge">0</span></button>
  </div>

</div>

  </header>  <div class="layout">
    <!-- Sidebar: فلاتر و اقسام -->
    <aside class="sidebar" aria-label="المرشحات">
      <h3 id="filtersTitle">الأقسام</h3>
      <div class="categories" id="categoriesList"></div><div class="filter-section">
    <h3 id="filterTitlePrice">فلتر بالسعر</h3>
    <div class="range">
      <input id="minPrice" type="number" placeholder="أدنى" style="width:100%;padding:.5rem;border-radius:8px;border:1px solid #eee" />
      <input id="maxPrice" type="number" placeholder="أقصى" style="width:100%;padding:.5rem;border-radius:8px;border:1px solid #eee" />
    </div>
    <div style="margin-top:.6rem;display:flex;gap:.4rem">
      <button class="btn btn-ghost" id="applyFiltersBtn">تطبيق</button>
      <button class="btn" id="resetFiltersBtn">إعادة</button>
    </div>
  </div>

  <div class="filter-section">
    <h3 id="sortTitle">ترتيب حسب</h3>
    <select id="sortSelect" style="width:100%;padding:.5rem;border-radius:8px;border:1px solid #eee">
      <option value="popular">الأكثر شعبية</option>
      <option value="price-asc">الأرخص</option>
      <option value="price-desc">الأغلى</option>
    </select>
  </div>

  <div style="margin-top:1rem;font-size:.9rem;color:var(--muted)">
    <div id="sidebarHint">تصفّح وقم بإضافة ما يعجبك إلى السلة. السلة محفوظة محليًا بالمتصفح.</div>
  </div>
</aside>

<!-- Main: المنتجات -->
<main>
  <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem">
    <h2 id="productsTitle">المنتجات</h2>
    <div class="small text-muted" id="resultCount">0 منتج</div>
  </div>

  <section class="products-grid" id="productsGrid"></section>

  <div style="margin-top:1rem;text-align:center">
    <button class="btn btn-ghost" id="loadMoreBtn">تحميل المزيد</button>
  </div>
</main>

  </div>  <!-- Cart panel -->  <aside class="cart-panel" id="cartPanel" aria-hidden="true">
    <div class="inner">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <h3 id="cartTitle">سلة المشتريات</h3>
        <button id="closeCartBtn" class="btn btn-ghost">إغلاق</button>
      </div><div id="cartItemsContainer" style="margin-top:.6rem"></div>

  <div class="cart-actions">
    <div style="display:flex;justify-content:space-between;align-items:center">
      <div class="small">المجموع</div>
      <div id="cartTotal" style="font-weight:800">0 دج</div>
    </div>
    <button id="checkoutBtn" class="btn btn-primary">الدفع</button>
    <button id="clearCartBtn" class="btn btn-ghost">تفريغ السلة</button>
  </div>
</div>

  </aside>  <!-- Modal backdrop (quick view & checkout) -->  <div class="modal-backdrop" id="modalBackdrop" aria-hidden="true">
    <div class="modal" role="dialog" aria-modal="true">
      <div style="display:flex;justify-content:space-between;align-items:center;padding:0.6rem 1rem;border-bottom:1px solid #f1f5f9">
        <div id="modalTitle">تفاصيل المنتج</div>
        <button id="closeModalBtn" class="btn btn-ghost">إغلاق</button>
      </div>
      <div class="modal-body" id="modalBody">
        <!-- يتم تعبئتها ديناميكياً -->
      </div>
    </div>
  </div>  <footer>&copy; 2025 شمسو شوب — كل الحقوق محفوظة.</footer>  <script>
    /*************************************************
      نسخة متقدمة لواجهة E‑commerce
      - منتجات تخزن في مصفوفة (JSON)
      - تعدد اللغات (ar / fr / en)
      - فلترة، بحث، ترتيب
      - عربة مشتريات مخزنة محليًا (localStorage)
      - نافذة سريعة للمنتج + صفحة دفع افتراضية
    *************************************************/

    // ---------- بيانات مبدئية للمنتجات (أضف أو عدّل بسهولة) ----------
    const products = [
      {
        id: 'p1', category: 'رجالي', price: 2500, stock: 15, rating: 4.3,
        translations: {
          ar: {title: 'قميص رسمي رجالي', desc: 'قميص قطن ناعم، مثالي للمناسبات والعمل.'},
          en: {title: 'Men\'s Formal Shirt', desc: 'Soft cotton shirt, perfect for work and events.'},
          fr: {title: 'Chemise homme', desc: 'Chemise en coton doux, idéale pour le travail.'}
        },
        sizes: ['S','M','L','XL'], colors: ['أبيض','أزرق','أسود'],
        images:[
          'https://picsum.photos/seed/p1/800/1000'
        ]
      },
      {
        id: 'p2', category: 'نسائي', price: 3500, stock: 8, rating: 4.6,
        translations:{
          ar:{title:'فستان سهرة أنيق', desc:'فستان سهرة مطرز يناسب الحفلات والمناسبات الخاصة.'},
          en:{title:'Elegant Evening Dress', desc:'Embellished evening dress for special occasions.'},
          fr:{title:'Robe de soirée', desc:'Robe brodée pour occasions spéciales.'}
        },
        sizes:['S','M','L'], colors:['أحمر','أسود','زيتي'], images:['https://picsum.photos/seed/p2/800/1000']
      },
      {
        id:'p3', category:'أطفال', price:1200, stock:25, rating:4.1,
        translations:{ar:{title:'تي‑شيرت أطفال مريح', desc:'قماش ناعم ومقاوم للغسيل.'},en:{title:'Kids T-Shirt',desc:'Soft washable fabric.'},fr:{title:'T-shirt enfant',desc:'Tissu doux et lavable.'}},
        sizes:['2-3','4-5','6-7'], colors:['أصفر','أزرق'], images:['https://picsum.photos/seed/p3/800/1000']
      },
      {
        id:'p4', category:'أحذية', price:6000, stock:6, rating:4.7,
        translations:{ar:{title:'حذاء رياضي مريح',desc:'مصنوع بجودة عالية مع تهوية ممتازة.'},en:{title:'Comfort Sneakers',desc:'Breathable and high-quality.'},fr:{title:'Baskets confort',desc:'Respirant et haute qualité.'}},
        sizes:['40','41','42','43'], colors:['أبيض','أسود'], images:['https://picsum.photos/seed/p4/800/1000']
      },
      {
        id:'p5', category:'أكسسوارات', price:900, stock:30, rating:4.0,
        translations:{ar:{title:'حزام جلد طبيعي',desc:'حزام جلد أنيق وقابل للتعديل.'},en:{title:'Leather Belt',desc:'Adjustable genuine leather belt.'},fr:{title:'Ceinture en cuir',desc:'Ceinture réglable en cuir véritable.'}},
        sizes:[], colors:['بني','أسود'], images:['https://picsum.photos/seed/p5/800/1000']
      },
      {
        id:'p6', category:'نسائي', price:2200, stock:10, rating:4.4,
        translations:{ar:{title:'بلوزة صيفية',desc:'مريحة وخفيفة للجو الحار.'},en:{title:'Summer Blouse',desc:'Light and comfortable for warm days.'},fr:{title:'Blouse d\'été',desc:'Légère et confortable.'}},
        sizes:['S','M','L'], colors:['وردي','أبيض'], images:['https://picsum.photos/seed/p6/800/1000']
      },
      {
        id:'p7', category:'رجالي', price:4200, stock:5, rating:4.5,
        translations:{ar:{title:'جاكيت شتوي',desc:'مقاوم للمطر مع تبطين دافئ.'},en:{title:'Winter Jacket',desc:'Water-resistant with warm lining.'},fr:{title:'Veste d\'hiver',desc:'Imperméable avec doublure chaude.'}},
        sizes:['M','L','XL'], colors:['أسود','رمادي'], images:['https://picsum.photos/seed/p7/800/1000']
      },
      {
        id:'p8', category:'محجبات', price:3000, stock:12, rating:4.8,
        translations:{ar:{title:'عباية محتشمة أنيقة',desc:'تصميم كلاسيكي يناسب العائلة المحافظة.'},en:{title:'Modest Abaya',desc:'Classic design for conservative families.'},fr:{title:'Abaya modeste',desc:'Design classique pour familles conservatrices.'}},
        sizes:['S','M','L'], colors:['أسود','كحلي'], images:['https://picsum.photos/seed/p8/800/1000']
      },
      {
        id:'p9', category:'أطفال', price:1800, stock:20, rating:4.2,
        translations:{ar:{title:'طقم رياضي أطفال',desc:'مناسب للمدرسة والنشاطات.'},en:{title:'Kids Sport Set',desc:'Good for school and activities.'},fr:{title:'Ensemble sport enfant',desc:'Convient pour l\'école et activités.'}},
        sizes:['4-6','7-9'], colors:['أخضر','أزرق'], images:['https://picsum.photos/seed/p9/800/1000']
      },
      {
        id:'p10', category:'أكسسوارات', price:4500, stock:7, rating:4.6,
        translations:{ar:{title:'حقيبة نسائية جلد',desc:'حقيبة يد فاخرة بسعة جيدة.'},en:{title:'Leather Handbag',desc:'Stylish handbag with good capacity.'},fr:{title:'Sac à main cuir',desc:'Sac élégant et spacieux.'}},
        sizes:[], colors:['أسود','بني'], images:['https://picsum.photos/seed/p10/800/1000']
      },
      {
        id:'p11', category:'رجالي', price:3200, stock:9, rating:4.0,
        translations:{ar:{title:'جينز مريح',desc:'قصة عملية ومريحة للاستخدام اليومي.'},en:{title:'Comfort Jeans',desc:'Casual fit for daily use.'},fr:{title:'Jeans confort',desc:'Coupe pratique pour usage quotidien.'}},
        sizes:['M','L','XL'], colors:['أزرق','أسود'], images:['https://picsum.photos/seed/p11/800/1000']
      },
      {
        id:'p12', category:'نسائي', price:2800, stock:11, rating:4.3,
        translations:{ar:{title:'تنورة أنيقة',desc:'قماش عالي الجودة ومظهر عصري.'},en:{title:'Elegant Skirt',desc:'High-quality fabric and modern look.'},fr:{title:'Jupe élégante',desc:'Tissu de haute qualité et look moderne.'}},
        sizes:['S','M','L'], colors:['أسود','بني'], images:['https://picsum.photos/seed/p12/800/1000']
      }
      // => يمكن إضافة المزيد من المنتجات هنا بسهولة
    ];

    // ---------- ترجمات الواجهة ----------
    const translations = {
      ar: {
        home: 'الرئيسية', products: 'المنتجات', cart: 'سلة المشتريات', contact: 'اتصل بنا',
        filters: 'الأقسام', priceFilter: 'فلتر بالسعر', sortBy: 'ترتيب حسب', popular: 'الأكثر شعبية', cheap: 'الأرخص', expensive: 'الأغلى',
        addToCart: 'أضف إلى السلة', view: 'عرض', checkout: 'الدفع', total: 'المجموع', emptyCart: 'السلة فارغة', loadMore: 'تحميل المزيد', apply: 'تطبيق', reset: 'إعادة'
      },
      en: {
        home: 'Home', products: 'Products', cart: 'Cart', contact: 'Contact',
        filters: 'Categories', priceFilter: 'Price Filter', sortBy: 'Sort by', popular: 'Popular', cheap: 'Cheapest', expensive: 'Most expensive',
        addToCart: 'Add to cart', view: 'View', checkout: 'Checkout', total: 'Total', emptyCart: 'Cart is empty', loadMore: 'Load more', apply: 'Apply', reset: 'Reset'
      },
      fr: {
        home: 'Accueil', products: 'Produits', cart: 'Panier', contact: 'Contact',
        filters: 'Catégories', priceFilter: 'Filtrer par prix', sortBy: 'Trier par', popular: 'Populaire', cheap: 'Le moins cher', expensive: 'Le plus cher',
        addToCart: 'Ajouter', view: 'Voir', checkout: 'Payer', total: 'Total', emptyCart: 'Le panier est vide', loadMore: 'Charger plus', apply: 'Appliquer', reset: 'Réinitialiser'
      }
    };

    // ---------- حالة التطبيق ----------
    let state = {
      lang: localStorage.getItem('shamso_lang_v1') || 'ar',
      productsShown: 8,
      activeCategory: 'الكل',
      search: '',
      minPrice: null,
      maxPrice: null,
      sort: 'popular',
      cart: JSON.parse(localStorage.getItem('shamso_cart_v1') || '[]')
    };

    // ---------- عناصر DOM ----------
    const productsGrid = document.getElementById('productsGrid');
    const cartCountEl = document.getElementById('cartCount');
    const cartPanel = document.getElementById('cartPanel');
    const cartItemsContainer = document.getElementById('cartItemsContainer');
    const cartTotalEl = document.getElementById('cartTotal');
    const modalBackdrop = document.getElementById('modalBackdrop');
    const modalBody = document.getElementById('modalBody');
    const langSelect = document.getElementById('langSelect');
    const searchInput = document.getElementById('searchInput');
    const categoriesList = document.getElementById('categoriesList');
    const resultCount = document.getElementById('resultCount');
    const productsTitle = document.getElementById('productsTitle');
    const loadMoreBtn = document.getElementById('loadMoreBtn');

    // ---------- مساعدات صغيرة ----------
    function t(key){ return translations[state.lang][key] || key }
    function pT(product){ return product.translations[state.lang] ? product.translations[state.lang].title : product.translations['ar'].title }
    function pD(product){ return product.translations[state.lang] ? product.translations[state.lang].desc : product.translations['ar'].desc }
    function formatPrice(price){ return price + ' دج' }

    // ---------- Init ----------
    function init(){
      // set language select
      langSelect.value = state.lang;
      applyLang();
      renderCategories();
      renderProducts();
      updateCartUI();
      // events
      langSelect.addEventListener('change', e=>{ state.lang = e.target.value; localStorage.setItem('shamso_lang_v1', state.lang); applyLang(); renderProducts(); renderCategories(); updateCartUI() });
      document.getElementById('openCartBtn').addEventListener('click', ()=>toggleCart(true));
      document.getElementById('closeCartBtn').addEventListener('click', ()=>toggleCart(false));
      document.getElementById('clearCartBtn').addEventListener('click', clearCart);
      document.getElementById('checkoutBtn').addEventListener('click', openCheckout);
      document.getElementById('closeModalBtn').addEventListener('click', closeModal);
      document.getElementById('applyFiltersBtn').addEventListener('click', applyFilters);
      document.getElementById('resetFiltersBtn').addEventListener('click', resetFilters);
      document.getElementById('sortSelect').addEventListener('change', e=>{ state.sort = e.target.value; renderProducts(); });
      document.getElementById('searchInput').addEventListener('input', e=>{ state.search = e.target.value; renderProducts(); });
      document.getElementById('minPrice').addEventListener('input', e=> state.minPrice = e.target.value ? Number(e.target.value) : null);
      document.getElementById('maxPrice').addEventListener('input', e=> state.maxPrice = e.target.value ? Number(e.target.value) : null);
      document.getElementById('loadMoreBtn').addEventListener('click', ()=>{ state.productsShown += 6; renderProducts(); });
      document.getElementById('clearBtn').addEventListener('click', ()=>{ document.getElementById('searchInput').value=''; state.search=''; renderProducts(); });
      // close modal backdrop when clicking outside
      modalBackdrop.addEventListener('click', (e)=>{ if(e.target === modalBackdrop) closeModal() });

      // set initial dir and lang
      document.documentElement.lang = state.lang;
      document.documentElement.dir = (state.lang === 'ar') ? 'rtl' : 'ltr';
    }

    // ---------- Language apply ----------
    function applyLang(){
      // adjust direction and some labels
      document.documentElement.dir = (state.lang === 'ar') ? 'rtl' : 'ltr';
      document.documentElement.lang = state.lang;
      document.getElementById('filtersTitle').innerText = translations[state.lang].filters || 'Filters';
      document.getElementById('filterTitlePrice').innerText = translations[state.lang].priceFilter || 'Price';
      document.getElementById('sortTitle').innerText = translations[state.lang].sortBy || 'Sort by';
      document.getElementById('productsTitle').innerText = translations[state.lang].products || 'Products';
      loadMoreBtn.innerText = translations[state.lang].loadMore || 'Load more';
      document.getElementById('cartTitle').innerText = translations[state.lang].cart || 'Cart';
      document.getElementById('checkoutBtn').innerText = translations[state.lang].checkout || 'Checkout';
    }

    // ---------- Categories render ----------
    function getCategories(){
      const cats = new Set(['الكل']);
      products.forEach(p=>cats.add(p.category));
      return Array.from(cats);
    }
    function renderCategories(){
      const cats = getCategories();
      categoriesList.innerHTML = '';
      cats.forEach(cat=>{
        const btn = document.createElement('button');
        btn.className = 'cat-btn' + (state.activeCategory===cat ? ' active' : '');
        btn.innerText = cat;
        btn.addEventListener('click', ()=>{ state.activeCategory = cat; document.querySelectorAll('.cat-btn').forEach(b=>b.classList.remove('active')); btn.classList.add('active'); renderProducts(); });
        categoriesList.appendChild(btn);
      })
    }

    // ---------- Products render ----------
    function filterAndSort(list){
      let out = [...list];
      // category
      if(state.activeCategory && state.activeCategory !== 'الكل') out = out.filter(p=>p.category === state.activeCategory);
      // search
      if(state.search) {
        const s = state.search.toLowerCase();
        out = out.filter(p=> pT(p).toLowerCase().includes(s) || pD(p).toLowerCase().includes(s) || p.category.toLowerCase().includes(s) );
      }
      // price
      if(state.minPrice !== null) out = out.filter(p => p.price >= state.minPrice);
      if(state.maxPrice !== null) out = out.filter(p => p.price <= state.maxPrice);
      // sort
      if(state.sort === 'price-asc') out.sort((a,b)=>a.price-b.price);
      else if(state.sort === 'price-desc') out.sort((a,b)=>b.price-a.price);
      else out.sort((a,b)=> (b.rating||0) - (a.rating||0));
      return out;
    }

    function renderProducts(){
      const filtered = filterAndSort(products);
      resultCount.innerText = filtered.length + ' منتج';
      productsGrid.innerHTML = '';
      const slice = filtered.slice(0, state.productsShown);
      slice.forEach(prod=>{
        const card = document.createElement('article');
        card.className = 'card';
        card.innerHTML = `
          <div class="card-media">
            <img src="${prod.images[0]}" alt="${escapeHtml(pT(prod))}" />
          </div>
          <div class="card-body">
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div>
                <div class="title">${escapeHtml(pT(prod))}</div>
                <div class="meta">${escapeHtml(prod.category)} · ${prod.rating || '-'} ★</div>
              </div>
              <div class="price">${formatPrice(prod.price)}</div>
            </div>
            <div style="display:flex;justify-content:space-between;align-items:center;margin-top:.6rem">
              <div class="actions">
                <button class="btn btn-ghost" onclick="openQuickView('${prod.id}')">${escapeHtml(translations[state.lang].view || 'View')}</button>
                <button class="btn btn-primary" onclick="addToCart('${prod.id}')">${escapeHtml(translations[state.lang].addToCart || 'Add')}</button>
              </div>
            </div>
          </div>
        `;
        productsGrid.appendChild(card);
      });

      // if less products than shown, hide load more
      loadMoreBtn.style.display = (filtered.length > state.productsShown) ? 'inline-block' : 'none';
    }

    // ---------- Modal quick view ----------
    function openQuickView(id){
      const p = products.find(x=>x.id===id); if(!p) return;
      modalBody.innerHTML = `
        <div style="padding:1rem">
          <img src="${p.images[0]}" alt="${escapeHtml(pT(p))}" />
        </div>
        <div style="padding:1rem;display:flex;flex-direction:column;gap:.6rem">
          <h3 style="margin:0">${escapeHtml(pT(p))}</h3>
          <div class="small text-muted">${escapeHtml(p.category)} · ${p.rating || '-'} ★</div>
          <div style="font-weight:800;font-size:1.1rem">${formatPrice(p.price)}</div>
          <p class="text-muted">${escapeHtml(pD(p))}</p>

          <div style="display:flex;gap:.5rem;align-items:center">
            <label class="small">الكمية:</label>
            <input id="qtyInput" type="number" value="1" min="1" max="${p.stock}" style="width:80px;padding:.4rem;border:1px solid #eee;border-radius:8px" />
          </div>

          ${p.sizes && p.sizes.length ? `<div><label class="small">المقاس:</label><div style="display:flex;gap:.4rem;margin-top:.3rem">${p.sizes.map(s=>`<button class=\"btn btn-ghost\" onclick=\"selectTempSize(this)\">${s}</button>`).join('')}</div></div>` : ''}

          ${p.colors && p.colors.length ? `<div><label class="small">اللون:</label><div style="display:flex;gap:.4rem;margin-top:.3rem">${p.colors.map(c=>`<button class=\"btn btn-ghost\" onclick=\"selectTempColor(this)\">${c}</button>`).join('')}</div></div>` : ''}

          <div style="margin-top:auto;display:flex;gap:.6rem">
            <button class="btn btn-primary" onclick="addToCart('${p.id}', Number(document.getElementById('qtyInput').value))">${escapeHtml(translations[state.lang].addToCart)}</button>
            <button class="btn btn-ghost" onclick="toggleCart(true)">${escapeHtml(translations[state.lang].view)}</button>
          </div>
        </div>
      `;
      openModal();
    }

    // small helpers for modal selections
    function selectTempSize(el){ document.querySelectorAll('.modal .btn-ghost').forEach(b=>b.classList.remove('selected')); el.classList.add('selected'); }
    function selectTempColor(el){ document.querySelectorAll('.modal .btn-ghost').forEach(b=>b.classList.remove('selected')); el.classList.add('selected'); }

    function openModal(){ modalBackdrop.classList.add('open'); modalBackdrop.setAttribute('aria-hidden', 'false'); }
    function closeModal(){ modalBackdrop.classList.remove('open'); modalBackdrop.setAttribute('aria-hidden', 'true'); }

    // ---------- Cart logic ----------
    function saveCart(){ localStorage.setItem('shamso_cart_v1', JSON.stringify(state.cart)); }
    function updateCartUI(){
      cartCountEl.innerText = state.cart.reduce((s,i)=>s+i.qty,0);
      cartItemsContainer.innerHTML = '';
      if(state.cart.length === 0){ cartItemsContainer.innerHTML = `<div class="small text-muted">${escapeHtml(translations[state.lang].emptyCart)}</div>`; cartTotalEl.innerText = '0 دج'; return; }
      let total = 0;
      state.cart.forEach((item, idx)=>{
        const prod = products.find(p=>p.id === item.productId);
        if(!prod) return;
        const el = document.createElement('div'); el.className='cart-item';
        el.innerHTML = `
          <img src="${prod.images[0]}" alt="${escapeHtml(pT(prod))}" />
          <div style="flex:1">
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div><strong>${escapeHtml(pT(prod))}</strong><div class="small text-muted">${escapeHtml(prod.category)}</div></div>
              <div style="text-align:right">${formatPrice(prod.price)}<div class="small">x ${item.qty}</div></div>
            </div>
            <div style="margin-top:.5rem;display:flex;gap:.4rem;align-items:center">
              <button class="btn btn-ghost" onclick="changeQty(${idx}, -1)">-</button>
              <div class="small">${item.qty}</div>
              <button class="btn btn-ghost" onclick="changeQty(${idx}, 1)">+</button>
              <button class="btn btn-ghost" style="margin-inline-start:auto" onclick="removeFromCart(${idx})">حذف</button>
            </div>
          </div>
        `;
        cartItemsContainer.appendChild(el);
        total += prod.price * item.qty;
      });
      cartTotalEl.innerText = formatPrice(total);
      saveCart();
    }

    function addToCart(productId, qty = 1){
      const prod = products.find(p=>p.id === productId); if(!prod) return alert('منتج غير موجود');
      // حاول دمج العناصر نفسها
      const existing = state.cart.find(c=>c.productId === productId);
      if(existing){ existing.qty += qty; } else { state.cart.push({ productId, qty }); }
      updateCartUI();
      toggleCart(true);
    }

    function removeFromCart(index){ state.cart.splice(index,1); updateCartUI(); }
    function changeQty(index, delta){ if(!state.cart[index]) return; state.cart[index].qty += delta; if(state.cart[index].qty < 1) state.cart[index].qty = 1; updateCartUI(); }
    function clearCart(){ if(confirm('هل تريد تفريغ السلة؟')){ state.cart = []; updateCartUI(); } }

    function toggleCart(open){ cartPanel.classList.toggle('open', !!open); cartPanel.setAttribute('aria-hidden', open ? 'false' : 'true'); }

    // ---------- Checkout (محاكاة) ----------
    function openCheckout(){
      if(state.cart.length === 0){ alert(translations[state.lang].emptyCart); return; }
      closeModal();
      // عرض نموذج في المودال
      modalBody.innerHTML = `
        <div style="padding:1rem;grid-column:1/-1">
          <h3>نموذج الدفع</h3>
          <p class="small text-muted">املأ المعلومات وسيتم محاكاة إرسال الطلب (لا يوجد باك‑إند في هذا المثال).</p>
          <div style="display:flex;flex-direction:column;gap:.6rem;margin-top:1rem">
            <input id="checkoutName" placeholder="الاسم الكامل" style="padding:.6rem;border-radius:8px;border:1px solid #eee" />
            <input id="checkoutPhone" placeholder="رقم الهاتف" style="padding:.6rem;border-radius:8px;border:1px solid #eee" />
            <input id="checkoutAddress" placeholder="العنوان" style="padding:.6rem;border-radius:8px;border:1px solid #eee" />
            <button class="btn btn-primary" onclick="submitOrder()">إرسال الطلب</button>
          </div>
        </div>
      `;
      openModal();
    }

    function submitOrder(){
      const name = document.getElementById('checkoutName').value.trim();
      const phone = document.getElementById('checkoutPhone').value.trim();
      const address = document.getElementById('checkoutAddress').value.trim();
      if(!name || !phone || !address){ return alert('يرجى تعبئة جميع الحقول'); }
      // نجمع تفاصيل الطلب
      const order = {
        id: 'ORD-' + Date.now(),
        name, phone, address,
        items: state.cart.map(ci=>({ productId:ci.productId, qty:ci.qty })),
        total: state.cart.reduce((s,i)=> s + (products.find(p=>p.id===i.productId).price * i.qty), 0),
        createdAt: new Date().toISOString()
      };
      // هنا يمكنك إرسال الطلب إلى السيرفر — في المثال نحفظه محليًا كمحفوظات
      const history = JSON.parse(localStorage.getItem('shamso_orders_v1') || '[]');
      history.push(order);
      localStorage.setItem('shamso_orders_v1', JSON.stringify(history));
      // تفريغ السلة
      state.cart = [];
      updateCartUI();
      closeModal();
      toggleCart(false);
      alert('تم إرسال الطلب بنجاح! رقم الطلب: ' + order.id);
    }

    // ---------- Utilities ----------
    function escapeHtml(str){ if(!str) return ''; return String(str).replace(/[&<>"']/g, function(m){ return ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'})[m]; }); }

    // ---------- Simple filter apply / reset ----------
    function applyFilters(){ state.minPrice = document.getElementById('minPrice').value ? Number(document.getElementById('minPrice').value) : null; state.maxPrice = document.getElementById('maxPrice').value ? Number(document.getElementById('maxPrice').value) : null; renderProducts(); }
    function resetFilters(){ document.getElementById('minPrice').value=''; document.getElementById('maxPrice').value=''; state.minPrice = null; state.maxPrice = null; state.activeCategory='الكل'; renderCategories(); renderProducts(); }

    // ---------- Expose some functions for inline onclick handlers ----------
    window.openQuickView = openQuickView;
    window.addToCart = addToCart;
    window.removeFromCart = removeFromCart;
    window.changeQty = changeQty;
    window.toggleCart = toggleCart;

    // ---------- Start ----------
    init();

  </script></body>
</html>
