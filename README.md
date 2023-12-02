# Process as a System II: A Unified Development Lifecycle Model for Systems Engineering

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

## Scope of this Document
### PDCA
### V-Model
### Agility
### Design Thinking
### Systems Thinking
### What's in
### What's out?

## Unified Development Lifecycle Model

### The purpose of a development lifecycle

*TODO*

### Activities and Artifacts shape the development lifecycle

*TODO*

#### Activities
*TODO*
```mermaid
   flowchart LR
      Plan-->Do
      Do-->Check
      Check-->Act
      Act-->Plan
```
*TODO*

#### Activities transform Artifacts
*TODO*
```mermaid
   flowchart LR
    Requirements["?"]
    Design["?"]
    System["?"]
    Feedback["?"]
    
    System--"check"-->Feedback
    Feedback--"act"-->Requirements
    Requirements--"plan"-->Design
    Design--"do"-->System
```
*TODO*

#### High level artifacts
*TODO*
```mermaid
   flowchart LR
    Requirements
    Design
    System
    Feedback
    
    System--"check"-->Feedback
    Feedback--"act"-->Requirements
    Requirements--"plan"-->Design
    Design--"do"-->System
```
*TODO*

### Problem space solution space

#### Requirements connect Problem space with solution space

```mermaid
   flowchart LR
      Problem-->Solution
```



```mermaid
   stateDiagram-v2
    Requirements
      state Problem{
         Feedback
      }

      state Solution{
         Design
         Result
      }

      [*]-->Requirements
      Result-->Feedback: check
      Feedback-->Requirements: act
      Requirements-->Design: plan
      Design-->Result: do
      Feedback --> [*]
```

Doesnt really make much sense.

#### Needs and Requirements

1. Stakeholder requirements vs System requirements
2. Needs preferred to stakeholder requirement
3. Needs are problem artifacts
4. Requirements are design artifacts

```mermaid
   stateDiagram-v2
      state Problem{
         Needs
         Feedback
      }

      state Solution{
        state Design{
            Requirements
        }
         System
      }

      [*]-->Needs
      System-->Feedback: check
      Feedback-->Needs: act
      Needs-->Design: plan
      Design-->System: do
      Feedback --> [*]
```
### ???

What are design artifacts?

```mermaid
   stateDiagram-v2
      state Problem{
         Needs
         Feedback
      }

      state Solution{
        state Design{
            Elements
            Relationships
            Requirements
        }
        System
      }
    Elements-->Requirements
    Relationships-->Requirements

      [*]-->Needs
      System-->Feedback: check
      Feedback-->Needs: act
      Needs-->Design: plan
      Design-->System: do
      Feedback --> [*]
```

#### V-model

```mermaid
   stateDiagram-v2
      state Problem{
         Needs
         Feedback
      }

      state Solution{
        state Design{
            Elements
            Relationships
            Requirements
        }
        System
      }
    Elements-->Requirements
    Relationships-->Requirements

      [*]-->Needs
      System-->Feedback: check
      Feedback-->Needs: act
      Needs-->Design: plan
      Design-->System: do
      System-->Design: verify
      System-->Needs: validate
      Feedback --> [*]
```

#### Maturity dimension

##### Iterations

```mermaid
   stateDiagram-v2
      state Problem{
         Need
         Feedback
      }

      state Solution{
        state Design{
            Element
            Relationship
            Requirement
        }
        System
      }
        Element-->Requirement
        Relationship-->Requirement

      [*]-->Need
      System-->Feedback: check
      Feedback-->Need: act
      Need-->Design: plan
      Design-->System: do
      System-->Design: verify
      System-->Need: validate
      Feedback --> [*]
```

##### Quality

#### System of systems

```mermaid
   stateDiagram-v2
      state Problem{
         Need
         Feedback
      }

      state Solution{
        state Design{
            Element
            Relationship
            Requirement
        }
       state Enviroment{
        state System{
        Part
       }
       }
      }
        Element-->Requirement
        Relationship-->Requirement

      [*]-->Need
      System-->Feedback: check
      Feedback-->Need: act
      Need-->Design: plan
      Design-->System: do
      System-->Design: verify
      System-->Need: validate
      Feedback --> [*]
```

#### Documents

##### Entities