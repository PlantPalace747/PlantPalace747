<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Virtuális Kert - Jó Napot!</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            text-align: center;
        }
        h1 {
            color: #2e7d32;
        }
        .garden {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        .plant {
            margin: 20px;
            padding: 10px;
            border: 2px solid #ccc;
            background-color: #fff;
            border-radius: 10px;
            width: 200px;
        }
        .plant img {
            width: 100px;
            height: 100px;
        }
        .water-btn {
            padding: 10px 20px;
            background-color: #4caf50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        .water-btn:hover {
            background-color: #45a049;
        }
        .name-input {
            margin-top: 10px;
        }
        .quote {
            background-color: #ffe082;
            padding: 10px;
            border-radius: 5px;
            font-style: italic;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Virtuális Kert</h1>
    <p>Gondozd virtuális növényeidet és nevezz el őket!</p>

    <div class="garden">
        <div class="plant">
            <h2>Paprika</h2>
            <img src="https://via.placeholder.com/100" alt="Paprika">
            <p>Állapot: Száraz</p>
            <input class="name-input" type="text" placeholder="Adj nevet!" oninput="namePlant(this)">
            <button class="water-btn" onclick="waterPlant(this)">Locsolás</button>
        </div>
        <div class="plant">
            <h2>Paradicsom</h2>
            <img src="https://via.placeholder.com/100" alt="Paradicsom">
            <p>Állapot: Száraz</p>
            <input class="name-input" type="text" placeholder="Adj nevet!" oninput="namePlant(this)">
            <button class="water-btn" onclick="waterPlant(this)">Locsolás</button>
        </div>
        <div class="plant">
            <h2>Hagyma</h2>
            <img src="https://via.placeholder.com/100" alt="Hagyma">
            <p>Állapot: Száraz</p>
            <input class="name-input" type="text" placeholder="Adj nevet!" oninput="namePlant(this)">
            <button class="water-btn" onclick="waterPlant(this)">Locsolás</button>
        </div>
    </div>

    <div class="quote" id="daily-quote">
        <!-- Napi pozitív üzenet jelenik meg itt -->
    </div>

    <script>
        const quotes = [
            "Ma egy új nap, tele lehetőségekkel!",
            "Mosolyogj, mert minden nap egy ajándék!",
            "A mai nap csodás lesz, csak higgy benne!",
            "Engedd, hogy a nap fénye átjárjon és boldoggá tegyen!",
            "Minden nap egy új kezdet. Tegyük nagyszerűvé!"
        ];

        // Véletlenszerű napi üzenet kiválasztása
        function displayDailyQuote() {
            const quoteElement = document.getElementById("daily-quote");
            const randomIndex = Math.floor(Math.random() * quotes.length);
            quoteElement.textContent = quotes[randomIndex];
        }

        // Esemény indítása az oldal betöltésekor
        window.onload = function() {
            displayDailyQuote();
        };

        // Növény locsolásának funkciója
        function waterPlant(button) {
            const plantDiv = button.parentElement;
            const status = plantDiv.querySelector('p');
            status.textContent = 'Állapot: Locsolva';
            button.disabled = true;
            button.textContent = 'Már locsolva';
        }

        // Növény elnevezése
        function namePlant(input) {
            const plantDiv = input.parentElement;
            const title = plantDiv.querySelector('h2');
            if (input.value.trim() !== "") {
                title.textContent = input.value;
            } else {
                title.textContent = "Névtelen növény";
            }
        }
    </script>
</body>
</html>
