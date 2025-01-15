# README: Dynamic Scraper for "Hesder Mutne"

## Overview
This script is a dynamic web scraper designed to collect data about "הסדר מותנה" (Conditional Arrangement) from the Israel Police website. The data collected includes detailed information about cases and agreements under this legal framework. The scraper automatically navigates through all pages on the site until it encounters a page without content, ensuring comprehensive data collection.

## What is "Hesder Mutne"?
"Hesder Mutne" (הסדר מותנה) is a legal agreement in which a suspect admits to certain offenses and agrees to fulfill specific conditions. In return, the prosecution agrees not to file formal charges. This arrangement serves as an alternative to criminal prosecution and is aimed at efficiently resolving cases while imposing proportional sanctions.
For more information, visit: [Wikipedia Article on Hesder Mutne](https://he.wikipedia.org/wiki/%D7%94%D7%A1%D7%93%D7%A8_%D7%9E%D7%95%D7%AA%D7%A0%D7%94#:~:text=%D7%94%D7%A1%D7%93%D7%A8%20%D7%9E%D7%95%D7%AA%D7%A0%D7%94%20%D7%94%D7%95%D7%90%20%D7%94%D7%A1%D7%9B%D7%9D%20%D7%9E%D7%A9%D7%A4%D7%98%D7%99,%D7%9C%D7%94%D7%92%D7%99%D7%A9%20%D7%9B%D7%AA%D7%91%20%D7%90%D7%99%D7%A9%D7%95%D7%9D%20%D7%A0%D7%92%D7%93%20%D7%94%D7%97%D7%A9%D7%95%D7%93.)

## Features
- **Dynamic Pagination**: Automatically navigates through all pages on the Israel Police website, appending data from each page until no more content is found.
- **Data Extraction**: Scrapes detailed case information, including:
  - Case Number (מספר תיק)
  - Branch (שלוחה)
  - Date (תאריך)
  - Hebrew Date (תאריך עברי)
  - Description of Facts (תיאור העובדות)
  - Relevant Legislation (הוראות החיקוק)
  - Settlement Conditions (תנאי הסדר)
  - Reasoning for Case Closure (נימוקים לסגירת התיק)
- **Output**: Saves extracted data into a CSV file for further analysis.

## Requirements
- Python 3.x
- Selenium
- ChromeDriver (automatically managed by `webdriver_manager`)

### Python Libraries
The script uses the following Python libraries:
- `selenium`: For web automation and scraping.
- `webdriver_manager`: To manage ChromeDriver installation automatically.
- `csv`: For saving extracted data.
- `time`: For delays during page interactions.

## How to Use
1. **Setup**:
   - Ensure Python and necessary libraries are installed.
   - Install required libraries with:
     ```bash
     pip install selenium webdriver-manager
     ```
2. **Run the Script**:
   - Execute the script in a Python environment. It will start scraping from the base URL and dynamically paginate until no content is found.

3. **Output**:
   - The script saves the extracted data in a file named `updated_blocks.csv` in the working directory.

## Code Workflow
1. **Initialization**:
   - Sets up a headless Chrome browser using Selenium.
2. **Dynamic Scraping**:
   - Starts from the base URL and iteratively accesses pages using the `?skip={offset}` query parameter.
   - Identifies and expands all content blocks using the "View More" button.
3. **Data Extraction**:
   - Scrapes details of each case while ensuring no duplicate entries are processed.
4. **CSV Export**:
   - Consolidates all data into a single CSV file.

## Error Handling
- Errors during data extraction are logged to the console with details of the problematic block.
- The script safely exits and closes the browser even if an error occurs.

## Limitations
- Assumes a consistent structure on the target website.
- Requires updates if the website's structure changes.

## Contribution
Feel free to extend the script by:
- Adding support for other data formats.
- Improving error handling.
- Enhancing the scraping efficiency.

---
**Author**: [Your Name]
**Contact**: [Your Email]

