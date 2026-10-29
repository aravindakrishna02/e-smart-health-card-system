# E-Smart Health Card System Using Cloud Computing

A responsive frontend prototype for a digital healthcare record system. It demonstrates a patient directory, digital health card, medical-record timeline, simulated Emergency Health Mode, and an access-audit screen.

> **Project status:** Frontend prototype only. It does not connect to a real cloud database, authenticate real users, scan a real QR code, or securely store medical records. Use fictional demo data only.

## Features in this prototype

- Dashboard with sample summary metrics
- Register fictional patients during the current browser session
- Digital health card with Health ID, blood group, allergies, and emergency contact
- Medical-record timeline with demo record creation
- Simulated Emergency Health Mode
- Access-audit table with CSV export
- Responsive layout for desktop and mobile screens

## Run locally

No installation or build tools are required.

1. Download or clone this repository.
2. Open `index.html` in Chrome, Edge, or Firefox.

## Deploy with GitHub Pages

1. Push the repository to GitHub.
2. Open **Settings → Pages** in the repository.
3. Under the build/deployment settings, select **Deploy from a branch**.
4. Choose the `main` branch and `/ (root)` folder, then save.
5. Wait for the deployment workflow to finish. GitHub will show the published URL in Pages settings.

GitHub Pages hosts the static frontend only. It does not provide the backend, authentication, or database required for a real healthcare system.

## Suggested production architecture

- **Frontend:** React or a similar framework
- **Backend API:** Python FastAPI or Flask
- **Authentication:** a trusted identity provider with MFA for clinical staff
- **Database:** PostgreSQL / managed database
- **Document storage:** private object storage with access controls
- **Hosting:** a managed cloud platform
- **Interoperability:** evaluate FHIR-compatible data structures if required by the project

## Important security requirements before real use

- Enforce role-based authorization on the server, not just in the UI.
- Never put medical details or long-lived secrets inside a QR code. Use a random, revocable token or protected URL and validate authorization on the server.
- Require authenticated, authorized staff for Emergency Health Mode; collect a reason and create a tamper-resistant audit event.
- Encrypt data in transit and at rest, use private storage, validate uploads, and apply least-privilege access.
- Add consent and retention rules, backups, monitoring, incident response, and applicable privacy/legal review.
- Do not use real patient data in this demo or a public repository.

## Repository structure

```text
e-smart-health-card/
├── index.html
├── README.md
├── LICENSE
├── .gitignore
├── CONTRIBUTING.md
├── SECURITY.md
├── docs/
│   ├── ARCHITECTURE.md
│   ├── FEATURES.md
│   └── PROJECT_REPORT.md
└── assets/
    └── README.md
```

## Current limitations

- Patient and record data exist only in JavaScript memory and are lost when the page is refreshed.
- The QR-style pattern is illustrative and is not scannable.
- The role selector is for demonstration; it does not secure any operation.
- Emergency access is simulated and does not contact emergency services.
- Dashboard figures are sample values, not live statistics.

## License

See [LICENSE](LICENSE).
