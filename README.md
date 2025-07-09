# Missing-Data-finder
✅
This Python script, new_correction.py, is designed to analyze text files within a specified main directory and its subfolders. Its primary function is to identify and count "alphabetical units" (sequences of letters) and extract numerical data found on the same lines as these alphabetical units. It then compiles this information into a structured CSV report
Here's a detailed breakdown of what it does:
Directory Traversal: The script starts by taking a main_folder_path (e.g., C:\Users\aaa\Desktop\climate data). It then walks through this main folder and all its subdirectories.
File Analysis:
For each file encountered, it attempts to read its content line by line, ignoring decoding errors.
Alphabetical Unit Counting: If a line contains any alphabetical characters ([a-zA-Z]), the script counts all sequences of one or more alphabetical characters (e.g., "word", "abc") within that line. This count is accumulated for the file.
Numerical Data Extraction ("Following day"): On the same lines where alphabetical characters are found, it extracts all numerical sequences (integers or decimals). These extracted numbers are then joined by a semicolon for reporting.
File Filtering: Only files that contain at least one alphabetical unit are included in the final report; files with zero alphabetical units are excluded.
Data Aggregation:
It maintains a count of total alphabetical units for each subfolder.
It collects the file name, its alphabetical unit count, and the extracted "Following day" numerical data for each relevant file, associating it with its immediate subfolder.
Report Generation (CSV):
The gathered data is prepared for a CSV report.
Subfolders with a total alphabetical count of 0 are listed first in the report.
Subfolders with non-zero counts are sorted in ascending order based on their total alphabetical count.
Within each subfolder's entry, the files are sorted alphabetically by their filename.
The report uses a hierarchical structure in the CSV: a row for each subfolder (showing its total count) followed by rows for each file within that subfolder (showing its individual file name, alphabetical count, and "Following day" data).
The final report is saved as climate_data_analysis.csv in the main_folder_path.
Error Handling: The script includes basic error handling to silently skip files that are unreadable or cause processing errors.
