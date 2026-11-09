# Marks Mitra Over-The-Air (OTA) Updates Repository

All APKs (for Android) and .exe installers (for Windows) are stored directly inside the `Marks Mitra/` folder in this repository.

---

## 📁 Repository Structure

`	ext
OverAirUpdates/
├── README.md
└── Marks Mitra/
    ├── vHistory.tsv
    ├── MarksMitra-v1.0.0.apk
    ├── MarksMitra-v1.0.0.exe
    ├── MarksMitra-v1.0.1.apk
    └── MarksMitra-v1.0.1.exe
`

---

## 📄 Marks Mitra/vHistory.tsv Schema

Columns are **Tab-separated (\t)**:
`version_code	version_name	release_notes	apk_download_url	exe_download_url	size_formatted	mandatory	release_date`

### Direct Raw URLs for Files Stored in this Folder:
- **APK URL**: https://raw.githubusercontent.com/backendworkspacee/OverAirUpdates/main/Marks%20Mitra/<FILENAME>.apk
- **EXE URL**: https://raw.githubusercontent.com/backendworkspacee/OverAirUpdates/main/Marks%20Mitra/<FILENAME>.exe

### Example Row (v1.0.1):
`	sv
2	1.0.1	• Fixed dark mode transition\n• Improved exam card loading speed\n• Added notification sync reliability	https://raw.githubusercontent.com/backendworkspacee/OverAirUpdates/main/Marks%20Mitra/MarksMitra-v1.0.1.apk	https://raw.githubusercontent.com/backendworkspacee/OverAirUpdates/main/Marks%20Mitra/MarksMitra-v1.0.1.exe	19.2 MB	false	2026-11-10
`

---

## 🚀 How to Add a New App Update:

1. Build your new release file:
   - For Android APK: .\gradlew :Global:user-app:assembleRelease
   - For Windows .exe: .\gradlew :Global:user-app:packageReleaseExe
2. Name the files (e.g., MarksMitra-v1.0.1.apk, MarksMitra-v1.0.1.exe).
3. Place them directly inside the Marks Mitra/ folder in this repository.
4. Add a new row in Marks Mitra/vHistory.tsv with:
   - ersion_code (e.g. 2)
   - ersion_name (e.g. 1.0.1)
   - elease_notes (use \n for line breaks)
   - pk_download_url (https://raw.githubusercontent.com/backendworkspacee/OverAirUpdates/main/Marks%20Mitra/MarksMitra-v1.0.1.apk)
   - exe_download_url (https://raw.githubusercontent.com/backendworkspacee/OverAirUpdates/main/Marks%20Mitra/MarksMitra-v1.0.1.exe)
   - size_formatted (e.g. 19.2 MB)
   - mandatory (alse or 	rue)
   - elease_date (2026-11-10)
5. Commit & Push to GitHub.
