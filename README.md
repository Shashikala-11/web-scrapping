# Web Scraping with Scrapy

This repository contains a simple Scrapy project for learning web scraping techniques in Python.

## Project Structure

- `requirements.txt` - Python dependencies for the project.
- `myenv/` - Python virtual environment used for the project.
- `scrapy_01/` - Scrapy project folder.
  - `scrapy_01/spiders/quotes_spiders.py` - Example spider that scrapes the page title from `http://quotes.toscrape.com`.

## Setup

1. Activate the virtual environment (Windows PowerShell):

   ```powershell
   cd "d:\shashikala\ML100\data ingestion techniques in ml\web_scrapping"
   .\myenv\Scripts\Activate.ps1
   ```

2. Install dependencies:

   ```powershell
   pip install -r requirements.txt
   ```

## Usage

1. Change to the Scrapy project directory:

   ```powershell
   cd scrapy_01
   ```

2. Run the `quotes` spider:

   ```powershell
   scrapy crawl quotes
   ```

3. To save output to a file:

   ```powershell
   scrapy crawl quotes -o quotes.json
   ```

## Notes

- The example spider scrapes the title from `http://quotes.toscrape.com`.
- Scrapy obeys `robots.txt` by default. Requests to disallowed pages (for example some Amazon URLs) will be blocked unless you change the crawler settings.
- If you want to scrape a different website, update `start_urls` and the parsing logic in `scrapy_01/scrapy_01/spiders/quotes_spiders.py`.

## Best Practices

- Always respect website terms of service and `robots.txt` rules.
- Use delays and concurrency settings to avoid overloading target sites.
- Inspect pages with Scrapy shell before writing parsing rules:

  ```powershell
  scrapy shell "http://quotes.toscrape.com"
  ```
