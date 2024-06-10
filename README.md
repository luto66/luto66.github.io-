<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Juego: Adivina el Número</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f5f5f5;
        }
        h1 {
            color: #333;
        }
        #game {
            text-align: center;
            background: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input[type="number"] {
            padding: 10px;
            font-size: 16px;
            margin: 10px 0;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
        }
        button:hover {
            background-color: #0056b3;
        }
        #message {
            margin-top: 20px;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div id="game">
        <h1>Adivina el Número</h1>
        <p>Estoy pensando en un número entre 1 y 100. ¿Puedes adivinar cuál es?</p>
        <input type="number" id="guess" min="1" max="100" placeholder="Introduce tu número">
        <button onclick="checkGuess()">Adivinar</button>
        <p id="message"></p>
    </div>
    
    <script>
        let randomNumber = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        function checkGuess() {
            let userGuess = document.getElementById("guess").value;
            let message = document.getElementById("message");
            attempts++;

            if (userGuess == randomNumber) {
                message.textContent = `¡Felicidades! Adivinaste el número en ${attempts} intentos.`;
                message.style.color = "green";
            } else if (userGuess < randomNumber) {
                message.textContent = "El número es mayor. Intenta de nuevo.";
                message.style.color = "red";
            } else {
                message.textContent = "El número es menor. Intenta de nuevo.";
                message.style.color = "red";
            }
        }
    </script>
</body>
</html>
