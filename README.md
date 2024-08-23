# Slaycard - Technical Documentation
Technical Documentation for Slaycard - Turn-Based Combat Game

Project repository with the source code can be found [here](https://github.com/netspie/slaycard).

Thought process behind the development process available [here](https://medium.com/@netspie/building-a-highly-scalable-turn-based-combat-game-bd8117236364 ).

### Purpose

The project is primarily created for own educational purposes, to gather experience creating fullstack applications and distributed systems. Specifically it includes following subjects:
- Various architecture styles from the simplest to more advanced:
  - Client-Server
  - Vertical Slices / Clean Architecture / CQRS
  - Event-Driven Architecture / Event Sourcing
  - API Gateway
  
- Programming Languages
  - C#
  - JavaScript / TypeScript
  - Html / CSS
  - Other (optional) - potentially Go

- Communication Protocols
  - HTTP - RPC / REST / SSE
  - Message Queue  

- Frontend Frameworks
  - Next.js / React
  - Angular or Svelte
  - Nx and microfrontend architecture

- Databases
  - MSSQL
  - PostgreSQL

- Queues
  - RabbitMQ 

- CI/CD
  - Github Actions
  - Azure Devops

- Performance Testing Tools
  - k6
  - PerfView or other .NET performance tools 

- Monitoring Tools
  - Prometheus
  - Kibana / Grafana 

- Deployment or Hosting Tools and Platforms
  - Docker
  - Kubernetes
  - Azure / AWS  

### Description

Slaycard is a turn-based combat game where you can manage your team of characters and battle against the others. Each character can be developed in a unique way, which can influence the style of combat. You can choose from multiple opponents, gather experience from the concluded battles and improve your characters statistics and skills. Initially the game is going to offer PvE combat (Player vs Bot), but in the future it will allow for PvP gameplay as well. 

Each unit has four base statistics:
- Vitality
- Agility
- Power
- Mind
- .. and maybe Defence (optional, to be decided)

Each of the base statistics has an impact on your combat statistics which are used directly in the battle:
- Health - presented as % rather than concrete value 
- Energy (to be decided/improved)

- Damage - base damage dealt to the opponents in combat, it is compared with enemy's defence
- Defence - improves techniques to effectively defend oneself from an attack thus lowering the taken damage
- Accuracy - in combat it is compared with opponent's dodge to calculate the % of probability to hit or miss
- Dodge - helps to avoid opponent's attacks
- Speed - lets the character to perform action more often
- Critics - improves chances for critical damage in combat (1.5x, 2x, or 3x damage)

<br>  

**Base vs Combat Stats Dependency**
| Combat Stat | Influencing Base Stats |
| --- | --- |
| Damage | Power |
| Defence | Defence, Power |
| Accuracy | Mind, Power |
| Dodge | Agility, Mind |
| Speed | Agility |
| Critics | Mind |

In combat units can attack opponents from enemy's team, heal themselves and, in the future, use skills.

### Game Versions

Based on initial system design the game development is divided into separate releases/versions, where each one adds additional features or qualities to the product. Initial versions are described later in the documentation.

## Current Version - 1.0.0 (in development)

### Features

- Random Combat
  - Attack opponents when it's your unit's turn
  - Heal characters when low health level

### Non-Functional Attributes

- The Simplest Gameplay Possible - random generated or predefined battle instead of selection from options 
- Minimal UI
- Web-Browser Only
- Mandatory Integration Tests Only
- Simple Deployment Pipeline

*Out of scope*
- Authentication
- Persistence Storage
- Real-time Communication
- Availability, Scalability and Monitoring
- Performance Optimizations

### Domain Logic Boundaries/Modules

- Combat - responsible for executing the ongoing combat

*Optional*
- Combat Teams Preview and Selection - own and opponent's
- Unit Details - details about every unit's level, xp and statistics

### Constraints

- Starting from simplest possible system architecture and over time expanding towards better scalability, availability and observability.
- Use of .NET and Next.js and related to them technologies first - as it's the most familiar ones, then in later stages of product life using others for additional features or modules for extending the scope of compentece slightly
- Use of Client-Server high level architecture first, skipping this way more simplistic approaches like - offline single deliverable app develop or SSR, because of goal to learn public api development
- Use of technologies dictated by the business goals

### System Level Architecture

![Architecture](img/slaycard-v1.0.0-diagram.png)

### Frontend Architecture

### Backend Architecture

## Future Version - 1.1.0

### New Features

- Combat Team Selection - Select the team you want to perform battle with from predefined sets of units and battle against opponents
  
### Non-Functional Improvements

- Real-time events communication between the client and server.

### Architecture

![Architecture](img/slaycard-v1.1.0-diagram.png)

## Future Version - 1.2.0

### New Features

- Replay completed battles anytime you want and learn from the mistakes you made..

### Non-Functional Improvements

- Store events in the database allowing for later processing
  
### Architecture

![Architecture](img/slaycard-v1.2.0-diagram.png)

## Future Version - 2.0.0

### New Features

- Character Progression - Gain experience from completed battles and increase you characters statistics

### Non-Functional Improvements

- ..

### Architecture

![Architecture](img/slaycard-v2.0.0-diagram.png)

## Future Version - 2.1.0

### Non-Functional Improvements

- Add monitoring system to ensure correct performance and availability
  
### Architecture

![Architecture](img/slaycard-v2.1.0-diagram.png)

