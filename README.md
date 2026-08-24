# DocumentFlow

Open-source document extraction API built with Django REST Framework.

DocumentFlow is a self-hosted, developer-friendly service for turning documents and images into structured data through a simple REST API.

> **Status:** Early development — API and extraction features are being built incrementally.

## Vision

DocumentFlow aims to provide a modular document-processing pipeline that developers can run on their own infrastructure without depending on a hosted SaaS platform.

```text
PDF / Image
    ↓
DocumentFlow API
    ↓
Text / OCR Extraction
    ↓
Document Parser
    ↓
Structured JSON
```

## Planned capabilities

- Document upload and metadata management
- PDF and image processing
- OCR-based text extraction
- Structured JSON extraction
- Invoice extraction
- Receipt extraction
- Quotation extraction
- Purchase-order extraction
- Pluggable extraction backends
- REST API documentation
- Docker-based deployment
- Automated tests and CI

## Technology

The initial implementation uses:

- Python
- Django
- Django REST Framework
- SQLite for local development
- Tesseract OCR for OCR workflows
- pytest / Django test framework
- Docker for deployment

The architecture is intentionally modular so additional OCR engines, parsers, and AI extraction providers can be added without changing the public API.

## Quick start

### Requirements

- Python 3.11+
- pip
- Tesseract OCR (required for OCR features)

### Setup

```bash
git clone https://github.com/abdulmuqeetosama99/DocumentFlow.git
cd DocumentFlow
python -m venv .venv

# Linux / macOS
source .venv/bin/activate

# Windows
# .venv\\Scripts\\activate

pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

The development server will be available at `http://127.0.0.1:8000/`.

## API direction

The first API version will use the following base path:

```text
/api/v1/
```

Planned endpoints include:

```text
POST /api/v1/documents/upload/
GET  /api/v1/documents/{id}/
POST /api/v1/documents/{id}/extract/
```

## Design principles

1. **Self-hosted first** — users should be able to run DocumentFlow on their own infrastructure.
2. **Modular extraction** — OCR, parsing, and structured extraction should remain replaceable components.
3. **API first** — functionality should be accessible through a stable REST API.
4. **Developer friendly** — clear documentation, predictable responses, tests, and simple local setup.
5. **Privacy conscious** — documents should not require transmission to a third-party hosted service.

## Contributing

Contributions are welcome once the initial API foundation is in place.

For larger changes, please open an issue first so the proposed design can be discussed before implementation.

## Roadmap

### 0.1 — Foundation

- [x] Public repository
- [x] Project documentation
- [ ] Django REST Framework project
- [ ] Document model
- [ ] Upload endpoint
- [ ] Basic extraction service
- [ ] Automated tests

### 0.2 — OCR

- [ ] Tesseract integration
- [ ] Image preprocessing
- [ ] OCR result model
- [ ] OCR API endpoint

### 0.3 — Structured extraction

- [ ] Generic JSON extraction
- [ ] Invoice extraction
- [ ] Receipt extraction
- [ ] Quotation extraction

### 0.4 — Developer experience

- [ ] OpenAPI / Swagger documentation
- [ ] Docker image
- [ ] CI workflow
- [ ] Python client

## License

DocumentFlow is licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.
