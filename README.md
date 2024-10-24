<!DOCTYPE html>
<html lang="kk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сұхбат парағы</title>
    <style>
        body {
            font-family: 'Monrserrat', sans-serif;
            margin: 0;
            padding: 0;
            background-image: url('Le9zsr8bQmv7gmZW40UXiVaPsGcpVwaY65mw28tU.png');
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            width: 500px;
            min-height: 400px;
            text-align: center;
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        input[type="text"] {
            color: black;
            padding: 10px;
            width: 80%;
            margin-top: 20px;
            border-radius: 5px;
            border: 1px solid #ccc;
            font-size: 16px;
        }

        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            margin-top: 20px;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: green;
        }

        .result {
            margin-top: 30px;
            font-size: 18px;
        }

        .correct {
            color: green;
            font-weight: bold;
            font-size: 23px;
        }

        .incorrect {
            color: red;
            font-weight: bold;
            font-size: 23px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Сәлем! Мен жасанды интеллектпін. Сіздің орыныңызды табуға көмектесемін!</h1>

        <p>Тек қана есіміңізді енгізіңіз (бас әріппен):</p>
        <input type="text" id="nameInput" placeholder="Есіміңізді енгізіңіз" required>
        <br>
        <button onclick="submitName()">Жіберу</button>

        <div class="result" id="result"></div>
    </div>

    <script>
        const correctNames = ['Күлайша', 'Мадина', 'Ғалымжан', 'Қасқырбек', 'Сұлтан', 'Нұрай', 'Данияр', 'Жанерке']; // Дұрыс есімдер тізімі

        // Enter батырмасын басқанда submitName функциясын шақыру
        document.getElementById('nameInput').addEventListener('keydown', function(event) {
            if (event.key === 'Enter') {
                submitName();
            }
        });

        function submitName() {
            const input = document.getElementById('nameInput').value.trim();
            const resultDiv = document.getElementById('result');
            resultDiv.innerHTML = ''; // Алдыңғы нәтижені өшіру

            if (input === '') {
                alert('Есім енгізіңіз!');
                return;
            }

            let message = document.createElement('p');

            if (correctNames.includes(input)) {
                let place = correctNames.indexOf(input) + 1;
                message.className = 'correct';
                message.textContent = `${input} - Қош келдіңіз, кіре берсеңіз болады, сіздің орныңыз: ${place}`;
            } else {
                message.className = 'incorrect';
                message.textContent = `${input} - Өкінішке орай сізді мәліметтер қорынан таба алмадым.`;
            }

            resultDiv.appendChild(message);

            // Енгізу өрісін тазарту
            document.getElementById('nameInput').value = '';
        }
    </script>

</body>
</html>
