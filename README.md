# GAME
This is my second Git Repository
<br>
Author-Muskan Kumari


<html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guess the Number Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }

        #output {
            font-size: 18px;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h1>Guess the Number Game</h1>
    <p>Guess a number between 1 and 10:</p>

    <input type="text" id="guessInput">
    <button onclick="checkGuess()">Submit Guess</button>

    <p id="output"></p>

    <script>
        // Generate a random number between 1 and 10
        const secretNumber = Math.floor(Math.random() * 10) + 1;
        let attempts = 0;

        function checkGuess() {
            const guess = document.getElementById('guessInput').value;

            if (isNaN(guess) || guess < 1 || guess > 10) {
                alert('Please enter a valid number between 1 and 10.');
                return;
            }

            attempts++;

            if (parseInt(guess) === secretNumber) {
                document.getElementById('output').innerHTML = `Congratulations! You guessed the number ${secretNumber} in ${attempts} attempts.`;
                document.getElementById('output').style.color = 'green';
                document.getElementById('guessInput').setAttribute('disabled', 'true');
            } else {
                document.getElementById('output').innerHTML = `Wrong guess. Try again!`;
                document.getElementById('output').style.color = 'red';
            }
        }
    </script>

</body>
</html>
