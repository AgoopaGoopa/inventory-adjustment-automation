
# Inventory Adjustment Automation

## Overview
This Python script automates the daily generation of inventory adjustment reports by extracting, processing, and exporting data from a SQL Server-based warehouse management system (WMS). It merges ledger activity, adjustment headers, and reason code mappings to produce clean, client-specific Excel reports ready for operational and audit use.

## Key Features
- Connects to a SQL Server WMS database using `pyodbc`
- Joins data from multiple tables including adjustment headers, ledger entries, and reason codes
- Filters out non-relevant entries (e.g., RTS returns, zero-quantity adjustments)
- Segments final output by client code, either provided or auto-detected
- Automatically fetches distinct client codes from the database if none are provided

## Technologies Used
- Python 3.x
- Pandas
- NumPy
- PyODBC
- OpenPyXL / XlsxWriter (via `pandas.to_excel()`)

## Setup Instructions
1. Clone this repository:
```bash
git clone https://github.com/your-username/inventory-adjustment-automation.git
```

2. Install the required dependencies:
```bash
pip install pandas numpy pyodbc openpyxl
```

3. Update the database connection string and output file paths in the script to match your environment.

4. Run the script with optional client filtering:
```bash
python inventory_adjustment_report.py
```

Or specify client codes manually:
```bash
python inventory_adjustment_report.py --clients GRL MRA KAV
```

## Example Output
The script produces a separate Excel report for each client, containing validated adjustment data ready for operational and finance use.

## License
This project is licensed under the MIT License.

## Disclaimer
All database names, paths, and sample outputs have been anonymized to protect proprietary information. This script is intended for educational and demonstration purposes.
