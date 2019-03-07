---
title: Discussion
taxonomy:
  category: 
    - docs
  tag:
    - discussion
routes:
  canonical: /feature/information-architecture/discussion
---
# Discussion: Decision Framework

Discussions are unresolved topics having to do with any aspect of the feature it belongs to. Topics should be non-trivial and possibly non-obvious, though this can be highly subjective and it is better to create a discussion than to assume it isn't needed.

Discussions and Resolutions are the key elements of the Project Lab Decision Framework. When a Discussion is concluded, a status of "RESOLVED" should be placed at the top of the discussion, and linked to the Resolution.

## Examples

### Context

**Discussion:** What notifications and reminders should Staff receive within the application approval workflow?

**Resolution: ** Discovery on-site with customer concluded that ... because... It was confirmed to be technically feasible when....

### Technical Discussion

**Discussion:** Plugin A and Plugin B are both attempting to persist data from the transaction to the data store. We need a strategy to ensure data integrity and prevent conflicts in functioning of the plugins.

**Resolution:** Plugin A shall have authority over which data it will persist and which data Plugin B shall have responsibility delegated to. Plugin B will only persist data that has been flagged within the hook message by Plugin A.