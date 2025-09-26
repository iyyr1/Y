# Y
Happy Birthday Foufa &lt;3









<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عيد ميلاد سعيد يا فوفا!</title>
    <style>
        /* استيراد خط عربي جميل */
        @import url('https://fonts.googleapis.com/css2?family=Amiri+Quran&display=swap');
        
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(to right, #ff7e5f, #feb47b); /* خلفية متدرجة */
            margin: 0;
            overflow: hidden; /* لمنع ظهور أشرطة التمرير */
            font-family: 'Amiri Quran', serif;
            color: white;
            flex-direction: column;
        }

        /* تصميم عداد التحميل */
        .loading-container {
            font-size: 4em;
            font-weight: bold;
            text-shadow: 2px 2px 5px rgba(0,0,0,0.4);
            opacity: 1;
            transition: opacity 1s ease-out; /* حركة اختفاء ناعمة */
        }
        
        /* إخفاء عنصر التحميل بعد اكتماله */
        .hidden {
            opacity: 0;
            pointer-events: none;
            position: absolute; /* نقله بعيداً بعد الإخفاء */
        }

        /* تصميم رسالة عيد الميلاد */
        .birthday-message {
            font-size: 5em;
            font-weight: 800;
            text-shadow: 4px 4px 8px rgba(255, 255, 255, 0.7);
            color: #ff3366; /* لون مميز للرسالة */
            opacity: 0;
            transform: scale(0.5); /* يبدأ أصغر من حجمه الطبيعي */
            transition: opacity 1.5s ease-out, transform 1.5s ease-out;
            text-align: center;
            line-height: 1.2;
        }

        /* إظهار الرسالة وتكبيرها */
        .birthday-message.show {
            opacity: 1;
            transform: scale(1);
        }

        /* ------------------- تأثير قصاصات الحلوى (Confetti) ------------------- */
        .confetti {
            position: absolute;
            width: 12px;
            height: 12px;
            background-color: #f0f; 
            border-radius: 50%;
            animation: confetti-fall linear forwards;
            opacity: 0;
            z-index: 1000;
        }

        @keyframes confetti-fall {
            0% {
                transform: translateY(-100vh) rotateZ(0deg) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
                transform: translateY(-90vh) scale(1);
            }
            100% {
                transform: translateY(100vh) rotateZ(720deg) scale(1);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    
    <div class="loading-container" id="loading">0%</div>
    
    <div class="birthday-message" id="birthdayMessage">Happy Birthday Foufa ❤️</div>

    <script>
        const loadingElement = document.getElementById('loading');
        const birthdayMessageElement = document.getElementById('birthdayMessage');
        let progress = 0;

        function updateLoading() {
            if (progress <= 100) {
                loadingElement.textContent = `${progress}%`;
                progress++;
                setTimeout(updateLoading, 30); // سرعة التحميل: كل 30 مللي ثانية
            } else {
                // عند اكتمال التحميل
                loadingElement.classList.add('hidden'); // إخفاء العداد
                
                setTimeout(() => {
                    birthdayMessageElement.classList.add('show'); // إظهار الرسالة
                    createConfetti(150); // إطلاق 150 قصاصة حلوى
                }, 500); // تأخير نصف ثانية قبل الظهور
            }
        }

        function createConfetti(num) {
            const colors = ['#f0f', '#0ff', '#ff0', '#0f0', '#f80', '#80f', '#fff', '#ff5733'];
            for (let i = 0; i < num; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                // مواضع عشوائية
                confetti.style.left = Math.random() * 100 + 'vw';
                // مدة وسرعة عشوائية للسقوط
                confetti.style.animationDuration = Math.random() * 4 + 3 + 's'; // 3-7 ثواني
                confetti.style.animationDelay = Math.random() * 1 + 's'; // 0-1 ثانية تأخير
                // لون عشوائي
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                
                document.body.appendChild(confetti);

                // إزالة القصاصة بعد انتهاء الحركة
                confetti.addEventListener('animationend', () => {
                    confetti.remove();
                });
            }
        }

        // بدء عملية التحميل
        updateLoading();
    </script>
</body>
</html>
