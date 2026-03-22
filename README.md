# MASTER File Converter

A web-based file conversion application built with Flask that lets you convert files between a wide variety of audio, image, and document formats — all from your browser.

---

## Features

- 🎵 **Audio conversion** — convert between WAV, MP3, OGG, FLAC, AAC, and M4A
- 🖼️ **Image conversion** — convert between PNG, JPG/JPEG, GIF, and WebP
- 📄 **Document conversion** — convert between PDF, DOCX, TXT, Markdown, and HTML
- 🖱️ **Drag-and-drop upload** with real-time format selection
- 👤 **User authentication** — register and log in to access the converter
- 🔒 **Secure passwords** — bcrypt hashing via Flask-Bcrypt

---

## Supported Conversions

| Category  | Supported Formats                          |
|-----------|--------------------------------------------|
| Audio     | WAV, MP3, OGG, FLAC, AAC, M4A             |
| Image     | PNG, JPG, JPEG, GIF, WebP                 |
| Document  | PDF, DOCX, TXT, Markdown (`.md`), HTML    |

---

## Prerequisites

- Python 3.8+
- [FFmpeg](https://ffmpeg.org/) — required for audio conversion (a static binary is included in `ffmpeg-static/` for Linux and Windows)
- `wkhtmltopdf` — required for HTML → PDF conversion ([download here](https://wkhtmltopdf.org/downloads.html))

---

## Installation

```bash
# 1. Clone the repository
git clone https://github.com/Atx-Guy/MASTER-file-converter.git
cd MASTER-file-converter

# 2. Create and activate a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r modules.txt

# 4. Initialize the database
python init_db.py
```

---

## Running the App

```bash
python app.py
```

Then open [http://localhost:5000](http://localhost:5000) in your browser.

> **Note:** The app runs in debug mode by default. Before deploying to production, set a strong `SECRET_KEY` via an environment variable and disable debug mode.

---

## Usage

1. **Sign up** for an account or **log in** if you already have one.
2. On the main page, drag and drop a file (or click to browse) onto the upload area.
3. Select the desired **output format** from the dropdown (options are filtered to match the type of file you uploaded).
4. Optionally enter a custom output filename.
5. Click **Convert** and the converted file will download automatically.

---

## Project Structure

```
MASTER-file-converter/
├── app.py                  # Flask application and routes
├── audio_converter.py      # FFmpeg wrapper for audio conversion
├── models.py               # SQLAlchemy User model
├── init_db.py              # Database initialization script
├── config.py               # App configuration
├── modules.txt             # Python dependencies
├── ffmpeg-static/          # Bundled FFmpeg binaries
│   ├── ffmpeg              # Linux/macOS binary
│   └── ffmpeg.exe          # Windows binary
├── instance/
│   └── users.db            # SQLite user database (auto-created)
├── static/
│   ├── css/styles.css      # Application styles
│   ├── js/file-upload.js   # Client-side upload and conversion logic
│   └── img/                # Logo and other images
├── templates/
│   ├── index.html          # Main converter page
│   ├── login.html          # Login page
│   └── signup.html         # Sign-up page
└── temp/                   # Temporary storage for in-progress conversions
```

---

## Tech Stack

| Layer    | Technology                                                     |
|----------|----------------------------------------------------------------|
| Backend  | Python, Flask, Flask-SQLAlchemy, Flask-Login, Flask-Bcrypt     |
| Frontend | HTML5, CSS3, JavaScript, Bootstrap 5                           |
| Audio    | FFmpeg                                                         |
| Images   | Pillow (PIL)                                                   |
| Documents| PyPDF2, python-docx, pdfkit, pdf2docx, docx2pdf, markdown2    |
| Database | SQLite                                                         |

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## License

This project does not currently include a license file. Please contact the repository owner for usage terms.
