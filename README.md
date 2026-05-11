<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1304 임채현 - 익산시 실시간 기상 정보</title>
    <style>
        /* (기존 디자인 스타일은 그대로 유지됩니다) */
        body { margin: 0; padding: 0; font-family: 'Pretendard', sans-serif; background: linear-gradient(135deg, #a1c4fd 0%, #c2e9fb 100%); height: 100vh; display: flex; justify-content: center; align-items: center; }
        .weather-card { background: rgba(255, 255, 255, 0.7); backdrop-filter: blur(10px); border-radius: 30px; padding: 40px; width: 90%; max-width: 500px; box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1); text-align: center; }
        h1 { font-size: 24px; color: #1e3799; }
        .student-id { font-size: 18px; font-weight: bold; color: #4a69bd; margin-bottom: 30px; }
        .info-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 30px; }
        .info-item { background: rgba(255, 255, 255, 0.5); padding: 15px; border-radius: 15px; }
        .label { font-size: 13px; color: #7f8c8d; margin-bottom: 5px; display: block; }
        .value { font-size: 16px; font-weight: bold; color: #2c3e50; }
        .weather-table { width: 100%; border-collapse: separate; border-spacing: 0 10px; }
        .weather-table td { background: rgba(255, 255, 255, 0.4); padding: 15px 10px; font-size: 15px; }
        .weather-table tr td:first-child { border-radius: 15px 0 0 15px; font-weight: bold; }
        .weather-table tr td:last-child { border-radius: 0 15px 15px 0; color: #1e3799; font-weight: bold; }
        .refresh-btn { background: #1e3799; color: white; border: none; padding: 12px 30px; border-radius: 50px; cursor: pointer; margin-top: 20px; }
    </style>
</head>
<body>

    <div class="weather-card">
        <h1>익산시 현재 날씨 상태</h1>
        <div class="student-id">1304 임채현</div>

        <div class="info-grid">
            <div class="info-item">
                <span class="label">📍 조회 지역</span>
                <span class="value">전라북도 익산시</span>
            </div>
            <div class="info-item">
                <span class="label">🕒 업데이트 시각</span>
                <span class="value" id="current-time">로딩 중...</span>
            </div>
        </div>

        <table class="weather-table">
            <tbody>
                <tr><td>강수형태</td><td>0 (코드)</td></tr>
                <tr><td>습도</td><td>62 %</td></tr>
                <tr><td>기온</td><td>19.9 °C</td></tr>
                <tr><td>풍속</td><td>1.2 m/s</td></tr>
            </tbody>
        </table>

        <button class="refresh-btn" onclick="location.reload()">새로고침</button>
    </div>

    <script>
        // 현재 시간을 가져와서 화면에 뿌려주는 기능
        function updateTime() {
            const now = new Date();
            const year = now.getFullYear();
            const month = String(now.getMonth() + 1).padStart(2, '0');
            const day = String(now.getDate()).padStart(2, '0');
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            
            const timeString = `${year}.${month}.${day} ${hours}:${minutes}`;
            document.getElementById('current-time').innerText = timeString;
        }

        // 페이지가 열릴 때 실행
        updateTime();
    </script>
</body>
</html>
</html>
