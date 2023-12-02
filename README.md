# Process as a System II: A Unified Development Lifecycle Model for Systems Engineering

## Introduction
### Issue
### Concepts
### First principles

## Scope
### What's in
### what's out 

## PCDA cycle
### How its known
```mermaid
   flowchart LR
      Plan-->Do
      Do-->Check
      Check-->Act
      Act-->Plan
```
### Its actually activities
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
### Whats in between
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

## Problem space solution space

### Requirements connect Problem space with solution space

1. Doesnt really make much sense.

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

### Needs and Requirements

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
## ???

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

### V-model

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

### Maturity dimension

#### Iterations

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

#### Quality

### System of systems

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

### Documents

#### Entities