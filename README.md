# Team DVA Final Project
# J.R.R. Tolkien - Lord of the Rings Trilogy: A Natural Language Processing Analysis

**Group Members:** Adilya Korkmaz, Vladyslav Stupak, Daniil Zykov


This repository contains Natural Language Processing analysis of J.R.R. Tolkien's Lord of the Rings trilogy, exploring character interactions, narrative patterns, linguistic features, and textual dynamics across all three books.

---

# Medium Article
**Link:** https://medium.com/@daniil.zykov2004/lords-rings-natural-language-processing-48fe3286a592?postPublishedType=repub

---

## Table of Contents

- [Project Overview](#-project-overview)
- [Why Analyse Tolkien?](#-why-analyse-tolkien)
- [Key Features](#-key-features)
- [Repository Structure](#-repository-structure)
- [Environment Setup](#-environment-setup)
- [Analysis Methods](#-analysis-methods)
- [Results](#-results)
- [Learn More](#-learn-more)

---

## Project Overview

This project applies NLP methods to analyze the Lord of the Rings trilogy, examining:
- **Character Interaction Networks** - Mapping relationships through textual proximity
- **Gender Representation** - Analyzing pronoun usage and character presence
- **Character Activity Patterns** - Categorizing actions, speech, and perception

- **Additional Data:**
- **Narrative Complexity** - Measuring readability and pacing
- **Stylistic Patterns** - Comparing dialogue vs. narration across books
- **Topic Shifts** - Tracking narrative flow using semantic similarity

---

## Why Analyse Tolkien?

We chose J.R.R. Tolkien's Lord of the Rings trilogy for several compelling reasons:

1. **Native English Writing** - Ensures nothing is lost or misinterpreted in translation
2. **Cultural Significance** - A widely-known series with multiple media adaptations that resonates across generations
3. **Linguistic Excellence** - J.R.R. Tolkien was a linguist before becoming an author, bringing his expertise to the creative process

---

## Key Features

### Character Network Analysis
- **15-Word Window Approach**: Characters appearing within 15 words of each other are considered "interacting"
- **Network Visualization**: Node size represents character centrality; edge thickness indicates relationship strength
- **Spatial Clustering**: Reveals characters who share similar social circles
- Individual network graphs for each book in the trilogy

### Gender Analysis
- Pronoun usage patterns across the trilogy
- Character representation by gender
- Bechdel test evaluation (Note: The trilogy does not pass, with *The Two Towers* featuring only three female characters, including Shelob)

### Character Activity Metrics
- **Mention Counting**: Tallying character name appearances throughout the trilogy
- **Action-Perception-Speech (APS) Ratios**: 
  - Analyzes character activity by identifying action verbs within a 6-word window
  - Categories: Speaking, Physical Action, Perception/Thought
  - Provides insight into how characters are portrayed

---

## Repository Structure

```
NLP-Final-Project-TeamDVA/
│
├── notebooks/          # Jupyter notebooks with analysis code
├── data/              # Dataset files (place LOTR text files here)
├── results/           # Generated figures, tables, and visualizations
├── slides/            # Presentation materials
├── requirements.txt   # Python dependencies
└── README.md         # This file
```

---

## Environment Setup

Before starting, please **fork this repository** and create a fresh Python virtual environment.  
All required libraries are listed in `requirements.txt`.

> **Troubleshooting:** If you encounter errors during `pip install`, try removing the version pinning for the failing package(s) in `requirements.txt`.  
> **Apple M1/M2 Users:** You may need to install additional system packages.

### macOS / Linux (bash/zsh)

```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate

# Upgrade pip and install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

### Windows (PowerShell)

```powershell
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
.venv\Scripts\Activate.ps1

# Upgrade pip and install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Windows (Git Bash)

```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
source .venv/Scripts/activate

# Upgrade pip and install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

You're now ready to run the analysis notebooks!

**Deactivate the environment when you're done:**
```bash
deactivate
```

---

## Analysis Methods

### Character Interaction Detection
The algorithm scans text for character names and identifies co-occurrences:
1. When a character name (Character A) is found, the next 15 words are examined
2. If another name (Character B) appears within this window, a directed edge is recorded from A → B
3. Repeated co-occurrences strengthen relationship weights

### Gendered Pronoun Analysis
- Identifies all gendered pronouns in the text
- Analyzes the word immediately following each pronoun
- Counts and categorizes instances across all three books

### Action-Perception-Speech Classification
- Searches for character names in the text
- Examines the following 6 words for verbs
- Categorizes verbs into three types:
  - **Speaking**: Dialogue and verbal communication
  - **Action**: Physical activities and movements
  - **Perception/Thought**: Mental processes and observations

## Additional Data

### Readability Metrics
- **Flesch Reading Ease**: Higher scores indicate easier-to-read text
- **Flesch-Kincaid Grade Level**: Lower levels indicate simpler text
- Comparative analysis across all three books

### Semantic Similarity Analysis
Uses **Sentence-Transformers** to:
1. Convert each sentence into a high-dimensional vector
2. Calculate cosine similarity between consecutive sentences
3. Plot similarity scores to visualize narrative pacing and topic transitions

---

## Results

All visualizations, figures, and tables are available in the [`results/`](./results/) folder, including:
- Character interaction network graphs for each book
- Gender representation charts
- APS (Action-Perception-Speech) ratio comparisons

---

## Contributing

This project was completed as a final assignment for a Natural Language Processing course. While not actively maintained, feel free to fork and adapt for your own analyses!

---

## Team DVA

**Adilya Korkmaz** - SRH ID 100001930  
**Vladyslav Stupak** - SRH ID 100001664  
**Daniil Zykov** - SRH ID 100003596
