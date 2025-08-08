# ApexPlanetTask3
Objective:  Gain advanced skills in CSS and JavaScript for building interactive, responsive sites.  

responsive.html  File

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Responsive Design Example</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin: 0;
        padding: 0;
    }
    .container {
        padding: 20px;
        background: lightblue;
    }
    /* Tablet View */
    @media (max-width: 768px) {
        .container {
            background: lightgreen;
            font-size: 18px;
        }
    }
    /* Mobile View */
    @media (max-width: 480px) {
        .container {
            background: lightcoral;
            font-size: 16px;
        }
    }
</style>
</head>
<body>
    <div class="container">
        <h1>Responsive Design Demo</h1>
        <p>Resize the browser to see changes.</p>
    </div>
</body>
</html>


quiz.html  file

<!DOCTYPE html>
<html>
<head>
<title>Interactive Quiz</title>
<style>
    body { font-family: Arial; margin: 20px; }
    .question { margin-bottom: 15px; }
    button { padding: 8px 15px; cursor: pointer; }
</style>
</head>
<body>
<h2>JavaScript Quiz</h2>
<div id="quiz"></div>
<p id="result"></p>
<button onclick="checkAnswers()">Submit</button>

<script>
const quizData = [
    { q: "What does CSS stand for?", a: "Cascading Style Sheets" },
    { q: "What is 2 + 2?", a: "4" }
];

let quizHTML = "";
quizData.forEach((item, index) => {
    quizHTML += `
        <div class="question">
            <p>${item.q}</p>
            <input type="text" id="answer${index}" placeholder="Your answer">
        </div>
    `;
});
document.getElementById("quiz").innerHTML = quizHTML;

function checkAnswers() {
    let score = 0;
    quizData.forEach((item, index) => {
        let userAns = document.getElementById(`answer${index}`).value.trim();
        if(userAns.toLowerCase() === item.a.toLowerCase()) score++;
    });
    document.getElementById("result").textContent = `You scored ${score}/${quizData.length}`;
}
</script>
</body>
</html>


fetch-api.html   File


<!DOCTYPE html>
<html>
<head>
<title>Fetch API Example</title>
</head>
<body>
<h2>Random Joke Generator</h2>
<p id="joke">Click the button to get a joke!</p>
<button onclick="getJoke()">Get Joke</button>

<script>
async function getJoke() {
    const response = await fetch("https://official-joke-api.appspot.com/random_joke");
    const data = await response.json();
    document.getElementById("joke").textContent = `${data.setup} - ${data.punchline}`;
}
</script>
</body>
</html>


interactive-site.html   File
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        text-align: center;
    }
    header {
        background: #4CAF50;
        color: white;
        padding: 15px;
    }
    section {
        padding: 20px;
        max-width: 800px;
        margin: auto;
    }
    /* Responsive Design */
    @media (max-width: 768px) {
        header {
            background: #3e8e41;
            font-size: 18px;
        }
    }
    @media (max-width: 480px) {
        header {
            background: #2e7031;
            font-size: 16px;
        }
    }
    /* Quiz styling */
    .question {
        margin-bottom: 15px;
        text-align: left;
        background: #f9f9f9;
        padding: 10px;
        border-radius: 8px;
    }
    button {
        padding: 8px 15px;
        margin-top: 10px;
        cursor: pointer;
        border: none;
        border-radius: 5px;
        background: #4CAF50;
        color: white;
    }
    button:hover {
        background: #45a049;
    }
    #joke-section {
        margin-top: 30px;
        background: #f0f0f0;
        padding: 15px;
        border-radius: 8px;
    }
</style>
</head>
<body>

<header>
    <h1>Interactive & Responsive Website</h1>
</header>

<section>
    <h2>Responsive Design Demo</h2>
    <p>Resize the browser to see header color change for tablet and mobile view.</p>
</section>

<section id="quiz-section">
    <h2>JavaScript Quiz</h2>
    <div id="quiz"></div>
    <p id="result"></p>
    <button onclick="checkAnswers()">Submit Quiz</button>
</section>

<section id="joke-section">
    <h2>Random Joke Generator</h2>
    <p id="joke">Click the button to get a joke!</p>
    <button onclick="getJoke()">Get Joke</button>
</section>

<script>
// QUIZ FUNCTIONALITY
const quizData = [
    { q: "What does CSS stand for?", a: "Cascading Style Sheets" },
    { q: "What is 2 + 2?", a: "4" },
    { q: "Which HTML tag is used to create a hyperlink?", a: "<a>" }
];

let quizHTML = "";
quizData.forEach((item, index) => {
    quizHTML += `
        <div class="question">
            <p>${item.q}</p>
            <input type="text" id="answer${index}" placeholder="Your answer">
        </div>
    `;
});
document.getElementById("quiz").innerHTML = quizHTML;

function checkAnswers() {
    let score = 0;
    quizData.forEach((item, index) => {
        let userAns = document.getElementById(`answer${index}`).value.trim();
        if(userAns.toLowerCase() === item.a.toLowerCase()) score++;
    });
    document.getElementById("result").textContent = `You scored ${score}/${quizData.length}`;
}

// API FETCH FUNCTIONALITY
async function getJoke() {
    try {
        const response = await fetch("https://official-joke-api.appspot.com/random_joke");
        const data = await response.json();
        document.getElementById("joke").textContent = `${data.setup} - ${data.punchline}`;
    } catch (error) {
        document.getElementById("joke").textContent = "Oops! Couldn't fetch a joke.";
    }
}
</script>

</body>
</html>

