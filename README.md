# Online Hospital Appointment & Queue Orchestration

**70–80% Reduction in Patient Wait Times | PDPA-Compliant | Senior Nurse-Validated**

A high-performance registration framework engineered to automate public healthcare intake. This system transitioned manual paper-based processes into a sub-second digital synchronization, drastically improving clinical operational efficiency.

---

## 1. System Architecture & Data Flow

The system employs a direct integration pattern between the frontend framework and the data layer to ensure maximum performance and minimal latency.

### 🔄 Data Retrieval Flow


```mermaid
graph TD
    subgraph Client_Interface [Client-Side Interface]
        A[Patient / User] -->|1. Input National ID| B[Next.js Web Application]
        B -->|5. Reactive UI Update| A
    end

    subgraph Serverless_Orchestration [Logic & Parsing Layer]
        B -->|2. HTTPS GET Request| C{Vercel Edge Gateway}
        C -->|2.1 Data Sanitization| D[CSV Parser Middleware]
        D -->|4. Filtered JSON Result| B
    end

    subgraph Persistence_Layer [Cloud Data Store]
        D -->|3. Fetch CSV Stream| E[(Google Sheets CSV Endpoint)]
        E -->|3.1 Return Raw Data| D
    end

    %% Visual Styling
    style B fill:#f9f,stroke:#333,stroke-width:2px
    style E fill:#007bff,color:#fff
    style C fill:#fff,stroke:#333,stroke-dasharray: 5 5
