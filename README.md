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
// Global registry for all game chapters
const gameStory = {
    chapters: {}
};

gameStory.chapters["ch1"] = {
    title: "Chapter 1: The Void Awakening",
    nodes: {
        start: {
            text: "You wake up in a windowless white room. A blinking digital panel sits before you, and a heavy iron door locks the exit to your left. What do you do?",
            choices: [
                { text: "Interact with the digital panel", nextNode: "panel" },
                { text: "Try to force the iron door open", nextNode: "door" }
            ]
        },
        panel: {
            text: "The screen triggers a 60-second countdown. It demands biometric data you do not possess. A mechanical click echoes nearby.",
            choices: [
                { text: "Turn back and check the door", nextNode: "door" },
                { text: "Smash the glass on the panel", nextNode: "smash_panel" }
            ]
        },
        door: {
            text: "The door is sealed tight from the outside. However, you notice a narrow seam bleeding an eerie blue light into the room.",
            choices: [
                { text: "Peer through the seam", nextNode: "look_inside" },
                { text: "Kick the door with full force", nextNode: "cliffhanger" }
            ]
        },
        smash_panel: {
            text: "The panel delivers a sharp electrical shock. As you stumble backward, a hidden floor compartment pops open.",
            choices: [
                { text: "Inspect the hidden compartment", nextNode: "cliffhanger" }
            ]
        },
        look_inside: {
            text: "You spot a massive silhouette moving in the corridor. It freezes, turns, and stares directly at you with glowing purple eyes.",
            choices: [
                { text: "Step away immediately", nextNode: "cliffhanger" }
            ]
        },
        cliffhanger: {
            text: "Your action triggers a sudden system failure. The lights cut out. Total darkness. End of Part 1.",
            choices: [] // Empty choices array signals the end of the loaded content
        }
    }
};
