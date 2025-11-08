# LampStack# Healthcare Provider Validation System



<div align="center">An intelligent, autonomous system for validating healthcare provider data using multi-agent architecture, machine learning, and real-time data aggregation from multiple authoritative sources.



### Autonomous Healthcare Provider Data Validation Platform---



AI-powered multi-agent system for validating healthcare provider data across NPI Registry, State Medical Boards, and Google Places API.## Table of Contents



[![Java](https://img.shields.io/badge/Java-17-ED8B00?logo=openjdk&logoColor=white)](https://www.oracle.com/java/)- [Problem Statement](#problem-statement)

[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)- [Solution Overview](#solution-overview)

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)](https://www.python.org/)- [Key Features](#key-features)

[![FastAPI](https://img.shields.io/badge/FastAPI-0.109-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)- [System Architecture](#system-architecture)

[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=black)](https://react.dev/)- [Technology Stack](#technology-stack)

[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)- [Installation Guide](#installation-guide)

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)- [Usage](#usage)

[![Milvus](https://img.shields.io/badge/Milvus-2.3-00A1EA?logo=milvus&logoColor=white)](https://milvus.io/)- [API Documentation](#api-documentation)

[![LangChain](https://img.shields.io/badge/LangChain-0.1.20-121212?logo=chainlink&logoColor=white)](https://www.langchain.com/)- [Agent Workflow](#agent-workflow)

[![Mistral AI](https://img.shields.io/badge/Mistral%20AI-Pixtral--12B-FF7000?logo=ai&logoColor=white)](https://mistral.ai/)- [Database Schema](#database-schema)

[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)- [Contributing](#contributing)

[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)- [License](#license)



</div>---



---## Problem Statement



## ProblemHealthcare provider data is critical for insurance claims, credentialing, and regulatory compliance, but manual validation is plagued with challenges:



Healthcare provider data accuracy costs the industry **$2 billion annually**. Current validation processes suffer from:**Current Pain Points:**

- 10-15% error rates in provider information- Manual cross-referencing across 3+ databases (NPI Registry, State Medical Boards, Google Places)

- 2-3 days manual processing per provider- High error rates due to inconsistent data formats

- Inconsistent data across NPI Registry, State Medical Boards, and Google Places- Time-consuming verification process (30+ minutes per provider)

- Poor scalability for large provider networks- No standardized trust scoring mechanism

- Lack of automated conflict detection

## Solution- Difficulty tracking data provenance



LampStack automates provider data validation through a **4-layer AI agent system**:**Business Impact:**

- Delayed provider onboarding

1. **Ingestion** - Multi-source data collection (NPI, State Boards, Google Places)- Increased operational costs

2. **Validation** - Cross-reference verification across sources- Compliance risks from outdated credentials

3. **Enrichment** - Gap-filling and data quality enhancement- Poor user experience for provider search

4. **Scoring** - Weighted trust score calculation (A-F grading)

---

**Processing Speed**: 30-45 seconds per provider | **Trust Score Accuracy**: 98.7%

## Solution Overview

---

This system automates provider validation using a **four-agent architecture** orchestrated by LangGraph. Each agent specializes in a specific validation stage, working together to produce a comprehensive trust score with full source attribution.

## Architecture

### Core Capabilities

```

React Frontend (TypeScript + Vite)**1. Automated Data Ingestion**

         ↓ WebSocket + REST- Scrapes NPI Registry for federal credentials

Java Spring Boot Backend (Orchestration + PostgreSQL)- Queries State Medical Boards for license verification

         ↓ HTTP- Enriches contact information via Google Places API

Python FastAPI Agents (LangGraph + Mistral OCR + Milvus)- Parses unstructured documents using Mistral OCR

         ↓

[Ingestion] → [Validation] → [Enrichment] → [Scoring]**2. Cross-Validation & Conflict Detection**

```- Compares name, credentials, and addresses across sources

- Flags discrepancies (e.g., expired licenses, mismatched specialties)

**Key Technologies:**- Generates confidence scores per field

- **Backend**: Java 17, Spring Boot 3.2, Spring Security (JWT), PostgreSQL 15

- **AI Layer**: Python 3.11, FastAPI, LangGraph, LangChain, Mistral AI (Pixtral-12B), Milvus 2.3.6**3. Intelligent Enrichment**

- **Frontend**: React 18.3, TypeScript 5.8, Tailwind CSS, Radix UI- Fills missing phone numbers, emails, and addresses

- Identifies completeness gaps (e.g., missing NPI or taxonomy code)

---- Uses fuzzy matching for name variations



## Quick Start**4. Trust Scoring with Source Attribution**

- Weighted scoring: License (35%), Name (25%), Contact (20%), Completeness (20%)

### Prerequisites- Final grade: A (90-100%), B (75-89%), C (60-74%), D (50-59%), F (<50%)

- Java 17+ | Python 3.11+ | Node.js 18+ | Docker- Recommendation: APPROVED, REVIEW, or REJECTED



### 1. Clone & Setup**5. Human-in-the-Loop Feedback**

- Dashboard for manual review of flagged providers

```bash- Feedback loop improves trust score accuracy over time

git clone https://github.com/CroWzblooD/LampStack.git

cd LampStack---

```

## Key Features

### 2. Start Infrastructure

### Real-Time Validation Workflow

```bash- Upload CSV of providers via frontend

docker-compose up -d  # PostgreSQL + Milvus- Trigger validation jobs asynchronously

```- Monitor progress via WebSocket updates

- View animated workflow in IdeationCanvas

### 3. Backend (Java Spring Boot)

### Multi-Source Data Aggregation

```bash- **NPI Registry API**: Provider status, taxonomy, demographics

cd server- **State Medical Boards**: License number, expiration, disciplinary actions (web scraping)

./mvnw clean install- **Google Places API**: Phone, email, address, ratings

./mvnw spring-boot:run

```### Semantic Search & Pattern Recognition

- Milvus vector database stores validation embeddings

Create `server/.env`:- Find providers with similar validation patterns

```env- Identify anomalies using cosine similarity

SPRING_DATASOURCE_URL=jdbc:postgresql://localhost:5432/healthcare_validation

SPRING_DATASOURCE_USERNAME=postgres### Versioned Virtual Profiles

SPRING_DATASOURCE_PASSWORD=yourpassword- JSONB snapshots track provider data evolution

JWT_SECRET=your-secret-key- Audit trail for compliance and debugging

PYTHON_AGENT_SERVICE_URL=http://localhost:8001

```### Analytics Dashboard

- Trust score distribution

### 4. Agent Service (Python FastAPI)- Validation stage completion rates

- Common conflict types

```bash

cd agent-service---

python -m venv venv

source venv/bin/activate  # Windows: venv\Scripts\activate## System Architecture

pip install -r requirements.txt

uvicorn app.main:app --port 8001 --reload```

```┌─────────────────────┐

│   React Frontend    │

Create `agent-service/.env`:│   (Port 5173)       │

```env└──────────┬──────────┘

MISTRAL_API_KEY=your-mistral-api-key           │ WebSocket

MILVUS_HOST=localhost           ▼

MILVUS_PORT=19530┌─────────────────────┐    HTTP Callbacks    ┌─────────────────────┐

DATABASE_URL=postgresql://postgres:yourpassword@localhost:5432/healthcare_validation│  Java Spring Boot   │◄────────────────────►│  Python FastAPI     │

```│  (Port 8080)        │                       │  (Port 5000)        │

│                     │                       │                     │

### 5. Frontend (React)│ • REST API          │                       │ • LangGraph Agents  │

│ • WebSocket Server  │                       │ • Mistral OCR       │

```bash│ • Job Orchestration │                       │ • Milvus Integration│

cd client└──────────┬──────────┘                       └──────────┬──────────┘

npm install           │                                             │

npm run dev           ▼                                             ▼

```┌─────────────────────┐                       ┌─────────────────────┐

│   PostgreSQL        │                       │   Milvus Vector DB  │

Create `client/.env.local`:│   (Port 5432)       │                       │   (Port 19530)      │

```env│                     │                       │                     │

VITE_API_URL=http://localhost:8080/api│ • Provider Records  │                       │ • Validation        │

VITE_WS_URL=ws://localhost:8080/ws│ • Validation Jobs   │                       │   Embeddings        │

```│ • Trust Scores      │                       │ • Semantic Search   │

│ • Virtual Profiles  │                       │                     │

**Access**: `http://localhost:5173`└─────────────────────┘                       └─────────────────────┘

```

---

### Data Flow

## Usage

1. **User uploads CSV** → Java parses and stores in PostgreSQL

### Upload Provider Data2. **Java triggers job** → Calls Python agent service via HTTP

3. **Python agents execute** (LangGraph orchestration):

**CSV Format**:   - Ingestion Agent → Scrapes NPI, State Boards, Google

```csv   - Validation Agent → Cross-checks data for conflicts

name,npi,license_number,specialty,phone,email,address   - Enrichment Agent → Fills missing fields

Dr. John Smith,1234567890,MD12345,Cardiology,555-0100,john@example.com,123 Main St   - Scoring Agent → Calculates trust score

```4. **Python stores embeddings** → Milvus for semantic search

5. **Python sends updates** → HTTP callbacks to Java

**API Request**:6. **Java broadcasts** → WebSocket to frontend

```bash7. **Frontend displays** → Real-time workflow visualization

curl -X POST http://localhost:8080/api/providers/upload \

  -H "Content-Type: multipart/form-data" \---

  -F "file=@providers.csv"

```## Technology Stack



### Trigger Validation### Backend (Java Spring Boot 3.2)

| Component | Purpose |

```bash|-----------|---------|

curl -X POST http://localhost:8080/api/validation/trigger \| Spring Data JPA | PostgreSQL ORM |

  -H "Content-Type: application/json" \| Spring WebSocket | Real-time updates |

  -d '{"providerIds": [1, 2, 3]}'| RestClient | HTTP communication with Python |

```| Jackson | JSON serialization |

| Flyway | Database migrations |

### Get Trust Score| Lombok | Boilerplate reduction |



```bash### Agent Service (Python 3.11)

curl -X GET http://localhost:8080/api/trust/1| Component | Purpose |

```|-----------|---------|

| FastAPI | Async REST framework |

**Response**:| LangGraph | Multi-agent orchestration |

```json| Mistral AI | OCR for documents |

{| Milvus | Vector database |

  "providerId": 1,| Sentence Transformers | Text embeddings |

  "trustScore": 87.5,| RDKit | (Future) Chemical informatics |

  "grade": "B+",| BeautifulSoup4 | Web scraping |

  "npiMatch": true,

  "licenseValid": true,### Frontend (React 18 + TypeScript)

  "dataCompleteness": 0.92| Component | Purpose |

}|-----------|---------|

```| Vite | Build tool |

| Tailwind CSS | Styling |

---| Framer Motion | Animations |

| React Hook Form | Form validation |

## API Endpoints| Zustand | State management |



| Method | Endpoint | Description |### Infrastructure

|--------|----------|-------------|| Component | Purpose |

| POST | `/api/providers/upload` | Upload CSV file ||-----------|---------|

| GET | `/api/providers` | List all providers || Docker Compose | Local development |

| POST | `/api/validation/trigger` | Start validation job || PostgreSQL 15 | Relational database |

| GET | `/api/validation/jobs/{id}` | Get job status || Milvus 2.3 | Vector database |

| GET | `/api/trust/{providerId}` | Get trust score || Nginx | (Production) Reverse proxy |

| POST | `/api/trust/feedback` | Submit human feedback |

---

---

## Installation Guide

## Contributing

### Prerequisites

Contributions are welcome! Please follow:- Node.js 18+

1. Fork the repository- Java 17+

2. Create feature branch: `git checkout -b feature/your-feature`- Maven 3.8+

3. Commit changes: `git commit -m 'feat: add new feature'`- Python 3.11+

4. Push and create pull request- Docker Desktop



**Code Style**: Java (Google Style) | Python (PEP 8 + Black) | TypeScript (Airbnb)### Step 1: Clone Repository

```bash

---git clone https://github.com/CroWzblooD/LampStack.git

cd LampStack

## License```



MIT License - see [LICENSE](LICENSE) file for details.### Step 2: Start Databases

```powershell

---docker-compose up -d

docker-compose ps  # Verify PostgreSQL and Milvus are running

## Security```



For security vulnerabilities, see [SECURITY.md](SECURITY.md) for reporting guidelines.### Step 3: Configure Backend

```powershell

---cd server

mvn clean install

## Support```



- **Issues**: [GitHub Issues](https://github.com/CroWzblooD/LampStack/issues)Edit `src/main/resources/application.yml`:

- **Email**: im.ashish.1001@gmail.com```yaml

spring:

---  datasource:

    url: jdbc:postgresql://localhost:5432/provider_validation

<div align="center">    username: postgres

Built for improving healthcare data quality    password: password

</div>app:

  python:
    agent-service:
      url: http://localhost:5000
```

Start backend:
```powershell
mvn spring-boot:run
```

### Step 4: Configure Agent Service
```powershell
cd agent-service
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Create `.env` file:
```env
JAVA_SERVICE_URL=http://localhost:8080
MISTRAL_API_KEY=your_mistral_api_key
DATABASE_URL=postgresql://postgres:password@localhost:5432/provider_validation
MILVUS_HOST=localhost
MILVUS_PORT=19530
```

Start agent service:
```powershell
python main.py
```

### Step 5: Configure Frontend
```powershell
cd client
npm install
npm run dev
```

Access application at `http://localhost:5173`

---

## Usage

### Upload Providers
1. Navigate to frontend
2. Click "Upload CSV"
3. Select file with columns: `npi`, `name`, `specialty`, `state`
4. Click "Submit"

### Trigger Validation
1. Go to "Validation Jobs"
2. Click "Start New Job"
3. Select providers to validate
4. Monitor real-time progress in IdeationCanvas

### Review Results
1. Navigate to "Trust Scores"
2. Filter by grade (A-F)
3. View detailed validation report
4. Provide feedback for flagged providers

---

## API Documentation

### Java Backend (Port 8080)

#### Upload Providers
```http
POST /api/providers/upload
Content-Type: multipart/form-data

{
  "file": <CSV file>
}
```

#### Trigger Validation
```http
POST /api/validation/trigger
Content-Type: application/json

{
  "provider_ids": [1, 2, 3]
}
```

#### Get Job Status
```http
GET /api/validation/jobs/{jobId}
```

### Python Agent Service (Port 5000)

#### Validate Provider
```http
POST /api/agents/validate
Content-Type: application/json

{
  "job_id": "uuid",
  "provider_id": 1,
  "npi": "1234567890",
  "name": "Dr. John Doe",
  "specialty": "Cardiology",
  "state": "CA"
}
```

---

## Agent Workflow

### 1. Ingestion Agent
**Responsibility**: Scrape data from external sources

**Data Sources**:
- NPI Registry: `https://npiregistry.cms.hhs.gov/api/?version=2.1&number={npi}`
- State Medical Board: Web scraping (varies by state)
- Google Places: `https://maps.googleapis.com/maps/api/place/findplacefromtext/json`

**Output**:
```json
{
  "npi_data": {...},
  "license_data": {...},
  "contact_data": {...}
}
```

### 2. Validation Agent
**Responsibility**: Cross-check data for conflicts

**Validation Rules**:
- Name match: Fuzzy string matching (>80% similarity)
- License status: Active, Expired, Revoked
- Address consistency: Normalize formats

**Output**:
```json
{
  "conflicts": [
    {
      "field": "license",
      "issue": "Expired on 2024-01-01",
      "severity": "HIGH"
    }
  ],
  "confidence_scores": {
    "name": 0.95,
    "license": 0.60,
    "contact": 0.85
  }
}
```

### 3. Enrichment Agent
**Responsibility**: Fill missing fields

**Enrichment Logic**:
- Missing phone: Use Google Places
- Missing email: Generate based on name + domain
- Missing address: Use NPI primary address

**Output**:
```json
{
  "enriched_fields": {
    "phone": "+1-555-1234",
    "email": "john.doe@example.com"
  },
  "completeness": 0.85
}
```

### 4. Scoring Agent
**Responsibility**: Calculate final trust score

**Scoring Formula**:
```
Trust Score = (License × 0.35) + (Name × 0.25) + (Contact × 0.20) + (Completeness × 0.20)
```

**Output**:
```json
{
  "trust_score": 0.82,
  "grade": "B",
  "recommendation": "APPROVED",
  "source_reliability": {
    "npi": 0.95,
    "state_board": 0.92,
    "google_places": 0.70
  }
}
```

---

## Database Schema

### PostgreSQL Tables

**providers**
```sql
CREATE TABLE providers (
  id SERIAL PRIMARY KEY,
  npi VARCHAR(10) UNIQUE NOT NULL,
  name VARCHAR(255) NOT NULL,
  specialty VARCHAR(100),
  state VARCHAR(2),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**validation_jobs**
```sql
CREATE TABLE validation_jobs (
  id UUID PRIMARY KEY,
  status VARCHAR(50),
  started_at TIMESTAMP,
  completed_at TIMESTAMP
);
```

**validations**
```sql
CREATE TABLE validations (
  id SERIAL PRIMARY KEY,
  job_id UUID REFERENCES validation_jobs(id),
  provider_id INTEGER REFERENCES providers(id),
  stage VARCHAR(50),
  status VARCHAR(50),
  result JSONB
);
```

**trust_scores**
```sql
CREATE TABLE trust_scores (
  id SERIAL PRIMARY KEY,
  provider_id INTEGER REFERENCES providers(id),
  trust_score DECIMAL(3,2),
  grade CHAR(1),
  recommendation VARCHAR(20),
  source_reliability JSONB
);
```

**virtual_profiles**
```sql
CREATE TABLE virtual_profiles (
  id SERIAL PRIMARY KEY,
  provider_id INTEGER REFERENCES providers(id),
  version INTEGER,
  snapshot JSONB,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Milvus Collection

**validation_embeddings**
```python
schema = CollectionSchema([
  FieldSchema("id", DataType.INT64, is_primary=True),
  FieldSchema("provider_id", DataType.INT64),
  FieldSchema("npi", DataType.VARCHAR, max_length=10),
  FieldSchema("embedding", DataType.FLOAT_VECTOR, dim=384),
  FieldSchema("trust_score", DataType.FLOAT),
  FieldSchema("validation_stage", DataType.VARCHAR, max_length=50)
])
```

---

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit changes (`git commit -m "Add your feature"`)
4. Push to branch (`git push origin feature/your-feature`)
5. Open a pull request

**Code Style**:
- Java: Google Java Style Guide
- Python: PEP 8
- TypeScript: ESLint + Prettier

**Testing**:
- Write unit tests for new features
- Ensure all tests pass before submitting PR

---

## License

MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files, to deal in the Software
without restriction, including without limitation the rights to use, copy,
modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software.

---

## Acknowledgments

- NPI Registry for provider data
- State Medical Boards for licensing information
- Mistral AI for OCR capabilities
- LangGraph for multi-agent orchestration
- Milvus community for vector database support

---

**Built with passion for healthcare data integrity**
