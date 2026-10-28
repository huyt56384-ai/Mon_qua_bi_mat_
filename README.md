# Mon_qua_bi_mat
<!DOCTYPE html><html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Một Thế Giới Riêng</title><style>
    * {
        box-sizing: border-box;
    }

    body {
        margin: 0;
        background: #080b16;
        color: white;
        font-family: Arial, sans-serif;
        text-align: center;
    }

    h1 {
        font-size: 26px;
        color: #9beaff;
        margin: 25px 10px;
    }

    video {
        width: 100%;
        max-height: 75vh;
        background: black;
    }

    p {
        padding: 10px 20px;
        line-height: 1.8;
        color: #ddd;
    }

    button {
        background: #72dfff;
        color: #08101c;
        padding: 14px 24px;
        border: none;
        border-radius: 25px;
        font-size: 16px;
        margin: 15px;
    }
</style>

</head><body><h1>✨ Một Thế Giới Riêng ✨</h1>

<video id="video" autoplay playsinline controls>
    <source src="video.mp4" type="video/mp4">
    Trình duyệt không hỗ trợ video.
</video>

<p id="thongbao">
    Đang chuẩn bị phát video...
</p>

<button id="batdau">▶ Bắt đầu thưởng thức</button>

<script>
    const video = document.getElementById("video");
    const thongbao = document.getElementById("thongbao");
    const nut = document.getElementById("batdau");

    // Thử tự phát video kèm âm thanh
    video.muted = false;

    video.play()
        .then(() => {
            thongbao.textContent = "Chúc bạn thưởng thức vui vẻ ✨";
            nut.style.display = "none";
        })
        .catch(() => {
            // Nếu trình duyệt chặn, chờ người xem chạm nút
            thongbao.textContent =
                "Hãy nhấn nút bên dưới để bắt đầu video và âm thanh.";
            nut.style.display = "inline-block";
        });

    nut.addEventListener("click", async () => {
        video.muted = false;

        try {
            await video.play();
            thongbao.textContent = "Chúc bạn thưởng thức vui vẻ ✨";
            nut.style.display = "none";
        } catch (error) {
            thongbao.textContent =
                "Trình duyệt chưa thể phát video. Hãy thử nhấn Play trên video.";
        }
    });
</script>

</body>
</html>
