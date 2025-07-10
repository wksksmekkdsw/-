<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>123‑78 가사 타자 연습</title>
  <style>
    body { font-family: 'Arial'; background: #fafafa; padding: 30px; }
    h1 { font-size: 28px; color: #333; margin-bottom: 10px; }
    #lyrics { font-size: 22px; background: white; padding: 20px; border-radius: 8px; line-height: 1.6; }
    #input { font-size: 20px; width: 100%; padding: 10px; margin-top: 15px; }
    .correct { color: green; }
    .wrong { color: red; text-decoration: underline; }
  </style>
</head>
<body>

  <h1>🎵 보이넥스트도어 – 123‑78</h1>

  <div id="lyrics">
    Give me straight gin<br/>
    양말 하나 남기지 않고<br/>
    떠난 널 위해 cheers<br/>
    Wish you saw this<br/>
    엉망이 돼 버린 내 자태<br/>
    Oh my baby<br/>
    실컷 두들겨 맞은 마음<br/>
    전부 무너진 꼴 좀 봐<br/>
    이 정도 했음 됐잖아요<br/>
    Count 1 to 10<br/>
    Turn to turn to my heart<br/>
    123‑78
  </div>

  <textarea id="input" rows="6" placeholder="여기에 가사 따라 쳐보세요" autocomplete="off"></textarea>

  <script>
    const lyricsText = `Give me straight gin
양말 하나 남기지 않고
떠난 널 위해 cheers
Wish you saw this
엉망이 돼 버린 내 자태
Oh my baby
실컷 두들겨 맞은 마음
전부 무너진 꼴 좀 봐
이 정도 했음 됐잖아요
Count 1 to 10
Turn to turn to my heart
123‑78`;
    const input = document.getElementById('input');
    const lyricsDiv = document.getElementById('lyrics');

    input.addEventListener('input', () => {
      const typed = input.value;
      let html = '';
      for (let i = 0; i < lyricsText.length; i++) {
        const char = lyricsText[i];
        const t = typed[i];
        if (char === '\n') {
          html += '<br/>';
        } else if (t !== undefined) {
          if (t === char) html += `<span class="correct">${char}</span>`;
          else html += `<span class="wrong">${char}</span>`;
        } else {
          html += char;
        }
      }
      lyricsDiv.innerHTML = html;
    });
  </script>

</body>
</html>
