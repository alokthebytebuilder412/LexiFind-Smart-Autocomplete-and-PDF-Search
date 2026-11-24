# 🔍 LexiFind – Smart Auto-Complete & PDF Search

**LexiFind** is an intelligent word discovery and document search application that combines a Trie (Prefix Tree) data structure with frequency-based ranking to deliver fast and relevant word suggestions. It also allows users to upload PDF documents, index their content, search for specific words, and view matching pages with highlighted results.

The project demonstrates the practical application of Data Structures and Algorithms (DSA), particularly Trie-based searching, along with Flask backend development and interactive frontend integration.

## ✨ Features

- **Trie-Based Autocomplete:** Generates word suggestions efficiently using prefix-based searching.
- **Frequency-Based Ranking:** Prioritizes suggestions based on word frequency.
- **PDF Upload & Processing:** Upload PDF documents and extract their textual content using `pdfplumber`.
- **PDF Content Indexing:** Indexes extracted words and maintains page-level references for quick lookup.
- **Page-Level Search:** Identifies the pages containing a searched word.
- **Keyword Highlighting:** Highlights matching words in the extracted PDF text.
- **Interactive Interface:** Provides a responsive and user-friendly interface for autocomplete and document search.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core application logic |
| Flask | Backend and REST API development |
| Trie (Prefix Tree) | Prefix-based autocomplete |
| HashMap / Dictionary | Word frequency and page indexing |
| pdfplumber | PDF text extraction |
| HTML5 | Frontend structure |
| CSS3 | Styling and layout |
| JavaScript | Dynamic interactions and API communication |
| Fetch API | Asynchronous communication with Flask |

## 🧠 Data Structures & Algorithms

LexiFind uses the following concepts:

- **Trie:** Stores words character by character and supports efficient prefix searching.
- **HashMap (Dictionary):** Stores character references, word frequencies, and PDF page mappings.
- **Recursion:** Traverses the Trie to collect words matching a given prefix.
- **Sorting:** Ranks autocomplete suggestions according to their frequency.
- **Indexing:** Maintains a mapping between words and the PDF pages where they appear.

## ⚙️ How It Works

### 1. Autocomplete Workflow

1. The user enters a prefix in the search field.
2. JavaScript sends an HTTP GET request to the Flask `/autocomplete` endpoint.
3. Flask passes the prefix to the Trie implementation.
4. The Trie locates the corresponding prefix node.
5. Matching words are collected recursively.
6. Suggestions are sorted by frequency and returned as JSON.
7. JavaScript dynamically displays the suggestions.

### 2. PDF Search Workflow

1. The user uploads a PDF document.
2. Flask receives the document through the `/upload_pdf` endpoint.
3. `pdfplumber` extracts text from each page.
4. Extracted words are inserted into the Trie.
5. A dictionary maintains the page numbers associated with each word.
6. When a user selects a suggestion, the application retrieves the corresponding page text.
7. Matching words are highlighted in the results.

## 📁 Project Structure

```text
LexiFind/
│
├── app.py
│
├── trie.py
│
├── requirements.txt
│
├── templates/
│   └── index.html
│
└── README.md
```

## 🚀 Getting Started

Follow these steps to run LexiFind locally.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/LexiFind.git
```

### 2. Navigate to the Project Directory

```bash
cd LexiFind
```

### 3. Create a Virtual Environment (Optional)

```bash
python -m venv venv
```

Activate it:

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Application

```bash
python app.py
```

### 6. Open in Browser

Visit:

```text
http://127.0.0.1:5000/
```

Start typing to explore autocomplete suggestions or upload a PDF to search its contents.

## 🔗 Application Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Renders the application interface |
| GET | `/autocomplete?prefix=` | Returns autocomplete suggestions |
| POST | `/upload_pdf` | Uploads and indexes a PDF |
| GET | `/word_info?word=` | Returns page numbers containing a word |
| GET | `/page_texts?word=` | Returns extracted text from matching pages |

## 📌 Current Limitations

- The Trie and PDF index are maintained in application memory and are not persistent across server restarts.
- The application currently processes one uploaded PDF at a time.
- Scanned PDFs without an extractable text layer are not supported through OCR.
- Autocomplete suggestions are limited to the top 10 results by default.

## 🔮 Future Enhancements

- Implement OCR support for scanned PDF documents.
- Support indexing and searching across multiple PDF files.
- Introduce persistent storage for indexed documents and word frequencies.
- Implement autocomplete debouncing to reduce unnecessary API requests.
- Improve search ranking with more advanced relevance-based algorithms.
- Add search history and recently uploaded documents.
- Improve security through file validation and upload size restrictions.

## 🎯 Learning Outcomes

Through this project, I explored and implemented:

- Practical applications of Trie data structures.
- Prefix-based searching and autocomplete algorithms.
- Frequency-based ranking of search results.
- Recursive tree traversal.
- REST API development using Flask.
- PDF text extraction and indexing.
- Frontend-backend integration using JavaScript Fetch API.

---

**LexiFind – Making word discovery and document searching smarter, one prefix at a time.** 🔍
