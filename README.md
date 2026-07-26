# Operation Christmas Child Inventory Manager

Version **1.4.3**

A Windows desktop application for tracking donated Operation Christmas Child supplies.

## Features

- Dashboard with inventory totals and low-stock alerts
- Item, category, and subcategory management
- Search, filtering, duplicate detection, and quantity history
- CSV and XLSX import
- CSV and PDF reports
- SQLite database backup
- Windows installer and dedicated uninstall executable

## Development requirements

- Windows 10 or Windows 11
- Python 3.11 or newer
- Internet access when Python packages or the private Inno Setup compiler must be downloaded

A separate Inno Setup installation is not required.

## Run in development mode

Double-click `run_dev.bat`, or install `requirements.txt` and run `main.py`.

## Build

Double-click `build.bat`, choose an output folder, and select **Build Application and Installer**.

The builder creates:

- `OCC Inventory Manager.exe`
- `uninstall.exe`
- `OCC_Inventory_Manager_Setup.exe`

When no usable compiler is available, the builder downloads and prepares a private Inno Setup compiler under `tools\inno`.

## Database and uninstall behavior

The live SQLite database is stored in the current Windows user's LocalAppData application folder. Version 1.4.3 uninstall removes both the program and this local application-data folder after a permanent-deletion confirmation. Create an external backup before uninstalling when the data may be needed.

## Documentation

Detailed documentation is included under `docs`:

- Administrator Guide
- Installation Guide
- Quick Start
- User Guide
- Build Guide
- Troubleshooting
- Release Notes

## License

GNU General Public License v3.0 or later. See `LICENSE`.
