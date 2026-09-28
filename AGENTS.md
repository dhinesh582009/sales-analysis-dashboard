# Repository Guidelines — Northwind Sales Insight Hub

## Architecture
- **Frontend**: TanStack Start + React 19 + Tailwind CSS (Slate Navy + Amber theme).
- **Backend**: Flask API with SQLAlchemy ORM and MySQL 8.
- **Authentication**: JWT authentication with email verification and role-based access control (`admin` vs `user`).
- **SMTP**: Dual-mode email sender supporting live Gmail SMTP (`smtp.gmail.com:587`) and local test receiver (`127.0.0.1:1025`).

## Coding Standards
- Do not store plain text passwords; always use `generate_password_hash` (`scrypt`).
- Keep backend error responses consistent: `{"error": "message", "code": "OPTIONAL_CODE"}`.
- All protected endpoints must require JWT Bearer tokens.
- All product mutation endpoints require `@admin_required`.
