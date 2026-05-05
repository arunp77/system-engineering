## 4. Phase 3 — Model-Based Systems Engineering

### 4.1 Overview

Model-Based Systems Engineering (MBSE) is the modern approach to SE in which formal models replace or supplement traditional document-based methods. Instead of managing requirements and designs in Word documents and spreadsheets, MBSE uses structured models that capture the system's structure, behaviour, and requirements in a single coherent representation. EUMETSAT job postings consistently require practical experience with MBSE tools and SysML.

### 4.2 SysML — Systems Modeling Language

SysML is the primary modelling language for MBSE. It is a subset and extension of UML (Unified Modeling Language), adapted for systems engineering. SysML provides nine diagram types, of which the following are most important for ground segment systems engineering:

- **Block Definition Diagram (BDD)**: Defines the hierarchy and structure of the system, showing how blocks (representing hardware, software, or functions) relate to each other, their properties, and their interfaces. Analogous to a component decomposition tree.
- **Internal Block Diagram (IBD)**: Shows the internal structure of a single block — its ports, interfaces, and the connections between them. Used to model data flows and physical interfaces between subsystems.
- **Requirements Diagram**: Represents requirements as model elements and shows their derivation, refinement, and verification relationships. Enables graphical traceability.
- **Use Case Diagram**: Captures high-level system functions from the perspective of external actors (users, operators, other systems). Used in early mission analysis and operational concept definition.
- **Activity Diagram**: Models dynamic behaviour — workflows, data flows, control flows. Useful for modelling operations procedures and data processing pipelines.
- **Sequence Diagram**: Models time-ordered interactions between system elements. Used for modelling command-response sequences in satellite operations.
- **State Machine Diagram**: Models the modes and states of a system or subsystem and the transitions between them. Essential for modelling satellite and ground system operational modes. 

### 4.3 MBSE Tools

**Capella / Arcadia (Priority Tool)**

Capella is an open-source MBSE tool developed by Thales and now maintained by the Eclipse Capella open-source project. It is based on the Arcadia methodology, a structured approach to system and software architecture. Capella is widely used in European defence and space industries and is the recommended starting tool because it is free, well-documented, and methodologically guided.

Capella structures the model in four layers: Operational Analysis (what the system must do in operational context), System Analysis (what the system does), Logical Architecture (how the system is functionally structured), and Physical Architecture (how the system is physically implemented). This top-down decomposition approach is directly applicable to EUMETSAT ground segment design.

Practical steps:
- Download Capella from eclipse.dev/capella (free)
- Work through the official "Capella Day" training materials and the Arcadia/Capella tutorial model (Air Traffic Management example)
- Model a simplified version of the EUMETSAT EPS-SG ground segment as a personal exercise

**MagicDraw / Cameo Systems Modeler**

MagicDraw (now rebranded as Cameo Systems Modeler by No Magic/Dassault Systèmes) is the leading commercial MBSE tool and is widely used in the space industry. A student/trial license is available. It is more flexible than Capella but less methodologically guided. Knowledge of both tools is valuable.

**Papyrus**

Another open-source option within the Eclipse ecosystem, supporting UML and SysML. Less widely used in industrial contexts than Capella or MagicDraw but useful for learning SysML notation.

### 4.4 MBSE and Python Integration

Given your Python background, a differentiating skill is the ability to interact with MBSE models programmatically. Several approaches exist:

- **PyMBSE**: A Python library for creating and manipulating MBSE models
- **Capella's Python4Capella addon**: Allows Python scripting to query and manipulate Capella models, generate reports, extract data, and automate repetitive modelling tasks
- **Generating traceability reports**: Writing Python scripts that read DOORS or Capella model exports (XML/JSON) and produce custom traceability matrices or dashboards

This intersection of MBSE and Python scripting is not commonly mastered and would distinguish you in a SE role.
