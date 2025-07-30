# Praticaforyourmoney.io
<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <title>InfiniteLogin™ Deluxe Edition</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #0d0d0d;
      color: #f2f2f2;
      text-align: center;
      padding-top: 50px;
    }
    input, select {
      padding: 10px;
      margin: 8px;
      border: none;
      border-radius: 5px;
      width: 250px;
    }
    button {
      padding: 10px 20px;
      margin-top: 15px;
      background-color: #008cff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    #progressBar {
      width: 300px;
      background-color: #333;
      border-radius: 5px;
      margin: 20px auto;
    }
    #progressBarFill {
      height: 20px;
      width: 0%;
      background-color: #00ff88;
      border-radius: 5px;
    }
  </style>
</head>
<body>

  <h1>InfiniteLogin™ Deluxe Edition</h1>
  <p>Login sicuro. A vita.</p>

  <!-- Login -->
  <input type="text" placeholder="Username"><br>
  <input type="password" placeholder="Password"><br>
  
  <!-- CAPTCHA -->
  <p>Non sei un robot? Prova a cliccare sull’immagine del cammello (non c’è).</p>
  <input type="checkbox"> Sono un robot (ops...)<br>

  <!-- Domanda di sicurezza -->
  <select>
    <option>Domanda di sicurezza...</option>
    <option>Quante volte hai pensato di mollare oggi?</option>
    <option>Qual è il tuo cartone animato preferito da adulto?</option>
    <option>Inserisci la password che hai dimenticato</option>
  </select><br>
  <input type="text" placeholder="Risposta assurda"><br>

  <!-- 2FA -->
  <p>Inserisci il codice a 2 fattori inviato al tuo piccione viaggiatore</p>
  <input type="text" placeholder="Codice 2FA"><br>

  <!-- Fake Retina Scan -->
  <p>Posiziona l’occhio sullo schermo per la scansione della retina (✨)</p>
  <button onclick="startRetinaScan()">Scansiona Retina</button><br><br>

  <!-- Progress Bar -->
  <div id="progressBar"><div id="progressBarFill"></div></div>
  <p id="status">Pronto per il login...</p>
  <button onclick="fakeLogin()">Login</button>

  <script>
    let count = 0;
    function fakeLogin() {
      count++;
      document.getElementById('status').innerText = 
        `Login #${count} effettuato. Rilevata attività sospetta. Disconnesso. Effettua di nuovo il login.`;
      document.getElementById('progressBarFill').style.width = "0%";
    }

    function startRetinaScan() {
      let width = 0;
      const bar = document.getElementById('progressBarFill');
      const status = document.getElementById('status');
      status.innerText = "Scansione retina in corso...";
      const interval = setInterval(() => {
        if (width >= 99) {
          clearInterval(interval);
          status.innerText = "Scansione fallita. Occhio troppo umido. Riprova.";
          return;
        }
        width += Math.random() * 3;
        bar.style.width = width + "%";
      }, 100);
    }
  </script>

</body>
</html>
