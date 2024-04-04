# Cloud Foundry Intro

## Cloud Application Delivery Models

* Alternatives: OpenShift, Azure WebSite, ...
* Build and deploy application
* Why?
    - the new "middleware for the cloud era" 
    - Application-centric
    - Faster time to market
    - DevOps-friendly
    - Different runtimes, same policies
* 

### Twelve factor App  (made by Heroku team)
1. Code is version controlled
    - GitHUb
    - GitLab
    - ...
2. Dependencies are declared and isolated
    - never assume system-wide packages
    - dependency declaration manifest
    - isolated so no dependency "leak"from system
    - helps new programmers
3. Configuration is Stored in the Environment
    - Should store in env variables
    - should not be "constants" in code
    - ideally not in config files
    - avoid grouping as "environments"
4. Backing Services as Attached resources
    - Services consumed over the network
    - No distinction between local or 3rd party services
    - Keep dependencies de-coupled
    - attach and detach at will
5. Build and Run Stages are Separated
    - Impossible to change code at runtime
    - Releases should have IDs
    - Build may be complex, started by devs
    - Run is simple and completely unattended
6. Application Executed as Stateless Processes
    - Share nothing
    - Persisted data in stateful backing store
    - Memory and file system is cache only
    - Avoid sticky sessions
7. Services are Exported via Port Binding
    - Self contained
    - Embedded servers
    - Listen on a specific port
    - Very specific and idealistic
8. Application Scaled Out via Process Model
    - Processes are first-class citizens
    - Work assigned to a process type
    - Applications have processes that span servers
    - Use OS process managers, not daemons
9. Processes are Disposable
    - Can be started or stopped at any time
    - Minimal startup time, graceful shutdown
    - Worker processes return work to the queue
    - Robust against sudden death
10. Parity Between Application Environments
    - Avoid time/personnel/tool gaps
    - Design for continuous deployment
    - Very important for backing services
    - Containers and config mgmt. makes this easier
11. Logs treated as event streams
    - Logs are a strem of time-ordered events
    - App is never concerned with storing own logfiles
    - Execution environment captures and stores logs
    - May be routed to file, watched, sent to external service
12. Management Task Run as One-Off Processes
    - Run in identical environment
    - Separate out as scripts that are source controlled
    - Don't run from local terminal
    - Don't run directlly against DB

* Additional PaaS Design Considerations
    - Rely on asynchronous messaging 
    - Compose applications oout of services
    - Assess portability requirements
    - Embrace the abstraction


## PaaS Anti-Patterns

- Relying on the local file system
- Building services that scale up
- Trying to change code server-side
- Manually coordinating builds
- Hard-coding configuration
- Cramming averything into one app 


## About Cloud Foundry

An open-source Platform-as-a-Service for running orchestrated polyglot applications in an public or private environment. 

## Cloud Foundry Containers

- CF use containers (Warden,... maybe Bosh)

## Cloud Foundry Architecture

## Cloud Foundry Security

- System boundaries
- Secure routing
- Firewall rules
- Authentication and authorization
- RBAC
- Application isolation