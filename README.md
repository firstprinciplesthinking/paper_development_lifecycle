# Process as a System II: An Organic Development Lifecycle Model for Systems Engineering

## Introduction

### Organic development for organic resources
1. V-Model creates unnecessary abstraction at the architecture/integration level
2. Agility is perceived as a counter to v-model, which it is not
3. PDCA is too high level

### First principles
1. Establish purpose
2. Understand elements and their function
3. Challenge pre-existing concepts
4. Re-align the model towards the purpose

## Scope of this Document

### The purpose of a development lifecycle
1. The development lifecycle model shall guide the required activities and artifacts, to ensure the development achieves its purpose.
2. The development purpose, shall include customer satisfaction, to ensure that customer needs are met.
### Practical example
3. Building an energy efficient house
   1. Some of the work can only be done in a series
   2. Some of the work can be parallel
### Flow of development activities
### Hierarchy of development artifacts
### Requirements of activities & artifacts
### Model
### What's in
### What's out?

## An organic flow of development activities

### The fundamental development elements

#### The Deming(?) cycle
```mermaid
   flowchart LR
      Plan-->Do
      Do-->Check
      Check-->Act
      Act-->Plan
```
*Each step is an activity*

#### Activities and Artifacts shape the development lifecycle

```mermaid
   flowchart LR
    Mission["?"]
    Design["?"]
    Implementation["?"]
    Feedback["?"]
    
    Implementation--"check"-->Feedback
    Feedback--"act"-->Mission
    Mission--"plan"-->Design
    Design--"do"-->Implementation
```

#### Activities transform Artifacts

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

### Problem space solution space


```mermaid
   flowchart LR
      Problem-->Solution
```

1. The house shall be energy efficient.

#### Requirements connect Problem space with solution space

```mermaid
   flowchart LR
      subgraph  Solution
         Design
         Implementation
      end
      
      subgraph  Problem
         Mission
         Feedback
      end

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission
```

The heat pump should create less than 100g carbon dioxide equivalent.

### Design Thinking

#### Keeping the problem space and solution space separate

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
         subgraph Mission
            Needs
         end
         Feedback
      end

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission
```
### Systems Thinking

### Building blocks of a system model

```mermaid
   flowchart LR
      subgraph Solution
        subgraph Design
            Elements
            Relationships
            Requirements
         end
         Implementation
      end
      
      subgraph Problem
         subgraph Mission
            Needs
         end
         Feedback
      end

      Elements-."specify".->Requirements
      Elements-."specify".->Relationships
      Relationships-."specify".->Requirements

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission
```

### System of systems

```mermaid
   flowchart LR
      subgraph Solution
        subgraph Design
            Elements
            Relationships
            Requirements
         end
         subgraph Implementation
            Parts
            System
         end
      end
      
      subgraph Problem
         subgraph Mission
            Needs
         end
         Feedback
      end

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission

      Elements-."specify".->Requirements
      Elements-."specify".->Relationships
      Relationships-."specify".->Requirements

      System-."integrate".->Parts
```

### Mission control

```mermaid
   flowchart LR
      subgraph Solution
        subgraph Design
            Elements
            Relationships
            Requirements
         end
         subgraph Implementation
            Parts
            System
         end
      end
      
      subgraph Problem
         subgraph Mission
            Stakeholders
            Objectives
            Needs
         end
         Feedback
      end

      Mission--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Mission

      Elements-."specify".->Requirements
      Elements-."specify".->Relationships
      Relationships-."specify".->Requirements

      System-."integrate".->Parts

      Stakeholders-."specify".->Objectives
      Objectives-."specify".->Needs
```

### V-model

```mermaid
   flowchart LR
      subgraph Solution
        subgraph Design
            Elements
            Relationships
            Requirements
         end
         subgraph Implementation
            Parts
            System
            Test
         end
      end
      
      subgraph Problem
         Stakeholder
         Needs
         Use
         Feedback
      end

      Needs--"plan"-->Elements
      Elements--"contain"-->Requirements
      Elements--"contain"-->Relationships
      Relationships--"contain"-->Requirements
      Requirements--"implement"-->Parts
      Parts--"integrate"-->System
      Parts--"verify"-->Requirements
      System--"check"-->Feedback
      System--"validate"-->Needs
      Feedback--"act"-->Needs
```

### System of systems

#### Maturity & Iterations

- 2 week iteration makes no sense, depends on depths of design and implementation for a single need

```mermaid
   flowchart LR
      subgraph Solution ["Story"]
        subgraph Design
            Elements
            Relationships
            Requirements
         end
         subgraph Implementation
            Parts
            System
         end
      end
      
      subgraph Problem ["Refinement"]
         Needs
      end
      
      subgraph Demo
         Feedback
      end


      Needs--"plan"-->Elements
      Elements--"specify"-->Requirements
      Elements--"specify"-->Relationships
      Relationships--"specify"-->Requirements
      Requirements--"implement"-->Parts
      Parts--"integrate"-->System
      Parts--"verify"-->Requirements
      System--"check"-->Demo
      System--"validate"-->Needs
      Demo--"act"-->Needs
```


### Quality

## An organic hierarchy of development artifacts

### Negative effect of documents

### Entities

## Summary

### Development flow
