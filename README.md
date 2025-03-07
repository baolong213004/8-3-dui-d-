# 8-3-html

<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hộp Quà Bí Ẩn</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to bottom, #ffdde1, #ee9ca7);
            font-family: Arial, sans-serif;
        }

        .gift-container {
            position: relative;
            width: 220px;
            height: 250px;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Hộp quà */
        .gift-box {
            width: 200px;
            height: 200px;
            background: linear-gradient(to bottom, #ff3366, #ff6699);
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
            transition: transform 0.5s ease-in-out;
        }

        /* Nắp hộp */
        .gift-lid {
            width: 100%;
            height: 50px;
            background: linear-gradient(to bottom, #cc0055, #ff3366);
            position: absolute;
            top: 0;
            transition: transform 0.5s ease-in-out;
            border-radius: 10px 10px 0 0;
        }

        /* Ruy băng trang trí */
        .ribbon {
            width: 100%;
            height: 10px;
            background: #fff;
            position: absolute;
            top: 20px;
        }

        .ribbon::before, .ribbon::after {
            content: "";
            position: absolute;
            width: 20px;
            height: 20px;
            background: #fff;
            border-radius: 50%;
            top: -5px;
        }

        .ribbon::before {
            left: 20px;
        }

        .ribbon::after {
            right: 20px;
        }

        /* Tờ giấy bên trong */
        .paper {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.8);
            width: 160px;
            height: 100px;
            background: white;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.5s, transform 0.5s;
            font-size: 16px;
            font-weight: bold;
            color: #333;
            text-align: center;
            padding: 10px;
            cursor: pointer;
        }

        /* Hiệu ứng mở hộp */
        .gift-container.open .gift-lid {
            transform: translateY(-60px);
        }

        .gift-container.open .gift-box {
            transform: translateY(20px);
        }

        .gift-container.open .paper {
            opacity: 1;
            transform: translate(-50%, -50%) scale(1);
        }
    </style>
</head>
<body>
    <div class="gift-container" onclick="toggleGift()">
        <div class="gift-box">
            <div class="gift-lid">
                <div class="ribbon"></div>
            </div>
            <div class="paper" onclick="goToWebsite(event)">
                🎁 Nhấn vào đây để mở bất ngờ! 🎉
            </div>
        </div>
    </div>

    <script>
        function toggleGift() {
            document.querySelector('.gift-container').classList.toggle('open');
        }

        function goToWebsite(event) {
            event.stopPropagation(); // Ngăn không cho hộp đóng lại khi nhấn vào giấy
            window.location.href = "trái tim html.html"; // Thay bằng trang web bạn muốn
        }
    </script>
</body>
</html>
