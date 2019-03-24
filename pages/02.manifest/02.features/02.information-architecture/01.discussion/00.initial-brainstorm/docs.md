---
title: 'Initial Brainstorm'
visible: true
taxonomy:
    category:
        - docs
routes:
  canonical: /features/information-architecture/discussion/initial-brainstorm
---

# Information Architecture Brainstorm

How we want our Grav sites set up, and what each section is used for.

## Menu Structure

Our top-level menu structure is broken out into three main sections, with sub-sections:

- Guide 
    - Step-by-step
    - Reference
- Manifest
    - System Log (e.g. System admin changes, upgrades, deployments, config changes, etc.)
    - Resources (e.g. Servers, Accounts, and third-party dependancies such as Drupal or CiviCRM
    - Features (Deployed Features)
    - Control (e.g. Budget approvals, resource procurement, control documentation, etc.)
    
- Roadmap
    - Feature
        - Context
        - Technical Discovery
        - Brainstorm
        - Proposed Solution

## Guide

We need some documentation here about how we want our guides to be User Story centric, and the delineation between use-case guides and interface guides.

### Objective

Each objective, goal, or use case has it's own directory. How the information is organized can vary from project to project, based on the needs of the project. User stories should be kept thin by linking to internal and external references, rather than expounding on pre-requisites, concepts, or in-depth instructions.

### References

Can explain abstract concepts, detail tool (interface) documentation, or reference external documentation i.e. bibliographic reference.

## Manifest

### Feature (Deployed)

## Roadmap

Roadmap Primary page (i.e. menu item) displays all it's children, and is the overall plan for the project.

## Feature

A feature describes… something. Each Feature should have it's own directory in the Roadmap, and some sub-Features may be nested inside parent Features.

The feature components that follow (Context, Discussion, ~~Discovery~~Resolution, and Solution) are expected to be single pages. Each component to the feature might be broken down into sub-directories, but if a lot of sub-division is needed, [decomposing the feature](#composing-and-decomposing-features) should be considered. 

### Context

Describes the user stories and external systems that the feature exists within. Can include process diagrams, mockups or screenshots of interfaces the feature will build on or extend, personas, etc. Borrowing this concept largely from C4 architecture, this is the highest level of [abstraction](http://obstruction.org) in that system.

### Discussion

Brainstorms, disussions, wacky ideas, tentative decisions, questions, potential solutions to be tested and/or fleshed out, etc.

### Resolution

Technical discovery, requirements, establishment of default behavior, etc. Items should only be placed in Resolution when they are verified and accepted. **Example:** [Establishing Default Behavior](https://rtfm.ginkgo.st/~ca/architecture/organizational-membership-reminders/technical-discovery#establishing-default-behavior)

### Solution

Feature components, approaches, and other parts of the feature that have been validated for inclusion in the feature.

## Composing and Decomposing Features

### Composing

If a Feature is known to be built out of existing Features, we should not duplicate those Feature specifications. That is, Features should always be mutually exclusive. Features that are dependancies should be referenced in the Solution of the Feature.

### Decomposing

When a part of a Feature becomes important enough or large enough to warrant being it's own Feature. Essentially, when it becomes a `submodule`. Decomposing produces the same result as a composed Feature, but is just the act of spinning off Solution components into a mutually exclusive Feature.

> _**Example:**_ Event MultiReg for FIS spun off the [org.civicrm.fieldmetadata](https://github.com/ginkgostreet/org.civicrm.fieldmetadata) extension.

Features don't need to be broken down on components or technical boundaries to be considered mutually exclusive.  

## Feature Lifecycle

1. New feature will start off as a Roadmap item under Architecture.
2. Articulate the context (i.e. users and stories).
3. Do some brainstorming to create possible solutions, questions to be answered, etc.
4. Perform technical discovery to answer questions, inform decisions, determine feasibility of proposed solutions, etc.
5. Draft solution(s) that implement the feature
6. All roles in the project review the proposed solutions and documentation to date, to ensure, validate, and verify that any concerns from all perspectives have been addressed. 

## New Releases

**Scenario #1:** A feature is in production for some time, the org evolves, they want to make changes…assuming this is a minor change, that would equate to a Minor Release. We would create a Feature for the Minor Release e.g. `myFeature_v1.1`.The contents of the Feature would address the development of the changes, referencing the deployed Feature as appropriate and not duplicating it.

When it comes time to deploy the Minor Release, the whole Feature is simply moved into the Root of the Deployed Feature. 

Bam.

**Scenario #2:** The change is not minor and constitutes a Major Release e.g. `myFeature_v2.0`. As with the Minor Release, avoiding duplication is the strategy. When it comes time to deploy, the Major Releases replaces the earlier version of the Feature but maintains the previous version as a child.

Double Bam.

