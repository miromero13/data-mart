# Academic Analytics Data Mart & ETL Pipeline

[![NestJS](https://img.shields.io/badge/NestJS-10-E0234E?style=flat&logo=nestjs&logoColor=white)](https://nestjs.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-4169E1?style=flat&logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![TypeORM](https://img.shields.io/badge/TypeORM-0.3-FE0808?style=flat&logo=typeorm&logoColor=white)](https://typeorm.io)
[![Swagger](https://img.shields.io/badge/Swagger-OpenAPI_3.0-85EA2D?style=flat&logo=swagger&logoColor=black)](https://swagger.io)

Institutional Data Mart and automated ETL pipeline engineered to ingest university academic datasets, structure dimensional schemas, and expose institutional KPIs and enrollment statistics via RESTful endpoints.

---

## 🏛️ Dimensional Model & Architecture

The data mart organizes higher-education metrics into structured dimensional entities and fact records:

```text
data-mart/
├── src/
│   ├── indicators/
│   │   ├── entities/        # Dimensional entities:
│   │   │   ├── faculty.entity.ts    # Faculties & Academic Departments
│   │   │   ├── career.entity.ts     # Undergraduate & Graduate Programs
│   │   │   ├── semester.entity.ts   # Academic cycles and terms
│   │   │   ├── mode.entity.ts       # Delivery modes (In-person, Hybrid, Virtual)
│   │   │   ├── locality.entity.ts   # Campuses and regional headquarters
│   │   │   └── indicator.entity.ts  # Academic fact metrics (Admissions, Dropouts, Graduates)
│   │   ├── service/         # Business logic and Excel ingestion services
│   │   │   ├── excel.service.ts     # XLSX parser, schema mapper, and normalization
│   │   │   └── *.service.ts         # Query services per dimension
│   │   └── controller/      # REST API endpoints with Swagger documentation
│   └── config/              # TypeORM database connection & environment loader
```

---

## ⚡ Key Capabilities

- **Automated XLSX Ingestion:** Parses institutional Excel workbooks and extracts structured records across academic periods.
- **Data Normalization:** Validates and maps external spreadsheets to strongly-typed TypeORM entities in PostgreSQL.
- **Academic KPI Queries:** Exposes aggregated metrics by career, faculty, modality, and geographic campus.
- **Interactive Documentation:** Fully documented with Swagger UI at `/docs`.

---

## 🚀 Getting Started

### Prerequisites

- **Node.js:** `>= 18.x`
- **PostgreSQL:** `>= 14.x`

### 1. Installation

```bash
npm install
```

### 2. Environment Setup

Create `.env` based on `.env.example`:

```bash
cp .env.example .env
```

Configure your PostgreSQL credentials:

```env
PORT=3000
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password
DB_NAME=datamart_db
```

### 3. Running the Server

```bash
# Development mode with watch
npm run start:dev

# Production build
npm run build && npm run start:prod
```

API documentation will be available at `http://localhost:3000/docs`.

---

## 👤 Author

Developed by **María Ilse Romero Saavedra** ([@miromero13](https://github.com/miromero13)).
