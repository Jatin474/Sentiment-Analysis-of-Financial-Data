# Sentiment Analysis of Financial Data
## Project Overview

The Text Analysis URL Scraper is a Python-based tool that extracts textual content from a list of URLs and performs comprehensive text analysis. The analysis includes sentiment scoring, readability metrics, and linguistic features to help users gain insights from the text data extracted from various web pages.

## Features

- **URL Extraction**: Fetches text content from a list of URLs provided in an Excel file.
- **Text Analysis**: Calculates various metrics including:
  - Sentiment Polarity and Subjectivity
  - Average Sentence Length
  - Percentage of Complex Words
  - Fog Index
  - Word Count and Syllable Count
  - Personal Pronouns Count
  - Average Word Length
- **Output Generation**: Saves the analysis results to a new Excel file for further review.

## Requirements

To run this project, you need to have the following packages installed:

- `pandas`
- `requests`
- `beautifulsoup4`
- `textblob`
- `openpyxl` (for Excel file handling)

You can install these packages using pip:

```bash
pip install pandas requests beautifulsoup4 textblob openpyxl
