<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8" />
<title>123‑78 가사 타자 연습</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background: #fafafa;
    padding: 30px;
  }
  h1 {
    font-size: 28px;
    color: #333;
    margin-bottom: 10px;
  }
  #lyrics {
    font-size: 22px;
    background: white;
    padding: 20px;
    border-radius: 8px;
    line-height: 1.6;
    white-space: pre-wrap; /* 줄바꿈 유지 */
  }
  #input {
    font-size: 20px;
    width: 100%;
    padding: 10px;
    margin-top: 15px;
  }
  .correct {
    color: green;
  }
  .wrong {
    color: red;
    text-decoration: underline;
  }
</style>
</head>
<body>
<h1>🎵 보이넥스트도어 – 123‑78 가사 타자 연습</h1>

<div id="lyrics"></div>

<textarea id="input" rows="6" placeholder="여기에 가사 따라 쳐보세요" autocomplete="off"></textarea>

<script>
const lyricsText = `Give me Straight gin
양말 하나같이 도망가서
널 위해 응원합니다.
이것을 보길 바랍니다.
Count 1 to 10
Turn to my heart 123-78`;

const lyricsDiv = document.getElementById('lyrics');
const input = document.getElementById('input');

// 초기 가사 화면에 보여주기
lyricsDiv.textContent = lyricsText;

input.addEventListener('input', () => {
  const typed = input.value;
  let html = '';

  for(let i = 0; i < lyricsText.length; i++) {
    const char = lyricsText[i];
    const typedChar = typed[i];

    if(char === '\n') {
      html += '<br>';
    } else if(typedChar !== undefined) {
      if(typedChar === char) {
        html += `<span class="correct">${char}</span>`;
      } else {
        html += `<span class="wrong">${char}</span>`;
      }
    } else {
      html += char;
    }
  }

  lyricsDiv.innerHTML = html;
});
</script>
</body>
</html>
