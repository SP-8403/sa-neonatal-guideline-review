%%{init: {
  "theme": "default",
  "flowchart": { "useMaxWidth": false },
  "themeVariables": {
    "fontSize": "26px",
    "nodeSpacing": 110,
    "rankSpacing": 120
  }
}}%%

flowchart TB

A([Apnoea Episode Detected]):::start
A --> B[Assess Airway<br/>Breathing<br/>Circulation]:::assessment

B --> C{Is the Baby Stable?}:::decision

C -->|No| D[Immediate Stabilisation<br/>Airway Support<br/>Oxygen<br/>Monitoring]:::urgent
C -->|Yes| E[Gentle Tactile Stimulation<br/>Reposition Airway]:::action

D --> F[Monitor Heart Rate<br/>Respiratory Effort<br/>Oxygen Saturation]:::assessment
E --> F

F --> G{Recurrent Apnoea?}:::decision

G -->|No| H[Observe and Continue Monitoring]:::observe
G -->|Yes| I[Investigate Reversible Causes]:::assessment

%% Causes row

J[Check Blood Glucose]:::action
K[Check Temperature]:::action
L[Assess Infection Risk]:::action
M[Review Medications]:::action
N[Assess Airway Position]:::action

J --- K --- L --- M --- N

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

O --> P{Preterm Baby?}:::decision

P -->|Yes| Q[Consider Respiratory Stimulant Therapy<br/>according to gestational age<br/>and local protocol]:::treatment
P -->|No| R[Treat Identified Cause]:::action

Q --> S{Persistent Apnoea?}:::decision
R --> S

S -->|No| H
S -->|Yes| T[Start CPAP<br/>Respiratory Support]:::treatment

T --> U{Failure of Non-Invasive Support?}:::decision

U -->|No| H
U -->|Yes| V[Intubation<br/>Mechanical Ventilation]:::urgent

V --> W[Refer to Higher Level of Care]:::refer


%% Colour styling

classDef start fill:#196B24,color:#ffffff,stroke-width:0
classDef assessment fill:#2F8F83,color:#ffffff,stroke-width:0
classDef decision fill:#2A6F97,color:#ffffff,stroke-width:0
classDef action fill:#E8F4F3,color:#000000,stroke-width:0
classDef treatment fill:#E69F00,color:#000000,stroke-width:0
classDef urgent fill:#C0392B,color:#ffffff,stroke-width:0
classDef observe fill:#F4F6F6,color:#000000,stroke-width:0
classDef refer fill:#2C3E50,color:#ffffff,stroke-width:0
