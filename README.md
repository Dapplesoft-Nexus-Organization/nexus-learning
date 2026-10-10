# Nexus Learning

Post-execution intelligence pipeline extracting durable lessons and reusable skills from completed tasks.

## Safety & Governance
- **Candidate Pipeline:** Extracted skills are classified as *Candidate* and NEVER published to production without human review.
- **Trajectory Anonymization:** Automatic PII/secret scrubbing before dataset persistence.

## Directory Structure
```text
nexus-learning/
├── pipelines/
│   ├── skill-extraction/
│   └── trajectory-curation/
├── training/
└── evals/
```
