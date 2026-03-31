# casino-virtual
!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Tiger Vault</title>

<style>
body {
  background: linear-gradient(135deg, #0f172a, #020617);
  color: white;
  font-family: Arial;
  text-align: center;
}

h1 {
  color: gold;
}

.container {
  margin-top: 50px;
}

.slot {
  font-size: 70px;
  letter-spacing: 20px;
  margin: 30px;
  transition: 0.3s;
}

button {
  padding: 15px 40px;
  font-size: 18px;
  background: gold;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}

button:hover {
  background: orange;
}

#saldo {
  font-size: 22px;
  color: lightgreen;
}

.win {
  color: gold;
  font-size: 24px;
}
</style>
</head>

<body>

<h1>🐯 TIGER VAULT</h1>

<div class="container">
  <p id="saldo">Saldo: 100 moedas</p>
  <div class="slot" id="slots">🐯 🐯 🐯</div>
  <button onclick="girar()">GIRAR</button>
  <p id="msg"></p>
</div>

<script>
let saldo = 100;
const simbolos = ["🐯","💎","🔥","🍀","🍒"];

function girar() {
  if (saldo < 10) {
    alert("Sem moedas!");
    return;
  }

  saldo -= 10;

  let s1 = simbolos[Math.floor(Math.random()*simbolos.length)];
  let s2 = simbolos[Math.floor(Math.random()*simbolos.length)];
  let s3 = simbolos[Math.floor(Math.random()*simbolos.length)];

  document.getElementById("slots").innerText = `${s1} ${s2} ${s3}`;

  let msg = "";

  if (s1 === s2 && s2 === s3) {
    saldo += 80;
    msg = "🔥 JACKPOT INSANO!";
  } else if (s1 === s2 || s2 === s3) {
    saldo += 20;
    msg = "✨ Quase lá... ganhou algo!";
  } else {
    msg = "💀 Perdeu, tenta de novo.";
  }

  document.getElementById("saldo").innerText = "Saldo: " + saldo;
  document.getElementById("msg").innerText = msg;
}
</script>

</body>
</html>
<title>Tiger Vault - Ganhe Moedas Agora</color: gold; 
