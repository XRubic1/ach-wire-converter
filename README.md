# ACH & Wire File Converter

A web-based tool to convert NACHA ACH TXT files and Wire TXT files to CSV format for bank import.

## Features

- **ACH File Conversion**: Converts NACHA ACH TXT files to CSV format
- **Wire File Conversion**: Converts Wire TXT files to CSV format with email notification support
- **Email Matching**: Automatically matches beneficiary names with email addresses from Notification.csv
- **Modern UI**: Clean, responsive interface built with Tailwind CSS

## How to Use

### Option 1: Using a Web Server (Recommended)

1. **Start a local web server** in the project directory:
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Or using Node.js (if you have http-server installed)
   npx http-server -p 8000
   ```

2. **Open your browser** and navigate to:
   ```
   http://localhost:8000
   ```

3. **Upload files**:
   - (Optional) Upload `Notification.csv` for email matching in Wire files
   - Upload your ACH or Wire TXT file (must start with `ACH_` or `WIRE_`)
   - Click "Convert to CSV"
   - Download the generated CSV file

### Option 2: Direct File Access

1. **Open `index.html`** directly in your browser
2. **Upload Notification.csv** using the file input (required for email matching)
3. **Upload your ACH or Wire TXT file**
4. **Convert and download**

> **Note**: When opening directly, you must upload Notification.csv manually as the browser's security prevents loading it automatically.

## File Formats

### ACH Files
- Must start with `ACH_` in the filename
- Format: Standard NACHA ACH TXT format

### Wire Files
- Must start with `WIRE_` in the filename
- Format: Comma-separated values with the following fields:
  - Field 0: Debit Account
  - Field 1: Currency
  - Field 2: Debit Bank ID
  - Field 3: Date (MMDDYY format)
  - Field 4: Amount
  - Field 5: Purpose or Intent
  - Field 6: Beneficiary Account Number
  - Field 7: Beneficiary Name (used as Client Name)
  - Field 8: Instruction Code
  - Field 9: Beneficiary Bank ID

### Notification.csv Format

For Wire files, you can provide a `Notification.csv` file to match beneficiary names with email addresses:

```csv
Beneficiary Name,Beneficiary Notification Email Address 1,Beneficiary Notification Email Address 2,Beneficiary Notification Email Address 3,Beneficiary Notification Email Address 4,Beneficiary Notification Email Address 5
Default,p.kositc@trufunding.net,,,,
GBA GROUP LLC,accounting@gbaholding.net,,,,
RUSH TRANSLOGISTICS INC,accounting@rushtranslogistics.com,maria@rushtranslogistics.com,,,
```

- **Column A**: Beneficiary Name (case-insensitive matching)
- **Columns B-F**: Email addresses (up to 5 emails per beneficiary)
- **Default row**: Used when no match is found (beneficiary name must be "Default")

## Output Format

### Wire CSV Output
- **Column A**: WIRE
- **Column B**: Date (YYYYMMDD format)
- **Column D**: Amount (with commas)
- **Column E**: USD
- **Column F**: USD
- **Column G**: BEN
- **Column J**: 4941701393
- **Column S**: Client Name (from Beneficiary Name)
- **Column T**: Client Account Number (from Beneficiary Account Number)
- **Column AA**: Client Routing Number (from Beneficiary Bank ID)
- **Columns AJ-AN**: Email addresses (from Notification.csv)

## Requirements

- Modern web browser (Chrome, Firefox, Edge, Safari)
- No server-side dependencies - runs entirely in the browser
- For best experience, use a local web server (Python or Node.js)

## Browser Compatibility

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support
- Internet Explorer: ❌ Not supported

## License

This project is provided as-is for internal use.

## Support

For issues or questions, please contact the development team.

