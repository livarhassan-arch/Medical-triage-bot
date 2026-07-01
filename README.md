### System Data Flow Architecture
```mermaid
graph TD
    A[User Input: Symptom & Vitals] --> B(Patient Object Created)
    B --> C{TriageEngine Evaluation}
    C -->|Step 1| D[Match Baseline Symptom Protocol]
    C -->|Step 2| E[Calculate Physiological Vitals Risk Score]
    D --> F{Override Assessment Matrix}
    E --> F
    F -->|Risk Score >= 3| G[Upgrade to RED Critical Override]
    F -->|Risk Score >= 1| H[Upgrade to YELLOW Vitals Override]
    F -->|Normal Vitals| I[Maintain Baseline Priority]
    G --> J[Output Formatted Triage Summary]
    H --> J
    I --> J
