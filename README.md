# ANT Hospital Management System

A console-based Hospital Management System written in C++ for Windows. It lets hospital staff manage doctor records, patient records, and bed availability through a simple menu-driven interface, with a password-protected entry point.

## Features

- **Login/Intro screen** with a stylized ASCII banner and password protection before accessing sensitive modules.
- **Doctor Database**
  - Add a new doctor profile (ID, name, age, qualification, specialization, experience, city)
  - Edit an existing doctor's record
  - Display a single doctor's record by ID
  - Delete a doctor's record
  - Display the entire doctor database
  - View the total number of doctors
- **Patient Database**
  - Add a new patient profile (ID, name, age, phone number, occupation, city, disease/symptoms, admission/release dates, bill, required specialization)
  - Edit an existing patient's record
  - Display a single patient's record by ID
  - Delete a patient's record
  - Display the entire patient database
  - View the total number of patients
  - Check doctor availability by specialization
- **Bed Database**
  - Track total, occupied, and available hospital beds based on current patient records

## How It Works

Data is stored and persisted using flat text files:
- `doctor.txt` — stores all doctor records
- `patient.txt` — stores all patient records

Records are read/written using simple whitespace-delimited I/O (`ifstream`/`ofstream`/`fstream`). Edit and delete operations work by rewriting the file to a temporary file (`copy.txt`) and renaming it back.

## Requirements

- Windows OS (the program uses `windows.h`, `system("cls")`, and `system("color ...")`, which are Windows-specific)
- A C++ compiler that supports these Windows headers (e.g., MinGW or MSVC)

## Building

Using g++ (MinGW) on Windows:

```bash
g++ main.cpp -o HospitalManagementSystem.exe
```

Then run:

```bash
HospitalManagementSystem.exe
```

## Usage

1. Run the executable.
2. Press Enter through the intro screen.
3. Set a password when prompted (this is used for the current session).
4. Choose **1. Main Menu** to proceed.
5. Select a module: Doctors' Database, Patients' Database, or Bed Availability.
6. Re-enter the password when prompted to access a module.
7. Follow the on-screen numbered options to add, edit, view, or delete records.

> Note: The password is set fresh each time the program runs (it is not persisted between sessions).

## Project Structure

```
.
├── main.cpp        # Source code (all classes and logic)
├── doctor.txt      # Doctor records (auto-created/updated at runtime)
├── patient.txt     # Patient records (auto-created/updated at runtime)
└── README.md
```

