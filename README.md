<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora do Amor</title>
  <style>
    body { font-family: Arial; text-align: center; padding: 50px; background-color: pink; }
    input, button { padding: 10px; font-size: 16px; }
    #resultado { font-size: 24px; margin-top: 20px; color: red; }
  </style>
</head>
<body>
  <h1>Calculadora do Amor</h1>
  <p>Digite dois nomes:</p>
  <input type="text" id="nome1" placeholder="Seu nome">
  <input type="text" id="nome2" placeholder="Nome da pessoa">
  <br><br>
  <button onclick="calcularAmor()">Calcular</button>
  <div id="resultado"></div>

  <script>
    function calcularAmor() {
      const nome1 = document.getElementById("nome1").value.trim().toLowerCase();
      const nome2 = document.getElementById("nome2").value.trim().toLowerCase();
      if (!nome1 || !nome2) {
        document.getElementById("resultado").textContent = "Por favor, preencha os dois nomes.";
        return;
      }
      const combinacao = nome1 + nome2;
      let total = 0;
      for (let i = 0; i < combinacao.length; i++) {
        total += combinacao.charCodeAt(i);
      }
      const porcentagem = (total % 101); // De 0 a 100
      document.getElementById("resultado").textContent = `Compatibilidade: ${porcentagem}% de amor!`;
    }
