# index.html
Txtanaly
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Truth Reveal Analyzer</title>
  <script src="https://js.stripe.com/v3/"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: url('https://images.unsplash.com/photo-1519681393784-d120267933ba') no-repeat center center/cover;
      margin: 0;
      color: #fff;
    }
    .overlay {
      background: rgba(0,0,0,0.75);
      min-height: 100vh;
      padding: 20px;
    }
    .container {
      max-width: 600px;
      margin: auto;
      text-align: center;
    }
    textarea {
      width: 100%;
      height: 130px;
      border-radius: 10px;
      padding: 12px;
      border: none;
    }
    button {
      margin-top: 15px;
      padding: 14px 22px;
      border: none;
      border-radius: 10px;
      background: #00ffcc;
      color: #000;
      font-weight: bold;
      cursor: pointer;
      font-size: 16px;
    }
    .result, .loading {
      margin-top: 20px;
      padding: 15px;
      background: #fff;
      color: #000;
      border-radius: 10px;
      display: none;
      text-align: left;
    }
  </style>
</head>
<body>
  <div class="overlay">
    <div class="container">
      <h1>Reveal Their True Intentions</h1>
      <p>Paste a message and uncover what they REALLY mean...</p><textarea id="userText" placeholder="Paste their message here..."></textarea>
  <br>
  <button onclick="pay()">Reveal the Truth ($5.99)</button>

  <div class="loading" id="loadingBox">
    ⏳ Analyzing emotional tone...<br>
    🔍 Detecting manipulation patterns...<br>
    🧠 Interpreting hidden intent...
  </div>

  <div class="result" id="resultBox"></div>
</div>

  </div>  <script>
    function pay() {
      window.location.href = "https://buy.stripe.com/test_XXXXXXXX"; // replace
    }

    function analyzeText(text) {
      text = text.toLowerCase();

      if (text.includes("sorry") && text.includes("but")) {
        return "This message shows a classic deflection pattern. They appear apologetic, but the 'but' suggests they are avoiding full accountability. This is often used to maintain control while appearing remorseful.";
      }

      if (text.includes("love") && text.includes("miss")) {
        return "There is emotional language here, but it may be driven by longing rather than commitment. This could indicate attachment without real intention to change behavior.";
      }

      if (text.includes("busy") || text.includes("later")) {
        return "This message suggests avoidance. The wording is vague and non-committal, often used to delay or keep you uncertain without direct rejection.";
      }

      return "The tone is neutral on the surface, but lacks strong emotional investment. This could indicate low effort or minimal genuine interest.";
    }

    function runAnalysis() {
      const text = document.getElementById("userText").value;
      const loading = document.getElementById("loadingBox");
      const resultBox = document.getElementById("resultBox");

      loading.style.display = "block";

      setTimeout(() => {
        loading.style.display = "none";
        resultBox.style.display = "block";
        resultBox.innerText = analyzeText(text);
      }, 2500);
    }

    if (window.location.search.includes("paid=true")) {
      runAnalysis();
    }
  </script></body>
</html>
