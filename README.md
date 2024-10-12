# Sentiment Analysis of Financial Data

## Overview

The objective of this project is to perform sentiment analysis on financial texts, extracting sentiment scores, readability metrics, and various textual features to drive insights from the data.

## Table of Contents
1. [Sentiment Analysis](#sentiment-analysis)
   - [Cleaning using Stop Words Lists](#cleaning-using-stop-words-lists)
   - [Creating Dictionary of Positive and Negative Words](#creating-dictionary-of-positive-and-negative-words)
   - [Extracting Derived Variables](#extracting-derived-variables)
2. [Analysis of Readability](#analysis-of-readability)
3. [Average Number of Words Per Sentence](#average-number-of-words-per-sentence)
4. [Complex Word Count](#complex-word-count)
5. [Word Count](#word-count)
6. [Syllable Count Per Word](#syllable-count-per-word)
7. [Personal Pronouns](#personal-pronouns)
8. [Average Word Length](#average-word-length)
9. [Installation](#installation)
10. [Usage](#usage)
11. [Output](#output)
12. [Acknowledgments](#acknowledgments)

## 1. Sentiment Analysis

Sentiment analysis is the process of determining whether a piece of writing is positive, negative, or neutral. The algorithm implemented in this project is tailored for financial texts and includes the following steps:

### 1.1 Cleaning using Stop Words Lists

Stop words lists (located in the `StopWords` folder) are used to clean the text, allowing sentiment analysis to be performed by excluding words found in these lists.

### 1.2 Creating Dictionary of Positive and Negative Words

A master dictionary (found in the `MasterDictionary` folder) is used to create a list of positive and negative words. Only words not found in the stop words lists are included.

### 1.3 Extracting Derived Variables

The text is tokenized using the `nltk` tokenize module, and the following scores are calculated:

- **Positive Score**: Assigns +1 for each word found in the Positive Dictionary.
- **Negative Score**: Assigns -1 for each word found in the Negative Dictionary (the score is then multiplied by -1 to yield a positive number).
- **Polarity Score**: 
  \[
  \text{Polarity Score} = \frac{\text{Positive Score} - \text{Negative Score}}{(\text{Positive Score} + \text{Negative Score}) + 0.000001}
  \]
  The range is from -1 to +1.
- **Subjectivity Score**: 
  \[
  \text{Subjectivity Score} = \frac{\text{Positive Score} + \text{Negative Score}}{(\text{Total Words after cleaning}) + 0.000001}
  \]
  The range is from 0 to +1.

## 2. Analysis of Readability

Readability is assessed using the Gunning Fog index, calculated as follows:

- **Average Sentence Length** = Number of Words / Number of Sentences
- **Percentage of Complex Words** = Number of Complex Words / Number of Words
- **Fog Index** = \(0.4 \times (\text{Average Sentence Length} + \text{Percentage of Complex Words})\)

## 3. Average Number of Words Per Sentence

Calculated using the formula:
\[
\text{Average Number of Words Per Sentence} = \frac{\text{Total Number of Words}}{\text{Total Number of Sentences}}
\]

## 4. Complex Word Count

Complex words are defined as words containing more than two syllables.

## 5. Word Count

The total number of cleaned words is calculated by:
1. Removing stop words (using the stopwords class from the `nltk` package).
2. Removing punctuation (e.g., ?, !, ., etc.) before counting.

## 6. Syllable Count Per Word

The number of syllables in each word is counted by evaluating the number of vowels present. Exceptions are handled for words ending in "es" or "ed," which are not counted as syllables.

## 7. Personal Pronouns

The counts of personal pronouns are calculated using regex to find words such as "I," "we," "my," "ours," and "us." Special care is taken to exclude the country name "US."

## 8. Average Word Length

Calculated using the formula:
\[
\text{Average Word Length} = \frac{\text{Sum of Total Characters in Each Word}}{\text{Total Number of Words}}
\]

## 9. Installation

To run this project, ensure you have the following Python packages installed:

- `pandas`
- `requests`
- `beautifulsoup4`
- `textblob`
- `openpyxl` (for Excel file handling)
- `nltk`

You can install these packages using pip:

```bash
pip install pandas requests beautifulsoup4 textblob openpyxl nltk
