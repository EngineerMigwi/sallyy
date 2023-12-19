<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Add Bootstrap CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #343a40; /* Dark background color */
      overflow: hidden; /* Prevents horizontal scrollbar */
      animation: backgroundAnimation 30s infinite linear; /* Background animation */
      color: #ffffff; /* White text color */
    }

    @keyframes backgroundAnimation {
      0% {
        background-position: 0 0;
      }
      100% {
        background-position: 100% 0;
      }
    }

    .container {
      max-width: 90%;
      margin: auto;
      background-color: #2c3e50; /* Darker container background color */
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Subtle box shadow */
      margin-top: 20px;
    }

    h1 {
      color: #ff69b4; /* Pink text color */
      font-size: 24px;
    }

    p {
      font-size: 16px;
      color: #ecf0f1; /* Light gray text color */
    }

    button {
      margin: 10px;
      padding: 15px 30px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      width: 100%;
    }

    #yesButton {
      background-color: #27ae60; /* Dark green button color */
      color: white;
    }

    #noButton {
      background-color: #e74c3c; /* Red button color */
      color: white;
    }

    #noButton:hover {
      margin-left: 0; /* Reset margin on hover */
    }

    .love-emojis {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none; /* Allows clicks to go through the emojis to underlying elements */
      z-index: -1; /* Places the emojis behind other elements */
    }

    .love-emojis span {
      position: absolute;
      display: inline-block;
      font-size: 20px;
      opacity: 0.5;
      transform: rotate(45deg);
      color: #ff69b4; /* Pink color */
      animation: floatAnimation 10s infinite linear;
    }

    @keyframes floatAnimation {
      0% {
        transform: translateY(0) rotate(45deg);
      }
      50% {
        transform: translateY(-30px) rotate(45deg);
      }
      100% {
        transform: translateY(0) rotate(45deg);
      }
    }
  </style>
  <title>Sally💓💓</title>
</head>
<body>
  <div class="container">
    <h1 class="mt-4">Will you be my special someone?</h1>
    <p>Dear sally💓,</p>
    <p>From the moment we first met, Sally, you became my sweet obsession. Your smile and laughter captivated me, driving my heart into a delightful madness that persists every day.
        I love you sally💓</p>
    <button id="yesButton" class="btn btn-success" onclick="getResponse('Yes')">Yes, I'd love to!</button>
    <button id="noButton" class="btn btn-danger" onclick="shiftButton()">No, thank you</button>
  </div>

  <!-- Love Emojis -->
  <div class="love-emojis" id="loveEmojisContainer"></div>

  <!-- Add Bootstrap JS and Popper.js (required for Bootstrap) -->
  <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.10.2/dist/umd/popper.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"></script>

  <script>
    let userResponse;

    function getResponse(response) {
      userResponse = response;
      if (response === 'Yes') {
        confirmProposal(response);
      } else {
        shiftButton();
      }
    }

    function confirmProposal(response) {
      alert(`Yey!! Thankyou,Love you💓.Then msg me 'yes'`);
      // You can perform further actions based on the user's response here
    }

    function shiftButton() {
        
    const noButton = document.getElementById('noButton');
    const windowWidth = window.innerWidth - noButton.clientWidth;
    const windowHeight = window.innerHeight - noButton.clientHeight;

    const randomX = Math.floor(Math.random() * windowWidth);
    const randomY = Math.floor(Math.random() * windowHeight);

    noButton.style.position = 'absolute';
    noButton.style.left = randomX + 'px';
    noButton.style.top = randomY + 'px';
    }

    // Function to generate and position love emojis dynamically
    function generateLoveEmojis() {
      const loveEmojisContainer = document.getElementById('loveEmojisContainer');
      const windowWidth = window.innerWidth;
      const windowHeight = window.innerHeight;

      for (let i = 0; i < 30; i++) {
        const emoji = document.createElement('span');
        emoji.innerHTML = '❤️'; // You can customize the emoji
        emoji.style.top = Math.random() * windowHeight + 'px';
        emoji.style.left = Math.random() * windowWidth + 'px';
        loveEmojisContainer.appendChild(emoji);
      }
    }

    // Generate love emojis when the page loads
    window.onload = generateLoveEmojis;
  </script>
</body>
</html>

