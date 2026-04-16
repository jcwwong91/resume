# Project Reference
*Source of truth for resume tailoring — only confirmed facts, no embellishment*

---

## Observe — Application Triaging and Service Overview
**Company:** LinkedIn

**What it did:**
- Unified platform providing engineers a single interface for two things: identifying root causes during site incidents (Application Triaging) and understanding the current health of their services (Service Overview)
- Part of a broader ~80-person effort to consolidate LinkedIn's internal observability tooling
- Application Triaging experience consolidated all relevant infromation from the inference engine to present a user on why an alert fired
- Service Overview experience gave the overall status of a service at specific point in time

**Jason's specific contribution:**
- Led the backend development for Application Triaging and Service Overview experiences
- Built the backend service that served as the API layer and interfaced with the mysql databaser

**Tech:**
- Python, Go, typescript (not much contribution)
- MySQL (primary datastore)
- InLogs → Azure Blob Storage (light integration for log data features)

**Outcome:**
- Adopted by 1000+ engineers within 3 months of launch
- Reduced the Mean time to triage  from 2 hours to 30 minutes for deployment/experimental ramp issues

**What it was NOT:**
- Jason did not architect or deliver the full Observe platform
- Jason did not write Grafana dashboards
- Jason did not deprecate InGraphs

---

## Inference Engine V2
**Company:** LinkedIn

**What it did:**
- Series of Go microservices that consumed data from external messaging queues and normalized it for downstream triaging and remediation pipelines
- Served as the core data pipeline ("the guts") that powered the Observe platform

**Jason's specific contribution:**
- Inherited the v1 version and redesigned v2 of the Inference Engine
- Developed the framework test with real data on developer machines instead of "testing in prod" greatly increasing the developer velocity
- Set up the framework to extend it with new event types
- Built the backend API layer
- Designed the MYSQL schema and database migration framework
- Rearchtected the unit testing environment to allow for parallelization dropping build times from 20 minutes to 2
- Consolidated alerts, linkedin experiments (lix, aka A/B test framewortk and feature ramp controller), deployments into a single source of truth (there are more but these were the main)

**Tech:**
- Go microservices
- Kafka (external messaging queues)
- MySQL
- Distributed Systems

**Outcome:**
- v2 reduced P95 query latency from 4s to <100ms
- Enabled real-time triaging and new remediation workflows
- Enabled a sincle source of truth for all triaging applications at linkedin

**What it was NOT:**
- Did not process "logs, metrics, and distributed traces" in the OpenTelemetry sense — consumed operational event data from queues

---

## Clearview
**Company:** LinkedIn

**What it did:**
- Real-time impact assessment tool for SREs
- Consumed raw Real User Monitoring (RUM) events, ran them through a rules engine to determine the severity of a site issue
- Provided a UI showing the exact type of degradation experienced by LinkedIn members
- Stored the latest per-minute impact results in Redis
- Provided insights to customer service teams on which customers were affected by site issues
- RUM events are emitted to a kafka topic via an external app
- Samza jobs read RUMevents and summarize impact on a per minute basic

**Jason's specific contribution:**
- Drove the development effort for Clearview
- Led and architected the design for clearview
- Authored the Clearview RFC and the Clearview decommission RFC
- Led a team of 2 to drive the entire development cycle end to end
- Created the samza job to process RUM events

**Tech:**
- Python (rules engine / backend)
- Redis (per-minute impact result storage)
- Celery job scheduler
- Kafka
- Samza

**Outcome:**
- Reduced mean time to impact assessment for onboarded teams from 45 minutes to 15 minutes
- Provided insights to customer support specialist on which enterprise customers were affected and many of their users were affected
- Standardized and programically determined the impact accessment for site issues
- Adopted by all enterpise product facing SREs

---

## Bloodhound
**Company:** LinkedIn

**What it did:**
- Fault injection system that introduced synthetic errorsi/latency between the connections of various microservices
- Recorded the resulting errors and generated alerts/reports
- Gave insight into opportunities for graceful degradation across feature flows

**Jason's specific contribution:**
- Co-authored the project
- Wrote the logic to package/run various tests

**Tech:**
- Python / Java

**Outcome:**
- Surfaced graceful degradation opportunities across LinkedIn Sales Navigator feature flows

---

## Project Maize
**Company:** LinkedIn

**What it did:**
- Cross-functional initiative to standardize/validate that OS upgrades across LinkedIn's fleet

**Jason's specific contribution:**
- Served as the POC for all of product SRE (All SRE that manage specific application level services, ie. not database or infra stuff)
- Coordinated with the infrastructure team to verify service health through the upgrade process
- Proactively surfaced teams with specific use cases that would block the OS upgrades
- Worked closely with the team to identify/work through painpoints before rolling out to other product SREs to test

**Tech:**
- Linux / OS-level (coordination role, not a software build)

**Outcome:**
- Ensured smooth OS upgrade rollout across LinkedIn's fleet for product SRE
- Lowered the average upgrade timeline from 9 months to 3 weeks for each upgrade cycle

---

## Project Sales Navigator
**Company:** LinkedIn

**What it did:**
- LinkedIn's premium sales tool designed for B2B sales professionals. 
- helps sales professionals target the right prospects, understand key developments at accounts, and engage with leads within a ready-to-do-business environment. 
- Advanced Search & Lead Finding — It provides 30+ advanced search filters to find and connect with potential customers, decision-makers, and relevant companies. Snovio Unlike basic LinkedIn, you get unlimited searches.
- Real-Time Alerts — You receive notifications as soon as there's relevant news like a new executive, hiring changes, or when a company raises funding, so you can act at the right moment
- Buyer Intent Signals — You can prioritize accounts showing high buyer intent based on signals like recent hiring growth or when leads are researching your company
- CRM Integration — The Advanced Plus plan supports syncing with CRMs like Salesforce and Microsoft Dynamics, keeping lead and account data up to date across platforms.

**Jason's specific contribution:**
- A member of the SRE team to maintain the operational readiness of sales navigator
- Added/maintained monitoring alerts and 24/7 oncall (automated alert and tier 3 escalation)
- Worked with the devleopment to push for best practices to ensure new features rolled out with reliability in mind
- Reviewed designs to ensure they were fault tolerant and could scale
- Ensured new features launched with proper alerting/monitoring such as lists
- Acted as a representative for the LSS org for cross functional initiatives

**Tech:**
- Kafka
- Kuberentes
- AWS (CRM integration)
- Java
- Distributed System

**Outcome:**
- Brought the average SLA from 99.5% (at time of joining) to 99.95%
- Lowered the average oncall alert volume from 21 weekly alerts to 6 (while increasing the SLA)
- Lowered the average weekly overnight oncall volume from 6 nights of interrruptions to 1

---

## Project Linkedin Sales Insights
**Company:** LinkedIn

**What it did:**
- data enrichment and analytics platform specifically designed for sales operations teams. It offered reliable firmographic data to help teams size opportunities, enrich accounts in their CRM, and direct sales teams on where to focus their efforts. 

**Jason's specific contribution:**
- Acted as the SRE representative for the initial launch of the project
- Reviewed the architecture and identified specific relaibility concerns for the architecture
- Ensured the product launched with proper monitoring and alerting
- Championed new oncall processes to move the company towards a developer oncall model over SRE

**Tech:**
- Java
- Distributed System

**Outcome:**
- Enabled the new product launch of LSI

---

## Remote Cloud Key (RCK)
**Company:** Continental Intelligent Transportation Systems

**What it did:**
- Cloud service enabling users to lock/unlock their car and trigger remote start via a smartphone and Bluetooth dongle

**Jason's specific contribution:**
- Spearheaded the backend development as a greenfield project
- Developed Go microservices that ran this project
- Designed and maintained the PostgreSQL schema
- Instrumented services with Prometheus metrics and Grafana dashboards
- Created Docker configurations for microservices
- Authored Ansible playbooks for AWS infrastructure provisioning (VPCs, subnets, load balancers, security groups)
- Set up and maintained CI/CD via Jenkins
- Maintained protobuf files and gRPC integration
- Conducted code reviews via Gerrit
- Created Kubernetes deployment, secret, and service configurations

**Tech:**
- Go (microservices)
- Kubernetes / AWS (deployment)
- PostgreSQL (data store)
- Prometheus + Grafana (observability)
- Docker
- Ansible (infrastructure provisioning)
- Jenkins (CI/CD)
- gRPC / protobuf
- Python (Kubernetes install scripts)

**Outcome:**
- First documented lock/unlock/trunk-opening of an automobile from a cloud-generated key within Continental
- Setup the standard/framework for future apps such as a autonomous car rental application

---

## Intelligent Optical Switch Management Application
**Company:** Glimmerglass Cyber Solutions

**What it did:**
- Acted as the control plane to control the routing of various optical switches

**Jason's specific contribution:**
- Contributed to the development of the control of the optical switch

**Tech:**
- Java

**Outcome:**
- N/A

## Project 2: Metadata Extraction Probe
**Company:** Glimmerglass Cyber Solutions

**What it did:**
- It was a physical box that would be placed into a datacenter.  Network traffic would be passively mirrored and sent to the box

**Jason's specific contribution:**
- Pioneered development of the metadata probe
- Wrote the logic to ingest network traffic and extract/persist the network metadata
- Wrote teh backend to slice and dice the metadata nd surface analytics behind it

**Tech:**
- C
- Python
- Java

**Outcome:**
- N/A

---

## UC Davis — Agricultural Automation Lab

**What it did:**
- Data collection application used to model probability densities of various fruit trees

**Jason's contribution:**
- Developed the application in C++
- Used the application to gather data of various fruit trees

**Outcome:**
- Enabled multi-year studies on growth patterns of various pear and peach trees
- Enabled the generation of prabalistic fruit growth on various trees to create efficient designs for robotic harvesters
