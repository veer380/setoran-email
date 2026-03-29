<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Freelancer Mails - Pembayaran Cepat & Amanah</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap');
        
        body { 
            font-family: 'Plus Jakarta Sans', sans-serif; 
            scroll-behavior: smooth; 
        }

        .glass-nav {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
        }

        .card-hover {
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .card-hover:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1);
        }

        .blob {
            position: absolute;
            width: 400px;
            height: 400px;
            background: rgba(37, 99, 235, 0.15);
            filter: blur(60px);
            border-radius: 50%;
            z-index: -1;
        }

        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: #2563eb;
            box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.1);
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        .animate-spin-custom {
            animation: spin 1s linear infinite;
        }

        .modal-bg {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(4px);
            z-index: 100;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }

        .modal-content {
            animation: modalFadeIn 0.3s ease-out;
        }

        @keyframes modalFadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 antialiased">

    <!-- Modal Aturan AWALAN -->
    <div id="modal-awalan" class="modal-bg">
        <div class="bg-white w-full max-w-lg rounded-[2.5rem] shadow-2xl modal-content overflow-hidden flex flex-col max-h-[90vh]">
            <div class="p-6 border-b border-slate-100 flex justify-between items-center bg-blue-600 text-white shrink-0">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-star text-xl"></i>
                    <h3 class="text-lg font-extrabold tracking-tight uppercase">Aturan Kategori AWALAN</h3>
                </div>
                <button onclick="closeRulesModal('modal-awalan')" class="hover:rotate-90 transition-transform"><i class="fa-solid fa-xmark text-2xl"></i></button>
            </div>
            <div class="p-6 overflow-y-auto">
                <ul class="space-y-3">
                    <li class="flex gap-3 p-3 rounded-2xl bg-blue-50 border border-blue-100 items-start">
                        <span class="bg-blue-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">1</span>
                        <p class="text-slate-700 text-sm font-semibold italic">Nama email harus diawali sesuai instruksi Admin.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">2</span>
                        <p class="text-slate-700 text-sm font-semibold">Wajib <span class="font-bold">Nama Manusia</span> (Dilarang nama/pola serupa).</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-red-50 border border-red-100 items-start">
                        <span class="bg-red-500 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">3</span>
                        <p class="text-red-700 text-sm font-bold">Dilarang Verif No HP, Email Pemulihan, & Tap.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">4</span>
                        <p class="text-slate-700 text-sm font-semibold">Tidak terkait apapun & Angka <span class="font-bold text-blue-600">Maks 2 Digit</span> di belakang.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">5</span>
                        <p class="text-slate-700 text-sm font-semibold">Gender: Tidak diberitahu (Custom).</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-amber-50 border border-amber-100 items-start">
                        <span class="bg-amber-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">6</span>
                        <p class="text-amber-800 text-sm font-bold italic">Dilarang keluar akun/Logout jika tidak disuruh Admin.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-red-50 border border-red-100 items-start">
                        <span class="bg-red-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">7</span>
                        <p class="text-red-800 text-sm font-bold">Tidak menerima Gmail Web & Dilarang Jual Kembali.</p>
                    </li>
                </ul>
                <button onclick="closeRulesModal('modal-awalan')" class="w-full mt-6 py-4 bg-blue-600 text-white rounded-2xl font-bold hover:bg-slate-900 transition-all shadow-lg">SAYA MENGERTI</button>
            </div>
        </div>
    </div>

    <!-- Modal Aturan YASE -->
    <div id="modal-yase" class="modal-bg">
        <div class="bg-white w-full max-w-lg rounded-[2.5rem] shadow-2xl modal-content overflow-hidden flex flex-col max-h-[90vh]">
            <div class="p-6 border-b border-slate-100 flex justify-between items-center bg-indigo-600 text-white shrink-0">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-list-check text-xl"></i>
                    <h3 class="text-lg font-extrabold tracking-tight uppercase">Aturan Kategori YASE</h3>
                </div>
                <button onclick="closeRulesModal('modal-yase')" class="hover:rotate-90 transition-transform"><i class="fa-solid fa-xmark text-2xl"></i></button>
            </div>
            <div class="p-6 overflow-y-auto">
                <ul class="space-y-3">
                    <li class="flex gap-3 p-3 rounded-2xl bg-indigo-50 border border-indigo-100 items-start">
                        <span class="bg-indigo-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">1</span>
                        <p class="text-slate-700 text-sm font-semibold">Wajib ditambah kata <span class="text-indigo-600 font-bold">"yase"</span> di belakang email.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">2</span>
                        <p class="text-slate-700 text-sm font-semibold">Password wajib: <span class="font-mono bg-slate-200 px-1.5 rounded">aass1122</span></p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">3</span>
                        <p class="text-slate-700 text-sm font-semibold">Tahun lahir antara <span class="font-bold">1990 - 2000</span>.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-red-50 border border-red-100 items-start">
                        <span class="bg-red-500 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">4</span>
                        <p class="text-red-700 text-sm font-bold">Dilarang Verifikasi No HP & Tidak Terkait Apapun.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-amber-50 border border-amber-100 items-start">
                        <span class="bg-amber-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">5</span>
                        <p class="text-amber-800 text-sm font-bold uppercase italic">GMAIL HARUS SUDAH UPDATE.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">6</span>
                        <p class="text-slate-700 text-sm font-semibold italic">Nama dan nomor email tidak boleh ada yang sama atau berurutan.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">7</span>
                        <p class="text-slate-700 text-sm font-semibold">Angka di belakang username <span class="text-indigo-600 font-bold">Maksimal 2 Digit</span>.</p>
                    </li>
                </ul>
                <button onclick="closeRulesModal('modal-yase')" class="w-full mt-6 py-4 bg-indigo-600 text-white rounded-2xl font-bold hover:bg-slate-900 transition-all shadow-lg">SAYA MENGERTI</button>
            </div>
        </div>
    </div>

    <!-- Modal Aturan FULL BEBAS -->
    <div id="modal-fullbebas" class="modal-bg">
        <div class="bg-white w-full max-w-lg rounded-[2.5rem] shadow-2xl modal-content overflow-hidden flex flex-col max-h-[90vh]">
            <div class="p-6 border-b border-slate-100 flex justify-between items-center bg-emerald-600 text-white shrink-0">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-unlock-keyhole text-xl"></i>
                    <h3 class="text-lg font-extrabold tracking-tight uppercase">Aturan Kategori FULL BEBAS</h3>
                </div>
                <button onclick="closeRulesModal('modal-fullbebas')" class="hover:rotate-90 transition-transform"><i class="fa-solid fa-xmark text-2xl"></i></button>
            </div>
            <div class="p-6 overflow-y-auto">
                <ul class="space-y-3">
                    <li class="flex gap-3 p-3 rounded-2xl bg-red-50 border border-red-100 items-start">
                        <span class="bg-red-500 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">1</span>
                        <p class="text-red-700 text-sm font-bold italic uppercase">Dilarang Verifikasi No HP (No Verif).</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">2</span>
                        <p class="text-slate-700 text-sm font-semibold">Tahun lahir wajib: <span class="font-bold">2000</span>.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">3</span>
                        <p class="text-slate-700 text-sm font-semibold">Nama dan alamat email <span class="font-bold text-emerald-600">tidak boleh sama</span>.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-amber-50 border border-amber-100 items-start">
                        <span class="bg-amber-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">4</span>
                        <p class="text-amber-800 text-sm font-bold italic">Format dilarang berurutan dan dilarang serupa antar akun.</p>
                    </li>
                </ul>
                <button onclick="closeRulesModal('modal-fullbebas')" class="w-full mt-6 py-4 bg-emerald-600 text-white rounded-2xl font-bold hover:bg-slate-900 transition-all shadow-lg">SAYA MENGERTI</button>
            </div>
        </div>
    </div>

    <!-- Modal Aturan PASS1122 -->
    <div id="modal-pass1122" class="modal-bg">
        <div class="bg-white w-full max-w-lg rounded-[2.5rem] shadow-2xl modal-content overflow-hidden flex flex-col max-h-[90vh]">
            <div class="p-6 border-b border-slate-100 flex justify-between items-center bg-violet-600 text-white shrink-0">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-key text-xl"></i>
                    <h3 class="text-lg font-extrabold tracking-tight uppercase">Aturan Kategori PASS1122</h3>
                </div>
                <button onclick="closeRulesModal('modal-pass1122')" class="hover:rotate-90 transition-transform"><i class="fa-solid fa-xmark text-2xl"></i></button>
            </div>
            <div class="p-6 overflow-y-auto">
                <ul class="space-y-3">
                    <li class="flex gap-3 p-3 rounded-2xl bg-violet-50 border border-violet-100 items-start">
                        <span class="bg-violet-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">1</span>
                        <p class="text-slate-700 text-sm font-semibold italic italic">Username Email Bebas.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">2</span>
                        <p class="text-slate-700 text-sm font-semibold">Password Wajib: <span class="font-mono bg-violet-100 px-1.5 rounded text-violet-700">aass1122</span></p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-red-50 border border-red-100 items-start">
                        <span class="bg-red-500 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">3</span>
                        <p class="text-red-700 text-sm font-bold uppercase italic">Tidak Verifikasi No HP (No Verif).</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">4</span>
                        <p class="text-slate-700 text-sm font-semibold">Akun <span class="font-bold">Tidak Terkait Apapun</span>.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-slate-50 border border-slate-100 items-start">
                        <span class="bg-slate-400 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">5</span>
                        <p class="text-slate-700 text-sm font-semibold">Tahun lahir wajib: <span class="font-bold">2000</span>.</p>
                    </li>
                    <li class="flex gap-3 p-3 rounded-2xl bg-amber-50 border border-amber-100 items-start">
                        <span class="bg-amber-600 text-white w-5 h-5 rounded-full flex items-center justify-center text-[10px] font-bold shrink-0 mt-0.5">6</span>
                        <p class="text-amber-800 text-sm font-bold italic">Nama dan email <span class="font-bold">tidak boleh sama</span> & <span class="font-bold">dilarang berurutan</span>.</p>
                    </li>
                </ul>
                <button onclick="closeRulesModal('modal-pass1122')" class="w-full mt-6 py-4 bg-violet-600 text-white rounded-2xl font-bold hover:bg-slate-900 transition-all shadow-lg">SAYA MENGERTI</button>
            </div>
        </div>
    </div>

    <!-- Navbar -->
    <nav class="glass-nav sticky top-0 z-50 border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-20 items-center">
                <div class="flex items-center gap-3">
                    <div class="bg-blue-600 p-2 rounded-lg shadow-lg">
                        <i class="fa-solid fa-briefcase text-white text-xl"></i>
                    </div>
                    <div>
                        <span class="text-xl font-extrabold tracking-tight text-slate-900 block leading-none">FREELANCER MAILS</span>
                        <span class="text-[10px] font-bold text-blue-600 tracking-widest uppercase">Fast Payment 7 Hari</span>
                    </div>
                </div>
                
                <div class="hidden md:flex items-center space-x-8 font-bold text-sm text-slate-600 uppercase tracking-wide">
                    <a href="#beranda" class="hover:text-blue-600 transition-colors">Beranda</a>
                    <a href="#keunggulan" class="hover:text-blue-600 transition-colors">Keunggulan</a>
                    <a href="#form-setor" class="bg-blue-600 text-white px-6 py-2.5 rounded-full hover:bg-slate-900 transition-all">Setor Akun</a>
                </div>

                <button class="md:hidden text-2xl" onclick="toggleMenu()"><i class="fa-solid fa-bars-staggered"></i></button>
            </div>
        </div>
    </nav>

    <!-- Hero -->
    <section id="beranda" class="relative overflow-hidden pt-16 pb-12 px-4">
        <div class="blob top-0 right-0"></div>
        <div class="max-w-7xl mx-auto text-center">
            <h1 class="text-4xl md:text-6xl font-black text-slate-900 mb-6 leading-tight">
                Freelancer <span class="text-blue-600 italic">Mails ID</span>
            </h1>
            <p class="text-lg text-slate-500 mb-8 max-w-2xl mx-auto font-medium">
                Partner penyetoran Gmail terpercaya untuk para freelancer. Sistem transparan dan pembayaran rutin via DANA.
            </p>
            <div class="flex flex-wrap justify-center gap-4">
                <a href="#form-setor" class="bg-blue-600 text-white px-8 py-4 rounded-2xl font-bold hover:bg-slate-900 transition-all shadow-xl shadow-blue-200">Mulai Setor Sekarang</a>
                <a href="https://t.me/Takemail6_bot" target="_blank" class="bg-white border border-slate-200 text-slate-700 px-8 py-4 rounded-2xl font-bold hover:bg-slate-50 transition-all">Hubungi Admin</a>
            </div>
        </div>
    </section>

    <!-- Keunggulan -->
    <section id="keunggulan" class="py-12 bg-slate-900 text-white px-4">
        <div class="max-w-7xl mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="p-8 bg-slate-800/50 rounded-3xl border border-slate-700">
                    <i class="fa-solid fa-check-double text-blue-500 text-3xl mb-6"></i>
                    <h3 class="text-xl font-bold mb-3">Sistem Cek-Lolos</h3>
                    <p class="text-slate-400 text-sm">Setiap akun dicek secara transparan oleh Freelancer Mails. Jika lolos kriteria, status pembayaran langsung dikonfirmasi.</p>
                </div>
                <div class="p-8 bg-slate-800/50 rounded-3xl border border-slate-700">
                    <i class="fa-solid fa-clock-rotate-left text-emerald-500 text-3xl mb-6"></i>
                    <h3 class="text-xl font-bold mb-3">Pembayaran Rutin</h3>
                    <p class="text-slate-400 text-sm">Proses pembayaran terjadwal dengan rapi. Maksimal 7 hari kerja dana masuk ke akun DANA Anda.</p>
                </div>
                <div class="p-8 bg-slate-800/50 rounded-3xl border border-slate-700">
                    <i class="fa-solid fa-user-shield text-amber-500 text-3xl mb-6"></i>
                    <h3 class="text-xl font-bold mb-3">Privasi Terjamin</h3>
                    <p class="text-slate-400 text-sm">Data akun Anda dikelola secara profesional. Keamanan dan privasi supplier adalah prioritas utama kami.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing -->
    <section class="py-20 bg-white px-4">
        <div class="max-w-7xl mx-auto text-center mb-12">
            <h2 class="text-3xl font-black uppercase italic tracking-tight">Kategori Harga</h2>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 max-w-7xl mx-auto">
            <div onclick="openRulesModal('modal-awalan')" class="p-6 bg-blue-50 border border-blue-100 rounded-3xl card-hover text-center cursor-pointer group">
                <span class="text-[10px] font-bold text-blue-600 bg-white px-3 py-1 rounded-full uppercase mb-4 inline-block">Awalan</span>
                <h4 class="text-3xl font-black mb-2">Rp 3.200</h4>
                <p class="text-[11px] text-slate-500 font-medium italic mb-4">Nama Manusia & Custom</p>
                <button class="text-[10px] text-blue-600 font-extrabold uppercase tracking-widest group-hover:underline">Aturan</button>
            </div>
            <div onclick="openRulesModal('modal-yase')" class="p-6 bg-indigo-50 border border-indigo-100 rounded-3xl card-hover text-center cursor-pointer group">
                <span class="text-[10px] font-bold text-indigo-600 bg-white px-3 py-1 rounded-full uppercase mb-4 inline-block">Yase</span>
                <h4 class="text-3xl font-black mb-2">Rp 3.000</h4>
                <p class="text-[11px] text-slate-500 font-medium italic mb-4">Suffix "yase" & aass1122</p>
                <button class="text-[10px] text-indigo-600 font-extrabold uppercase tracking-widest group-hover:underline">Aturan</button>
            </div>
            <div onclick="openRulesModal('modal-pass1122')" class="p-6 bg-violet-50 border border-violet-100 rounded-3xl card-hover text-center cursor-pointer group">
                <span class="text-[10px] font-bold text-violet-600 bg-white px-3 py-1 rounded-full uppercase mb-4 inline-block">Pass1122</span>
                <h4 class="text-3xl font-black mb-2 text-violet-700">Rp 2.500</h4>
                <p class="text-[11px] text-slate-500 font-medium italic mb-4">Email Bebas & aass1122</p>
                <button class="text-[10px] text-violet-600 font-extrabold uppercase tracking-widest group-hover:underline">Aturan</button>
            </div>
            <div onclick="openRulesModal('modal-fullbebas')" class="p-6 bg-emerald-50 border border-emerald-100 rounded-3xl card-hover text-center cursor-pointer group">
                <span class="text-[10px] font-bold text-emerald-600 bg-white px-3 py-1 rounded-full uppercase mb-4 inline-block">Full Bebas</span>
                <h4 class="text-3xl font-black mb-2 text-emerald-700">Rp 1.500</h4>
                <p class="text-[11px] text-slate-500 font-medium italic mb-4">Tahun 2000 & Format Acak</p>
                <button class="text-[10px] text-emerald-600 font-extrabold uppercase tracking-widest group-hover:underline">Aturan</button>
            </div>
        </div>
    </section>

    <!-- Form -->
    <section id="form-setor" class="py-20 px-4 bg-slate-50">
        <div class="max-w-3xl mx-auto">
            <div class="bg-white rounded-[2.5rem] shadow-xl border border-slate-100 overflow-hidden">
                <div class="bg-blue-600 p-8 text-white text-center">
                    <h2 class="text-2xl font-black uppercase tracking-tight">Formulir Freelancer Mails</h2>
                    <p class="text-blue-100 text-sm">Data dikirim langsung ke @Takemail6_bot</p>
                </div>

                <form id="submission-form" class="p-8 space-y-6">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="space-y-2">
                            <label class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Nama Lengkap</label>
                            <input type="text" id="name" placeholder="Budi Santoso" class="w-full bg-slate-50 border border-slate-200 p-4 rounded-xl text-sm font-semibold" required>
                        </div>
                        <div class="space-y-2">
                            <label class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Username Telegram</label>
                            <input type="text" id="tele_user" placeholder="@user_anda" class="w-full bg-slate-50 border border-slate-200 p-4 rounded-xl text-sm font-semibold" required>
                        </div>
                    </div>

                    <div class="space-y-2">
                        <label class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Kategori Akun</label>
                        <select id="category" class="w-full bg-slate-50 border border-slate-200 p-4 rounded-xl text-sm font-semibold appearance-none cursor-pointer" required>
                            <option value="">-- Pilih Kategori --</option>
                            <option value="AWALAN">AWALAN (Admin) - Rp 3.200</option>
                            <option value="YASE">YASE (Suffix) - Rp 3.000</option>
                            <option value="PASS1122">PASS1122 (aass1122) - Rp 2.500</option>
                            <option value="FULL BEBAS">FULL BEBAS (Bebas) - Rp 1.500</option>
                        </select>
                    </div>

                    <div class="space-y-2">
                        <label class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">List Akun (Email|Sandi)</label>
                        <textarea id="account_list" rows="5" placeholder="bebas1@gmail.com|sandi123&#10;bebas2@gmail.com|sandi123" class="w-full bg-slate-50 border border-slate-200 p-4 rounded-xl text-sm font-mono" required></textarea>
                    </div>

                    <div class="p-6 bg-blue-50 rounded-2xl border border-blue-100">
                        <div class="flex items-center gap-2 mb-4">
                            <i class="fa-solid fa-wallet text-blue-600"></i>
                            <span class="text-xs font-bold text-blue-900 uppercase">Metode Pembayaran: DANA</span>
                        </div>
                        <div class="space-y-2">
                            <label class="text-[10px] font-bold text-slate-400 uppercase tracking-widest">Nomor DANA Penerima</label>
                            <input type="tel" id="dana_number" placeholder="0812345678xx" class="w-full bg-white border border-slate-200 p-4 rounded-xl text-sm font-bold" required>
                        </div>
                    </div>

                    <button type="submit" id="submit-button" class="w-full bg-blue-600 text-white py-5 rounded-2xl font-black text-lg hover:bg-slate-900 transition-all flex items-center justify-center gap-3">
                        <span id="btn-label">SUBMIT KE BOT</span>
                        <i id="btn-spinner" class="fa-solid fa-circle-notch animate-spin-custom hidden"></i>
                    </button>
                    <p class="text-[10px] text-center text-slate-400 font-bold uppercase italic tracking-tighter">*Freelancer Mails ID - Cek - Lolos - Payment</p>
                </form>
            </div>
        </div>
    </section>

    <!-- Success Modal -->
    <div id="success-modal" class="modal-bg">
        <div class="bg-white p-8 rounded-[2.5rem] max-w-sm w-full text-center shadow-2xl modal-content">
            <div class="w-20 h-20 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center mx-auto mb-6">
                <i class="fa-solid fa-paper-plane text-3xl"></i>
            </div>
            <h3 class="text-xl font-black mb-2 uppercase">Setoran Terkirim!</h3>
            <p class="text-slate-500 text-sm mb-6 font-medium">Laporan Anda telah masuk ke sistem Freelancer Mails Bot. Harap tunggu proses QC dari Admin.</p>
            <button onclick="closeSuccessModal()" class="w-full bg-slate-900 text-white py-4 rounded-2xl font-bold uppercase">Tutup</button>
        </div>
    </div>

    <!-- Mobile Menu -->
    <div id="mobile-menu" class="fixed inset-0 bg-white z-[60] p-6 flex flex-col gap-8 transform translate-x-full transition-transform md:hidden">
        <div class="flex justify-between items-center">
            <span class="font-black text-blue-600 uppercase tracking-tighter text-xl">Freelancer Mails</span>
            <button onclick="toggleMenu()" class="text-2xl"><i class="fa-solid fa-xmark"></i></button>
        </div>
        <div class="flex flex-col gap-6 font-bold text-lg">
            <a href="#beranda" onclick="toggleMenu()">Beranda</a>
            <a href="#keunggulan" onclick="toggleMenu()">Keunggulan</a>
            <a href="#form-setor" onclick="toggleMenu()" class="bg-blue-600 text-white py-4 rounded-2xl text-center">Setor Akun</a>
        </div>
    </div>

    <script>
        const BOT_TOKEN = '8516355515:AAG9VHpoDBKeBePVUYDq3Y7gvQFXUDPghzs';
        const CHAT_ID = '1358848961';

        const form = document.getElementById('submission-form');
        const submitBtn = document.getElementById('submit-button');
        const btnLabel = document.getElementById('btn-label');
        const btnSpinner = document.getElementById('btn-spinner');

        form.addEventListener('submit', async (e) => {
            e.preventDefault();

            const name = document.getElementById('name').value;
            const tele = document.getElementById('tele_user').value;
            const cat = document.getElementById('category').value;
            const list = document.getElementById('account_list').value;
            const dana = document.getElementById('dana_number').value;

            submitBtn.disabled = true;
            btnLabel.textContent = 'MENGIRIM...';
            btnSpinner.classList.remove('hidden');

            const message = `🚀 *FREELANCER MAILS - SETORAN BARU*\n\n` +
                          `👤 *Nama:* ${name}\n` +
                          `📱 *Telegram:* ${tele}\n` +
                          `📦 *Kategori:* ${cat}\n` +
                          `💰 *Metode:* DANA\n` +
                          `💳 *No DANA:* \`${dana}\`\n\n` +
                          `✅ *Status:* Antrean QC\n` +
                          `📅 *Sistem:* Fast Payment (7 Hari)\n\n` +
                          `📝 *List Akun:*\n\`\`\`\n${list}\n\`\`\``;

            try {
                const response = await fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        chat_id: CHAT_ID,
                        text: message,
                        parse_mode: 'Markdown'
                    })
                });

                if (response.ok) {
                    showSuccessModal();
                    form.reset();
                } else {
                    alert('Gagal mengirim data. Silakan coba lagi atau hubungi Admin.');
                }
            } catch (error) {
                alert('Terjadi kesalahan jaringan.');
            } finally {
                submitBtn.disabled = false;
                btnLabel.textContent = 'SUBMIT KE BOT';
                btnSpinner.classList.add('hidden');
            }
        });

        function showSuccessModal() {
            document.getElementById('success-modal').style.display = 'flex';
        }

        function closeSuccessModal() {
            document.getElementById('success-modal').style.display = 'none';
        }

        function openRulesModal(id) {
            document.getElementById(id).style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        function closeRulesModal(id) {
            document.getElementById(id).style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        function toggleMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('translate-x-full');
        }
    </script>
</body>
</html>
