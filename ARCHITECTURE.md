# Architecture

## Current prototype

```text
Browser
  └── index.html (HTML + CSS + JavaScript)
       ├── Dashboard
       ├── Patient directory
       ├── Digital health card (illustrative QR pattern)
       ├── Medical-record timeline
       ├── Simulated Emergency Health Mode
       └── In-memory audit log / CSV export
```

There is no backend, database, cloud file store, or real authentication in this version. Browser refresh clears any patients or records created during the demo.

## Proposed future architecture

```text
Patient / Doctor / Pharmacist / Admin
                  |
             HTTPS web app
                  |
          Backend API + identity
                  |
     Authorization / consent checks
            /             \
     SQL database      Private file storage
            \             /
              Audit service
```

### Design principles
- Least-privilege access based on user role and patient consent/policy.
- Server-side authorization for every sensitive request.
- QR codes should carry only a random, revocable identifier or protected URL.
- Emergency access should require authenticated staff, a reason, limited scope/time, and an audit event.
- Clinical data should be encrypted in transit and at rest.
- Audit records should be append-only or protected against tampering.
- Use standards such as HL7 FHIR only where the project requirements and implementation support them.
