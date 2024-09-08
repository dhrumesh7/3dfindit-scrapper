# 3D Findit Data Scraper

This Python-based web scraping script extracts product data from the 3DFindit platform, including part details, images, and other relevant metadata. It uses Selenium for dynamically loaded content, BeautifulSoup for parsing HTML, and stores the extracted data in JSON format. The script supports error handling, scrolling, and pagination for a robust scraping process.

## Features

- **Scraping Data**: Extracts product family details, part numbers, descriptions, and images.
- **Selenium WebDriver**: Handles dynamically loaded pages and scrolls to retrieve all data.
- **Retries & Error Handling**: Implements retry mechanisms for robust data extraction.
- **JSON Storage**: Saves the extracted data in JSON format for easy access and further processing.
- **Excel Integration**: Reads input URLs and Eclass codes from an Excel file and updates the status of processed records.

## Prerequisites

To run this project, you'll need to have the following installed on your machine:

- **Python 3.x**: [Download Python](https://www.python.org/downloads/)
- **Chrome Browser**: Ensure Google Chrome is installed.
- **Google ChromeDriver**: The script automatically installs and manages the ChromeDriver using the `webdriver_manager` package.
- **Required Python Libraries**: Use the provided requirements file to install dependencies.

## Installation

1. Clone the repository or download the script:
    ```bash
    git clone <repository_url>
    cd <repository_folder>
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have an Excel file named `eclass_codes.xlsx` with the necessary data (see below for format).

## Input Data Format

The script reads the URLs and Eclass codes from an Excel file named `eclass_codes.xlsx`. Ensure the file is in the root directory of the project.

- **Columns in the Excel File**:
    - Column B: URL of the product family page.
    - Column C: Processed status (will be marked "YES" after processing).
    - Column D: Any additional notes.
    - Column E: Eclass code (integer).

## Running the Script

1. Run the script by executing the following command in the terminal:
    ```bash
    python <script_name>.py
    ```

2. You will be prompted whether to continue from where it left off or start fresh. Enter `Y` or `N`.

3. You will also be prompted to set a delay between operations. Enter the number of seconds (0 for no delay).

The script will then start scraping and saving data in the following directories:
- **`pictures/`**: Contains downloaded images.
- **`data/`**: Stores the HTML pages for reference.
- **`json/`**: Contains JSON files with the scraped data.

## Logs

The script writes logs to a file named `3dfindit.log`, which will track errors and any issues encountered during scraping.

## File Structure

