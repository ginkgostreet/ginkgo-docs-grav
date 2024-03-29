---
title: Orientation
taxonomy:
  category: 
    - docs
  tag:
    - guide
routes:
  canonical: /guides/orientation
---
# Orientation

So, you'd like to learn to work in a Project Lab? Adjust your safety goggles, and let's begin.

> A Project Lab is a project nexus for all Stakeholders and Implementors to have a
> meeting of the minds, quickly find resources and knowledge, and quickly
> gain perspective on where we've been, and where we are going.

## Top-level Navigation

To get started, you need to understand:

* [Guides](/manifest/features/information-architecture/discussion/initial-brainstorm#guide)
* [Manifest](/manifest/features/information-architecture/discussion/initial-brainstorm#manifest)
* [Roadmap](/manifest/features/information-architecture/discussion/initial-brainstorm#roadmap)

The first two items represent mostly describe the state of the Solution the Lab was created to implement and maintain. Guides can be in a draft state however and either represent how the Solution functions, or how it eventually will function.

## Guides

"Reference" documentation is relegated to a sub-folder under Guides. It is necessary documentation but considered less useful because it must address a large audience with different skills, experience, and purposes. Reference documentation should be further limited because specific interfaces should be documented within the Solution of the Feature that implements it, or a meta-feature that brings together the several features that implement a single form or interface.

Most Guides are intended to be "Objective Centric". This means that a single audience is targetted, and usually an advanced user. Skill-building and familiarity are their own objectives, so most guides do not need to cater to beginners.

The gray area between Guides and References are conceptual guides. Use your judgment in organizing conceptual documentation as a Reference, or a Guide.

## Manifest

The Manifest brings together literally everything about the Solution. Mostly the domain of Maintenance and System Administration, Manifest is also an administrative space for Project Owners/Managers. Project Management documents are found in "Control".

## Roadmap

The Roadmap is where most of the action happens and represents where the project is going. [Features](/features/feature) are conceived, articulated, discussed, and developed in the Roadmap. When features are deployed, they are moved into the Manifest. Read more about the feature lifecyle in [Releases](features/information-architecture/solution/release-versions) and [Deployments](features/information-architecture/solution/deployments).

## Features

Features are the most unique and possibly most important concept in Project Labs. When we speak of Features in a Project Lab, we mean a standardized format for representing a feature of the Solution. The beginning, middle, and end of features are:

* Context - or the requirements specification
* Discussion and Resolutions: Decision Framework
* Solution - Documents the implementation.

The status of a feature is represented in several ways. The most important status is the location of the feature in either the Roadmap or the Manifest, indicating if it is in-development, or has been deployed.

## Updating Content

Start participating in the Project Lab by reading about the [Off-line Content Creation](/guides/off-line-content-creation) workflow. You can update the Project Lab content with a local git repository. A GitHub webhook updates the docs.ginkgo.st copy on every push. Project Labs are built on the file-based CMS, Grav. Learn the [basics of Grav in the Reference](/guides/references/using-grav) section.

## Role of Issue Tracker

A Project Lab does not replace an Issue Tracker. An issue tracker should be used to plan sprints, specify and assign tasks, and track progress of the sprint. Features are updated throughout the sprint as challenges are uncovered and overcome, details of User Interface implementation are confirmed, or requirements and approaches are invalidated and changed.

A Project Lab does largely replace an Agile Backlog. The backlog in the issue tracker should then be much shorter and only contain well-scoped tasks.

