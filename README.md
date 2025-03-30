#📷 Photo Web Interface
#A Raspberry Pi-powered web interface for capturing, viewing, and managing photos taken with a Canon EOS 400D. It includes remote capture, albums, sharing options, and system monitoring (temperature, storage, etc.).



🚀 Features
✅ Capture photos remotely via a web interface or camera button
✅ View, organize, and share photos in an album-style layout
✅ Swipe through photos like in the Apple Photos app
✅ Monitor temperature, storage, and system stats
✅ Portable mode: works without Wi-Fi using a Raspberry Pi hotspot
✅ Automatic startup when powered on

🛠️ Installation
1. Install Dependencies
Run the following on your Raspberry Pi:

bash
Copy
Edit
sudo apt update && sudo apt upgrade -y
sudo apt install python3 python3-pip git flask gphoto2 -y
Then install Flask dependencies:

bash
Copy
Edit
pip install flask flask-socketio
2. Clone the Repository
bash
Copy
Edit
git clone https://github.com/YourGitHubUsername/photo-web-interface.git
cd photo-web-interface
3. Start the Web Interface
bash
Copy
Edit
python3 app.py
Now, open your browser and go to:
📍 http://your-pi-ip:5000

📡 Wi-Fi Hotspot Mode (Portable Mode)
If you want to access the web interface anywhere without an internet connection:

Set up your Raspberry Pi as a Wi-Fi hotspot

Connect your phone or laptop to the Pi’s Wi-Fi

Open http://192.168.4.1:5000 in your browser

🔄 Auto-Start on Boot
Make the web app start automatically when the Pi is powered on:

bash
Copy
Edit
sudo nano /etc/rc.local
Before exit 0, add this line:

bash
Copy
Edit
python3 /home/pi/photo-web-interface/app.py &
Save and exit (CTRL + X, then Y, then Enter).

🔧 Troubleshooting
Photos not saving? Ensure the /home/pi/photos directory exists:

bash
Copy
Edit
mkdir -p /home/pi/photos
Flask app not starting? Check if port 5000 is in use:

bash
Copy
Edit
sudo lsof -i :5000
sudo kill -9 <PID>
(Replace <PID> with the process ID.)

🤝 Contributing
Pull requests are welcome! Feel free to fork the repo and submit improvements.

📜 License
This project is open-source under the MIT License.

