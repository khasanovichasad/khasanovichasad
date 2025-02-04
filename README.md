<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
    <title>iOS Style Login</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro:wght@400;600&display=swap');
        body {
            font-family: 'Source Code Pro', monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f2f2f7;
        }
        .login-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
            margin: 20px; /* Added margin for even spacing */
            display: flex;
            flex-direction: column;
            align-items: center; /* Center content horizontally */
        }
        .login-container h2 {
            margin: 0 0 20px;
            font-size: 24px;
            font-weight: 600;
            color: #333;
        }
        .login-container input, .login-container button {
            width: 100%; /* Ensure full width */
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }
        .login-container input {
            width: 90%; /* Slightly smaller width */
            padding: 8px; /* Slightly smaller padding */
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 14px; /* Slightly smaller font size */
        }
        .login-container button {
            width: 100%;
            padding: 10px;
            background-color: #007aff;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }
        .login-container button:hover {
            background-color: #005bb5;
        }
        .register-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
            margin: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .register-container h2 {
            margin: 0 0 20px;
            font-size: 24px;
            font-weight: 600;
            color: #333;
        }
        .register-container input {
            width: 90%;
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 14px;
        }
        .register-container button {
            width: 100%;
            padding: 10px;
            background-color: #007aff;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }
        .register-container button:hover {
            background-color: #005bb5;
        }
        .congratulations-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
            margin: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .congratulations-container h2 {
            margin: 0 0 20px;
            font-size: 24px;
            font-weight: 600;
            color: #333;
        }
        .congratulations-container p {
            font-size: 16px;
            color: #333;
            margin-bottom: 20px;
        }
        .congratulations-container button {
            width: 100%;
            padding: 10px;
            background-color: #007aff;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }
        .congratulations-container button:hover {
            background-color: #005bb5;
        }
        .warning-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
            margin: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .warning-container h2 {
            margin: 0 0 20px;
            font-size: 24px;
            font-weight: 600;
            color: #333;
        }
        .warning-container p {
            font-size: 16px;
            color: #333;
            margin-bottom: 20px;
        }
        .warning-container button {
            width: 100%;
            padding: 10px;
            background-color: #007aff;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }
        .warning-container button:hover {
            background-color: #005bb5;
        }
        .language-container {
            background-color: #fff;
            padding: 10px; /* Adjusted padding */
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 250px; /* Adjusted width */
            margin: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .language-container .language-option {
            display: flex;
            align-items: center;
            justify-content: center; /* Center content horizontally */
            width: 100%; /* Full width */
            padding: 10px; /* Padding for alignment */
            cursor: pointer;
            transition: transform 0.2s; /* Add transition for hover effect */
        }
        .language-container .language-option:hover {
            transform: scale(1.1); /* Scale up on hover */
        }
        .language-container .language-option img {
            width: 30px;
            height: 20px;
            margin-right: 10px;
        }
        .language-container .language-option span {
            text-align: center; /* Center text */
        }
        .language-warning {
            display: none;
            color: red;
            margin-top: 10px;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        @keyframes fadeOut {
            from { opacity: 1; }
            to { opacity: 0; }
        }
        .greeting {
            display: none;
            font-size: 72px; /* Set font size */
            animation: fadeIn 1s forwards, fadeOut 1s 2s forwards; /* Appear and disappear effect */
        }
        .units-container {
            display: none;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
            opacity: 1 !important;
        }
        .units-title {
            font-size: 24px;
            font-weight: 600;
            color: #333;
            margin-bottom: 20px;
        }
        .units-grid {
            display: flex;
            justify-content: space-around;
            width: 100%;
        }
        .unit {
            background-color: #007aff;
            color: #fff;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 200px;
            text-align: center;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
            opacity: 0;  /* Start hidden */
            animation: fadeSlideUp 0.6s ease-out forwards;
        }
        .unit:hover {
            transform: scale(1.1);
            background-color: #005bb5;
        }
        .result-container {
            display: none;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
        }
        .result-container h2 {
            font-size: 24px;
            font-weight: 600;
            color: #333;
            margin-bottom: 20px;
        }
        .result-container p {
            font-size: 16px;
            color: #333;
            margin-bottom: 10px;
        }
        .result-container button {
            width: 100%;
            padding: 10px;
            background-color: #007aff;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
        }
        .result-container button:hover {
            background-color: #005bb5;
        }
        /* iOS style for writing task container */
        .writing-task-container {
            display: none;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            width: 300px;
            margin: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        #writing-instruction {
            font-size: 16px;
            color: #333;
            text-align: center;
            margin-bottom: 10px;
        }
        #writing-timer {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        #writing-text {
            width: 90%;
            height: 150px;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
            font-size: 16px;
        }
        /* New iOS style for send button */
        .ios-button {
            width: 100%;
            padding: 10px;
            background-color: #007aff;
            border: none;
            border-radius: 5px;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }
        .ios-button:hover {
            background-color: #005bb5;
        }
        @media only screen and (max-width: 480px) {
            body {
                padding: 10px;
            }
            .login-container,
            .register-container,
            .congratulations-container,
            .warning-container,
            .language-container,
            .writing-task-container,
            .result-container {
                width: 90%;
                margin: 10px auto;
                padding: 15px;
            }
            .units-grid {
                flex-direction: column;
                align-items: center;
            }
            .unit {
                width: 100%;
                margin-bottom: 10px;
            }
            .ios-button, 
            .login-container button, 
            .register-container button, 
            .congratulations-container button, 
            .warning-container button, 
            .result-container button {
                font-size: 14px;
                padding: 8px;
            }
            .login-container input, 
            .register-container input {
                font-size: 14px;
                padding: 8px;
            }
        }
        .units-grid .unit {
            margin: 10px;
        }
        /* Updated About Us container to be larger and not square */
        .about-container {
            display: none;
            position: fixed;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            background-color: #fff;
            width: 250px;  /* increased width */
            padding: 10px;  /* adjusted padding */
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            text-align: center;
            font-size: 14px; /* slightly larger font */
            z-index: 1000;
            overflow: auto;
        }
        /* Updated fixed About Us button to be average-sized and square */
        #about-us-btn {
            position: fixed;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 60px;
            padding: 0;
            border-radius: 5px;
            font-size: 14px;
            line-height: 60px; /* vertically center the text */
        }
        .reading-content {
            font-size: 14px;
            max-height: 90vh;
            overflow-y: auto;
            padding: 10px;
        }

        .reading-content p {
            margin-bottom: 10px;
            line-height: 1.4;
        }

        .reading-questions {
            font-size: 13px;
            margin-top: 15px;
        }

        .reading-questions label {
            margin: 3px 0;
            display: block;
        }
        #balloon-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 9999;
        }
        .balloon {
            position: absolute;
            bottom: -150px;
            width: 40px;
            height: 60px;
            border-radius: 50%;
            opacity: 0.8;
            animation: floatUp 5s linear forwards;
        }
        @keyframes floatUp {
            0% { transform: translateY(0) scale(1); opacity: 0.8; }
            100% { transform: translateY(-110vh) scale(1.2); opacity: 0; }
        }
        @keyframes fadeSlideUp {
            0% {
                opacity: 0;
                transform: translateY(40px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .unit {
            /* ...existing unit styles... */
            opacity: 0;  /* Start hidden */
            animation: fadeSlideUp 0.6s ease-out forwards;
        }

        /* Add animation delay for each unit */
        #unit-listening { display: none; }
        #unit-test { animation-delay: 0.3s; }
        #unit-writing { animation-delay: 0.5s; }
        #unit-reading { animation-delay: 0.7s; }

        /* Make container visible immediately but children animate */
        .units-container {
            /* ...existing styles... */
            opacity: 1 !important;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h2>Login</h2>
        <input type="text" placeholder="Name" id="login-name" required pattern="^[A-Za-z]{2,}$" title="Use only Latin letters, at least 2.">
        <input type="text" placeholder="Surname" id="login-surname" required pattern="^[A-Za-z]{2,}$" title="Use only Latin letters, at least 2.">
        <button type="submit" id="login-button">Login</button>
        <p>Don't have an account? <a href="#" id="show-register">Register</a></p>
    </div>
    <div class="register-container" style="display: none;">
        <h2>Register</h2>
        <input type="text" placeholder="Name" id="register-name" required pattern="^[A-Za-z]{2,}$" title="Use only Latin letters, at least 2.">
        <input type="text" placeholder="Surname" id="register-surname" required pattern="^[A-Za-z]{2,}$" title="Use only Latin letters, at least 2.">
        <button type="submit" id="register-button">Register</button>
        <p>Already have an account? <a href="#" id="show-login">Login</a></p>
    </div>
    <div class="congratulations-container" style="display: none;">
        <h2>Congratulations!</h2>
        <p>You have successfully registered.</p>
        <button id="back-to-login">Back to Login</button>
    </div>
    <div class="warning-container" style="display: none;">
        <h2>Warning!</h2>
        <p>You need to register before logging in.</p>
        <button id="back-to-register">Back to Register</button>
    </div>
    <div class="language-container" style="display: none;">
        <div class="language-option" id="english">
            <img src="https://upload.wikimedia.org/wikipedia/en/a/a4/Flag_of_the_United_States.svg" alt="English">
            <span>English</span>
        </div>
        <div class="language-option" id="russian">
            <img src="https://upload.wikimedia.org/wikipedia/en/f/f3/Flag_of_Russia.svg" alt="Russian">
            <span>Russian</span>
        </div>
        <div class="language-option" id="uzbek">
            <img src="https://upload.wikimedia.org/wikipedia/commons/8/84/Flag_of_Uzbekistan.svg" alt="Uzbek">
            <span>Uzbek</span>
        </div>
        <div class="language-option" id="japanese">
            <img src="https://upload.wikimedia.org/wikipedia/en/9/9e/Flag_of_Japan.svg" alt="Japanese">
            <span>Japanese</span>
        </div>
        <p class="language-warning" id="language-warning">Currently, it is impossible to continue with this language. Now only English is available.</p>
    </div>
    <h2 class="greeting" id="greeting"></h2>
    <div class="units-container" id="units-container">
        <div class="units-title">Please choose the unit</div>
        <div class="units-grid">
            <div class="unit" id="unit-test">TEST</div>
            <div class="unit" id="unit-writing">WRITING</div>
            <div class="unit" id="unit-reading">READING</div>
        </div>
    </div>
    <!-- New fixed About Us button at the bottom of page -->
    <button id="about-us-btn" class="ios-button">About Us</button>
    <!-- New About Us modal container -->
    <div class="about-container" id="about-container">
        <h2>About Us</h2>
        <p>This site was developed by Asad Rajabov, a young and emerging developer in this field.</p>
        <button id="close-about" class="ios-button" style="margin-top:10px; font-size:12px;">Close</button>
    </div>
    <div class="result-container" id="result-container">
        <h2>Result</h2>
        <p id="result-score"></p>
        <p id="result-feedback"></p>
        <button id="back-to-units">Back to Units</button>
    </div>
    <!-- Add score board container -->
    <div id="score-board" style="position: fixed; top: 10px; left: 10px; background: rgba(0,0,0,0.1); padding: 5px 10px; border-radius: 5px; font-family: 'Source Code Pro', monospace;"></div>
    <div id="balloon-container"></div>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            let isRegistered = false;
            let registeredName = '';
            let registeredSurname = '';
            let writingTaskContainer; // Define outside to ensure scope availability
            // Track completed units and their scores
            const finishedUnits = {};
            const scoreBoard = document.getElementById('score-board');

            // Update scoreboard function: display unit names in uppercase
            function updateScoreBoard() {
                // Display each finished unit score in a neat list
                let listItems = "";
                for (const unit in finishedUnits) {
                    listItems += `<li>${unit.toUpperCase()}: ${finishedUnits[unit]}/10</li>`;
                }
                scoreBoard.innerHTML = `<ul style="list-style:none;margin:0;padding:0;">${listItems}</ul>`;
            }

            document.getElementById('show-register').addEventListener('click', function() {
                document.querySelector('.login-container').style.display = 'none';
                document.querySelector('.register-container').style.display = 'flex';
                toggleAboutButton(true);
            });

            document.getElementById('show-login').addEventListener('click', function() {
                document.querySelector('.register-container').style.display = 'none';
                document.querySelector('.login-container').style.display = 'flex';
                toggleAboutButton(true);
            });

            document.getElementById('register-button').addEventListener('click', function() {
                const nameVal = document.getElementById('register-name').value.trim();
                const surnameVal = document.getElementById('register-surname').value.trim();
                if(!isValidName(nameVal) || !isValidName(surnameVal)) {
                    alert("Please use only letters (at least 2).");
                    return;
                }
                isRegistered = true;
                registeredName = document.getElementById('register-name').value;
                registeredSurname = document.getElementById('register-surname').value;
                document.querySelector('.register-container').style.display = 'none';
                document.querySelector('.congratulations-container').style.display = 'flex';
            });

            document.getElementById('back-to-login').addEventListener('click', function() {
                document.querySelector('.congratulations-container').style.display = 'none';
                document.querySelector('.login-container').style.display = 'flex';
            });

            document.getElementById('login-button').addEventListener('click', function() {
                const loginNameVal = document.getElementById('login-name').value.trim();
                const loginSurnameVal = document.getElementById('login-surname').value.trim();
                if(!isValidName(loginNameVal) || !isValidName(loginSurnameVal)) {
                    alert("Please use only letters (at least 2).");
                    return;
                }
                const loginName = document.getElementById('login-name').value;
                const loginSurname = document.getElementById('login-surname').value;
                if (!isRegistered) {
                    document.querySelector('.warning-container p').textContent = "Please register first!";
                    document.querySelector('.login-container').style.display = 'none';
                    document.querySelector('.warning-container').style.display = 'flex';
                } else if (loginName !== registeredName || loginSurname !== registeredSurname) {
                    document.querySelector('.warning-container p').textContent = "Wrong username or surname, please register first!";
                    document.querySelector('.login-container').style.display = 'none';
                    document.querySelector('.warning-container').style.display = 'flex';
                } else {
                    document.querySelector('.login-container').style.display = 'none';
                    document.querySelector('.language-container').style.display = 'flex';
                }
            });

            document.getElementById('back-to-register').addEventListener('click', function() {
                document.querySelector('.warning-container').style.display = 'none';
                document.querySelector('.register-container').style.display = 'flex';
            });

            document.querySelectorAll('.language-option').forEach(option => {
                option.addEventListener('click', function() {
                    if (this.id !== 'english') {
                        document.getElementById('language-warning').style.display = 'block';
                    } else {
                        document.getElementById('language-warning').style.display = 'none';
                        const userName = document.getElementById('login-name').value;
                        const greeting = document.getElementById('greeting');
                        
                        // Hide About Us elements before showing greeting
                        document.getElementById('about-us-btn').style.display = 'none';
                        document.getElementById('about-container').style.display = 'none';
                        
                        // Show greeting with balloons
                        greeting.textContent = `Assalomu Aleykum, ${userName}`;
                        greeting.style.display = 'block';
                        
                        // Add balloon effect
                        const container = document.getElementById('balloon-container');
                        for (let i = 0; i < 15; i++) {
                            const balloon = document.createElement('div');
                            balloon.classList.add('balloon');
                            balloon.style.left = Math.random() * 100 + '%';
                            const colors = ['#FF6B6B', '#4ECDC4', '#45B7D1', '#96CEB4', '#FFEEAD', '#D4A5A5'];
                            balloon.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                            container.appendChild(balloon);
                        }

                        document.querySelector('.language-container').style.display = 'none';
                        
                        // Clear balloons and hide greeting after delay
                        setTimeout(() => {
                            greeting.style.display = 'none';
                            container.innerHTML = '';
                            const unitsContainer = document.getElementById('units-container');
                            unitsContainer.style.display = 'flex';
                            
                            // Reset animations by removing and re-adding units
                            const units = unitsContainer.querySelectorAll('.unit');
                            units.forEach(unit => {
                                const clone = unit.cloneNode(true);
                                unit.parentNode.replaceChild(clone, unit);
                                // Reattach event listeners
                                if (clone.id === 'unit-test') {
                                    clone.addEventListener('click', function() {
                                        document.getElementById('unit-test').click();
                                    });
                                } else if (clone.id === 'unit-writing') {
                                    clone.addEventListener('click', function() {
                                        document.getElementById('unit-writing').click();
                                    });
                                } else if (clone.id === 'unit-reading') {
                                    clone.addEventListener('click', function() {
                                        document.getElementById('unit-reading').click();
                                    });
                                }
                            });
                        }, 3000);
                    }
                });
            });

            document.getElementById('back-to-units').addEventListener('click', function() {
                document.getElementById('result-container').style.display = 'none';
                document.getElementById('units-container').style.display = 'flex';
            });

            // Modify WRITING unit event to start timer immediately and setup send button validation/evaluation
            document.getElementById('unit-writing').addEventListener('click', function() {
                // Check if unit already passed
                if (finishedUnits['WRITING']) {
                    alert("You have already passed the Writing unit with score: " + finishedUnits['WRITING'] + "|10");
                    return;
                }
                document.getElementById('units-container').style.display = 'none';
                if (!writingTaskContainer) {
                    writingTaskContainer = document.createElement('div');
                    writingTaskContainer.id = 'writing-task-container';
                    writingTaskContainer.className = 'writing-task-container';
                    writingTaskContainer.innerHTML = `
                        <h2>Writing Task</h2>
                        <p id="writing-instruction">In this task you must write at least 30 words in 20 minutes on the topic "Sizning sevimli kitobingiz"</p>
                        <div id="writing-timer"><span id="bomb-emoji">💣</span> <span id="timer-display">20:00</span></div>
                        <textarea id="writing-text" placeholder="Write your text here..."></textarea>
                        <button id="send-writing" class="ios-button">Send</button>
                    `;
                    document.body.appendChild(writingTaskContainer);
                }
                writingTaskContainer.style.display = 'flex';
                // Start the timer immediately when the writing task is opened
                startTimer(20 * 60, writingTaskContainer.querySelector('#timer-display'), function(){
                    // Auto evaluate and send user back to units page when time expires
                    evaluateWritingTask();
                });
                
                // Add send button click event for validating text and evaluating its quality
                const sendButton = writingTaskContainer.querySelector('#send-writing');
                sendButton.addEventListener('click', function() {
                    // Always evaluate; evaluation function will assign score 0 if text has < 30 words.
                    evaluateWritingTask();
                });
            });

            // Updated startTimer to accept a callback on completion
            function startTimer(duration, display, onComplete) {
                if (!display) return;
                
                let timer = duration, minutes, seconds;
                let interval = setInterval(function() {
                    if (!display) {
                        clearInterval(interval);
                        return;
                    }
                    
                    minutes = parseInt(timer / 60, 10);
                    seconds = parseInt(timer % 60, 10);
                    minutes = minutes < 10 ? "0" + minutes : minutes;
                    seconds = seconds < 10 ? "0" + seconds : seconds;
                    display.textContent = minutes + ":" + seconds;
                    
                    if (--timer < 0) {
                        clearInterval(interval);
                        timer = 0;
                        if(onComplete) { onComplete(); }
                    }
                }, 1000);
                return interval;
            }

            // Common evaluation function for manual and auto submission
            function evaluateWritingTask() {
                const textArea = writingTaskContainer.querySelector('#writing-text');
                const text = textArea.value.trim();
                const words = text.split(/\s+/).filter(word => word.length > 0);
                let rating;
                let suggestions = "";
                if (words.length < 30) {
                    // If less than 30 words, assign score 0 with a corresponding message.
                    rating = 0;
                    suggestions = "Your text is too short.";
                } else {
                    const uniqueWords = new Set(words.map(word => word.toLowerCase())).size;
                    const uniquenessRatio = uniqueWords / words.length;
                    rating = Math.floor(uniquenessRatio * 10);
                    if (rating < 1) rating = 1;
                    if (rating > 10) rating = 10;
                    if (uniquenessRatio < 0.5) {
                        suggestions += "Try to use a more varied vocabulary. ";
                    }
                    suggestions += "Also, consider using complex words and avoid repeating the same word multiple times.";
                }
                finishedUnits['WRITING'] = rating;
                updateScoreBoard();
                writingTaskContainer.innerHTML = `
                    <h2>Writing Task Evaluation</h2>
                    <p>Your score: ${rating} / 10</p>
                    <p>Suggestions: ${suggestions}</p>
                    <button id="back-to-units-from-writing" class="ios-button">Back to Units</button>
                `;
                writingTaskContainer.querySelector('#back-to-units-from-writing').addEventListener('click', function(){
                    writingTaskContainer.style.display = 'none';
                    document.getElementById('units-container').style.display = 'flex';
                });
            }

            function isValidName(str) {
                return /^[A-Za-z]{2,}$/.test(str);
            }

            // Add event listener for Test unit
            document.getElementById('unit-test').addEventListener('click', function() {
                if (finishedUnits['TEST']) {
                    alert("You have already passed the Test unit with score: " + finishedUnits['TEST'] + "/10");
                    return;
                }
                document.getElementById('units-container').style.display = 'none';

                // Create container if it doesn't exist
                if (!window.testTaskContainer) {
                    window.testTaskContainer = document.createElement('div');
                    testTaskContainer.id = 'test-task-container';
                    testTaskContainer.className = 'writing-task-container';
                    document.body.appendChild(testTaskContainer);
                }

                // Update container content with friendlier wording for test instructions:
                testTaskContainer.innerHTML = `
                    <h2>Test Instructions</h2>
                    <p>
                        Welcome to your practical test. You will face 10 questions one at a time.
                        Take your time – you have 10 minutes to answer at a comfortable pace.
                    </p>
                    <button id="start-test" class="ios-button">Start</button>
                    <div id="test-timer" style="margin-top:10px;">10:00</div>
                    <div id="question-container" style="display:none;"></div>
                `;
                testTaskContainer.style.display = 'flex';

                // Add event listener after container is added to DOM
                document.getElementById('start-test').addEventListener('click', function startTestHandler() {
                    // Hide the start button and show questions container
                    document.getElementById('start-test').style.display = 'none';
                    document.getElementById('question-container').style.display = 'block';
                    // Start 10-minute timer
                    startTimer(10 * 60, document.getElementById('test-timer'), finishTest);
                    displayQuestion();
                });

                let currentTestIndex = 0;
                const testQuestions = [
                    { 
                        question: "1-savol: To'gri ketma-ketlikda yozilgan variantni toping",
                        options: [
                            "Xayrli tong. Xayrli kech. Xayrli kun. Xayrli tun",
                            "Xayrli kun. Xayrli tong. Xayrli kech. Xayrli tun",
                            "Xayrli tong. Xayrli kun. Xayrli kech. Xayrli tun",
                            "Xayrli tong. Xayrli kun. Xayrli tun. Xayrli kech"
                        ],
                        correct: 2
                    },
                    { 
                        question: "2-savol: “I am used to drink too much alcohol ten years ago” gapini o’zbek tilida tarjimasi qanday bo’ladi?",
                        options: [
                            "Men o’n yil avval ko’p alkogol ichishga o’rganib qolgan edim",
                            "Men o’n yil unchalik ko’p alkogol ichmas edim",
                            "Men o’n yildan beri ko’p alkogol ichib kelaman",
                            "Men o’n yildan beri ko’p alkogol ichishim kerak edi deb o’ylardim"
                        ],
                        correct: 0
                    },
                    { 
                        question: "3-savol: NUQTALAR O'RNIDA MOS KELADIGAN SO'ZNI QO'YING:\nAnvar kompyuter … yaxshi ko’radi",
                        options: [
                            "o’ynashni",
                            "sakrashni",
                            "yeyishni",
                            "sayohat qilishni"
                        ],
                        correct: 0
                    },
                    { 
                        question: "4-savol: \"Albatta\" so'zining sinonimi nima?",
                        options: [
                            "Har doim",
                            "Iloji yo'q",
                            "Kamdan kam",
                            "Shak shubhasiz"
                        ],
                        correct: 3
                    },
                    { 
                        question: "5-savol: The most beautiful so'zining tarjimasi nima?",
                        options: [
                            "Chiroyliroq",
                            "Chiroyli",
                            "Eng chiroyli",
                            "Chiroyli emas"
                        ],
                        correct: 2
                    },
                    { 
                        question: '6-savol: "She is the most talented student in our class" gapini oʻzbek tiliga toʻgʻri tarjima qiling.',
                        options: [
                            "U bizning sinfimizda eng isteʼdodli oʻquvchi",
                            "U bizning sinfimizda isteʼdodli oʻquvchi",
                            "U bizning sinfimizda eng yaxshi oʻquvchi",
                            "U bizning sinfimizda isteʼdodli emas"
                        ],
                        correct: 0
                    },
                    { 
                        question: "7-savol: Which sentence has negative form?",
                        options: [
                            "U ko'p kulmaydi",
                            "U ko'p o'rganadi",
                            "U ko'p kuladimi?",
                            "U ko'p gapiryapti"
                        ],
                        correct: 0
                    },
                    { 
                        question: "8-savol: Village so'zi o'zbek tilida nima bo'ladi?",
                        options: [
                            "Shahar",
                            "Vodiy",
                            "Qishloq",
                            "Mahalla"
                        ],
                        correct: 2
                    },
                    { 
                        question: "9-savol: Find the sentence in past tense",
                        options: [
                            "U ertaga keladi",
                            "U hozir kelyapti",
                            "U kecha ketgan edi",
                            "U ertaga ketmoqchi"
                        ],
                        correct: 2
                    },
                    { 
                        question: "10-savol: Suddenly so'zining o'zbek tilidagi tarjimasini toping",
                        options: [
                            "To'satdan",
                            "Sekingina",
                            "Tezda",
                            "Allaqachon"
                        ],
                        correct: 0
                    }
                ];

                let userAnswers = [];

                function displayQuestion() {
                    const qContainer = document.getElementById('question-container');
                    const current = testQuestions[currentTestIndex];
                    let optionsHtml = "";
                    current.options.forEach((opt, index) => {
                        optionsHtml += `<label><input type="radio" name="test-option" value="${index}"> ${opt}</label><br/>`;
                    });
                    qContainer.innerHTML = `
                        <h3>${current.question}</h3>
                        ${optionsHtml}
                        <button id="next-question" class="ios-button">Next</button>
                    `;
                    document.getElementById('next-question').addEventListener('click', function() {
                        const selected = qContainer.querySelector('input[name="test-option"]:checked');
                        if (!selected) { 
                            alert("Please select an option.");
                            return;
                        }
                        userAnswers.push(parseInt(selected.value));
                        currentTestIndex++;
                        if (currentTestIndex < testQuestions.length) {
                            displayQuestion();
                        } else {
                            finishTest();
                        }
                    });
                }

                function finishTest() {
                    let score = 0;
                    let feedback = '';
                    testQuestions.forEach((q, i) => {
                        const userAnswer = userAnswers[i];
                        const isCorrect = userAnswer === q.correct;
                        score += isCorrect ? 1 : 0;
                        feedback += `
                            <div style="margin: 8px 0; padding: 8px; background: ${isCorrect ? '#e8f5e9' : '#ffebee'}; border-radius: 5px;">
                                <p style="margin: 0 0 5px;"><strong>${q.question}</strong></p>
                                <p style="margin: 0; color: ${isCorrect ? '#2e7d32' : '#c62828'};">
                                    Your answer: ${q.options[userAnswer]}<br>
                                    ${isCorrect ? '✓ Correct!' : `✗ Correct answer was: ${q.options[q.correct]}`}
                                </p>
                            </div>
                        `;
                    });
                    finishedUnits['TEST'] = score;
                    updateScoreBoard();
                    const finalScore = Math.round((score / testQuestions.length) * 10);
                    let motivation = '';
                    if (finalScore >= 8) {
                        motivation = "Excellent work on the test! You nailed it!";
                    } else if (finalScore >= 6) {
                        motivation = "Good job! A little more practice will lead to perfection.";
                    } else {
                        motivation = "Don't worry, every mistake is a step closer to mastery. Keep trying!";
                    }

                    // Later, in the finishTest() function, update the evaluation text:
                    testTaskContainer.innerHTML = `
                        <h2>Test Evaluation</h2>
                        <p style="font-size: 18px; margin: 15px 0;">Your score: ${finalScore} / 10</p>
                        <p style="color: #1976d2; font-weight: bold; margin: 15px 0;">
                            ${motivation}
                        </p>
                        <div style="max-height: 400px; overflow-y: auto; margin: 15px 0;">
                            ${feedback}
                        </div>
                        <button id="back-to-units-from-test" class="ios-button" style="margin-top: 15px;">
                            Back to Units
                        </button>
                    `;

                    document.getElementById('back-to-units-from-test').addEventListener('click', function(){
                        testTaskContainer.style.display = 'none';
                        document.getElementById('units-container').style.display = 'flex';
                    });
                }
            });

            // Add event listener for About Us button
            if (document.getElementById('about-us-btn')) {
                document.getElementById('about-us-btn').addEventListener('click', function() {
                    document.getElementById('about-container').style.display = 'flex';
                    document.getElementById('about-container').style.flexDirection = 'column';
                    document.getElementById('about-container').style.alignItems = 'center';
                });
            }

            if (document.getElementById('close-about')) {
                document.getElementById('close-about').addEventListener('click', function(){
                    document.getElementById('about-container').style.display = 'none';
                });
            }

            document.getElementById('unit-reading').addEventListener('click', function() {
                if (finishedUnits['READING']) {
                    alert("You have already passed the Reading unit with score: " + finishedUnits['READING'] + "/10");
                    return;
                }
                document.getElementById('units-container').style.display = 'none';

                // Create container if it doesn't exist
                if (!window.readingTaskContainer) {
                    window.readingTaskContainer = document.createElement('div');
                    readingTaskContainer.id = 'reading-task-container';
                    readingTaskContainer.className = 'writing-task-container';
                    document.body.appendChild(readingTaskContainer);
                }

                // Update container content
                readingTaskContainer.innerHTML = `
                    <h2 style="font-size: 18px; margin-bottom: 10px;">Reading Task</h2>
                    <p style="font-size: 13px;">In this unit you must read the text and answer the questions. You have 10 minutes to complete.</p>
                    <button id="start-reading" class="ios-button">Start</button>
                    <div id="reading-timer" style="margin-top:10px; font-size: 16px;">10:00</div>
                    <div id="reading-content" class="reading-content" style="display:none;">
                        <div style="margin: 10px 0;">
                            <p>Otabek ertalab erta uyg'onib, maktabga borishga hozirlandi. U oldin tishini yuvdi, keyin esa nonushta qildi. Onasi unga choy va non berdi. Otabek maktabga piyoda bordi, chunki u maktabga juda yaqin yashaydi.</p>
                            <p>Maktabda Otabek matematika, ona tili va jismoniy tarbiya darslariga qatnashdi. Unga eng yoqadigan dars – matematika. O'qituvchisi unga qiyin misollar berdi, lekin Otabek ularni to'g'ri yechdi.</p>
                            <p>Darsdan keyin u do'stlari bilan futbol o'ynadi. Ular juda qiziqarli o'yin o'tkazishdi. Keyin u uyga qaytib, uy vazifalarini bajardi. Kechqurun esa oilasi bilan kechki ovqat yedi va ertangi kun uchun sumkasini tayyorladi.</p>
                        </div>
                        <div id="questions-container" class="reading-questions"></div>
                    </div>
                `;
                readingTaskContainer.style.display = 'flex';

                const readingQuestions = [
                    {
                        question: "1. Otabek ertalab birinchi bo'lib nima qildi?",
                        options: [
                            "A) Nonushta qildi",
                            "B) Tishini yuvdi", 
                            "C) Futbol o'ynadi",
                            "D) Uy vazifasini bajardi"
                        ],
                        correct: 1
                    },
                    {
                        question: "2. Otabek qanday transport vositasi bilan maktabga bordi?",
                        options: [
                            "A) Mashina",
                            "B) Velosiped",
                            "C) Piyoda",
                            "D) Avtobus"
                        ],
                        correct: 2
                    },
                    {
                        question: "3. Otabekning eng yoqadigan darsi qaysi?",
                        options: [
                            "A) Jismoniy tarbiya",
                            "B) Matematika",
                            "C) Ona tili",
                            "D) Ingliz tili"
                        ],
                        correct: 1
                    },
                    {
                        question: "4. Otabek maktabdan keyin nima qildi?",
                        options: [
                            "A) Kino ko'rdi",
                            "B) Bozorga bordi",
                            "C) Futbol o'ynadi",
                            "D) Do'stlari bilan kinoteatrga bordi"
                        ],
                        correct: 2
                    },
                    {
                        question: "5. Otabek kechqurun nima qildi?",
                        options: [
                            "A) Tez uxlab qoldi",
                            "B) Oilasi bilan ovqat yedi",
                            "C) O'yin o'ynadi",
                            "D) Do'stlari bilan sayr qildi"
                        ],
                        correct: 1
                    }
                ];

                let userAnswers = [];

                document.getElementById('start-reading').addEventListener('click', function() {
                    this.style.display = 'none';
                    document.getElementById('reading-content').style.display = 'block';
                    startTimer(10 * 60, document.getElementById('reading-timer'), finishReadingTest);
                    displayText(0); // Start with first text
                });

                let currentTextIndex = 0;
                const readingTexts = [
                    {
                        text: `<p>Otabek ertalab erta uyg'onib, maktabga borishga hozirlandi. U oldin tishini yuvdi, keyin esa nonushta qildi. Onasi unga choy va non berdi. Otabek maktabga piyoda bordi, chunki u maktabga juda yaqin yashaydi.</p>
                              <p>Maktabda Otabek matematika, ona tili va jismoniy tarbiya darslariga qatnashdi. Unga eng yoqadigan dars – matematika. O'qituvchisi unga qiyin misollar berdi, lekin Otabek ularni to'g'ri yechdi.</p>
                              <p>Darsdan keyin u do'stlari bilan futbol o'ynadi. Ular juda qiziqarli o'yin o'tkazishdi. Keyin u uyga qaytib, uy vazifalarini bajardi. Kechqurun esa oilasi bilan kechki ovqat yedi va ertangi kun uchun sumkasini tayyorladi.</p>`,
                        questions: [
                            {
                                question: "1. Otabek ertalab birinchi bo'lib nima qildi?",
                                options: ["Nonushta qildi", "Tishini yuvdi", "Futbol o'ynadi", "Uy vazifasini bajardi"],
                                correct: 1
                            },
                            {
                                question: "2. Otabek qanday transport vositasi bilan maktabga bordi?",
                                options: ["Mashina", "Velosiped", "Piyoda", "Avtobus"],
                                correct: 2
                            },
                            {
                                question: "3. Otabekning eng yoqadigan darsi qaysi?",
                                options: ["Jismoniy tarbiya", "Matematika", "Ona tili", "Ingliz tili"],
                                correct: 1
                            },
                            {
                                question: "4. Otabek maktabdan keyin nima qildi?",
                                options: ["Kino ko'rdi", "Bozorga bordi", "Futbol o'ynadi", "Do'stlari bilan kinoteatrga bordi"],
                                correct: 2
                            },
                            {
                                question: "5. Otabek kechqurun nima qildi?",
                                options: ["Tez uxlab qoldi", "Oilasi bilan ovqat yedi", "O'yin o'ynadi", "Do'stlari bilan sayr qildi"],
                                correct: 1
                            }
                        ]
                    },
                    {
                        text: `<p>Dilafruz yozgi ta'tilni buvisi va buvasining qishlog'ida o'tkazdi. U yerda havo juda toza va atrof yam-yashil edi. Har kuni erta tongda u buvisi bilan bog'ga chiqib, gullarga suv sepdi va sabzavotlarni parvarish qildi.</p>
                              <p>Buvisi unga qanday qilib pomidor va bodring ekish kerakligini o'rgatdi. Dilafruz har kuni sabzavotlarning qanday o'sayotganini kuzatib bordi. Buvi va buva har doim unga mehnatsevar bo'lish kerakligini uqtirishardi.</p>
                              <p>Kunduzi u qishloqdagi tengdoshlari bilan daryoga borib, u erda cho'mildi va baliq ovlashni o'rgandi. Kechqurun esa oilasi bilan o't o'chirib, choy ichib, buvasining qiziqarli hikoyalarini tingladi. Shu tariqa yozgi ta'til juda maroqli o'tdi.</p>`,
                        questions: [
                            {
                                question: "1. Dilafruz yozgi ta'tilni qayerda o'tkazdi?",
                                options: ["Shaharda", "Buvasi va buvisi bilan qishloqda", "Tog'larda", "Dengiz bo'yida"],
                                correct: 1
                            },
                            {
                                question: "2. Dilafruz bog'da nimalarga g'amxo'rlik qildi?",
                                options: ["Mevalarga", "Gullarga va sabzavotlarga", "Daraxtlarga", "G'o'zaga"],
                                correct: 1
                            },
                            {
                                question: "3. Buvisi Dilafruzga nimani o'rgatdi?",
                                options: ["Baliq ovlashni", "Pomidor va bodring ekishni", "O't yoqishni", "Non pishirishni"],
                                correct: 1
                            },
                            {
                                question: "4. Dilafruz kunduzi do'stlari bilan nima qildi?",
                                options: ["O'rmonga bordi", "Baliq ovladi va daryoda cho'mildi", "Kinoteatrga bordi", "Sport bilan shug'ullandi"],
                                correct: 1
                            },
                            {
                                question: "5. Kechqurun Dilafruz oilasi bilan nima qildi?",
                                options: ["Muzqaymoq yedi", "Futbol o'ynadi", "Buvasining hikoyalarini tingladi", "Rasm chizdi"],
                                correct: 2
                            }
                        ]
                    }
                ];

                function displayText(textIndex) {
                    const textContainer = document.getElementById('reading-content').getElementsByTagName('div')[0];
                    textContainer.innerHTML = readingTexts[textIndex].text;
                    displayQuestions(textIndex);
                }

                function displayQuestions(textIndex) {
                    const qContainer = document.getElementById('questions-container');
                    let questionsHtml = "";
                    readingTexts[textIndex].questions.forEach((q, qIndex) => {
                        questionsHtml += `
                            <div style="margin: 12px 0;">
                                <p style="margin-bottom: 8px;"><strong>${q.question}</strong></p>
                                ${q.options.map((opt, i) => `
                                    <label style="display: block; margin: 4px 0;">
                                        <input type="radio" name="question${qIndex}" value="${i}"> ${opt}
                                    </label>
                                `).join('')}
                            </div>
                        `;
                    });
                    
                    // Add navigation buttons based on current text
                    if (textIndex === 0) {
                        questionsHtml += `
                            <div style="margin-top: 15px;">
                                <button id="next-text" class="ios-button">Next Text</button>
                            </div>
                        `;
                    } else {
                        questionsHtml += `
                            <div style="margin-top: 15px;">
                                <button id="submit-reading" class="ios-button">Submit</button>
                            </div>
                        `;
                    }
                    
                    qContainer.innerHTML = questionsHtml;

                    // Add event listeners for navigation
                    if (textIndex === 0) {
                        document.getElementById('next-text').addEventListener('click', function() {
                            // Save answers from first text before moving to second
                            const answers = readingTexts[textIndex].questions.map((_, i) => {
                                const selected = document.querySelector(`input[name="question${i}"]:checked`);
                                return selected ? parseInt(selected.value) : -1;
                            });
                            
                            if (answers.includes(-1)) {
                                alert("Please answer all questions before proceeding to the next text.");
                                return;
                            }
                            
                            userAnswers = [...userAnswers, ...answers];
                            currentTextIndex++;
                            displayText(currentTextIndex);
                        });
                    } else {
                        document.getElementById('submit-reading').addEventListener('click', checkAnswers);
                    }
                }

                function checkAnswers() {
                    const answers = readingTexts[currentTextIndex].questions.map((_, i) => {
                        const selected = document.querySelector(`input[name="question${i}"]:checked`);
                        return selected ? parseInt(selected.value) : -1;
                    });
                    
                    if (answers.includes(-1)) {
                        alert("Please answer all questions.");
                        return;
                    }
                    
                    finishReadingTest(answers);
                }

                function finishReadingTest() {
                    let score = 0;
                    let feedback = '';
                    const allAnswers = [...userAnswers];
                    
                    // First text feedback
                    feedback += '<h3 style="margin: 15px 0 10px">First Text Results:</h3>';
                    readingTexts[0].questions.forEach((q, i) => {
                        const isCorrect = allAnswers[i] === q.correct;
                        score += isCorrect ? 1 : 0;
                        feedback += `
                            <div style="margin: 8px 0; padding: 8px; background: ${isCorrect ? '#e8f5e9' : '#ffebee'}; border-radius: 5px;">
                                <p style="margin: 0 0 5px"><strong>${q.question}</strong></p>
                                <p style="margin: 0; color: ${isCorrect ? '#2e7d32' : '#c62828'}">
                                    Your answer: ${q.options[allAnswers[i]]}<br>
                                    ${isCorrect ? '✓ Correct!' : `✗ Correct answer was: ${q.options[q.correct]}`}
                                </p>
                            </div>
                        `;
                    });

                    // Second text feedback
                    feedback += '<h3 style="margin: 15px 0 10px">Second Text Results:</h3>';
                    readingTexts[1].questions.forEach((q, i) => {
                        const answerIndex = i + readingTexts[0].questions.length;
                        const isCorrect = allAnswers[answerIndex] === q.correct;
                        score += isCorrect ? 1 : 0;
                        feedback += `
                            <div style="margin: 8px 0; padding: 8px; background: ${isCorrect ? '#e8f5e9' : '#ffebee'}; border-radius: 5px;">
                                <p style="margin: 0 0 5px"><strong>${q.question}</strong></p>
                                <p style="margin: 0; color: ${isCorrect ? '#2e7d32' : '#c62828'}">
                                    Your answer: ${q.options[allAnswers[answerIndex]]}<br>
                                    ${isCorrect ? '✓ Correct!' : `✗ Correct answer was: ${q.options[q.correct]}`}
                                </p>
                            </div>
                        `;
                    });

                    // Calculate final score and add motivational message
                    const finalScore = Math.round((score / (readingTexts[0].questions.length + readingTexts[1].questions.length)) * 10);
                    let motivation = '';
                    if (finalScore >= 8) {
                        motivation = "Excellent work! Your reading comprehension is outstanding! 🌟";
                    } else if (finalScore >= 6) {
                        motivation = "Good job! Keep practicing and you'll get even better! 💪";
                    } else {
                        motivation = "Don't give up! Every attempt helps you improve. Try reading more Uzbek texts daily! 📚";
                    }

                    finishedUnits['READING'] = finalScore;
                    updateScoreBoard();
                    
                    readingTaskContainer.innerHTML = `
                        <h2>Reading Evaluation</h2>
                        <p style="font-size: 18px; margin: 15px 0;">Your score: ${finalScore} / 10</p>
                        <p style="color: #1976d2; font-weight: bold; margin: 15px 0;">${motivation}</p>
                        <div style="max-height: 400px; overflow-y: auto; margin: 15px 0;">
                            ${feedback}
                        </div>
                        <button id="back-to-units-from-reading" class="ios-button" style="margin-top: 15px;">Back to Units</button>
                    `;

                    document.getElementById('back-to-units-from-reading').addEventListener('click', function(){
                        readingTaskContainer.style.display = 'none';
                        document.getElementById('units-container').style.display = 'flex';
                    });
                }
            });

            // Add this function to handle About Us button visibility
            function toggleAboutButton(show) {
                const aboutBtn = document.getElementById('about-us-btn');
                aboutBtn.style.display = show ? 'block' : 'none';
            }
        });
    </script>
</body>
</html>
