# Process as a System II: An Organic Development Lifecycle Model for Systems Engineering

## Introduction

### Concepts don't quite fit
1. V-Model creates unnecessary abstraction at the architecture/integration level
2. Agility is perceived as a counter to v-model, which it is not
3. PDCA is too high level

### First principles
1. Establish purpose
2. Understand elements and their function
3. Challenge pre-existing concepts
4. Re-align the model towards the purpose

### The purpose of a development lifecycle

1. The development lifecycle model shall guide the required activities and artifacts, to ensure the development achieves its purpose.
2. The development purpose, shall include customer satisfaction, to ensure that customer needs are met.

## Scope of this Document
### Practical examples
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
    Requirements["?"]
    Design["?"]
    Implementation["?"]
    Feedback["?"]
    
    Implementation--"check"-->Feedback
    Feedback--"act"-->Requirements
    Requirements--"plan"-->Design
    Design--"do"-->Implementation
```

#### Activities transform Artifacts

```mermaid
   flowchart LR
    Requirements
    Design
    Implementation
    Feedback
    
    Implementation--"check"-->Feedback
    Feedback--"act"-->Requirements
    Requirements--"plan"-->Design
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
         Requirements
         Feedback
      end

      Requirements--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Requirements
```

|---|---|
|Requirements|The heat pump should create less than 100g carbon dioxide equivalent.|

### Design Thinking

#### Keeping the problem space and solution space separate

1. Stakeholder requirements vs System requirements
2. Needs preferred to stakeholder requirement
3. Needs are problem artifacts
4. Requirements are design artifacts

```mermaid
   flowchart LR
      subgraph Solution
        subgraph Design
            Requirements
         end
         Implementation
      end
      
      subgraph Problem
         Needs
         Feedback
      end

      Needs--"plan"-->Design
      Design--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Needs
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
         Needs
         Feedback
      end

      Needs--"plan"-->Elements
      Elements--"plan"-->Requirements
      Elements--"plan"-->Relationships
      Relationships--"plan"-->Requirements
      Requirements--"do"-->Implementation
      Implementation--"check"-->Feedback
      Feedback--"act"-->Needs

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
         end
      end
      
      subgraph Problem
         Needs
         Feedback
      end

      Needs--"plan"-->Elements
      Elements--"specify"-->Requirements
      Elements--"specify"-->Relationships
      Relationships--"specify"-->Requirements
      Requirements--"implement"-->Parts
      Parts--"integrate"-->System
      Parts--"verify"-->Requirements
      System--"check"-->Feedback
      System--"validate"-->Needs
      Feedback--"act"-->Needs
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
         subgraph Needs
         end
         subgraph Feedback
            Demo
            Retrospective
         end
      end

      Needs--"plan"-->Elements
      Elements--"plan"-->Requirements
      Elements--"plan"-->Relationships
      Relationships--"plan"-->Requirements
      Requirements--"do"-->Parts
      Parts--"do"-->System
      System--"check"-->Feedback
      Feedback--"act"-->Needs
```

#### Maturity & Iterations

- 2 week iteration makes no sense, depends on depths of design and implementation for a single need

```mermaid
   flowchart LR
      subgraph Solution
         subgraph Story
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
      end
      
      subgraph Problem
         Needs
         Feedback
      end

      Needs--"plan"-->Elements
      Elements--"plan"-->Requirements
      Elements--"plan"-->Relationships
      Relationships--"plan"-->Requirements
      Requirements--"do"-->Parts
      Parts--"do"-->System
      System--"check"-->Feedback
      Feedback--"act"-->Needs
```


### Quality

## An organic hierarchy of development artifacts

### Negative effect of documents

### Entities

## Summary

### Development flow
