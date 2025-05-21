## Methodology at a Glance

```mermaid
flowchart LR
    A[LMS Content] --> ETL[Extract + Clean]
    ETL --> VEC[Vector Index]
    ETL --> BM[BM25 Index]
    VEC --> PROMPT
    BM  --> PROMPT
    PROMPT --> LLM[Llama 2 MCQ]
    LLM --> QUIZ[Quiz JSON]
    QUIZ --> CHAT[Student UI]
    CHAT --> GAP[Analytics]
    GAP -->|Reinforce| VEC
    GAP -->|Dash| DASH[Instructor Dashboard]