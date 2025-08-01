# 📦 Architecture Kata: A Foundational Multi-Tenant Message Gateway

## Context

You are part of a fintech company specialized in the restaurant industry.  
Over the years, the engineering team has built dozens of services, each with its own 
custom implementation for sending messages — often by directly integrating with third-party 
SDKs such as Twilio, Brevo, or Firebase.  

This approach has led to duplicated logic, inconsistent handling of errors and bounces, 
limited observability, and difficulties in managing costs across tenants.  

The company is now migrating to a **platform approach**, consolidating all messaging 
capabilities into a single **Message Gateway**.  
The Message Gateway will act as a unified, multi-tenant service providing reliable 
**email and SMS**, with consistent **templating, auditing, 
fallback strategies, and cost metering**.  

As part of the migration, existing services will gradually shift from using their 
provider SDKs directly to consuming the Message Gateway APIs. During this transition, 
the platform must support **progressive adoption**, ensuring backward compatibility 
while offering clear incentives (e.g., better deliverability, centralized reporting, 
fraud protection) for teams to migrate.

---

## Requirements

### Functional
- **Email Sending**
  - Support multiple providers
  - Automatic **fallback** when a provider fails
  - Support **templating**
  - Handle **subscription preferences**
  - Handle **hard & soft bounces**
  - Daily volume: **100,000+ emails**

- **SMS Sending**
  - Support multiple providers
  - **OTP** (one-time-password) messages
  - Optimize for **deliverability** 
  - Daily volume: **50,000 SMS**
  - World wide traffic

- **Auditing**
  - Ability to **trace a message end-to-end** across all channels
  - Tenant-support tooling: search by recipient, tenant, time range, and channel

### Non-Functional
- **Scalable & Highly Available**
  - Handle burst loads gracefully
- **Cost Metering**
  - Track usage and cost per tenant, per channel
- **Migration Friendly**
  - Support progressive migration from legacy SDK-based integrations

---

## Deliverables

### 1. System Architecture Diagram
Draw a **high-level architecture** that shows:
- API entry points (REST/gRPC API, Admin UI, etc)
- Channel-specific processing pipelines (Email, SMS)
- Provider abstraction layers with fallback logic
- Datastores

### 2. Key Design Decisions
Explain:
- How you implement **multi-provider email & SMS fallback**
- How you support **cost-tracking** & **cost-optimization**
- Strategies for **optimizing deliverability** in SMS.
- How you handle **idempotency** to prevent double sends
- Your approach for **templatization** across channels
- How you enable **auditing**

### 4. Observability & Auditing Plan
Define how you will:
- Track per-tenant **success/failure rates**.
- Collect metrics (emails sent, SMS cost, push latency).
- Generate tenant-specific cost reports.
- Alert on anomalies (e.g., sudden SMS spikes → fraud).
- Support **customer support audits**: searchable history, evidence export.

### 5. Scaling Plan
Discuss how you will:
- Partition workloads (per channel, per tenant).
- How will you handle 10x throughput.
- Handle backpressure if a provider slows down.
- Ensure retries and DLQs don’t overwhelm the system.

---

## Exercise Format
- **Timebox**: 60 minutes.
- **Group Deliverables**:
  1. A rough architecture diagram.
  2. A clear explanation of fallback, auditing and cost optimization
  3. High-level thinking on observability & cost metering
  4. At least a mention of migration (progressive adoption)
- **Discussion**:
  - Present your design.
  - Highlight trade-offs (latency vs reliability, cost vs observability).
  - Defend your approach to scalability and auditing.

---

