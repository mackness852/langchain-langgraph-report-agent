# README Template

Below is a template provided for use when building your README file for students.

# Project Title

Project description goes here.

## Getting Started

Instructions for how to get a copy of the project running on your local machine.

### Dependencies

```
- Python3+ along with ./starter/requirements.txt PIP dependencies in your venv
- We will install these via pip in the installation step below
```

### Installation

Step by step explanation of how to get a dev environment running.

List out the steps
- Ensure python3 is installed via your package manager
- Create a virtual environment in the workspace folder
- Install dependencies in requirements.txt via PIP
- Run the main.py file

```
python3 --version
cd report_building_agent
python -m venv .venv
source .venv/bin/activate
pip install -r starter/requirements.txt
python3 starter/main.py
```

## Testing

After running main.py using the steps above, end to end testing is available via the CLI. 
- Input a user name when prompted
- Happy Path: type /help to see multiple happy path prompts to try
- Unhappy Path tests:
  - Illegal calculator operations: Ask for an invoice amount modulo or exponent and view the error message
  - Unknown document: 
    - Ask the agent to list all invoice titles
      - Ask for the total of an invoice that doesn't exist, such as INV-004
      - View the Assistant feedback
  - No document exists for parameters
    - Ask the agent for all invoices a total amount less than $100
    - View the assistant feedback

### Break Down Tests

Explain what each test does and why

```
- Happy Path Tests: These tests will retrieve invoices for display, summarisation or calculation
- Unhappy Path Tests:
  - Illegal calculator operations: The only allowed operations are defined in starter/tools.py #create_calculator_tool: allowed_chars = "1234567890+-*/. "
  - Unknown document: Documents available are retrieved by the tool defined in starter/tools.py #create_document_search_tool. If it cannot find a document it will return "No documents found matching your search criteria."
  - No document exists for parameters
    - Given a request to find documents that match user input, such as 'all invoices totalling under $100', retrieval.py will return None and the starter/tools.py #create_document_search_tool will return "No documents found matching your search criteria."
```
## Demonstrate complete system functionality
See the files in /logs and /sessions for output saved from recent sessions aligning with the project rubric.

## Project Instructions

See file starter/README.md

## Built With
Python 3 in visual studio code and git as VCS
Note, PEP8 compliance was not requested so syntax linters like Ruff were not used.
