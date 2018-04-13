# Distributed Systems On AWS

## What are Distributed Systems

A distributed system is a software system in which components located on networked computers communicate and coordinate their actions by passing messages. The components interact with each other in order to achieve a common goal.

## Falacies of Distributed Systems

- Network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure
- Topology doesn't change
- Only one administrator
- Transport cost zero

## Characteristics of distributed web systems

- Many different architectural styles
- Data sharing
    - Shared database
    - Synchronization
        - Database replication
        - Messaging
    - Caching
- Fault toelrance techniques
- Core principles
    - Availability
    - Reliability
    - Scalability
    - Performance
    - Manageability

## Distributed web systems in the cloud

- More geographic options
- Shared resources
    - Hardwware, storage, network
- Promotes "design for failure"
    - Commodity hardware
    - Decouple
- Different expectations
    - Speed
    - Agility
    - Scale
    - Performance
    - Control

## Making distributed cloud systems highly available

- Scour the architecture for single points of failure
    - Every tier of the application
- Distribute components across geographies
- Aggressive monitoring and response
    - High latency worse than failure
    - Self healing environments
- Understand the different objectives
    - Load balancing
    - High availability
    - Disaster recovery

## AWS service portfolio
- Compute and Networking
- Storage and CDN
- Databases
- Deployment and Management
- Aplication Services