<!doctype html>
<html lang="uz">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Surpriz sahifa</title>
  <style>
    body { font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif; display:flex; height:100vh; align-items:center; justify-content:center; background:#f7f7fb; }
    .card { background:white; padding:28px; border-radius:12px; box-shadow:0 6px 30px rgba(20,20,50,0.06); width:320px; text-align:center; }
    input { width:100%; padding:10px; margin-top:12px; border-radius:8px; border:1px solid #ddd; }
    button { margin-top:10px; padding:10px 16px; border-radius:8px; border:0; cursor:pointer; }
    .result { margin-top:18px; font-weight:700; color:#222; font-size:18px; }
  </style>
</head>
<body>
  <div class="card">
    <h3>Biror narsani yozing — shou bo‘ladi 😄</h3>
    <form id="f">
      <input id="inputBox" placeholder="Nimadir yozing..." autocomplete="off"/>
      <button type="submit">Yuborish</button>
    </form>
    <div class="result" id="result"></div>
  </div>

  <script>
    // SEN CHIQARMOQCHI BO‘LGAN XABAR:
    const displayedMessage = ""; // agar bo‘sh qoldirsang — URL dan o‘qiydi

    const params = new URLSearchParams(location.search);
    const urlMsg = params.get('m');
    const finalMessage = displayedMessage.trim() || (urlMsg ? decodeURIComponent(urlMsg) : "Salom!");

    document.getElementById('f').addEventListener('submit', function(e){
      e.preventDefault();
      document.getElementById('result').textContent = finalMessage;
    });
  </script>
</body>
</html>
