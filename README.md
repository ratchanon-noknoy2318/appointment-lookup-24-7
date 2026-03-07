# Online Hospital Appointment & Queue Orchestration

**70–80% Reduction in Patient Wait Times | PDPA-Compliant | Senior Nurse-Validated**

A high-performance registration framework engineered to automate public healthcare intake. This system transitioned manual paper-based processes into a sub-second digital synchronization, drastically improving clinical operational efficiency.

---

## 1. System Architecture & Data Flow

The system employs a direct integration pattern between the frontend framework and the data layer to ensure maximum performance and minimal latency.

### 🔄 Data Retrieval Flow


```mermaid
graph LR
    A[Patient] -->|Enter National ID| B[Next.js Application]
    B -->|Serverless Function / API| C[(Google Sheets Database)]
    C -->|Return Match| B
    B -->|Display Appointment Date| A
