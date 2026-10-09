AM/NS INDIA — FINAL GITHUB UPDATE PACKAGE

THIS VERSION FIXES THE 116 vs 121 PROBLEM
------------------------------------------
The dashboard no longer depends on a permanently fixed 121-record data file.
GitHub Actions regenerates data.json whenever the confined-space Excel workbook changes.

IMPORTANT FIRST UPLOAD
----------------------
1. In your GitHub repository, delete the OLD 121-record confined-space Excel workbook.
2. Upload your CURRENT 116-record confined-space Excel workbook.
3. Keep only one confined-space workbook in the repository.
4. Keep AMNS_Pune_Gas_Hazardous_Area_Safety_Register.xlsx for Gas Hazards Area.
5. Commit the changes to the main branch.

WORKBOOK NAME
-------------
The generator gives priority to:
Copy of Updated CS Identification all (2).xlsx
then Updated CS Identification all.xlsx
then Updated CS Identification all (1).xlsx
If none exists, it selects the newest non-gas Excel workbook.

AUTOMATIC UPDATE
----------------
After the Excel file is committed, GitHub Actions runs automatically:
.github/workflows/update-dashboard.yml

It regenerates:
- data.json (Confined Space)
- gas_data.json (Gas Hazards Area)

It then commits the refreshed JSON back to main. GitHub Pages will publish the updated files when Pages is configured from the main branch.

MANUAL UPDATE
-------------
If needed, open GitHub -> Actions -> AMNS Dashboard - Excel Auto Update -> Run workflow.

DO NOT EDIT data.json MANUALLY.

EXPECTED RESULT
---------------
After the 116-record workbook is uploaded and the workflow completes, the dashboard count will be taken from the workbook, not a hard-coded 121.
The dashboard also normalizes NGH to NGHA and keeps Size (mm).
