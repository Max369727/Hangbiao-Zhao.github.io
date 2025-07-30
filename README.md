<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Flash Cards</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 40px 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            transform: translateY(-50px);
            opacity: 0;
            animation: slideIn 1s forwards 0.5s;
        }
        
        @keyframes slideIn {
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }
        
        h1 {
            font-size: 2.5rem;
            color: #3a4a6d;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        
        .subtitle {
            color: #6c757d;
            font-size: 1.1rem;
        }
        
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
            max-width: 1300px;
            margin: 0 auto;
        }
        
        .card {
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            padding: 25px;
            height: 200px;
            position: relative;
            overflow: hidden;
            transition: all 0.5s ease;
            transform: scale(0.95);
            opacity: 0;
            animation: cardAppear 0.8s forwards;
        }
        
        @keyframes cardAppear {
            to {
                transform: scale(1);
                opacity: 1;
            }
        }
        
        .card:nth-child(1) { animation-delay: 0.8s; }
        .card:nth-child(2) { animation-delay: 1s; }
        .card:nth-child(3) { animation-delay: 1.2s; }
        .card:nth-child(4) { animation-delay: 1.4s; }
        .card:nth-child(5) { animation-delay: 1.6s; }
        .card:nth-child(6) { animation-delay: 1.8s; }
        .card:nth-child(7) { animation-delay: 2s; }
        .card:nth-child(8) { animation-delay: 2.2s; }
        
        .question {
            font-size: 1.3rem;
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 15px;
            transition: all 0.4s ease;
        }
        
        .answer {
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            height: 100%;
            padding: 25px;
            background: #3a4a6d;
            color: white;
            display: flex;
            align-items: center;
            transition: all 0.4s ease;
            border-radius: 15px;
            opacity: 0;
        }
        
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }
        
        .card:hover .question {
            transform: translateY(-40px);
            opacity: 0;
        }
        
        .card:hover .answer {
            top: 0;
            opacity: 1;
        }
        
        .welcome-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #3a4a6d;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            z-index: 1000;
            animation: fadeOut 1s forwards 2s;
        }
        
        @keyframes fadeOut {
            to {
                opacity: 0;
                visibility: hidden;
            }
        }
        
        .welcome-text {
            color: white;
            font-size: 3rem;
            margin-bottom: 20px;
            transform: scale(0);
            animation: scaleIn 0.5s forwards 0.5s;
        }
        
        @keyframes scaleIn {
            to {
                transform: scale(1);
            }
        }
        
        .loading-bar {
            width: 200px;
            height: 4px;
            background: rgba(255,255,255,0.3);
            border-radius: 2px;
            overflow: hidden;
        }
        
        .loading-progress {
            height: 100%;
            width: 0;
            background: white;
            animation: load 1.5s forwards;
        }
        
        @keyframes load {
            to {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="welcome-animation">
        <div class="welcome-text">Flash Cards</div>
        <div class="loading-bar">
            <div class="loading-progress"></div>
        </div>
    </div>
    
    <div class="header">
        <h1>JavaScript Concepts Review</h1>
        <p class="subtitle">Hover over cards to reveal answers</p>
    </div>
    
    <div class="cards-container">
        <div class="card">
            <div class="question">What is the difference between let, const, and var?</div>
            <div class="answer">
                <p><strong>var</strong> is function-scoped and hoisted. <strong>let</strong> and <strong>const</strong> are block-scoped. <strong>const</strong> cannot be reassigned after declaration, while <strong>let</strong> can.</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">What is closure in JavaScript?</div>
            <div class="answer">
                <p>A closure is a function that has access to its own scope, the outer function's variables, and global variables, even after the outer function has returned.</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">Explain the event loop in JavaScript</div>
            <div class="answer">
                <p>The event loop is what allows JavaScript to be non-blocking despite being single-threaded. It handles asynchronous callbacks by placing them in a queue to be executed after the call stack is empty.</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">What is hoisting in JavaScript?</div>
            <div class="answer">
                <p>Hoisting is JavaScript's behavior of moving declarations to the top of their scope before code execution. Only declarations are hoisted, not initializations.</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">What are promises in JavaScript?</div>
            <div class="answer">
                <p>Promises are objects representing the eventual completion (or failure) of an asynchronous operation. They can be in one of three states: pending, fulfilled, or rejected.</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">What is the difference between == and ===?</div>
            <div class="answer">
                <p><strong>==</strong> performs type coercion before comparing values, while <strong>===</strong> (strict equality) checks both value and type without coercion.</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">What is the 'this' keyword in JavaScript?</div>
            <div class="answer">
                <p>The 'this' keyword refers to the object it belongs to. Its value depends on how a function is called: in a method, 'this' refers to the owner object; in a function, it refers to the global object (or undefined in strict mode).</p>
            </div>
        </div>
        
        <div class="card">
            <div class="question">What are template literals?</div>
            <div class="answer">
                <p>Template literals are string literals allowing embedded expressions, created with backticks (`). They support multi-line strings and string interpolation with ${expression} syntax.</p>
            </div>
        </div>
    </div>
</body>
</html>
