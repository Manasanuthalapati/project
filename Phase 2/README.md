# HR BOT

An automated system to analyze resumes against job descriptions (JDs) and generate detailed reports, including scores, strengths, weaknesses, and analysis in both PDF and CSV formats. The outputs are zipped together for easy download.

## Features

- **Resume Analysis**: Compares resumes against JDs to compute scores (1-100).
- **Strengths & Weaknesses**: Highlights key strengths and areas of improvement.
- **Report Generation**:
  - Generates individual PDF reports for each candidate.
  - Creates a summary CSV with all candidate details.
- **ZIP Packaging**: Packages the CSV and PDFs into a single ZIP file.

## Installation

### Prerequisites

- Python 3.10 or higher
- Pip package manager

### Steps

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd HR-BOT
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   # On Windows
   venv\Scripts\activate
   # On macOS/Linux
   source venv/bin/activate
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Running the Application

1. Navigate to the project directory.
2. Start the FastAPI server:
   ```bash
   uvicorn app.main:app --reload
   ```
3. Open your browser and go to `http://127.0.0.1:8000`.

### API Endpoints

#### Upload Resumes

Endpoint: `POST /upload/`

**Request**:
- Upload a file containing resumes and job descriptions.

**Response**:
- A ZIP file containing:
  - Individual PDF reports.
  - A summary CSV with candidate details.

### Example Analysis Results Structure

Ensure the analysis results are structured as follows:

```json
[
  {
    "candidate_name": "John Doe",
    "score": 85,
    "strengths": "Excellent technical skills, Team player",
    "weaknesses": "Limited experience with cloud technologies",
    "analysis": "John has a strong background in software development..."
  },
  {
    "candidate_name": "Jane Smith",
    "score": 90,
    "strengths": "Good problem-solving, Experienced in AI",
    "weaknesses": "Needs improvement in communication skills",
    "analysis": "Jane has significant expertise in artificial intelligence..."
  }
]
```

## Project Structure

```
HR-BOT/
├── app/
│   ├── main.py       # Main application file
│   ├── utils.py      # Utility functions (PDF, CSV, ZIP generation)
│   ├── models.py     # Data models (if any)
│   ├── static/       # Static files (e.g., CSS)
│   └── templates/    # HTML templates
├── requirements.txt  # Dependencies
├── README.md         # Project documentation
└── tests/            # Test cases
```

## Dependencies

- **FastAPI**: Web framework for building APIs.
- **Uvicorn**: ASGI server for running the FastAPI application.
- **FPDF**: Library for creating PDF reports.
- **Zipfile**: Standard Python library for ZIP operations.

Install all dependencies using `pip install -r requirements.txt`.

## Development

### Testing

To run test cases:
```bash
pytest
```

### Linting

Ensure code quality with:
```bash
flake8
```

## Contributions

Feel free to submit issues and pull requests. Ensure that code changes are tested thoroughly before submitting.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
