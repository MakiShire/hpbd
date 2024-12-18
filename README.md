<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Wishes</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f8ff;
            font-family: Arial, sans-serif;
        }
        #message {
            font-size: 24px;
            font-weight: bold;
            color: #333;
            white-space: nowrap; /* Prevent line breaks */
        }
        .word {
            display: inline-block;
            opacity: 0; /* Start hidden */
            transform: translateY(20px); /* Start slightly below */
            transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out; /* Transition for fade-in and slide-up effect */
            margin-left: 20px; /* Indent space between words */
        }
        .word.visible {
            opacity: 1; /* Fade in */
            transform: translateY(0); /* Slide up to original position */
        }
    </style>
</head>
<body>

<div id="message"></div>

<script>
    const message = "Happy birthday, THT, sorry for late wishes";
    const words = message.split(" ");
    let wordIndex = 0;

    function displayNextWord() {
        if (wordIndex < words.length) {
            const messageElement = document.getElementById("message");
            const span = document.createElement("span");
            span.textContent = words[wordIndex];
            span.className = "word"; // Add class for styling
            messageElement.appendChild(span);

            // Trigger the fade-in and slide-up effect
            setTimeout(() => {
                span.classList.add("visible"); // Add visible class to trigger animation
            }, 50); // Small delay to ensure the opacity change is visible

            wordIndex++;
            setTimeout(displayNextWord, 1000); // Display next word after 1 second
        }
    }

    displayNextWord();
</script>

</body>
</html>
