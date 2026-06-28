<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>سيرفر القنوات الخاص بي</title>
    <link href="https://cdn.jsdelivr.net/npm/video.js@7.14.3/dist/video-js.css" rel="stylesheet">
    <style>
        body { background-color: #111; color: white; font-family: Arial, sans-serif; text-align: center; direction: rtl; }
        .container { max-width: 800px; margin: auto; padding: 20px; }
        select { width: 100%; padding: 10px; margin: 20px 0; background: #222; color: white; border: 1px solid #444; font-size: 16px; }
        video { width: 100%; max-width: 100%; border-radius: 8px; background: black; }
    </style>
</head>
<body>
    <div class="container">
        <h2>سيرفر البث المباشر الشخصي 📺</h2>
        <p>اختر القناة للمشاهدة فوراً:</p>
        
        <select id="channelSelect" onchange="playChannel(this.value)">
            <option value="">-- اختر القناة من هنا --</option>
            <!-- قنوات عراقية -->
            <option value="https://imn.bcshd.com/live/news/index.m3u8">العراقية الإخبارية</option>
            <option value="https://sharqiya.bcshd.com/live/sharqiya/index.m3u8">قناة الشرقية</option>
            <option value="https://sumaria.bcshd.com/live/sumaria/index.m3u8">قناة السومرية</option>
            <option value="https://utv.bcshd.com/live/utv/index.m3u8">قناة UTV العراق</option>
            <!-- قنوات MBC -->
            <option value="https://mbc.bcshd.com/live/mbc1/index.m3u8">MBC 1</option>
            <option value="https://mbc.bcshd.com/live/mbc2/index.m3u8">MBC 2 (الأفلام)</option>
            <option value="https://mbc.bcshd.com/live/mbcdrama/index.m3u8">MBC دراما</option>
            <option value="https://mbc.bcshd.com/live/mbciraq/index.m3u8">MBC العراق</option>
            <!-- قنوات الرياضة -->
            <option value="https://imn.bcshd.com/live/sports/index.m3u8">العراقية الرياضية</option>
            <option value="https://bein.bcshd.com/live/news/index.m3u8">بي إن سبورت الإخبارية</option>
            <option value="https://bein.bcshd.com/live/sports1/index.m3u8">بي إن سبورت 1</option>
            <option value="https://bein.bcshd.com/live/sports2/index.m3u8">بي إن سبورت 2</option>
            <option value="https://bein.bcshd.com/live/sports3/index.m3u8">بي إن سبورت 3</option>
        </select>

        <video id="my-video" class="video-js vjs-default-skin" controls preload="auto" width="640" height="360"></video>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/video.js@7.14.3/dist/video-js.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/videojs-contrib-hls@5.15.0/dist/videojs-contrib-hls.js"></script>
    <script>
        var player = videojs('my-video');
        function playChannel(url) {
            if(url) {
                player.src({ src: url, type: 'application/x-mpegURL' });
                player.play();
            }
        }
    </script>
</body>
</html>
