# Marks Mitra Over-The-Air (OTA) Updates Repository Guide

This folder demonstrates the exact structure to maintain in your GitHub repository:
`https://github.com/backendworkspacee/OverAirUpdates.git`

---

## 📁 Repository Structure on GitHub

```text
OverAirUpdates/
├── README.md
└── Marks Mitra/
    └── vHistory.tsv
```

---

## 📄 `Marks Mitra/vHistory.tsv` File Format

`vHistory.tsv` is a **Tab-Separated Values (TSV)** file. 
Column names (Row 1):
`version_code	version_name	release_notes	apk_download_url	size_formatted	mandatory	release_date`

### Example Row for Version 1.0.1:
```tsv
version_code	version_name	release_notes	apk_download_url	size_formatted	mandatory	release_date
2	1.0.1	• Fixed dark mode transition\n• Improved exam card loading speed\n• Added notification sync reliability	https://github.com/backendworkspacee/OverAirUpdates/releases/download/v1.0.1/marksmitra-v1.0.1.apk	19.2 MB	false	2026-11-10
```

> **Important**:
> - Columns are separated by **TAB characters** (`\t`), not spaces.
> - Multi-line release notes can use `\n` which will be automatically rendered as line breaks in the update dialog.
> - `mandatory`: set to `true` if you want to require users to update before continuing, or `false` to let them dismiss the dialog.
> - `version_code`: Always an increasing integer (`1`, `2`, `3`...). When this is greater than the app's current version code (`CURRENT_VERSION_CODE = 1`), the app automatically notifies the user.

---

## 🚀 How to Publish an Update:

1. Create a new Release in your GitHub repo: `https://github.com/backendworkspacee/OverAirUpdates/releases/new`
2. Set Tag name (e.g. `v1.0.1`).
3. Upload your built `.apk` file into the GitHub Release assets.
4. Copy the direct download link of the uploaded APK file.
5. In your repo's `Marks Mitra/vHistory.tsv` file, add a new row with:
   - `version_code`: `2` (or incremented number)
   - `version_name`: `1.0.1`
   - `release_notes`: What's new in this release
   - `apk_download_url`: The direct link to your GitHub release APK
   - `size_formatted`: e.g. `19.5 MB`
   - `mandatory`: `false`
   - `release_date`: `2026-11-10`
6. Commit & Push to `main`.
7. All installed Marks Mitra user apps will instantly detect the new update on next launch or when checked in Settings!

