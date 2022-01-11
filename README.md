# Volkswagen Automotive Cloud Project Structure

```
    _    _
   /=\""/=\
  (=(0_0 |=)__       Ely
   \_\ _/_/   )      A stub project-structure for .NET services
     /_/   _  /\
    |/ |\ || |       "how to eat an elephant"
       ~ ~  ~
```       

Welcome to Ely, a bare-bones project structure intended to capture code, tests, specs, docs, and contributing guidelines.

## Goals

- **Self-contained** - everything needed to understand, build, deploy, test, and contribute to the project is contained in the repo
- **Familiar** - follows common open-source conventions and practices for easier on-boarding
- **Inclusive** - accounts for non-code assets such as requirements, samples, docs

## Designs

### Information Spread

Information is now spread out between repos. Can be managed via consistency and links.

# Getting Started

This project structure can be used either as a reference while restructuring an existing project or as a starting point for new projects. To use as a starting point first fork this repo and then add project files.

## Project Layout

```text
Ely/
├── CHANGELOG.md
├── README.md          # main page
├── LICENSE.md
├── infrastructure/    # infrastructure as code
    ├── alerts/
├── docs/              # design decisions
    ├── design/
        ├── architecture.md
    ├── development/
        ├── setup.md
├── src/               # source code
├── tests/             # test code/mocks
```

## Files

### CHANGELOG.md

Contains all notable changes to the project, organized by date and version. Changelogs are often overlooked yet are one of the most commonly requested pieces of information needed by other teams. While multiple methods exist to generate changelogs from work items or git commit history it's often more useful to update it by hand, either by individuals making the changes or by the team at known intervals such as sprint end.

- Used as release notes for both internal and external customers
- Based on the [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) format
- Works best in conjunction with semantic versioning
- Internal work item links should include description for those without access
- Dev Manager and Product Owner are responsible by default
  - Dev Manager ensures all technical changes are captured
  - Product Owner ensures consistent tone and public facing changes
- Is reviewed by entire team as part of Sprint End and Review

**Example**

```markdown
## [1.0.0] - YYYY.MM.DD

### Added

- A README.md file to describe using the project, setup, build, and test
- A CHANGELOG.md to track notable changes
```

### README.md

A project's README is the most important document in the project. It describes the project, it's goals, and provides links to all the information needs to work with the project. It serves as onboarding material for new developers, captures important security and legal requirements such as software licenses, open-source attribution, describes how others can and should interact with the team, how to file bugs, etc.

- Main landing page for the project
- Serves as welcome and guide
- Contains installation, build, test, and contribution instructions or links
- Can be either a single, large document or a collection of links to detailed documents that exist in the same repo

### LICENSE.md

A copy of the license agreement.

- Source code license
- Opt for more permissive, open-source licenses for common, non-IP code, such as MIT
  - Publishing non-critical code to public repos builds community trust and support

### CONTRIBUTING.md

Details how to contribute code, who to contact, how to file bugs, expectations of submitted code from non-Team members.

- How pull requests are handled
- How and where to file bugs
- How to search the existing bug list to see if it's already been reported
- Optionally describe how to interact with the team
- [Dapr Example](https://github.com/dapr/dapr/blob/master/CONTRIBUTING.md)

## Folders

### `/docs`

Contains all documentation, specs, major design decisions, diagrams and any other supporting documentation that describes the project. Traditionally this type of information lives in Word docs, wiki pages, work items, buried meeting notes or tribal knowledge.

Moving document management out of external systems and into a repo offers several advantages:

1. Decisions live next to the code, reducing the time to look up specific design details
2. Works consistently across all source control and work item tracking systems
3. Provides a consistent and accessible version of document history

**Best Practices**

- Prefer Markdown over binary formats
- Provide light-weight, simple templates
- Ensure all team members, including POs, coaches, tech writers, SREs have access
- Keep information with the project and provide links instead of copying/duplicating
- Keep documents up to date

### `/docs/decisions`

Architecture Decision Records (ADRs or simply decision records) are a collection of records for "architecturally significant" decisions. A decision record is a short markdown file in a specific light-weight format.

### `/docs/development`

Files