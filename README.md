my-novel-game/
├── index.html
├── style.css
├── script.js
└── chapters/
    └── ch1.js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Project Genesis: An Episodic Game</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="game-container">
        <header>
            <h1>PROJECT GENESIS</h1>
            <p id="chapter-title">Loading story...</p>
        </header>

        <main>
            <div id="text-display"></div>
            <div id="choices-container"></div>
        </main>

        <footer>
            <p>Stay tuned for upcoming parts on GitHub...</p>
        </footer>
    </div>
    <!-- Load chapters here. Order matters: early chapters must load first -->
    <script src="chapters/ch1.js"></script>
    <script src="script.js"></script>
</body>
</html>
body {
    background-color: #0b0c10;
    color: #c5c6c7;
    font-family: 'Courier New', Courier, monospace;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

#game-container {
    width: 100%;
    max-width: 600px;
    background-color: #1f2833;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0px 0px 15px #66fcf1;
    border: 1px solid #66fcf1;
}

h1 {
    color: #66fcf1;
    text-align: center;
    margin-top: 0;
}

#text-display {
    font-size: 1.1rem;
    line-height: 1.6;
    margin-bottom: 20px;
    min-height: 120px;
}

.btn-choice {
    display: block;
    width: 100%;
    background-color: transparent;
    color: #66fcf1;
    border: 2px solid #66fcf1;
    padding: 10px;
    margin: 10px 0;
    cursor: pointer;
    font-size: 1rem;
    transition: 0.3s;
    border-radius: 4px;
}

.btn-choice:hover {
    background-color: #66fcf1;
    color: #0b0c10;
}

footer {
    text-align: center;
    font-size: 0.8rem;
    color: #45a29e;
    margin-top: 20px;
}
