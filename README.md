# Process as a System II: An Organic Development Lifecycle Model for Systems Engineering

## Introduction

### Organic development
1. Development is done by humans
2. Needs to be executable organically by humans
3. Some issues with system development are caused by inorganic processes
   1. Against human thought process
      1. Requirements, Architecture, Implementation
   2. Against physical existence
      1. Documents and specification

Systems development (for the time being) is conducted by human beings with the support of technology through tools, software, and electronics. While a lot of focus is set on the technology aspect of systems engineering, little attention is given to the human aspects regarding the understanding and performance of systems engineering processes.

### Illusion of explanatory depth
   1. The sense that one understands complex issues more deeply than one does.
      1. Quickly rate knowledge of various issues x/10 (t1 rating)
      2. Ask to deeply one issue
      3. Re-rate the knowledge of issue (t3 rating)

We seldomly are asked to really explain a concept.

*See: intellectual humility*

Questions:
- Requirements engineering
  - How does requirements engineering support the development?
  - What does an appropriate breakdown of requirements depend on?
  - To which type of artifacts within the architectural design should requirements be linked?
  - How does linking requirements to the architectural design support the development?
  - How do you identify requirements that should be covered by unit tests?
  - How do you identify requirements that should be covered by integration tests?
- Architectural design
  - How does architectural design support the development?
  - Which types of artifacts are used within an architectural design?
  - How does architectural design differ from detailed design?
  - What does the appropriate level of detail of architectural design depend on?
  - Why are interface definitions part of the architectural design instead of the implementation?
  - What is the difference between an interaction and an interface?
  - Are interfaces static or dynamic definitions?
- Detailed design
  - How does detailed design support the development?
  - What does the appropriate level of detail for detailed design depend on?
- Unit construction
  - What does the identification of a unit depend on?
- Unit verification
- Integration
  - What does the identification of a component/module depend on?
- Integration test
- Release
- Qualification test
- Verification
- Validation

Survey:
- Avoid "it depends" answers: WHAT does it depend on
- Control set of questions
- Get honest answers, how?
- Avoid personal judgements
- Questions that require explanations not facts/statements

### Hill climbing

Incremental improvement finds local maxima

Finding the global maximum requires non-incremental improvement

## Scope of this Document

Relationship instead of interaction, interface, dependency

### First principles thinking

1. Establish purpose
2. Understand elements and their function
3. Challenge pre-existing concepts
4. Re-align the model towards the purpose

### Structure leads behavior

### Real world development
1. Development concepts should suit to real world practice
2. Existing development concepts 
   1. V-Model creates unnecessary abstraction at the architecture/integration levelx
   2. Agility is perceived as a counter to v-model, which it is not
   3. PDCA is too high level
3. Building an energy efficient house
   1. Some of the work can only be done in a series
   2. Some of the work can be parallel

### No difference between system/software/hardware/mechanic

### No difference between unit/component

### Design is not documentation

### Hierarchy model for development artifacts

### Algorithm for development activities

## An organic flow of development activities

### The purpose of a development lifecycle
1. The development lifecycle model shall guide the required activities and artifacts, to ensure the development achieves its purpose.
2. The development purpose, shall include customer satisfaction, to ensure that customer needs are met.

### The fundamental development elements

```mermaid
   flowchart LR
      Plan-->Do
      Do-->Check
      Check-->Act
      Act-->Plan
```
*Each step is an activity*

```mermaid
   flowchart LR
    Mission["?"]
    Design["§"]
    Implementation["!"]
    Feedback["&"]
    
    Implementation--"check"-->Feedback
    Feedback--"act"-->Mission
    Mission--"plan"-->Design
    Design--"do"-->Implementation
```

```mermaid
   flowchart LR
    Mission
    Design
    Implementation
    Feedback
    
    Implementation--"check"-->Feedback
    Feedback--"act"-->Mission
    Mission--"plan"-->Design
    Design--"do"-->Implementation
```

### Keeping the problem space and solution space separate


```mermaid
   flowchart LR
      subgraph  Solution
         !
      end

      subgraph  Problem
         ?
      end
      
      ?-->!
```

1. The house shall be energy efficient.

```mermaid
   flowchart LR
      subgraph  Solution
         Design
         System
      end
      
      subgraph  Problem
         Feedback
         Mission
      end

      Mission--"plan"-->Design
      Design--"do"-->System
      System--"check"-->Feedback
      Feedback--"act"-->Mission
```

The heat pump should create less than 100g carbon dioxide equivalent.


1. "Technical" requirements is meaningless
2. Stakeholder needs vs System requirements
   1. 
3. Needs preferred to stakeholder requirement
4. Needs are problem artifacts
5. Requirements are design artifacts

```mermaid
   flowchart LR
      subgraph Solution
        subgraph Design
            Requirements
         end
         Implementation
      end
      
      subgraph Problem
         Feedback
         subgraph Mission
            Needs
         end
      end

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission
```

### Mission control

```mermaid
   flowchart LR
      subgraph Design
         Requirements
      end

      Implementation

      Feedback
  
      subgraph Mission
         Stakeholders
         Objectives
         Needs
      end
      
      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission

      Stakeholders--"specify"-->Objectives
      Objectives--"elicit"-->Needs
```

### System of systems

```mermaid
   flowchart LR
      subgraph Design
         Requirements
      end

      subgraph Implementation
         System["System"]
         Parts["Parts"]
      end
   
      Feedback

      subgraph Mission
         Stakeholders
         Objectives
         Needs
      end

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission

      Parts--"integrate"-->System
      Parts--"integrate"-->Parts
      System~~~Parts

      Stakeholders--"specify"-->Objectives
      Objectives--"elicit"-->Needs
```

### Systems Thinking

Systems thinking is an approach to abstract a system and its parts into a model as elements and relationships between elements. As the system contains parts and those parts contain other parts, so does the model and its elements. Every part of the system is directly represented by an element and its relationships. An element demarcates the boundaries of a part, while the relationships connect it to other parts.

```mermaid
   flowchart LR
      subgraph Design["Design Model"]
         subgraph Model["System Model"]
            Elements
            Relationships
         end
         Requirements
      end

      subgraph System
         Parts["Parts"]
      end

      subgraph Mission
         Needs
      end

      Parts--"integrate"-->Parts

       Elements~~~Requirements
      Relationships~~~Requirements


      Requirements~~~Parts

      Needs--"analyze"-->Elements
      Elements--"configure"-->Relationships
      Elements--"configure"-->Elements

      Elements<-."represents".->Parts
```


Using this abstraction one can understand the complexity of the system.

Another way of looking at this abstraction is to understand its complexity


Structure yields behavior -> It is important to structure the model organically to ensure that development takes place organically.

### Systems Design

The word "design" has its origins in the Latin word "designare," which originally meant "to mark out," "to choose," or "to appoint." In the context of systems engineering design activities can be seen as a series of choices based on the analysis of preconditions or alternatives for the system. The design documents choices regarding the makeup of the system by assigning requirements to specific elements or relationships. These choices support the development of the system for low complexity through, decoupling, separation, and simplification. The depth of the model shall support the effective allocation of the requirements, meaning that the chosen element or relationship can actually implement the requirement.

```mermaid
   flowchart LR
      subgraph Design
         subgraph Model
            Elements
            Relationships
         end
         Requirements
      end

      subgraph System
         Parts["Parts"]
      end

      subgraph Mission
         Needs
      end

      Parts--"integrate"-->Parts

      Elements--"allocate"-->Requirements
      Relationships--"allocate"-->Requirements
      Requirements--"implement"-->Parts

      Needs--"analyze"-->Elements
      Elements--"configure"-->Relationships
      Elements--"configure"-->Elements

      Elements<-."represents".->Parts
      Design<-."represents".->System
```

In traditional systems engineering processes, requirements engineering is seen as a precursor to design activities, despite the fact that a requirement can not be formulated without referencing elements from within the design. In this development lifecycle the design definition can not be separated, a requirement is dependent on the definition of its element and an element is characterized by its requirement.

Concepts, Diagrams are requirements

### V-model

The v-model introduces the aspect of verifying the system based on the defined design and validating based on the defined needs. This ensures two crucial objectives within system engineering, building the right system (validation), the right way (verification).

*TODO: Add image v-model*

One of the common issues with the v-model is the question of: what is the appropriate level of detail for testing? The model establishes abstraction layers between unit tests, integration tests, qualification tests, acceptance tests, and so on. These artificial separations are based on the separation of units, components, architectural design and detailed design. Yet, there is no common definition of what each of those artifacts are, or how to identify them. They are largely based on individual organizational needs and add little benefit to the development process itself. Even worse, when used to structure organizations they cause unproductive process separations that are here to stay.

With the use of an organic design model verification strategies can be appropriately applied, as the focus of the verification can be determined by an element's position and surroundings in the model. An implemented part can be tested according to the requirements that are directly specified for its element in the model. Once integrated, the element’s relationships and their requirements determine the integration tests. After all relevant parts are integrated and the system is to be base lined, all verification tests can be executed. This approach offers a nuanced and automate-able approach to verification testing without the need for an artificial hierarchy of units, parts, and components.

```mermaid
   flowchart LR
      subgraph Design
         Elements
         Relationships
         Requirements
      end

      subgraph Implementation
         subgraph Tests
            UC["Use cases"]
            TC["Test cases"]
         end
         System["System"]
         Parts["Parts"]
      end
   
      subgraph Feedback
      end

      subgraph Mission
         Needs
      end

      Feedback--"act"-->Mission

      Parts--"integrate"-->System
      Parts--"integrate"-->Parts
      System~~~Parts

      Elements--"specify"-->Requirements
      Relationships--"specify"-->Requirements
      Requirements--"implement"-->Parts

      Needs--"demarcate"-->Elements
      Elements--"coordinate"-->Relationships
      Elements--"integrate"-->Elements

      Needs--"specify"-->UC
      Requirements--"specify"-->TC

      Parts--"verify"-->TC
      System--"verify"-->TC
      System--"validate"-->UC

      TC--"collect"-->Feedback
      UC--"collect"-->Feedback
```

- **Objective**: The development process ensures that the system has no undesirable or unnecessary parts.
  - **Need**: The development process implements a system according to the design.
    - **Test cases**
      - verifies the achievement of a requirement
      - **Verify Parts**
        - After implementation of a part, verify all requirements of its respective element via their respective test cases.
        - After integration of a part, verify all requirements of its respective element's relationships via their respective test cases.
      - **Verify System**
        - After integration of all relevant parts into the system, verify all requirements via their respective test cases.
  - **Need**: The development process implements a system that satisfies the needs.
    - **Use cases**
      - **Validate System**
        - After integration of all relevant parts into the system, validate all needs via their respective use cases.

### Model Based Systems Engineering

Needs to connect properly to architecture before actually being used

Design vs Code generation

Values & Signals

Generation

```mermaid
   flowchart LR
      subgraph Analysis
         subgraph Design
            subgraph Model
               Elements
               Relationships
            end
            Requirements
         end
      end

      subgraph Synthesis
         subgraph Realization
            Properties
            Interfaces
            Behaviors
         end

         subgraph System
            Parts["Parts"]
         end
      end

      Elements--allocate-->Requirements
      Relationships--allocate-->Requirements

      Elements--"configure"-->Relationships
      Elements--"configure"-->Elements

      Requirements--implement-->Behaviors
      Elements--implement-->Properties
      Relationships--implement-->Interfaces

      Properties--integrate-->Parts
      Interfaces--integrate-->Parts
      Behaviors--integrate-->Parts
      Parts--integrate-->Parts
```

## An organic hierarchy of development artifacts

```mermaid
   flowchart LR
      A
      B
      A--"transfer"-->B
      B-."retrieval".->A
```

### Negative effect of documents

### Entities


```mermaid
   erDiagram
      System }|..|| Development : asd
      Stakeholders }|..|| Development : asd
      Model }|..|| Development : asd
      
      Parts }|..|| System : asd
      Parts ||..|| Elements : asd

      Elements }|..|| Model : asd
      Relationships }|..|| Elements : asd
      Requirements }|..|| Elements : asd
      Requirements }|..|| Relationships : asd

      Objectives }|..|| Stakeholders : asd
      Needs }|..|| Objectives : asd


```

      Requirements }|..|| Needs : asd
      Requirements ||..|| Parts : asd


## Summary

- Requirements are design artifacts

### Development flow

## Addendum

### Agile

Works as well -> Stories

Implications:
- 2 weeks makes no sense

### System of systems

#### Maturity & Iterations

- 2 week iteration makes no sense, depends on depths of design and implementation for a single need

### Quality
