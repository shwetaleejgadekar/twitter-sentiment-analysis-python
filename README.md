# Twitter Sentiment Analysis — Python

A from-scratch sentiment analysis pipeline built in pure Python, applied to a raw tweet dataset.
No NLP libraries used — sentiment is derived through lexicon-based word matching and ratio scoring.

## What It Does

1. **Preprocesses** raw tweet text — splits on `@` mentions, decodes hex/unicode escape sequences,
   strips URLs, special characters, and stopwords
2. **Classifies** each word against curated positive, negative, and stopword lexicons
3. **Scores** overall sentiment using a positive-to-negative word ratio

## Result

| Metric | Value |
|---|---|
| Total Words | 51,428 |
| Positive Words | 3,108 |
| Negative Words | 2,365 |
| Positive/Negative Ratio | 1.31 |
| **Overall Sentiment** | **Weakly Positive** |

## Tech Stack

`Python` · `re (Regex)` · `File I/O` · `Unicode/Hex Decoding`

## Key Implementation Details

- Hex-encoded characters (e.g. `\x80`) are decoded back to readable text manually using `bytes` and `utf-8`
- All lexicons are stored as Python `set` objects for O(1) word lookup
- Regex handles mention removal (`@username`), non-alphanumeric stripping, and whitespace normalization
```

---

**.gitignore**
```
# Jupyter checkpoints
.ipynb_checkpoints/

# Auto-generated intermediate file
modified_new_line_trump_tweets.txt

# Python cache
__pycache__/
*.pyc

# OS files
.DS_Store
Thumbs.db
