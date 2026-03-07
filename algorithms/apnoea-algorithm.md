# Recognition and Management of Apnoea in the Newborn

```mermaid
flowchart TD

A([Apnoea Episode Detected]):::start
A --> B[Assess Airway, Breathing, Circulation]:::assessment

B --> C{Is the Baby Stable?}:::decision

C -->|No| D[Immediate Stabilisation<br/>Airway Support<br/>Oxygen<br/>Monitoring]:::urgent
C -->|Yes| E[Gentle Tactile Stimulation<br/>Reposition Airway]:::action

D --> F[Monitor Heart Rate<br/>Respiratory Effort<br/>Oxygen Saturation]:::assessment
E --> F

F --> G{Recurrent Apnoea?}:::decision

G -->|No| H[Observe and Continue Monitoring]:::observe
G -->|Yes| I[Investigate Reversible Causes]:::assessment

subgraph Causes
J[Check Blood Glucose]:::action
K[Check Temperature]:::action
L[Assess Infection Risk]:::action
M[Review Medications]:::action
N[Assess Airway Position]:::action
end

I --> J
I --> K
I --> L
I --> M
I --> N

J --> O[Correct Underlying Cause]:::action
K --> O
L --> O
M --> O
N --> O

O --> P{Preterm Infant?}:::decision

P -->|Yes| Q[Start Caffeine Therapy]:::treatment
P -->|No| R[Treat Identified Cause]:::action

Q --> S{Persistent Apnoea?}:::decision
R --> S

S -->|No| H
S -->|Yes| T[Start CPAP / Respiratory Support]:::treatment

T --> U{Failure of Non-Invasive Support?}:::decision

U -->|No| H
U -->|Yes| V[Intubation and Mechanical Ventilation]:::urgent

V --> W[Refer to Higher Level of Care]:::refer

classDef start fill:#196B24,color:#ffffff,stroke:#0b3d16,stroke-width:2px
classDef assessment fill:#2F8F83,color:#ffffff
classDef decision fill:#2A6F97,color:#ffffff
classDef action fill:#E8F4F3,color:#000000,stroke:#2F8F83
classDef treatment fill:#E69F00,color:#000000
classDef urgent fill:#C0392B,color:#ffffff
classDef observe fill:#F4F6F6,color:#000000
classDef refer fill:#8E44AD,color:#ffffff
