# Enterprise Document Intelligence Assistant

A learning project for building a Python application that answers questions about business documents, compares policy versions, and returns verifiable citations to the source document and page.

## Project goals

- Ingest business documents such as PDF policies, procedures, and handbooks.
- Extract page-aware text and metadata.
- Retrieve relevant passages for natural-language questions.
- Generate grounded answers with document and page citations.
- Compare policy versions and explain meaningful changes.
- Make every answer traceable so a user can verify it against the source.

## Guiding principles

- **Citations are required:** claims should link back to a document and page.
- **No unsupported answers:** the assistant should say when the supplied documents do not contain enough evidence.
- **Preserve provenance:** chunks must retain their source document, version, and page range.
- **Evaluate as we build:** retrieval quality, answer faithfulness, and citation correctness should be testable.
- **Keep it understandable:** this is a learning project, so architecture and trade-offs should be documented.

## Planned learning path

1. Build PDF ingestion and page-aware text extraction.
2. Add chunking while preserving document and page metadata.
3. Implement search and retrieval over the document collection.
4. Generate answers only from retrieved evidence.
5. Render verifiable citations in every answer.
6. Compare two versions of a policy at section and semantic levels.
7. Add automated evaluations, an API, and a simple user interface.

## Repository layout

```text
.
|-- src/
|   `-- enterprise_document_intelligence/
|       `-- __init__.py
|-- tests/
|-- .env.example
|-- .gitignore
|-- .python-version
|-- pyproject.toml
`-- README.md
```

## Environment setup

Requirements:

- Python 3.12+
- Git

From PowerShell:

```powershell
cd F:\Ahmed\Repos\enterprise-document-intelligence-assistant
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
Copy-Item .env.example .env
```

On this workstation, if the Windows `python` launcher is unavailable, create the environment with the installed interpreter directly:

```powershell
& 'C:\Users\acer\AppData\Local\Python\bin\python.exe' -m venv .venv
```

If PowerShell blocks activation for the current process:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

## Development commands

```powershell
pytest
ruff check .
ruff format --check .
```

## Configuration

Keep local secrets in `.env`; it is ignored by Git. `.env.example` documents expected variables without containing credentials. Provider-specific configuration will be added when the application architecture is selected.

## Current status

Repository scaffold created. Application features have not been implemented yet.
