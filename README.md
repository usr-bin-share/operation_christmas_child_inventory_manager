# Operation Christmas Child Inventory Manager

A modern Windows desktop application for tracking donated Operation Christmas Child supplies.

## Included features

- Modern Windows-style PySide6 interface
- Dashboard with inventory totals and low-stock alerts
- Add, edit, delete, search, and filter inventory
- Category and sub-category management
- Duplicate item detection
- Quantity adjustment history
- CSV and XLSX import with flexible header recognition
- Full-inventory and low-stock reports
- CSV and PDF export
- SQLite database backup
- Safe database storage under Windows Local AppData
- PyInstaller build script
- Inno Setup installer script
- GPL-3.0-or-later licensing

## Requirements

- Windows 10 or Windows 11
- Python 3.11 or newer for development
- Inno Setup only if you want to build the installer

## Run in development mode

Double-click:

```text
run_dev.bat
```

Or use PowerShell:

```powershell
py -m venv .venv
.venv\Scripts\activate
py -m pip install -r requirements.txt
py main.py
```

## Build the Windows application


### First builder launch

The first time `build.bat` is opened, it creates a small private builder
environment and installs PySide6. This may take a moment and requires an
internet connection. Later launches open directly.

If startup fails, a Windows error dialog is displayed instead of silently
closing.


Double-click:

```text
build.bat
```

The standalone program will be created directly in the project folder at:

```text
OCC Inventory Manager.exe
```

## Build the installer

1. Install Inno Setup.
2. Build the app with `build.bat`.
3. Open `installer\OCC_Inventory_Manager.iss`.
4. Click **Compile**.

The installer will be created in:

```text
installer\Output\
```

## Database location

The live database is stored at:

```text
%LOCALAPPDATA%\usr-bin-share\OCC Inventory Manager\occ_inventory.db
```

This keeps the data writable and separate from the installed program files.

## Excel/CSV import columns

The importer recognizes common variants of:

- Name
- Category
- Subcategory
- Quantity
- Minimum
- Age Group
- Gender
- Notes

It also scans the first 20 rows to locate the header row.

## Author

Created by **usr-bin-share**.

## License

GNU General Public License v3.0 or later.


## Uninstalling

When installed with the Inno Setup installer, the application can be removed through:

- Windows **Settings → Apps → Installed apps**
- The **Uninstall OCC Inventory Manager** Start Menu shortcut
- `unins000.exe` inside the installation folder

Uninstalling the program does not automatically delete the inventory database stored in Local AppData. This protects user data during upgrades or accidental removal.
