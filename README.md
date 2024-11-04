<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Forças - Segunda e Terceira Lei de Newton</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Calculadora de Força</h1>
    <h2>Situação 1: Força Resultante (Segunda Lei de Newton)</h2>
    <label for="massa1">Informe a massa do objeto (em kg):</label>
    <input type="number" id="massa1" placeholder="Massa (kg)" step="0.01" />
    <br>
    <label for="aceleracao1">Informe a aceleração 1 (a1 em m/s²):</label>
    <input type="number" id="aceleracao1" placeholder="Aceleração 1 (m/s²)" step="0.01" />
    <br>
    <label for="aceleracao2">Informe a aceleração 2 (a2 em m/s²):</label>
    <input type="number" id="aceleracao2" placeholder="Aceleração 2 (m/s²)" step="0.01" />
    <br>
    <button onclick="calcularForcaResultante()">Calcular Força Resultante</button>
    <div class="result">
        <p>Força Resultante: <span id="forcaResultante"></span> N</p>
    </div>
    <h2>Situação 2: Força de Ação e Reação (Terceira Lei de Newton)</h2>
    <label for="massa2">Informe a massa do objeto 1 (em kg):</label>
    <input type="number" id="massa2" placeholder="Massa objeto 1 (kg)" step="0.01" />
    <br>
    <label for="aceleracaoObj1">Informe a aceleração do objeto 1 (m/s²):</label>
    <input type="number" id="aceleracaoObj1" placeholder="Aceleração objeto 1 (m/s²)" step="0.01" />
    <br>
    <label for="massa3">Informe a massa do objeto 2 (em kg):</label>
    <input type="number" id="massa3" placeholder="Massa objeto 2 (kg)" step="0.01" />
    <br>
    <label for="aceleracaoObj2">Informe a aceleração do objeto 2 (m/s²):</label>
    <input type="number" id="aceleracaoObj2" placeholder="Aceleração objeto 2 (m/s²)" step="0.01" />
    <br>
    <button onclick="calcularForcaAcaoReacao()">Calcular Força de Ação e Reação</button>
    <div class="result">
        <p>Força de Ação: <span id="forcaAcao"></span> N</p>
        <p>Força de Reação: <span id="forcaReacao"></span> N</p>
    </div>
    <script>
        function calcularForcaResultante() {
            const massa = parseFloat(document.getElementById('massa1').value);
            const aceleracao1 = parseFloat(document.getElementById('aceleracao1').value);
            const aceleracao2 = parseFloat(document.getElementById('aceleracao2').value);
            if (isNaN(massa) || isNaN(aceleracao1) || isNaN(aceleracao2)) {
                alert("Por favor, insira valores válidos.");
                return;
            }
            const aresultante = aceleracao1 - aceleracao2;
            const forcaResultante = massa * aresultante;
            document.getElementById('forcaResultante').textContent = forcaResultante.toFixed(2);
        }
        function calcularForcaAcaoReacao() {
            const massa1 = parseFloat(document.getElementById('massa2').value);
            const aceleracao1 = parseFloat(document.getElementById('aceleracaoObj1').value);
            const massa2 = parseFloat(document.getElementById('massa3').value);
            const aceleracao2 = parseFloat(document.getElementById('aceleracaoObj2').value);
            if (isNaN(massa1) || isNaN(aceleracao1) || isNaN(massa2) || isNaN(aceleracao2)) {
                alert("Por favor, insira valores válidos.");
                return;
            }
            const forcaAcao = massa1 * aceleracao1;
            const forcaReacao = massa2 * aceleracao2;
            document.getElementById('forcaAcao').textContent = forcaAcao.toFixed(2);
            document.getElementById('forcaReacao').textContent = forcaReacao.toFixed(2);
        }
    </script>
</body>
</html>
