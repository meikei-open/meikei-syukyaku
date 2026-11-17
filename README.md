<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MEIKEI OPEN 2026 - 特別ご招待</title>
    <style>
        body { font-family: sans-serif; text-align: center; padding: 20px; background-color: #f4f4f9; }
        #vip-message { display: none; background-color: #ffd700; padding: 15px; border-radius: 8px; font-weight: bold; margin-bottom: 20px; }
        .btn { display: inline-block; padding: 15px 30px; background-color: #0056b3; color: white; text-decoration: none; border-radius: 50px; font-weight: bold; margin-top: 20px;}
    </style>
</head>
<body>

    <!-- ここがコーチごとの特別メッセージに切り替わる部分 -->
    <div id="vip-message"></div>

    <h1>MEIKEI OPEN 2026</h1>
    <p>プロのハイレベルな試合を観戦しよう！</p>
    <p>会場でデジタルスタンプを押すと、<br>プロのサイングッズが当たる特賞抽選に参加できます。</p>

    <a href="#" class="btn" onclick="stampPressed()">会場でスタンプを押す</a>

    <script>
        // ① URLからパラメータ（?coach=〇〇）を取得する
        const urlParams = new URLSearchParams(window.location.search);
        const coachName = urlParams.get('coach');

        // ② もしパラメータがあれば、画面の表示をVIP仕様に切り替える
        const vipDiv = document.getElementById('vip-message');
        
        if (coachName === 'tanaka') {
            vipDiv.innerHTML = "✨ 田中コーチからの特別ご招待！ ✨<br>「今日は〇〇選手のフットワークに注目！」<br><small>※この画面からの参加で特賞抽選確率が2倍になります</small>";
            vipDiv.style.display = 'block';
        } else if (coachName === 'suzuki') {
            vipDiv.innerHTML = "✨ 鈴木コーチからの特別ご招待！ ✨<br>「テニス仲間の皆、プロの戦術を盗んでおいで！」<br><small>※この画面からの参加で特賞抽選確率が2倍になります</small>";
            vipDiv.style.display = 'block';
        }

        // ③ スタンプを押した時の処理（今回は仮のアラート）
        function stampPressed() {
            if(coachName) {
                alert("スタンプ完了！\n裏側で「" + coachName + "コーチの紹介」としてデータが記録されました！");
            } else {
                alert("スタンプ完了！\n（一般来場者として記録されました）");
            }
        }
    </script>
</body>
</html>
