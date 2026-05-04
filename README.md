**Assignment 1 – Singlish to Sinhala Transliteration Accuracy Testing**


Module: IT3040 – ITPM
Year: 3 | Semester: 1
Option: 1 – Transliteration Accuracy Testing (for students familiar with Sinhala)
Target URL: https://www.pixelssuite.com/chat-translator

📌 Project Overview
This project automates the testing of the Chat Sinhala transliteration feature on the PixelsSuite chat translator. The goal is to identify cases where the system fails to correctly convert chat-style Singlish input into Sinhala output.
The automation is built using Playwright (Python) and reads test cases from an Excel file, types each input into the web application, captures the actual output, compares it with the expected output, and records the results back into the same Excel file.

📁 Project Structure
test_automation/
│
├── test_automation.py          # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx  # Excel file with all 50 test cases
├── Commands.txt                # Quick reference for running commands
└── README.md                   # This file

✅ Prerequisites
Before running the project, make sure you have the following installed:
RequirementVersionDownloadPython3.11 or 3.12python.orgGoogle ChromeLatestgoogle.com/chromepipLatestComes with Python

⚠️ During Python installation, make sure to tick "Add Python to PATH" before clicking Install.


⚙️ Installation Steps (One-Time Setup)
Step 1 – Extract the project
Save the ZIP file to your D: drive and extract it. You should have:
D:\test_automation\
Step 2 – Open Command Prompt or VS Code Terminal
If using VS Code:

Open VS Code
Click File → Open Folder → select D:\test_automation
Press Ctrl + ` to open the terminal

If using Command Prompt:
cmdcd /d D:\test_automation
Step 3 – Install dependencies
Run the following commands one by one:
bashpip install -U pip
bashpip install playwright openpyxl
bashplaywright install

The last command downloads browser binaries. It may take a few minutes depending on your internet speed.


▶️ How to Run the Tests
Once setup is complete, run the following command from inside the D:\test_automation folder:
bashpython test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
What happens when you run it:

A Chrome browser window opens automatically
The script navigates to the chat translator website
For each test case in the Excel file, it:

Types the Singlish input into the chat box
Waits for the Sinhala translation to appear
Captures the actual output
Compares it with the expected output
Records Pass or Fail in the Excel file


The Excel file is saved after every test case (--save-every 1)
The browser stays open after finishing (--keep-open)


💡 Do not click or interact with the browser while the script is running.


🔧 Command Options Explained
OptionValue UsedDescription--excel"Assignment 1 - Test cases.xlsx"Path to the Excel test case file--url"https://www.pixelssuite.com/chat-translator"URL of the application to test--wait-ms5000Wait 5 seconds for the translation to appear--type-delay-ms80Delay between each keystroke (ms)--slow-mo-ms200Slows down browser actions for visibility--save-every1Saves Excel after every single test case--keep-open(flag)Keeps browser open after all tests finish

If your internet is slow, increase --wait-ms to 8000 or 10000.


📊 Checking Results
After the script finishes:

Go to the D:\test_automation folder
Open Assignment 1 - Test cases.xlsx
Check the Actual output and Status columns — they will be filled automatically
Since all 50 test cases are designed to fail, most Status values should show FAIL


🐛 Troubleshooting
ProblemFixpython not foundReinstall Python and tick "Add to PATH"playwright not foundRun pip install playwright againBrowser doesn't openRun playwright install chromiumExcel file not foundMake sure the .xlsx file is inside D:\test_automationScript crashes midwayJust run the same command again — it continues from where it stoppedTranslation not capturedIncrease --wait-ms to 8000Wrong Python versionCheck with python --version — needs 3.11 or 3.12

📝 Test Case Summary

Total test cases: 50
Type: Negative (all expected to FAIL)
TC ID format: Neg_0001 to Neg_0050
Input length types:

S → Short (≤ 30 characters)
M → Medium (31–299 characters)
L → Long (300–450 characters)


Singlish input types covered: All 24 types from Appendix 1 (minimum 2 per type)
