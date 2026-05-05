
---

## Objective

The main objective of this assignment is to assess how accurately the application at the link below converts **chat-style Singlish** input into **Sinhala** output:

🔗 [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

The **Chat Sinhala transliteration** function is evaluated by testing it with words, phrases, and sentence structures commonly used in informal Sinhala typing.

> **Out of scope:** Standard Sinhala transliteration, backend APIs, performance, scalability, and security testing.

---

## Project Structure

```
test_automation/
├── test_automation.py           # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx  # Excel file with all 50 test cases
├── Commands.txt                 # Useful command references
└── README.md                    # This file
```

---

## Prerequisites (One-Time Setup)

1. **Python 3.11 or 3.12** – [Download here](https://www.python.org/downloads/)
2. **Google Chrome** (recommended) – or let Playwright install Chromium automatically

---

## Setup Instructions

### Step 1 – Extract the Project

- Save the provided ZIP file to your **D: drive** and extract it.
- You should now have a folder at `D:\test_automation`.

### Step 2 – Open Command Prompt and Navigate to the Folder

```bash
cd /d D:\test_automation
```

### Step 3 – Install Required Dependencies (One-Time)

Run the following commands from inside `D:\test_automation`:

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## How to Run the Tests

### Step 4 – Add Test Cases to the Excel File

- Open `Assignment 1 - Test cases.xlsx` from the extracted folder.
- Fill in your test data under the columns: **TC ID**, **Input length type**, **Input**, and **Expected output**.
- Do **NOT** enter values under **Actual output** or **Status** — these are filled automatically by the script.

### Step 5 – Run the Playwright Script

```bash
python test_automation.py --excel "test_automation/Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Step 6 – Check the Results

- Go to the `test_automation` folder.
- Reopen the Excel file and verify the values automatically recorded under **Actual output** and **Status**.

### Step 7 – Add Additional Columns (Manual Step)

After reviewing the automated results, add two columns next to **Status**:

| Column | Description |
|--------|-------------|
| **Singlish input types covered** | The Singlish input type(s) from Appendix 1 that apply to this test case |
| **Evidence or rationale for the input type covered** | Specific evidence from the input or a rationale explaining why that type applies |

Refer to **Appendix 2** of the assignment document for guidance on how to fill these columns.

---

## Test Case Specifications

| Field | Rule |
|-------|------|
| **TC ID** | Negative test cases begin with `Neg_` (e.g., `Neg_0001`) |
| **Input length type** | `S` = ≤ 30 characters, `M` = 31–299 characters, `L` = 300–450 characters |
| **Total test cases** | 50 negative test cases |
| **Coverage requirement** | At least **2 test cases per Singlish input type** (24 types × 2 = 48 minimum; remaining 2 can be any type) |
| **Exclusion** | Do not use any examples from Appendix 1 or Appendix 2 |

---

## Singlish Input Types (Appendix 1)

The 24 Singlish input types that must be covered are:

1. Question forms
2. Command forms
3. Greetings
4. Requests
5. Responses
6. Repeated Words
7. Inputs with Punctuation Marks
8. Romanization / Spelling Variants
9. Isolated English Word Insertions in Singlish
10. Multi-Word English Phrases in Singlish
11. English Digital Terms in Singlish
12. Platform/App Names in Singlish
13. English Abbreviations/Acronyms in Singlish
14. English Clipped Forms in Singlish
15. Place Names Embedded in Singlish
16. Person Names Embedded in Singlish
17. Inputs with Numbers and Numeric Suffixes
18. Inputs with Currency
19. Inputs with Time Formats
20. Inputs with Dates
21. Inputs with Unit of Measurements
22. Inputs with Slang and Casual Phrasing
23. Online Identifiers in Singlish
24. Inputs Containing Emojis
