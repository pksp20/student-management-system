# ScholarTrack Student Management System

**ScholarTrack** is a mini project web application for managing student records. It uses **Python Flask** for the web server, **SQLite** for data storage, and **HTML/CSS** for the interface.

## Features

- Add, view, search, edit, and delete student records
- Search by student name, roll number, or class
- Show total students and average marks
- Validate required fields, unique roll numbers, contact numbers, and marks from 0 to 100
- Create the SQLite database automatically when the app starts

## Requirements

- Windows 10 or 11
- Python 3.9 or newer
- Internet connection for the first Flask installation

## Run the app on Windows

1. Download or clone this project and extract it if it is a ZIP file.
2. In File Explorer, open the `student-management-system` folder. It must contain `app.py` and `requirements.txt`.
3. Click the File Explorer address bar, type `powershell`, and press Enter. PowerShell will open in the project folder.
4. Create a virtual environment:

   ```powershell
   py -m venv .venv
   ```

5. Install Flask into that environment:

   ```powershell
   .\.venv\Scripts\python.exe -m pip install -r requirements.txt
   ```

6. Start the application:

   ```powershell
   .\.venv\Scripts\python.exe app.py
   ```

7. Open <http://127.0.0.1:5000> in a web browser. Keep the PowerShell window open while using the app. Press **Ctrl+C** in that window to stop it.

These instructions call the virtual environment's Python directly, so you do not need to run `Activate.ps1`.

### If PowerShell opens in the wrong folder

Use `Set-Location` with the path to the extracted project folder. For example:

```powershell
Set-Location "C:\path\to\student-management-system"
Get-ChildItem
```

Confirm the file list includes `app.py` and `requirements.txt` before continuing with the setup commands above. Replace the example path with the location where you extracted the project.

### If `py` is not recognized

Use `python` instead. For example:

```powershell
python -m venv .venv
```

Then continue with the `.venv\Scripts\python.exe` commands.

## Database

The app uses SQLite. On first start, it creates `students.db` in the project folder, including a `students` table. The database file is local runtime data and is excluded from Git by `.gitignore`; each person running the project gets their own database.

## Project files

```text
student-management-system/
├── app.py                 # Flask routes, validation, and database operations
├── requirements.txt       # Python dependencies
├── PROJECT_REPORT.md      # Mini project report template
├── README.md              # Setup and project guide
├── static/
│   └── style.css          # Interface styling
└── templates/
    ├── form.html          # Add and edit student form
    └── index.html         # Student list and search page
```

## Main routes

| URL | Purpose |
|---|---|
| `/` | View and search student records |
| `/students/new` | Add a student |
| `/students/<id>/edit` | Edit a student |
| `/students/<id>/delete` | Delete a student using a POST request |
| `/health` | Return a basic application health response |

## Uploading to GitHub

Include `app.py`, `requirements.txt`, `README.md`, `PROJECT_REPORT.md`, `.gitignore`, `static/`, and `templates/`. Do not upload `.venv/`, `students.db`, or `__pycache__/`.

## Before submitting

- Fill in your name, roll number, class, institution, and submission date in `PROJECT_REPORT.md`.
- Run the app and demonstrate adding, searching, editing, and deleting a record.
- The built-in Flask development server is for local classroom demonstration, not public production hosting.
