# Manoj OS

A personal AI operating system built around specialized AI agents that transform personal data into contextual insights, automation, and intelligent decision support.

## 🧠 About Manoj OS

Manoj OS is an evolving personal AI ecosystem designed to bring multiple specialized AI agents together under one system.

Rather than building a single general-purpose assistant, Manoj OS explores how purpose-built agents can collect data, process context, reason about it, and deliver useful actions or insights.

The first active module is **Manoj's Fitness AI Agent**, which uses health and fitness data to generate personalized daily coaching and recovery insights.
## 🏋️ Manoj's Fitness AI Agent

The Fitness AI Agent is the first working agent within Manoj OS.

It is designed to transform raw health and fitness data into a structured daily coaching report instead of simply displaying health metrics.

The agent collects health data through the Google Health API, processes the raw responses through an automated n8n pipeline, builds structured AI context, evaluates data quality, and uses AI reasoning to generate personalized fitness insights.

### What It Currently Analyzes

- Sleep and recovery
- Daily steps and activity
- Resting heart rate
- Body weight
- Calories burned
- Nutrition
- Hydration
- Data freshness and completeness
- Training readiness

### What It Produces

The agent automatically generates a daily HTML fitness report containing:

- Overall daily status
- Recovery assessment
- Nutrition analysis
- Hydration analysis
- Training readiness
- Personalized coaching notes
- Today's focus
- Data-quality caveats
## 🏗️ System Architecture

The Fitness AI Agent is designed as a layered data-processing and AI reasoning pipeline.

```text
Manual / Schedule Trigger
        ↓
Initialize Workflow
        ↓
Google Health API
        ↓
Raw Health Data Nodes
        ↓
Summary / Transformation Nodes
        ↓
Merge
        ↓
Daily Health Summary
        ↓
AI Context
        ↓
AI Agent
        ↓
Structured Output Parser
        ↓
HTML Formatting
        ↓
Gmail Delivery
```




## 🛠️ Tech Stack

The current Manoj OS and Fitness AI Agent implementation uses the following technologies:

### AI & Automation

- AI Agent reasoning
- Structured prompt/context design
- Structured Output Parser
- n8n workflow automation

### APIs & Authentication

- Google Health API
- Google OAuth 2.0
- REST API integration

### Data Processing

- JavaScript
- JSON transformation
- Data normalization
- Aggregation and validation logic
- Multi-branch workflow processing

### Frontend

- HTML
- CSS
- JavaScript

### Version Control & Deployment

- Git
- GitHub
- GitHub Pages

### Communication & Delivery

- Gmail automation
- HTML email reporting

### Engineering Concepts

- Workflow orchestration
- API integration
- Context engineering
- Data-quality handling
- Modular pipeline design
- Reusable processing logic
- Automated reporting

## 🛡️ Reliability & Data Quality

The Fitness AI Agent is designed to reason about the quality of its input data instead of assuming every health metric is complete and current.

### Data Quality Awareness

The processing pipeline evaluates conditions such as:

- Missing health records
- Stale measurements
- Incomplete daily data
- Weight measurement freshness
- Hydration timing and completeness
- Nutrition completeness
- Sleep-data availability
- Partial API responses

This allows the AI Agent to distinguish between a genuine health signal and a limitation in the available data.

For example, missing hydration data should not automatically be interpreted as poor hydration.

### Modular Processing

Health metrics are processed through dedicated workflow branches before being merged into the final AI context.

This isolates transformation logic and makes individual data sources easier to inspect, debug, and improve.

### Shared Workflow Context

A centralized initialization stage provides shared context such as the target date to the major health-data branches.

This reduces duplicated date logic and helps keep different parts of the workflow synchronized.

### Failure Isolation

Non-critical workflow components are designed so that failures do not unnecessarily prevent the primary user-facing report from being delivered.

For example, historical logging can be separated from the main email-delivery path so a logging failure does not automatically block the daily fitness report.

### Retry and Error Handling

External integrations can encounter temporary failures or rate limits.

Retry and continue-on-error strategies can be applied where appropriate so non-critical integration failures are handled more gracefully.

### Reliable AI Reasoning

The AI layer receives processed, structured context rather than relying directly on large raw API responses.

The overall design follows the principle:

Raw Data
→ Validate
→ Transform
→ Summarize
→ Evaluate Data Quality
→ Build AI Context
→ Reason
→ Deliver

## 🔐 Privacy & Security

The Fitness AI Agent processes personal health information, making privacy and credential security important parts of the system design.

### OAuth 2.0 Authorization

Access to Google health data is handled through Google OAuth 2.0 rather than storing a user's Google password.

The authorization model allows access to be controlled through the permissions granted to the application.

### Credential Protection

Sensitive authentication information is not intended to be stored in the public source repository.

Examples of information that must remain private include:

- OAuth Client Secrets
- Access Tokens
- Refresh Tokens
- Credential files
- Private health datasets
- Personal exported health data

Git and GitHub should contain application code and documentation, not private credentials or personal health records.

### Data Minimization

The Fitness AI Agent retrieves and processes health information required for its coaching and analysis workflows rather than treating all available personal data as necessary input.

### Public vs. Private Architecture

The public Manoj OS website and GitHub repository are designed to demonstrate the architecture, engineering approach, and capabilities of the project.

Private credentials and personal health information remain separate from the public project showcase.

### User Control

Google OAuth permissions can be revoked by the user, allowing access to connected Google data to be withdrawn.

### Production Security Direction

As Manoj OS evolves, additional security controls can be introduced for areas such as:

- Secrets management
- Environment-specific configuration
- Authentication and authorization
- Encryption
- Access control
- Audit logging
- Secure cloud infrastructure
- Monitoring and alerting

## 🚧 Project Status

Manoj OS is an actively evolving personal AI engineering project.

The first working module, Manoj's Fitness AI Agent, currently includes:

- Automated health-data collection
- Multi-branch health-data processing
- Daily health summaries
- Structured AI context generation
- AI-powered fitness reasoning
- Data-quality awareness
- Automated HTML fitness reports
- Gmail delivery
- Public Manoj OS project website
- Git-based version control
- GitHub repository
- GitHub Pages deployment

The project is being developed incrementally, with each stage introducing new capabilities while improving reliability, maintainability, and system architecture.


## 🗺️ Roadmap

Future development areas include:

### Fitness Intelligence

- Historical health trend analysis
- Weekly and monthly reports
- Workout intelligence
- Deeper recovery analysis
- Long-term coaching context and memory
- Improved nutrition and hydration intelligence

### Platform Development

- Additional specialized Manoj OS agents
- Shared services between agents
- User-facing dashboards
- Authentication and user management
- Persistent application data

### Infrastructure & DevOps

- Containerization
- CI/CD pipelines
- Cloud infrastructure
- Infrastructure as Code
- Secrets management
- Environment separation
- Monitoring and observability
- Logging and alerting
- Reliability improvements

The roadmap will evolve as Manoj OS progresses from a personal AI automation project toward a broader agent-based platform.


## 🌐 Live Demo

The Manoj OS project website is publicly available through GitHub Pages:

**https://mmaddela2201.github.io/Manoj-os/**

The website provides a product-focused view of Manoj OS and includes:

- Fitness AI Agent capabilities
- System workflow
- Architecture screenshots
- Example AI-generated fitness reports
- Privacy Policy
- Terms of Service


## 📌 Repository Purpose

This repository documents the ongoing development of Manoj OS and demonstrates practical experience across:

- AI agent engineering
- Workflow automation
- API integration
- OAuth 2.0
- JavaScript-based data processing
- Reliability and data-quality design
- Git and GitHub
- Web development
- Automated reporting
- Software delivery and deployment

The project is intentionally being built iteratively so that new engineering concepts can be implemented, tested, documented, and improved as the system evolves.