<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chúc Tổ 1 Ngày Phụ Nữ</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Alex+Brush&family=Dancing+Script:wght@600;700&family=Montserrat:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;0,700;1,400;1,600&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        roseGold: '#B76E79',
                        blushPink: '#FFD1DC',
                        deepRose: '#D81B60',
                        goldAccent: '#D4AF37',
                        softCream: '#FFFDF9',
                        wineRed: '#7A1C31',
                    },
                    fontFamily: {
                        serif: ['Playfair Display', 'serif'],
                        handwriting: ['Dancing Script', 'cursive'],
                        calligraphy: ['Alex Brush', 'cursive'],
                        sans: ['Montserrat', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background: radial-gradient(circle at center, #fff0f5 0%, #ffd1dc 50%, #fbcfe8 100%);
            color: #4a3e3d;
            overflow-x: hidden;
            font-family: 'Montserrat', sans-serif;
            min-height: 100vh;
        }

        .gold-border {
            border: 2px solid #D4AF37;
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.35);
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.88);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 15px 35px rgba(216, 27, 96, 0.12);
        }

        #fx-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            pointer-events: none;
            z-index: 40;
        }

        .envelope-wrapper {
            perspective: 1000px;
        }

        .envelope {
            position: relative;
            width: 320px;
            height: 220px;
            background-color: #f43f5e;
            border-bottom-left-radius: 12px;
            border-bottom-right-radius: 12px;
            box-shadow: 0 20px 40px rgba(190, 18, 60, 0.3);
            cursor: pointer;
            transition: transform 0.5s ease;
        }

        @media (min-width: 640px) {
            .envelope {
                width: 440px;
                height: 290px;
            }
        }

        .envelope:hover {
            transform: translateY(-8px) scale(1.02);
        }

        .envelope .flap {
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 0;
            border-left: 160px solid transparent;
            border-right: 160px solid transparent;
            border-top: 130px solid #e11d48;
            transform-origin: top;
            transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1), z-index 0.2s;
            z-index: 5;
        }

        @media (min-width: 640px) {
            .envelope .flap {
                border-left-width: 220px;
                border-right-width: 220px;
                border-top-width: 175px;
            }
        }

        .envelope.open .flap {
            transform: rotateX(180deg);
            z-index: 1;
        }

        .envelope .pocket {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 0;
            border-left: 160px solid #fb7185;
            border-right: 160px solid #fb7185;
            border-bottom: 120px solid #f43f5e;
            border-bottom-left-radius: 12px;
            border-bottom-right-radius: 12px;
            z-index: 3;
        }

        @media (min-width: 640px) {
            .envelope .pocket {
                border-left-width: 220px;
                border-right-width: 220px;
                border-bottom-width: 160px;
            }
        }

        .envelope .letter {
            position: absolute;
            bottom: 10px;
            left: 15px;
            right: 15px;
            height: 190px;
            background: #fffdf9;
            border-radius: 8px;
            padding: 15px;
            z-index: 2;
            transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            border: 1px solid #fbcfe8;
        }

        @media (min-width: 640px) {
            .envelope .letter {
                bottom: 15px;
                left: 20px;
                right: 20px;
                height: 250px;
                padding: 20px;
            }
        }

        .envelope.open .letter {
            transform: translateY(-130px);
            z-index: 4;
        }

        @media (min-width: 640px) {
            .envelope.open .letter {
                transform: translateY(-170px);
            }
        }

        .seal {
            position: absolute;
            top: 105px;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 50px;
            height: 50px;
            background: radial-gradient(circle, #ffd700 0%, #b8860b 100%);
            border-radius: 50%;
            z-index: 6;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.25);
            color: #fff;
            font-size: 20px;
            border: 2px solid #fff;
            transition: opacity 0.4s;
        }

        @media (min-width: 640px) {
            .seal {
                top: 140px;
                width: 60px;
                height: 60px;
                font-size: 24px;
            }
        }

        .envelope.open .seal {
            opacity: 0;
            pointer-events: none;
        }

        @keyframes subtleGlow {
            0%, 100% { box-shadow: 0 0 15px rgba(216, 27, 96, 0.3); }
            50% { box-shadow: 0 0 30px rgba(216, 27, 96, 0.6); }
        }
        .glow-button {
            animation: subtleGlow 2.5s infinite ease-in-out;
        }

        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #fff0f3; }
        ::-webkit-scrollbar-thumb { background: #f472b6; border-radius: 10px; }
    </style>
</head>
<body class="relative flex flex-col justify-between items-center min-h-screen">

    <canvas id="fx-canvas"></canvas>

    <!-- Nút Bật/Tắt Nhạc Nền -->
    <div class="fixed top-4 right-4 z-50">
        <button id="music-btn" onclick="toggleMusic()" class="glass-card p-3 rounded-full text-deepRose hover:scale-110 transition duration-300 shadow-xl flex items-center justify-center w-12 h-12 border border-rose-200">
            <i id="music-icon" class="fas fa-music text-lg"></i>
        </button>
    </div>

    <main class="container mx-auto px-4 py-6 max-w-4xl relative z-10 flex-grow flex flex-col items-center justify-center">

        <!-- MÀN HÌNH 1: CHỌN NGƯỜI NHẬN -->
        <div id="selection-screen" class="w-full text-center transition-all duration-500 my-auto">
            
            <div class="inline-block px-5 py-2 rounded-full glass-card text-roseGold font-medium text-xs sm:text-sm mb-4 tracking-widest uppercase border border-rose-200 shadow-sm">
                Tôn Vinh Ngày Phụ Nữ Tổ 1
            </div>
            
            <h1 class="font-serif text-3xl sm:text-5xl md:text-6xl font-bold text-deepRose mb-3 leading-tight drop-shadow-sm">
                Gửi Trọn Yêu Thương
            </h1>
            <p class="font-handwriting text-xl sm:text-3xl text-goldAccent font-semibold mb-8">
                Vui lòng chọn tên người nhận để mở thiệp chúc mừng riêng biệt:
            </p>

            <!-- Grid 7 Người Nhận -->
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4 sm:gap-6 max-w-4xl mx-auto px-2">
                
                <!-- 1. My My -->
                <button onclick="selectRecipient('my-my')" class="glass-card group p-5 rounded-2xl border border-rose-200 hover:border-deepRose hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-pink-100 text-deepRose flex items-center justify-center text-xl group-hover:bg-deepRose group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-crown"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-deepRose transition-colors">1. My My</span>
                    <span class="text-xs text-rose-500 font-medium">Xinh đẹp & Rạng rỡ</span>
                </button>

                <!-- 2. Quỳnh Trang -->
                <button onclick="selectRecipient('quynh-trang')" class="glass-card group p-5 rounded-2xl border border-rose-200 hover:border-deepRose hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-rose-100 text-deepRose flex items-center justify-center text-xl group-hover:bg-deepRose group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-heart"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-deepRose transition-colors">2. Quỳnh Trang</span>
                    <span class="text-xs text-rose-500 font-medium">Bình an & Hạnh phúc</span>
                </button>

                <!-- 3. P.Quỳnh Trang -->
                <button onclick="selectRecipient('p-quynh-trang')" class="glass-card group p-5 rounded-2xl border border-rose-200 hover:border-deepRose hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-purple-100 text-purple-600 flex items-center justify-center text-xl group-hover:bg-purple-600 group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-gem"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-deepRose transition-colors">3. P.Quỳnh Trang</span>
                    <span class="text-xs text-purple-500 font-medium">Tự tin & Thăng hoa</span>
                </button>

                <!-- 4. Thu Hà -->
                <button onclick="selectRecipient('thu-ha')" class="glass-card group p-5 rounded-2xl border border-rose-200 hover:border-deepRose hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-amber-100 text-amber-600 flex items-center justify-center text-xl group-hover:bg-amber-600 group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-sun"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-deepRose transition-colors">4. Thu Hà</span>
                    <span class="text-xs text-amber-600 font-medium">Dịu dàng & Ngọt ngào</span>
                </button>

                <!-- 5. Thùy Lâm -->
                <button onclick="selectRecipient('thuy-lam')" class="glass-card group p-5 rounded-2xl border border-rose-200 hover:border-deepRose hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-teal-100 text-teal-600 flex items-center justify-center text-xl group-hover:bg-teal-600 group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-sparkles"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-deepRose transition-colors">5. Thùy Lâm</span>
                    <span class="text-xs text-teal-600 font-medium">Thanh lịch & May mắn</span>
                </button>

                <!-- 6. Đức Khang -->
                <button onclick="selectRecipient('duc-khang')" class="glass-card group p-5 rounded-2xl border border-amber-200 hover:border-goldAccent hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-amber-200 text-amber-800 flex items-center justify-center text-xl group-hover:bg-amber-600 group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-gift"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-amber-700 transition-colors">6. Đức Khang</span>
                    <span class="text-xs text-amber-700 font-medium">Vui vẻ & Thành công</span>
                </button>

                <!-- 7. Phú -->
                <button onclick="selectRecipient('phu')" class="glass-card group p-5 rounded-2xl border border-rose-200 hover:border-deepRose hover:scale-105 transition-all duration-300 shadow-lg flex flex-col items-center justify-center gap-2 relative overflow-hidden">
                    <div class="w-12 h-12 rounded-full bg-emerald-100 text-emerald-600 flex items-center justify-center text-xl group-hover:bg-emerald-600 group-hover:text-white transition-colors duration-300 shadow-inner">
                        <i class="fas fa-star"></i>
                    </div>
                    <span class="font-serif text-base font-bold text-gray-800 group-hover:text-deepRose transition-colors">7. Phú</span>
                    <span class="text-xs text-emerald-600 font-medium">Nhiệt huyết & May mắn</span>
                </button>

            </div>
        </div>

        <!-- MÀN HÌNH 2: TƯƠNG TÁC MỞ PHONG THƯ 3D -->
        <div id="envelope-screen" class="hidden flex-col items-center justify-center my-auto transition-all duration-500">
            
            <button onclick="backToSelection()" class="mb-6 px-4 py-2 rounded-full glass-card text-xs sm:text-sm text-gray-700 hover:text-deepRose hover:border-deepRose transition flex items-center gap-2 shadow-sm">
                <i class="fas fa-arrow-left"></i> Chọn người khác
            </button>

            <h2 class="font-serif text-2xl sm:text-3xl text-center text-gray-800 mb-2 font-bold">
                Bức thư tay dành tặng: <span id="envelope-recipient-name" class="text-deepRose font-handwriting text-3xl sm:text-4xl">...</span>
            </h2>
            <p class="text-xs sm:text-sm text-gray-600 mb-8 text-center">Nhấn vào phong thư để mở thiệp chúc mừng</p>

            <div class="envelope-wrapper my-4">
                <div id="envelope" class="envelope" onclick="openEnvelope()">
                    <div class="flap"></div>
                    <div class="pocket"></div>
                    <div class="seal">
                        <i class="fas fa-heart text-amber-300"></i>
                    </div>
                    <div class="letter text-center flex flex-col justify-center items-center">
                        <span class="font-calligraphy text-2xl sm:text-3xl text-deepRose font-bold">Best Wishes</span>
                        <p class="font-handwriting text-base sm:text-lg text-gray-700 mt-1">Chúc Mừng Ngày Phụ Nữ</p>
                        <i class="fas fa-certificate text-goldAccent text-xl mt-2"></i>
                    </div>
                </div>
            </div>

            <button id="open-btn" onclick="openEnvelope()" class="mt-8 px-8 py-3.5 bg-gradient-to-r from-rose-500 to-deepRose text-white font-semibold rounded-2xl shadow-xl hover:opacity-95 active:scale-95 transition glow-button flex items-center gap-2">
                <i class="fas fa-envelope-open-text text-lg"></i> Mở Thiệp Chúc Mừng
            </button>
        </div>

        <!-- MÀN HÌNH 3: HIỂN THỊ THIỆP CHI TIẾT -->
        <div id="card-screen" class="hidden w-full max-w-2xl my-auto transition-all duration-700">
            
            <div class="glass-card rounded-3xl p-6 sm:p-10 text-center relative overflow-hidden gold-border shadow-2xl">

                <div class="flex justify-between items-center mb-6 relative z-10 border-b border-rose-100 pb-4">
                    <button onclick="backToSelection()" class="px-3.5 py-1.5 rounded-full bg-white/80 text-xs sm:text-sm text-gray-700 hover:text-deepRose transition flex items-center gap-1.5 border border-rose-200">
                        <i class="fas fa-th-large"></i> Danh sách
                    </button>

                    <span class="font-serif text-xs uppercase tracking-widest text-goldAccent font-semibold">Special Greeting</span>

                    <button onclick="toggleEditWish()" class="px-3.5 py-1.5 rounded-full bg-rose-50 text-xs sm:text-sm text-deepRose hover:bg-rose-100 transition flex items-center gap-1.5 border border-rose-200">
                        <i class="fas fa-pen"></i> <span id="edit-btn-text">Sửa lời chúc</span>
                    </button>
                </div>

                <div class="relative z-10">
                    <div class="inline-block px-4 py-1 rounded-full bg-rose-100 text-deepRose font-semibold text-xs mb-3">
                        Happy Women's Day
                    </div>

                    <h2 class="font-serif text-xl sm:text-2xl text-gray-700 mb-1">Thân gửi:</h2>
                    <div id="card-recipient-name" class="font-handwriting text-4xl sm:text-5xl md:text-6xl text-deepRose font-bold mb-6">
                        ...
                    </div>

                    <div id="wish-display-container" class="my-6 px-2 sm:px-6 min-h-[120px] flex items-center justify-center">
                        <p id="card-wish-text" class="text-base sm:text-lg text-gray-800 leading-relaxed font-serif italic">
                            ...
                        </p>
                    </div>

                    <div id="wish-edit-container" class="hidden my-4 px-2 sm:px-6">
                        <textarea id="wish-input" rows="4" class="w-full p-4 rounded-xl border-2 border-rose-300 focus:outline-none focus:ring-2 focus:ring-deepRose font-serif text-sm sm:text-base text-gray-800 bg-white/90 shadow-inner"></textarea>
                        <div class="flex justify-end gap-2 mt-2">
                            <button onclick="saveWish()" class="px-4 py-2 bg-deepRose text-white rounded-lg text-xs font-semibold hover:opacity-90 transition">
                                <i class="fas fa-check mr-1"></i> Lưu Lời Chúc
                            </button>
                        </div>
                    </div>

                    <p class="font-handwriting text-xl sm:text-2xl text-goldAccent font-semibold my-4">
                        "Thân chúc bạn một ngày ngập tràn nụ cười, may mắn và hạnh phúc vẹn tròn!"
                    </p>

                    <div class="pt-6 border-t border-rose-100 flex flex-wrap justify-center gap-3">
                        <button onclick="copyCardContent()" class="px-4 py-2.5 bg-white text-rose-700 border border-rose-300 font-medium text-xs sm:text-sm rounded-xl hover:bg-rose-50 transition shadow-sm flex items-center gap-2">
                            <i class="fas fa-copy"></i> Sao Chép Lời Chúc
                        </button>
                        <button onclick="triggerFireworks()" class="px-4 py-2.5 bg-gradient-to-r from-amber-400 to-goldAccent text-white font-medium text-xs sm:text-sm rounded-xl hover:brightness-110 transition shadow-md flex items-center gap-2">
                            <i class="fas fa-fireworks"></i> Bắn Pháo Hoa
                        </button>
                    </div>
                </div>

            </div>
        </div>

    </main>

    <footer class="text-center py-4 text-xs text-gray-600 relative z-10 bg-white/40 backdrop-blur-md w-full border-t border-rose-100 flex flex-col items-center gap-2">
        <div class="flex items-center gap-3 font-medium">
            <span>Nhạc nền: <b>Muốn Được Cùng Em - Freaky x CM1X ft. Quỳnh Gai</b></span>
            <a href="https://www.youtube.com/watch?v=BZYp-6D0SDY" target="_blank" class="text-rose-600 hover:underline flex items-center gap-1 font-semibold">
                <i class="fab fa-youtube text-red-500 text-sm"></i> Nghe trên YouTube
            </a>
        </div>
        <p class="font-medium">Trân trọng và tôn vinh nét đẹp của Phụ Nữ Tổ 1</p>
    </footer>

    <audio id="bg-music" loop preload="auto">
        <source src="https://files.catbox.moe/5v4p0u.mp3" type="audio/mp3">
    </audio>

    <script>
        /* DỮ LIỆU LỜI CHÚC TẤT CẢ 7 NGƯỜI ĐỒNG ĐỀU (XÓA TOÀN BỘ EMOJI / BIỂU TƯỢNG TRÊN CHỮ) */
        const recipientsData = {
            'my-my': {
                name: 'My My',
                wish: 'Chúc My My có một ngày Phụ Nữ ngập tràn niềm vui, xinh đẹp rạng rỡ và gặt hái thật nhiều may mắn cùng thành công trong cuộc sống.'
            },
            'quynh-trang': {
                name: 'Quỳnh Trang',
                wish: 'Chúc Quỳnh Trang có một ngày Phụ Nữ luôn bình an, tươi trẻ, tràn ngập hạnh phúc và đong đầy tình yêu thương bên gia đình.'
            },
            'p-quynh-trang': {
                name: 'P.Quỳnh Trang',
                wish: 'Chúc P.Quỳnh Trang ngày càng xinh đẹp, tự tin, rạng rỡ và thăng hoa trong mọi dự định cũng như sự nghiệp phía trước.'
            },
            'thu-ha': {
                name: 'Thu Hà',
                wish: 'Chúc Thu Hà một ngày lễ thật dịu dàng, ngọt ngào, an nhiên và vẹn tròn niềm vui bên những người thân yêu nhất.'
            },
            'thuy-lam': {
                name: 'Thùy Lâm',
                wish: 'Chúc Thùy Lâm luôn thanh lịch, duyên dáng, tràn đầy năng lượng tích cực và luôn gặp nhiều may mắn trong cuộc sống.'
            },
            'duc-khang': {
                name: 'Đức Khang',
                wish: 'Chúc Đức Khang ngày lễ thật vui vẻ, luôn mạnh khỏe, hạnh phúc và gặt hái thêm nhiều thành công rực rỡ trong tương lai.'
            },
            'phu': {
                name: 'Phú',
                wish: 'Chúc Phú có một ngày lễ trọn vẹn niềm vui, luôn giữ vững tinh thần nhiệt huyết, may mắn và hạnh phúc trên mọi chặng đường.'
            }
        };

        let currentKey = '';
        let isEditing = false;

        function selectRecipient(key) {
            currentKey = key;
            const data = recipientsData[key];

            document.getElementById('envelope-recipient-name').textContent = data.name;
            document.getElementById('card-recipient-name').textContent = data.name;
            document.getElementById('card-wish-text').textContent = `"${data.wish}"`;
            document.getElementById('wish-input').value = data.wish;

            const envelope = document.getElementById('envelope');
            envelope.classList.remove('open');

            document.getElementById('selection-screen').classList.add('hidden');
            document.getElementById('envelope-screen').classList.remove('hidden');
            document.getElementById('card-screen').classList.add('hidden');

            triggerFireworks();
        }

        function openEnvelope() {
            const envelope = document.getElementById('envelope');
            envelope.classList.add('open');

            if (!isPlaying) {
                toggleMusic();
            }

            setTimeout(() => {
                document.getElementById('envelope-screen').classList.add('hidden');
                document.getElementById('card-screen').classList.remove('hidden');
                triggerFireworks();
            }, 1200);
        }

        function backToSelection() {
            document.getElementById('selection-screen').classList.remove('hidden');
            document.getElementById('envelope-screen').classList.add('hidden');
            document.getElementById('card-screen').classList.add('hidden');
            
            if(isEditing) toggleEditWish();
        }

        function toggleEditWish() {
            const displayBox = document.getElementById('wish-display-container');
            const editBox = document.getElementById('wish-edit-container');
            const editBtnText = document.getElementById('edit-btn-text');

            if (!isEditing) {
                displayBox.classList.add('hidden');
                editBox.classList.remove('hidden');
                editBtnText.textContent = "Hủy sửa";
                isEditing = true;
            } else {
                displayBox.classList.remove('hidden');
                editBox.classList.add('hidden');
                editBtnText.textContent = "Sửa lời chúc";
                isEditing = false;
            }
        }

        function saveWish() {
            const newWish = document.getElementById('wish-input').value.trim();
            if (newWish !== "") {
                recipientsData[currentKey].wish = newWish;
                document.getElementById('card-wish-text').textContent = `"${newWish}"`;
                showToast("Đã lưu lời chúc mới thành công!");
            }
            toggleEditWish();
        }

        function copyCardContent() {
            const name = recipientsData[currentKey].name;
            const wish = recipientsData[currentKey].wish;
            const fullText = `Thân gửi ${name}:\n${wish}\n\nChúc Mừng Ngày Phụ Nữ!`;

            const dummy = document.createElement("textarea");
            document.body.appendChild(dummy);
            dummy.value = fullText;
            dummy.select();
            document.execCommand("copy");
            document.body.removeChild(dummy);

            showToast("Đã sao chép lời chúc vào bộ nhớ tạm!");
        }

        function showToast(msg) {
            const toast = document.createElement('div');
            toast.className = 'fixed bottom-8 left-1/2 transform -translate-x-1/2 bg-gray-900/90 text-white px-6 py-3 rounded-full text-sm z-50 shadow-2xl transition duration-300';
            toast.textContent = msg;
            document.body.appendChild(toast);
            setTimeout(() => {
                toast.style.opacity = '0';
                setTimeout(() => toast.remove(), 300);
            }, 2500);
        }

        let isPlaying = false;
        const bgMusic = document.getElementById('bg-music');
        const musicIcon = document.getElementById('music-icon');

        function toggleMusic() {
            if (isPlaying) {
                bgMusic.pause();
                musicIcon.className = 'fas fa-music text-lg';
            } else {
                bgMusic.play().then(() => {
                    musicIcon.className = 'fas fa-pause text-lg text-deepRose animate-spin';
                }).catch(() => {
                    showToast("Nhấp vào màn hình để nghe nhạc nền!");
                });
            }
            isPlaying = !isPlaying;
        }

        // Canvas animation
        const canvas = document.getElementById('fx-canvas');
        const ctx = canvas.getContext('2d');

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        const petals = [];
        const petalCount = 40;
        const petalColors = ['#FFC0CB', '#FFB6C1', '#FF69B4', '#E6E6FA', '#FFE4E1', '#F472B6'];

        class Petal {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * canvas.width;
                this.y = -20;
                this.size = Math.random() * 9 + 5;
                this.speedY = Math.random() * 1.5 + 0.7;
                this.speedX = Math.random() * 1 - 0.5;
                this.angle = Math.random() * 360;
                this.spin = (Math.random() - 0.5) * 0.02;
                this.color = petalColors[Math.floor(Math.random() * petalColors.length)];
                this.opacity = Math.random() * 0.6 + 0.4;
            }
            update() {
                this.y += this.speedY;
                this.x += Math.sin(this.y * 0.01) + this.speedX;
                this.angle += this.spin;
                if (this.y > canvas.height + 20) this.reset();
            }
            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.angle);
                ctx.globalAlpha = this.opacity;
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.ellipse(0, 0, this.size, this.size / 2, Math.PI / 4, 0, 2 * Math.PI);
                ctx.fill();
                ctx.restore();
            }
        }

        for (let i = 0; i < petalCount; i++) petals.push(new Petal());

        let particles = [];

        class Particle {
            constructor(x, y, color) {
                this.x = x;
                this.y = y;
                this.color = color;
                this.radius = Math.random() * 3 + 1.5;
                const angle = Math.random() * Math.PI * 2;
                const speed = Math.random() * 6 + 1.5;
                this.vx = Math.cos(angle) * speed;
                this.vy = Math.sin(angle) * speed;
                this.alpha = 1;
                this.decay = Math.random() * 0.02 + 0.015;
            }
            update() {
                this.x += this.vx;
                this.y += this.vy;
                this.vy += 0.06;
                this.alpha -= this.decay;
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = Math.max(0, this.alpha);
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        function triggerFireworks() {
            const colors = ['#FFD700', '#FF1493', '#FF69B4', '#A855F7', '#38BDF8', '#D4AF37'];
            for (let b = 0; b < 4; b++) {
                setTimeout(() => {
                    const rx = Math.random() * (canvas.width * 0.8) + canvas.width * 0.1;
                    const ry = Math.random() * (canvas.height * 0.5) + canvas.height * 0.1;
                    const color = colors[Math.floor(Math.random() * colors.length)];
                    for (let i = 0; i < 45; i++) particles.push(new Particle(rx, ry, color));
                }, b * 250);
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            petals.forEach(p => { p.update(); p.draw(); });
            for (let i = particles.length - 1; i >= 0; i--) {
                const p = particles[i];
                p.update();
                p.draw();
                if (p.alpha <= 0) particles.splice(i, 1);
            }
            requestAnimationFrame(animate);
        }

        window.onload = function() {
            animate();
            setTimeout(triggerFireworks, 600);
        };
    </script>
</body>
</html>
