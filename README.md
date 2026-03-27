**🎬 Subtitle Translator using API**

A powerful and user-friendly Subtitle Translator that automatically translates subtitle files (like .srt) into different languages using external translation APIs. This project simplifies multilingual content accessibility and enhances global reach.

**📌 Table of Contents
Introduction
Features
Tech Stack
How It Works
Installation
Usage
API Integration
Project Structure
Example
Future Improvements
Contributing
License**

**📖 Introduction**

This project is designed to translate subtitle files automatically using APIs. It reads subtitle files, processes the text, sends it to a translation API, and generates a translated subtitle file while preserving timestamps.

**✨ Features**
🌍 Translate subtitles into multiple languages
📄 Supports .srt subtitle format
⏱ Preserves original timestamps
⚡ Fast API-based translation
🧠 Clean and readable output
💻 Easy-to-use interface (CLI or GUI based on your version)

**🛠 Tech Stack**
Programming Language: Python
Libraries Used:
requests (API calls)
pysrt or srt (subtitle parsing)
API Used:
Google Translate API / LibreTranslate API / DeepL API


**⚙️ How It Works**
Load the subtitle file (.srt)
Parse subtitle text and timestamps
Send text to translation API
Receive translated text
Replace original text with translated text
Save new translated subtitle file


**🔧 Installation**
1. Clone the repository
git clone https://github.com/your-username/subtitle-translator.git
cd subtitle-translator
2. Install dependencies
pip install -r requirements.txt


**🚀 Usage**
Run the script
python translator.py
Example input
Enter file name: sample.srt
Enter target language: hi
Output
translated_sample.srt


**🔌 API Integration**

This project uses translation APIs to perform language conversion.

Example (LibreTranslate API)
import requests

url = "https://libretranslate.com/translate"

payload = {
    "q": "Hello world",
    "source": "en",
    "target": "hi",
    "format": "text"
}

response = requests.post(url, data=payload)
print(response.json())


**📂 Project Structure**
subtitle-translator/
│── translator.py
│── requirements.txt
│── sample.srt
│── translated_sample.srt
│── README.md

📌 Example
Input Subtitle
1
00:00:01,000 --> 00:00:03,000
Hello, how are you?

Output Subtitle
1
00:00:01,000 --> 00:00:03,000
नमस्ते, आप कैसे हैं?


**🚧 Future Improvements**

🎯 Add GUI using Tkinter or React
🌐 Support more subtitle formats (.vtt)
🔊 Add speech-to-text integration
📊 Batch file translation
🧾 Auto language detection
🤝 Contributing

**Contributions are welcome!**

Fork the repo
Create a new branch
Commit your changes
Push and create a Pull Request


**📜 License**

This project is licensed under the MIT License.
