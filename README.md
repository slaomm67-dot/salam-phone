<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق سلام فون - النسخة الذهبية الفاخرة</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body { font-family: 'Tajawal', sans-serif; background-color: #f4f6f8; -webkit-tap-highlight-color: transparent; }
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
        @keyframes cart-bounce {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); rotate: -10deg; }
            100% { transform: scale(1); }
        }
        .animate-cart { animation: cart-bounce 0.4s ease-in-out; }
        .gold-text {
            background: linear-gradient(to right, #ffe596 0%, #ffc107 50%, #b58400 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            filter: drop-shadow(0px 2px 4px rgba(0, 0, 0, 0.3));
        }
    </style>
</head>
<body class="pb-24 text-gray-800">

    <!-- شريط علوي ذكي ثابت بتصميم ذهبي -->
    <div id="main-nav" class="bg-white sticky top-0 z-40 shadow-sm border-b border-gray-100">
        <div class="container mx-auto px-4 py-3 flex items-center justify-between gap-3">
            <div class="flex items-center gap-2" onclick="goBackToHome()">
                <div class="w-10 h-10 bg-gradient-to-br from-red-700 to-red-900 text-amber-400 rounded-full flex items-center justify-center font-black text-xl shadow-md border border-amber-400 cursor-pointer">S</div>
                <div class="cursor-pointer">
                    <h1 class="text-md font-black text-gray-900 leading-tight">سلام <span class="text-amber-500">فون</span></h1>
                    <span class="text-[10px] bg-red-50 text-red-600 px-1.5 py-0.5 rounded-full font-medium border border-red-100">المتجر الرسمي</span>
                </div>
            </div>
            
            <div class="relative cursor-pointer bg-gray-50 px-3 py-2 rounded-xl border border-gray-100 flex items-center gap-2" onclick="openCartPage()">
                <i id="cart-icon-nav" class="fa-solid fa-bag-shopping text-xl text-gray-700 transition"></i>
                <span id="cart-badge" class="bg-red-600 text-white text-[11px] w-5 h-5 rounded-full flex items-center justify-center font-bold">0</span>
            </div>
        </div>
    </div>

    <!-- إشعار نجاح الإضافة -->
    <div id="toast-notification" class="fixed top-16 left-4 right-4 bg-gray-900/95 text-white text-xs text-center py-3 px-4 rounded-xl shadow-xl z-50 hidden transition-all duration-300">
        <i class="fa-solid fa-circle-check text-green-400 ml-1.5"></i> تم إضافة الجهاز بالفئة واللون المختار إلى سلتك!
    </div>

    <!-- ==================== 1. صفحة الرئيسية ==================== -->
    <div id="page-home" class="app-page">
        <div class="container mx-auto px-4 mt-4">
            
            <!-- لوحة سلام فون الاحترافية الجديدة باللون الأحمر والخط الذهبي الفاخر -->
            <div class="w-full h-44 bg-gradient-to-br from-red-800 via-red-600 to-red-950 rounded-2xl p-6 text-white relative overflow-hidden shadow-xl border-2 border-amber-400/80 flex items-center">
                <div class="z-10 max-w-[70%] space-y-1">
                    <span class="bg-amber-400/20 text-amber-300 text-[9px] font-bold px-2.5 py-0.5 rounded-full border border-amber-400/30 uppercase tracking-wider">التميز والأصالة لعام 2026</span>
                    <h2 class="text-3xl font-black gold-text tracking-tight">سلام فون</h2>
                    <h3 class="text-xs font-bold text-amber-200/90">تسوّق أحدث الهواتف الذكية نقداً وبأقساط ميسرة</h3>
                    <p class="text-[10px] text-white/70 pt-1">نظام أقساط مرن ومريح لمدة 10 أشهر لجميع زبائننا الكرام.</p>
                </div>
                <i class="fa-solid fa-crown absolute left-4 text-8xl opacity-10 text-amber-300 transform -rotate-12"></i>
            </div>
            
        </div>

        <div class="container mx-auto px-4 mt-5">
            <div id="brands-bar" class="flex gap-2.5 overflow-x-auto no-scrollbar py-1">
                <button onclick="filterBrand('all', this)" class="brand-btn bg-red-600 text-white text-xs font-bold px-4 py-2 rounded-xl shadow-sm whitespace-nowrap">كل الشركات</button>
                <button onclick="filterBrand('apple', this)" class="brand-btn bg-white text-gray-700 border border-gray-200 text-xs font-medium px-4 py-2 rounded-xl whitespace-nowrap">آبل Apple</button>
            </div>
        </div>

        <div class="container mx-auto px-4 mt-6">
            <h3 class="text-sm font-bold text-gray-900 border-r-4 border-red-600 pr-2 mb-4">الأجهزة المتاحة حالياً للطلب</h3>
            <div id="products-grid" class="grid grid-cols-2 gap-3">
                
                <div class="product-card bg-white rounded-2xl border border-gray-100 overflow-hidden shadow-sm flex flex-col justify-between cursor-pointer hover:border-red-500 transition duration-200" data-brand="apple" onclick="goToProductDetails('apple1')">
                    <div class="bg-gray-50 h-36 flex items-center justify-center relative p-2">
                        <img id="main-apple-thumb" src="" class="h-full w-full object-contain" alt="iPhone 17 Pro Max">
                        <span class="absolute top-2 left-2 bg-red-600 text-white text-[9px] font-bold px-2 py-0.5 rounded">إصدار 2026 🔥</span>
                    </div>
                    <div class="p-3">
                        <h4 class="text-xs font-bold text-gray-800 line-clamp-1">iPhone 17 Pro Max (2 شريحة)</h4>
                        <div class="text-xs font-black text-red-600 mt-1">1,850,000 د.ع</div>
                        <div class="text-[9px] text-gray-500 mt-1 bg-gray-50 p-1 rounded text-center">قسط 10 أشهر: 185,000 د.ع</div>
                    </div>
                </div>

            </div>
        </div>
    </div>

    <div id="page-categories" class="app-page hidden container mx-auto px-4 mt-4">
        <h3 class="text-md font-bold text-gray-900 mb-4 border-r-4 border-red-600 pr-2">الأقسام الرئيسية</h3>
        <div class="bg-white p-5 rounded-2xl shadow-sm text-xs text-gray-400 text-center">الأقسام جاهزة ومثبتة.</div>
    </div>
    <div id="page-offers" class="app-page hidden container mx-auto px-4 mt-4">
        <h3 class="text-md font-bold text-gray-900 mb-4 border-r-4 border-red-600 pr-2">العروض الحالية</h3>
        <div class="bg-white p-4 rounded-2xl shadow-sm text-sm text-gray-500">هدية شاحن أصلي سريع مجاناً مع كل عملية شراء! 🎁</div>
    </div>
    <div id="page-profile" class="app-page hidden container mx-auto px-4 mt-4">
        <div class="bg-white rounded-2xl p-6 text-center shadow-sm"><h3 class="font-bold text-sm">حساب المشترك</h3></div>
    </div>

    <!-- ==================== 2. واجهة تفاصيل المنتج المتطورة ==================== -->
    <div id="page-product-view" class="app-page hidden bg-white min-h-screen absolute top-0 left-0 right-0 z-50 pb-24">
        <div class="bg-white shadow-sm border-b border-gray-100 sticky top-0 px-4 py-3.5 flex items-center gap-4">
            <button onclick="goBackToHome()" class="w-9 h-9 bg-gray-100 rounded-full flex items-center justify-center text-gray-700"><i class="fa-solid fa-arrow-right"></i></button>
            <h2 class="font-bold text-gray-900 text-sm">مواصفات وتخصيص الجهاز</h2>
        </div>

        <div class="container mx-auto max-w-md px-4 mt-4 space-y-5">
            <div class="w-full h-72 bg-gray-50 rounded-2xl overflow-hidden shadow-sm border border-gray-100 flex items-center justify-center p-4 relative group">
                <button onclick="prevProductImage()" class="absolute right-3 top-1/2 -translate-y-1/2 w-9 h-9 bg-white/90 backdrop-blur rounded-full flex items-center justify-center shadow-md z-10 active:scale-95 transition text-gray-700 hover:bg-white">
                    <i class="fa-solid fa-chevron-right text-xs"></i>
                </button>
                <img id="details-img" src="" class="h-full w-auto object-contain transition-all duration-300" alt="Product Image">
                <button onclick="nextProductImage()" class="absolute left-3 top-1/2 -translate-y-1/2 w-9 h-9 bg-white/90 backdrop-blur rounded-full flex items-center justify-center shadow-md z-10 active:scale-95 transition text-gray-700 hover:bg-white">
                    <i class="fa-solid fa-chevron-left text-xs"></i>
                </button>
                <div id="gallery-dots" class="absolute bottom-3 left-1/2 -translate-x-1/2 flex gap-1.5 z-10"></div>
            </div>

            <div class="space-y-1.5">
                <div class="flex justify-between items-center">
                    <h3 id="details-title" class="text-base font-bold text-gray-900 leading-snug">اسم الجهاز</h3>
                    <span class="bg-amber-100 text-amber-800 text-[10px] font-bold px-2.5 py-1 rounded-full"><i class="fa-solid fa-calendar-days ml-1"></i>الأقساط: 10 أشهر</span>
                </div>
                <p id="details-description" class="text-xs text-gray-600 leading-relaxed text-justify">المواصفات الكاملة تظهر هنا.</p>
            </div>

            <hr class="border-gray-100">

            <div class="space-y-2">
                <span class="text-xs font-bold text-gray-500 block"><i class="fa-solid fa-credit-card text-red-600 ml-1"></i> طريقة السداد المطلوبة:</span>
                <div class="grid grid-cols-2 gap-3">
                    <div id="option-cash" onclick="selectProductPaymentType('cash')" class="cursor-pointer border-2 border-red-600 bg-red-50/40 rounded-2xl p-3 text-center relative shadow-sm">
                        <span id="check-icon-cash" class="absolute top-1.5 right-2 text-red-600 text-xs"><i class="fa-solid fa-circle-check"></i></span>
                        <span class="text-[10px] font-bold text-gray-400 block mb-0.5">شراء نقداً</span>
                        <span id="details-cash-price" class="text-xs font-black text-red-600">0 د.ع</span>
                    </div>
                    <div id="option-inst" onclick="selectProductPaymentType('inst')" class="cursor-pointer border-2 border-gray-200 bg-white rounded-2xl p-3 text-center relative shadow-sm">
                        <span id="check-icon-inst" class="absolute top-1.5 right-2 text-amber-500 text-xs hidden"><i class="fa-solid fa-circle-check"></i></span>
                        <span class="text-[10px] font-bold text-gray-400 block mb-0.5">قسط شهري (10 أشهر)</span>
                        <span id="details-inst-price" class="text-xs font-black text-gray-700">0 د.ع / شهر</span>
                    </div>
                </div>
            </div>

            <div class="space-y-2">
                <span class="text-xs font-bold text-gray-500 block"><i class="fa-solid fa-microchip text-gray-400 ml-1"></i> اختر سعة التخزين (الذاكرة):</span>
                <div id="storage-container" class="flex gap-2.5"></div>
            </div>

            <div class="space-y-2">
                <span class="text-xs font-bold text-gray-500 block"><i class="fa-solid fa-palette text-gray-400 ml-1"></i> اختر اللون المتوفر:</span>
                <div id="color-container" class="flex gap-4 items-center py-1"></div>
            </div>

            <div class="pt-2">
                <button onclick="triggerAddToCartAnimation()" class="w-full bg-gray-900 hover:bg-black text-white font-bold text-xs py-4 rounded-xl flex items-center justify-center gap-2 shadow-lg transition">
                    <i class="fa-solid fa-cart-plus text-sm"></i> إضافة إلى السلة واعتماد الاختيارات 🛒
                </button>
            </div>
        </div>
    </div>

    <!-- ==================== 3. واجهة مراجعة الطلب والفاتورة ==================== -->
    <div id="page-cart" class="app-page hidden bg-white min-h-screen absolute top-0 left-0 right-0 z-50 pb-24">
        <div class="bg-white shadow-sm border-b border-gray-100 sticky top-0 px-4 py-3.5 flex items-center gap-4">
            <button onclick="goBackToHome()" class="w-9 h-9 bg-gray-100 rounded-full flex items-center justify-center text-gray-700"><i class="fa-solid fa-arrow-right"></i></button>
            <h2 class="font-bold text-gray-900 text-sm">مراجعة الفاتورة النهائية</h2>
        </div>
        <div class="container mx-auto max-w-md px-4 mt-4">
            <div id="cart-items-list" class="space-y-3 mb-4"></div>
            <div class="bg-gray-50 rounded-2xl p-4 border border-gray-100 space-y-2 shadow-inner">
                <div class="flex justify-between items-center">
                    <span class="text-xs font-bold text-gray-900">إجمالي الفاتورة النهائي المجمع:</span>
                    <span id="cart-total-price" class="text-sm font-black text-red-600">0 د.ع</span>
                </div>
            </div>
            <div class="pt-2">
                <button onclick="confirmOrderAndGoToTracking()" class="w-full bg-red-600 hover:bg-red-700 text-white font-bold text-xs py-4 rounded-xl mt-5 flex items-center justify-center gap-2 shadow-md transition">
                    <i class="fa-solid fa-circle-check"></i> تأكيد الطلب بالكامل وتوجيهه للواتساب
                </button>
            </div>
        </div>
    </div>

    <!-- ==================== 4. واجهة تتبع الطلب ==================== -->
    <div id="page-tracking" class="app-page hidden bg-white min-h-screen absolute top-0 left-0 right-0 z-50 pb-24">
        <div class="bg-white shadow-sm border-b border-gray-100 sticky top-0 px-4 py-3.5 flex items-center gap-4">
            <button onclick="goBackToHome()" class="w-9 h-9 bg-gray-100 rounded-full flex items-center justify-center text-gray-700"><i class="fa-solid fa-arrow-right"></i></button>
            <h2 class="font-bold text-gray-900 text-sm">شريط تتبع حالة شحنتك الحالية</h2>
        </div>
        <div class="container mx-auto max-w-md px-4 mt-4">
            <div class="bg-white rounded-2xl p-6 border border-gray-100 shadow-md relative space-y-8">
                <div class="absolute right-9 top-10 bottom-10 w-0.5 bg-gray-100"></div>
                <div id="progress-line" class="absolute right-9 top-10 w-0.5 bg-green-500 h-0 transition-all duration-700"></div>

                <div id="step-1" class="flex items-center gap-4 relative z-10 text-gray-300">
                    <div class="step-circle w-7 h-7 bg-gray-200 rounded-full flex items-center justify-center text-xs font-bold text-white"><i class="fa-solid fa-clock text-[10px]"></i></div>
                    <div><h4 class="font-bold text-xs text-gray-900">قيد التجهيز في المخزن</h4><p class="text-[10px] text-gray-400 mt-0.5">نراجع ونثبت فاتورة جهازك سلام فون الآن</p></div>
                </div>
                <div id="step-2" class="flex items-center gap-4 relative z-10 text-gray-300">
                    <div class="step-circle w-7 h-7 bg-gray-200 rounded-full flex items-center justify-center text-xs font-bold text-white"><i class="fa-solid fa-box text-[10px]"></i></div>
                    <div><h4 class="font-bold text-xs text-gray-900">تم التجهيز والتغليف الآمن</h4><p class="text-[10px] text-gray-400 mt-0.5">تم فحص وضمان الجهاز بالكامل وملحقاته</p></div>
                </div>
                <div id="step-3" class="flex items-center gap-4 relative z-10 text-gray-300">
                    <div class="step-circle w-7 h-7 bg-gray-200 rounded-full flex items-center justify-center text-xs font-bold text-white"><i class="fa-solid fa-truck-fast text-[10px]"></i></div>
                    <div><h4 class="font-bold text-xs text-gray-900">المندوب في الطريق إليك الآن</h4><p class="text-[10px] text-gray-400 mt-0.5">الشحنة خرجت وتتوجه لعنوانك السكني</p></div>
                </div>
            </div>
            <button onclick="startTrackingSimulation()" class="w-full bg-gray-900 hover:bg-black text-white font-bold text-xs py-3.5 rounded-xl mt-5 flex items-center justify-center gap-2 shadow-md transition">
                <i class="fa-solid fa-play"></i> ابدأ محاكاة خطوة حركة التوصيل اللحظية 🔁
            </button>
        </div>
    </div>

    <!-- شريط التنقل السفلي الثابت -->
    <div id="bottom-nav" class="fixed bottom-0 left-0 right-0 bg-white border-t border-gray-200 shadow-[0_-2px_10px_rgba(0,0,0,0.05)] z-40">
        <div class="max-w-md mx-auto flex justify-around py-2 text-center text-gray-500">
            <div onclick="switchPage('page-home', this)" class="nav-item flex flex-col items-center text-red-600 font-bold cursor-pointer transition">
                <i class="fa-solid fa-house text-lg mb-0.5"></i><span class="text-[10px]">الرئيسية</span>
            </div>
            <div onclick="switchPage('page-categories', this)" class="nav-item flex flex-col items-center hover:text-red-600 cursor-pointer transition">
                <i class="fa-solid fa-layer-group text-lg mb-0.5"></i><span class="text-[10px]">الأقسام</span>
            </div>
            <div onclick="switchPage('page-offers', this)" class="nav-item flex flex-col items-center hover:text-red-600 cursor-pointer transition">
                <i class="fa-solid fa-percent text-lg mb-0.5"></i><span class="text-[10px]">العروض</span>
            </div>
            <div onclick="switchPage('page-profile', this)" class="nav-item flex flex-col items-center hover:text-red-600 cursor-pointer transition">
                <i class="fa-solid fa-user text-lg mb-0.5"></i><span class="text-[10px]">حسابي</span>
            </div>
        </div>
    </div>

    <script>
        const galleryOrange = [
            "https://i.ibb.co/Q7zHK8Bs/iphone-17-pro-1.png",       
            "https://i.ibb.co/WqRMvHb/ASSET-MMS-161585005.jpg", 
            "https://i.ibb.co/FbJVCjVS/ASSET-MMS-161585003.jpg"  
        ];

        const gallerySilver = [
            "https://i.ibb.co/ZpTb723t/iphone-17-pro-3.png",       
            "https://i.ibb.co/6R5ZLMT9/ASSET-MMS-161584970.jpg", 
            "https://i.ibb.co/vxGs3469/ASSET-MMS-161584969.jpg"  
        ];

        const galleryBlack = [
            "https://i.ibb.co/N6fwXqB9/iphone-17-pro-2.png",       
            "https://i.ibb.co/9m3LHsYd/ASSET-MMS-161585026.jpg", 
            "https://i.ibb.co/1fsgj87v/ASSET-MMS-161585023.jpg"  
        ];

        const productsDatabase = {
            apple1: {
                name: 'iPhone 17 Pro Max (نسخة 2 شريحة اتصال فعالة)',
                cashPrice: 1850000,
                instPrice: 185000, 
                desc: 'الإصدار الخارق لعام 2026 من آبل بنسخة متميزة تدعم شريحتين اتصال فعليتين معاً بدون eSIM. معالج A19 Pro فائق الذكاء، وهيكل متين مكسو بالتيتانيوم خفيف الوزن والمقاوم للخدوش مع كاميرات سينمائية احترافية تظهر تفاصيلها بالمعرض العلوي المقلب المطور.',
                storages: ['256GB', '512GB', '1TB'],
                colors: [
                    { name: 'البرتقالي الصحراوي الفخم', hex: '#e06a3b', gallery: galleryOrange }, 
                    { name: 'التيتانيوم الفضي البلاتيني', hex: '#a8a9ad', gallery: gallerySilver },
                    { name: 'الأسود الملكي الداكن', hex: '#232426', gallery: galleryBlack }
                ]
            }
        };

        let currentCart = [];
        let selectedProduct = null;
        let currentProductId = '';
        let currentImageIndex = 0;
        let currentGallery = [];

        window.onload = function() {
            document.getElementById('main-apple-thumb').src = productsDatabase.apple1.colors[0].gallery[0];
        };

        function switchPage(pageId, element) {
            const pages = document.querySelectorAll('.app-page');
            for (let i = 0; i < pages.length; i++) {
                pages[i].classList.add('hidden');
            }
            const targetPage = document.getElementById(pageId);
            if(targetPage) targetPage.classList.remove('hidden');
            
            document.getElementById('main-nav').classList.remove('hidden');
            document.getElementById('bottom-nav').classList.remove('hidden');
            
            if(element) {
                const items = document.querySelectorAll('.nav-item');
                for (let i = 0; i < items.length; i++) {
                    items[i].classList.remove('text-red-600', 'font-bold');
                }
                element.classList.add('text-red-600', 'font-bold');
            }
        }

        function goToProductDetails(productId) {
            currentProductId = productId;
            const product = productsDatabase[productId];
            if(!product) return;

            const pages = document.querySelectorAll('.app-page');
            for (let i = 0; i < pages.length; i++) {
                pages[i].classList.add('hidden');
            }
            document.getElementById('main-nav').classList.add('hidden');
            document.getElementById('bottom-nav').classList.add('hidden');

            document.getElementById('details-title').innerText = product.name;
            document.getElementById('details-description').innerText = product.desc;
            document.getElementById('details-cash-price').innerText = product.cashPrice.toLocaleString() + " د.ع";
            document.getElementById('details-inst-price').innerText = product.instPrice.toLocaleString() + " د.ع / شهر";

            currentGallery = [];
            for (let i = 0; i < product.colors[0].gallery.length; i++) {
                currentGallery.push(product.colors[0].gallery[i]);
            }
            currentImageIndex = 0;
            renderGalleryDots();
            updateSliderDisplay();

            selectedProduct = {
                name: product.name,
                cashPrice: product.cashPrice,
                instPrice: product.instPrice,
                img: currentGallery[0], 
                chosenMethod: 'cash',
                chosenStorage: product.storages[0],
                chosenColor: product.colors[0].name
            };

            const storageContainer = document.getElementById('storage-container');
            storageContainer.innerHTML = "";
            for (let i = 0; i < product.storages.length; i++) {
                const st = product.storages[i];
                const activeClass = i === 0 ? "border-red-600 bg-red-50 text-red-600" : "border-gray-200 bg-white text-gray-700";
                storageContainer.innerHTML += `<button onclick="selectStorage('${st}', this)" class="storage-btn border-2 ${activeClass} text-xs font-bold px-4 py-2 rounded-xl transition shadow-sm">${st}</button>`;
            }

            const colorContainer = document.getElementById('color-container');
            colorContainer.innerHTML = "";
            for (let i = 0; i < product.colors.length; i++) {
                const col = product.colors[i];
                const activeClass = i === 0 ? "ring-2 ring-offset-2 ring-red-600 scale-110" : "";
                colorContainer.innerHTML += `<div onclick="selectColor(${i}, this)" class="color-circle w-7 h-7 rounded-full cursor-pointer border border-gray-300 shadow-inner transition-all duration-150 ${activeClass}" style="background-color: ${col.hex};" title="${col.name}"></div>`;
            }

            selectProductPaymentType('cash');
            document.getElementById('page-product-view').classList.remove('hidden');
            window.scrollTo(0,0);
        }

        function updateSliderDisplay() {
            const imgDisplay = document.getElementById('details-img');
            if(imgDisplay && currentGallery.length > 0) {
                imgDisplay.src = currentGallery[currentImageIndex];
            }
            const dots = document.querySelectorAll('.gallery-dot');
            for (let i = 0; i < dots.length; i++) {
                if(i === currentImageIndex) {
                    dots[i].className = "gallery-dot w-4 h-1.5 bg-red-600 rounded-full transition-all duration-200";
                } else {
                    dots[i].className = "gallery-dot w-1.5 h-1.5 bg-gray-300 rounded-full transition-all duration-200";
                }
            }
            if(selectedProduct) {
                selectedProduct.img = currentGallery[currentImageIndex];
            }
        }

        function nextProductImage() {
            if(currentGallery.length <= 1) return;
            currentImageIndex = (currentImageIndex + 1) % currentGallery.length;
            updateSliderDisplay();
        }

        function prevProductImage() {
            if(currentGallery.length <= 1) return;
            currentImageIndex = (currentImageIndex - 1 + currentGallery.length) % currentGallery.length;
            updateSliderDisplay();
        }

        function renderGalleryDots() {
            const dotsContainer = document.getElementById('gallery-dots');
            dotsContainer.innerHTML = "";
            for (let i = 0; i < currentGallery.length; i++) {
                dotsContainer.innerHTML += `<span class="gallery-dot w-1.5 h-1.5 bg-gray-300 rounded-full transition-all duration-200"></span>`;
            }
        }

        function selectStorage(storage, element) {
            if(!selectedProduct) return;
            selectedProduct.chosenStorage = storage;
            const buttons = document.querySelectorAll('.storage-btn');
            for (let i = 0; i < buttons.length; i++) {
                buttons[i].className = "storage-btn border-2 border-gray-200 bg-white text-gray-700 text-xs font-bold px-4 py-2 rounded-xl transition shadow-sm";
            }
            element.className = "storage-btn border-2 border-red-600 bg-red-50 text-red-600 text-xs font-bold px-4 py-2 rounded-xl transition shadow-sm";
        }

        function selectColor(colorIndex, element) {
            if(!selectedProduct || !currentProductId) return;
            const product = productsDatabase[currentProductId];
            const col = product.colors[colorIndex];
            
            selectedProduct.chosenColor = col.name;
            currentGallery = [];
            for (let i = 0; i < col.gallery.length; i++) {
                currentGallery.push(col.gallery[i]);
            }
            currentImageIndex = 0;
            renderGalleryDots();
            updateSliderDisplay();

            const circles = document.querySelectorAll('.color-circle');
            for (let i = 0; i < circles.length; i++) {
                circles[i].className = "color-circle w-7 h-7 rounded-full cursor-pointer border border-gray-300 shadow-inner transition-all duration-150";
            }
            element.className = "color-circle w-7 h-7 rounded-full cursor-pointer border border-gray-300 shadow-inner transition-all duration-150 ring-2 ring-offset-2 ring-red-600 scale-110";
        }

        function selectProductPaymentType(type) {
            if(!selectedProduct) return;
            selectedProduct.chosenMethod = type;
            const cardCash = document.getElementById('option-cash');
            const cardInst = document.getElementById('option-inst');
            const iconCash = document.getElementById('check-icon-cash');
            const iconInst = document.getElementById('check-icon-inst');

            if(type === 'cash') {
                cardCash.className = "cursor-pointer border-2 border-red-600 bg-red-50/40 rounded-2xl p-3 text-center relative shadow-sm";
                cardInst.className = "cursor-pointer border-2 border-gray-200 bg-white rounded-2xl p-3 text-center relative shadow-sm";
                if(iconCash) iconCash.classList.remove('hidden');
                if(iconInst) iconInst.classList.add('hidden');
            } else {
                cardCash.className = "cursor-pointer border-2 border-gray-200 bg-white rounded-2xl p-3 text-center relative shadow-sm";
                cardInst.className = "cursor-pointer border-2 border-amber-500 bg-amber-50/40 rounded-2xl p-3 text-center relative shadow-sm";
                if(iconCash) iconCash.classList.add('hidden');
                if(iconInst) iconInst.classList.remove('hidden');
            }
        }

        function goBackToHome() {
            switchPage('page-home');
        }

        function triggerAddToCartAnimation() {
            if(!selectedProduct) return;
            selectedProduct.img = currentGallery[0]; 
            currentCart.push({ ...selectedProduct });
            document.getElementById('cart-badge').innerText = currentCart.length;
            
            const bagIcon = document.getElementById('cart-icon-nav');
            if(bagIcon) {
                bagIcon.classList.add('animate-cart', 'text-red-600');
                setTimeout(function() { bagIcon.classList.remove('animate-cart'); }, 400);
            }
            const toast = document.getElementById('toast-notification');
            if(toast) {
                toast.classList.remove('hidden');
                setTimeout(function() { toast.classList.add('hidden'); }, 2500);
            }
            goBackToHome();
        }

        function openCartPage() {
            const pages = document.querySelectorAll('.app-page');
            for (let i = 0; i < pages.length; i++) {
                pages[i].classList.add('hidden');
            }
            document.getElementById('main-nav').classList.add('hidden');
            document.getElementById('bottom-nav').classList.add('hidden');
            
            const listContainer = document.getElementById('cart-items-list');
            listContainer.innerHTML = "";
            let grandTotalCash = 0;
            let grandTotalInst = 0;

            if(currentCart.length === 0) {
                listContainer.innerHTML = `<div class="bg-white p-8 rounded-2xl text-center text-xs text-gray-400 border border-gray-100">سلتك فارغة حالياً!</div>`;
                document.getElementById('cart-total-price').innerText = "0 د.ع";
                document.getElementById('page-cart').classList.remove('hidden');
                return;
            }

            for (let index = 0; index < currentCart.length; index++) {
                const item = currentCart[index];
                const isCash = item.chosenMethod === 'cash';
                const methodLabel = isCash ? '<span class="bg-green-100 text-green-800 text-[9px] font-bold px-2 py-0.5 rounded-md">نقداً</span>' : '<span class="bg-amber-100 text-amber-800 text-[9px] font-bold px-2 py-0.5 rounded-md">أقساط</span>';
                const displayedPrice = isCash ? item.cashPrice : item.instPrice;
                
                if(isCash) grandTotalCash += item.cashPrice;
                else grandTotalInst += item.instPrice;

                listContainer.innerHTML += `
                    <div class="bg-white p-3.5 rounded-2xl border border-gray-100 shadow-sm flex items-center justify-between gap-3">
                        <div class="flex items-center gap-3">
                            <img src="${item.img}" class="w-12 h-12 rounded-xl object-contain bg-gray-50 p-0.5">
                            <div>
                                <h4 class="text-xs font-bold text-gray-900">${item.name}</h4>
                                <p class="text-[9px] text-gray-400 mt-0.5">الذاكرة: ${item.chosenStorage} | اللون: ${item.chosenColor}</p>
                                <div class="flex items-center gap-2 mt-1">${methodLabel} <span class="text-xs font-black text-gray-800">${displayedPrice.toLocaleString()} د.ع</span></div>
                            </div>
                        </div>
                        <button onclick="removeItemFromCart(${index})" class="text-gray-300 hover:text-red-500 text-xs p-1"><i class="fa-solid fa-trash-can"></i></button>
                    </div>`;
            }

            let totalString = "";
            if(grandTotalCash > 0) totalString += grandTotalCash.toLocaleString() + " د.ع (نقداً)";
            if(grandTotalInst > 0) {
                if(totalString !== "") totalString += " + ";
                totalString += grandTotalInst.toLocaleString() + " د.ع / شهرياً";
            }
            document.getElementById('cart-total-price').innerText = totalString;
            document.getElementById('page-cart').classList.remove('hidden');
        }

        function removeItemFromCart(index) {
            currentCart.splice(index, 1);
            document.getElementById('cart-badge').innerText = currentCart.length;
            openCartPage();
        }

        function confirmOrderAndGoToTracking() {
            if(currentCart.length === 0) return;
            const totalPrice = document.getElementById('cart-total-price').innerText;
            let itemsDetailsText = "";
            for (let i = 0; i < currentCart.length; i++) {
                const item = currentCart[i];
                const typeText = item.chosenMethod === 'cash' ? 'شراء نقداً' : 'نظام أقساط (10 أشهر)';
                const pr = item.chosenMethod === 'cash' ? item.cashPrice : item.instPrice;
                itemsDetailsText += `- ${item.name}\n  [الذاكرة: ${item.chosenStorage} | اللون: ${item.chosenColor} | النظام: ${typeText} | السعر: ${pr.toLocaleString()} د.ع]\n`;
            }

            const message = `مرحباً سلام فون، أود تأكيد الطلب بالفئات والخيارات المحددة:\n\n📋 تفاصيل الفاتورة الفنية:\n${itemsDetailsText}\n\n💵 الحساب الإجمالي الكلي:\n${totalPrice}\n\nيرجى تثبيت الفاتورة لبدء التجهيز الفوري للشحنة.`;
            window.open(`https://wa.me/9647862601021?text=${encodeURIComponent(message)}`, '_blank');

            const pages = document.querySelectorAll('.app-page');
            for (let i = 0; i < pages.length; i++) {
                pages[i].classList.add('hidden');
            }
            document.getElementById('page-tracking').classList.remove('hidden');
            resetTrackingVisuals();
        }

        function resetTrackingVisuals() {
            document.getElementById('progress-line').style.height = "0%";
            const circles = document.querySelectorAll('.step-circle');
            for (let i = 0; i < circles.length; i++) {
                circles[i].classList.remove('bg-green-500', 'scale-110');
                circles[i].classList.add('bg-gray-200');
            }
        }

        function startTrackingSimulation() {
            resetTrackingVisuals();
            setTimeout(function() {
                const step1 = document.getElementById('step-1').querySelector('.step-circle');
                step1.classList.replace('bg-gray-200', 'bg-green-500');
                step1.classList.add('scale-110');
                document.getElementById('progress-line').style.height = "20%";
            }, 500);
            setTimeout(function() {
                document.getElementById('step-1').querySelector('.step-circle').classList.remove('scale-110');
                const step2 = document.getElementById('step-2').querySelector('.step-circle');
                step2.classList.replace('bg-gray-200', 'bg-green-500');
                step2.classList.add('scale-110');
                document.getElementById('progress-line').style.height = "60%";
            }, 3000);
            setTimeout(function() {
                document.getElementById('step-2').querySelector('.step-circle').classList.remove('scale-110');
                const step3 = document.getElementById('step-3').querySelector('.step-circle');
                step3.classList.replace('bg-gray-200', 'bg-green-500');
                step3.classList.add('scale-110');
                document.getElementById('progress-line').style.height = "100%";
            }, 6000);
        }

        function filterBrand(brand, element) {
            const buttons = document.querySelectorAll('.brand-btn');
            for (let i = 0; i < buttons.length; i++) {
                buttons[i].classList.replace('bg-red-600', 'bg-white');
                buttons[i].classList.add('text-gray-700', 'border-gray-200');
            }
            element.classList.replace('bg-white', 'bg-red-600');
            element.classList.remove('text-gray-700', 'border-gray-200');

            const cards = document.querySelectorAll('.product-card');
            for (let i = 0; i < cards.length; i++) {
                if(brand === 'all' || cards[i].getAttribute('data-brand') === brand) {
                    cards[i].classList.remove('hidden');
                } else {
                    cards[i].classList.add('hidden');
                }
            }
        }
    </script>
</body>
</html>

