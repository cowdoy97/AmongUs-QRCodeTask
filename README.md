Among Us IRL - Verification Terminal
This is a simple, self-contained web application designed for "Among Us IRL" games. It simulates a crewmate verification task by scanning a QR code, capturing a face photo, and displaying an "Approved" message, complete with thematic sounds.
The entire application runs locally in a web browser and requires no internet connection after the initial setup.
(Feel free to replace this placeholder image with a screenshot or GIF of your own!)
Features
Live QR Code Scanning: Uses a device's webcam to scan a player's unique QR code.
Player Name Display: Shows the name of the crewmate decoded from the QR code.
Automatic Face Photo: Simulates a face scan by capturing a frame from the webcam.
Thematic "Processing" Step: A 10-second processing animation with a looping sound effect.
"Approved" Notification: A final approval screen with a confirmation sound.
Automatic Reset: After 15 seconds, the page automatically refreshes, making it ready for the next player.
File Structure
Your project folder should be set up as follows:
code
Code
/verification-terminal
|-- index.html          (The main HTML structure)
|-- style.css           (All styling rules)
|-- script.js           (The application logic and flow)
|-- html5-qrcode.min.js (The local QR code scanning library)
|-- /media
    |-- verifying.m4a   (The looping processing sound effect)
    |-- approved.m4a    (The final approval sound effect)
|-- README.md           (This file)
Setup and Installation
To get this terminal running on your machine, follow these steps.
1. Player QR Codes
Each player will need a unique QR code that contains their name.
Use any free online QR code generator (like The QR Code Generator).
Create a "Text" QR code from each player's name (e.g., "Red", "BlueSus", "Green").
Print these QR codes out for players to use during the game.
2. Sound Files
This project expects two sound files.
Place your looping "verifying" sound effect in the /media folder and name it verifying.m4a.
Place your "approved" sound effect in the /media folder and name it approved.m4a.
(You can use other formats like .mp3, but you will need to update the filenames in index.html).
3. Run a Local Server
For security reasons, modern web browsers will not allow camera access for files opened directly from your computer (i.e., file:///...). You must serve the files from a local server. The easiest way to do this is with Python.
Open a command prompt or terminal in the root directory of the project (the folder containing index.html).
Run the following command:
code
Bash
python -m http.server
(If that doesn't work, you might need to use python3 -m http.server or py -m http.server).
The terminal will show a message like Serving HTTP on 0.0.0.0 port 8000 ....
Usage
With the local server running, open your web browser (Chrome, Firefox, etc.).
Navigate to the address: http://localhost:8000
The "Verification Terminal" screen will appear. Click the "Begin Scan" button.
The browser will ask for permission to use your camera. You must click "Allow".
A live video feed will appear. Hold a player's QR code up to the camera so it is inside the blue guide box.
The application will automatically proceed through the verification steps.
After approval, the page will automatically refresh for the next player.
Customization
You can easily change the timings and sounds to fit your game's theme.
Sounds: To change the sound effects, simply replace the audio files in the /media folder. If you change the filenames, make sure to update the <audio> tags in index.html.
Timings: All timings are controlled by setTimeout functions in script.js. You can change the duration for the "processing" step or the "reset" countdown by modifying the number values (in milliseconds) in these functions.
