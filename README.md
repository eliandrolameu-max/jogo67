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
