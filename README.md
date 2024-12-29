# Truthout Article Scraper

This Python script scrapes articles from the "Truthout" website, focusing on articles related to Donald Trump. It collects essential details such as article headlines, publication dates, authors, and article content, and saves the data in a CSV file for further analysis.

## Features

- **Scrapes Headlines**: Extracts the title of each article.
- **Collects Publication Dates**: Retrieves the publication date of articles.
- **Identifies Authors**: Extracts the names of the authors.
- **Fetches Article Content**: Retrieves the main content of the articles up to a specific section.
- **Pagination Support**: Automatically iterates through all available pages of the website for the specified topic.
- **CSV Export**: Saves the extracted data into a CSV file.

## Requirements

- Python 3.x
- Required libraries: `requests`, `beautifulsoup4`, `pandas`

Install the dependencies using:
```bash
pip install requests beautifulsoup4 pandas
```

## How to Use

1. Clone or download the repository containing this script.
2. Ensure all dependencies are installed.
3. Run the script:
   ```bash
   python script_name.py
   ```
4. The script will generate a CSV file named `truthout1.csv` in the current directory.

## Code Breakdown

### Key Functionalities
- **Headlines Extraction**: Extracts the `<h1>` tag with the specific class.
- **Date Extraction**: Retrieves the `<time>` tag for publication date.
- **Author Name Extraction**: Extracts the `<a>` tag associated with the author's name.
- **Article Content**: Scrapes all `<p>` tags until encountering the specified stop point.

### Pagination
The script iterates through multiple pages using the URL pattern:
```
https://truthout.org/topics/donald-trump/page/{page_number}/
```
It stops when a "Page not found" title is detected.

### CSV Export
The data is stored in a dictionary and converted to a CSV file using Pandas for structured output.

## Output

The final CSV file includes the following columns:
- **Headlines**: Title of the article.
- **Publish_date**: Date of publication.
- **Writers**: Author(s) of the article.
- **Articles**: The content of the article.

## Notes

- Ensure a stable internet connection to avoid connection errors during scraping.
- The script uses headers to mimic a real browser and avoid blocks by the server.
