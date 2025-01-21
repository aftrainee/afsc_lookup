
# AFSC Lookup Tool

The **AFSC Lookup Tool** is a web-based application designed to help users explore and filter Air Force Specialty Codes (AFSCs) based on various criteria. This tool provides a clean and intuitive interface for recruiters and users to quickly find relevant AFSCs and their requirements.

## Features

- **Upload AFSC Dataset**: Easily upload `.xlsx` files containing AFSC data.
- **Search Functionality**: Search for AFSCs by name or code.
- **Advanced Filtering**:
  - Filter by MAGE requirements (Mechanical, Administrative, General, and Electrical scores).
  - Filter by driver's license requirement.
  - Filter by citizenship requirement.
  - Filter by security clearance level (ENTNAC, NACLC, SSBI).
- **Dynamic Sorting**:
  - Sort AFSCs by name, clearance level, driver's license requirement, and MAGE scores.
- **Responsive Design**: Fully responsive interface for desktop and smaller screen sizes.
- **Dynamic Dataset Loading**: Automatically populates the table with data from the uploaded file.

## How to Use

1. **Open the Application**:
   - Open the `index.html` file in any modern web browser (e.g., Chrome, Edge, Firefox).

2. **Upload the Dataset**:
   - Click the "Upload File" input field.
   - Select an `.xlsx` file containing AFSC data.

3. **Apply Filters**:
   - Use the search bar to find AFSCs by name or code.
   - Adjust the filters (e.g., MAGE scores, driver's license, citizenship, clearance level) to refine the results.

4. **Sort Results**:
   - Click on the column headers in the table to sort AFSCs by that column.

5. **View Details**:
   - Each AFSC name is a hyperlink. Click the name to open more information about the AFSC in a new tab.

6. **Reset Filters**:
   - Click the "Reset Filters" button to clear all applied filters.

## File Structure

- **`afsc.html`**: The main HTML file containing the application logic and interface.
- **`afsc.xlsx`**: Sample dataset containing AFSC details. Includes columns like:
  - `AFSC`: Air Force Specialty Code.
  - `NAME`: AFSC name.
  - `LICENSE`: Indicates if a driver's license is required.
  - `CITIZENSHIP`: Indicates if U.S. citizenship is required.
  - `MAGE`: Minimum Mechanical, Administrative, General, and Electrical scores.
  - `URL`: Hyperlink to more information about the AFSC.
  - `CLEARANCE`: Security clearance requirements.

## Understanding the `.xlsx` Dataset Structure

The `.xlsx` file serves as the data backbone for the AFSC Lookup Tool. It uses a structured format with specific column names and conventions that must be followed to ensure the application processes the data correctly.

### Columns in the Dataset

| **Column Name**         | **Description**                                                                 |
|--------------------------|---------------------------------------------------------------------------------|
| `AFSC`                  | The primary Air Force Specialty Code (e.g., "1N0X1").                          |
| `AFSC DOC`              | An alternative or document-based code for the same AFSC, if applicable.        |
| `NAME`                  | The official name of the AFSC (e.g., "Operations Intelligence").               |
| `LICENSE`               | Indicates if a driver's license is required (`Yes` or `No`).                  |
| `CITIZENSHIP`           | Indicates if U.S. citizenship is required (`true` for required, `false` otherwise). |
| `MIN M`, `MIN A`, `MIN G`, `MIN E` | Minimum Mechanical, Administrative, General, and Electrical scores required for the AFSC. Enter numbers (e.g., 50). Leave blank if not applicable. |
| `MIN ALL` | Indicates whether a single or multiple minimum MAGE scores are required for an AFSC. |
| `URL`                   | A hyperlink to additional information about the AFSC.                         |
| `SSBI`, `NATIONAL AGENCY CHECK`, `LOCAL AGENCY CHECK` | Indicate security clearance requirements (`true` or `false`). At least one must be provided for clearance determination. |

### Adding a New AFSC Entry

1. **Open the `.xlsx` File**:
   - Use any spreadsheet software that supports `.xlsx` (e.g., Microsoft Excel, Google Sheets, LibreOffice Calc).

2. **Insert a New Row**:
   - Add a new row below the existing data.

3. **Populate the Columns**:
   - Fill in the required columns:
     - `AFSC`: Enter the primary code.
     - `NAME`: Provide the AFSC name.
     - `MIN M`, `MIN A`, `MIN G`, `MIN E`: Enter the MAGE scores if applicable. Leave blank if not required.
     - `MIN ALL`: Specifies whether multiple minimum MAGE scores are required for an AFSC. When TRUE, all specified MAGE scores must be met (logical AND). When FALSE, meeting any one of the specified scores is sufficient (logical OR).
     - `LICENSE`: Specify `true` or `false` for driver's license requirements.
     - `CITIZENSHIP`: Use `true` for required or `false` for not required.
     - `URL`: Add a valid hyperlink for additional details.
     - Clearance columns (`SSBI`, etc.): Use `true` or `false` based on clearance requirements.

4. **Save the File**:
   - Ensure the file is saved in `.xlsx` format to maintain compatibility.

### Editing Existing Data

1. **Locate the Row**:
   - Use the `AFSC` or `NAME` column to find the entry you want to edit.

2. **Modify the Values**:
   - Change the data in the respective columns as needed (e.g., update MAGE scores or add a missing URL).

3. **Save Changes**:
   - Save the file in `.xlsx` format to preserve the updated data.

### Deleting an AFSC Entry

1. **Identify the Row**:
   - Find the row corresponding to the AFSC you want to delete.

2. **Delete the Row**:
   - Use your spreadsheet software's delete row function.

3. **Save the File**:
   - Save the updated `.xlsx` file.

## Known Issues

- The filtering and sorting logic currently supports only the default columns in the sample dataset. Custom datasets may require adjustments to the JavaScript functions.
- Ensure the uploaded `.xlsx` file follows the same structure as the provided `afsc.xlsx` file.

## License

This project is open-source and available under the MIT License.

---

Feel free to ask questions or report issues to improve this tool further!
