# DevOps and Agile Interview Questions

## Agile and Azure DevOps

### 1. What is Azure Boards?
Azure Boards is the work-management service in Azure DevOps. Teams use it to plan, track, and discuss work through backlogs, Kanban boards, sprint boards, queries, and dashboards. Work items can represent epics, features, user stories, tasks, bugs, and other tracked items.

### 2. What is Jira?
Jira is Atlassian’s project and issue-tracking tool. Software teams commonly use it to manage backlogs, sprints, bugs, workflows, and reports. It supports Scrum and Kanban and can integrate with source-control and CI/CD tools.

### 3. What is Trello?
Trello is a visual work-management tool based on boards, lists, and cards. It is often used for lightweight Kanban workflows, personal task tracking, and smaller projects. Compared with Jira or Azure Boards, it generally offers less built-in support for software development processes and complex reporting.

### 4. What are Agile work items such as Epic, Feature, User Story, Task, Bug, and Issue?
These are records used to describe and track work. Their exact names and hierarchy can vary by tool and configured process.

- Epic: A large goal or initiative that may span multiple releases or teams.
- Feature: A significant capability that contributes to an epic.
- User Story: A user-focused requirement, often phrased as “As a…, I want…, so that…”
- Task: A specific piece of implementation or operational work, often associated with a story.
- Bug: A defect where software does not behave as expected.
- Issue: A general tracked item; in some tools it is an umbrella term, while in Azure Boards it may be a specific work-item type in certain processes.

### 5. How do you organize work items on an Agile board?
Start with a prioritized backlog, then group related work under larger goals such as epics or features. Break user stories into manageable tasks, estimate and prioritize them, and assign them to a sprint or Kanban workflow. On the board, move work through agreed stages—for example, To Do → In Progress → Review → Done—and keep ownership, acceptance criteria, and status up to date. Teams should also limit work in progress where appropriate.

### 6. What are Azure DevOps dashboards?
Dashboards are configurable pages that display project or team information using widgets. They can show items such as sprint progress, work-item queries, build and release status, test results, and team velocity. Dashboards help teams monitor work and identify issues without opening each report or pipeline separately.

### 7. What are Azure Pipelines, and how do you create a pipeline?
Azure Pipelines is Azure DevOps’ CI/CD service. It can build, test, and deploy applications to Azure or other environments.

A typical setup is:

1. Put the application code in a supported repository, such as Azure Repos or GitHub.
2. Create a pipeline and select the repository.
3. Choose a starter template or configure a YAML pipeline.
4. Define triggers, build steps, tests, and deployment stages.
5. Configure required permissions, environments, and service connections.
6. Run the pipeline, review its results, and add approvals or checks where needed.

A pipeline commonly builds and tests changes on pull requests, then deploys approved artifacts through one or more environments.

### 8. What are service connections, and how do you connect Azure DevOps to external services?
A service connection is a configured integration that lets an Azure DevOps pipeline authenticate to an external system, such as an Azure subscription, container registry, Kubernetes cluster, or cloud provider.

To create one, an authorized user selects the target service type in project settings, configures its authentication details, and grants the pipeline access. Prefer short-lived credentials or workload identity federation where supported, limit permissions to what the pipeline needs, and avoid storing secrets in source code.

## DevOps Concepts

### 9. What is GitOps?
GitOps is an approach to operating infrastructure and applications where Git is the source of truth for the desired system state. Changes are proposed and reviewed through Git, and automation applies those changes to the target environment. A reconciliation tool can continuously compare the actual state with the declared state and correct drift.

### 10. What are the advantages and disadvantages of DevOps?
Advantages
- Faster, more frequent delivery through automation.
- Earlier feedback from builds, tests, and monitoring.
- More consistent environments and deployments.
- Better collaboration between development and operations.
- Faster detection and recovery from failures.

Disadvantages or challenges
- Requires organizational and cultural change, not just new tools.
- Automation and platform setup take time and ongoing maintenance.
- Poorly designed automation can spread mistakes quickly.
- Teams need appropriate security controls and access management.
- Continuous delivery can expose gaps in testing, observability, or ownership if those practices are immature.

### 11. What is the role and importance of DevOps in full-stack development?
DevOps connects full-stack development with the processes needed to build, test, deploy, and operate an application. It helps coordinate changes across the user interface, APIs, databases, infrastructure, and configuration. CI/CD pipelines automate checks and deployments, while monitoring and feedback help teams spot problems in production and improve the product. This makes delivery more repeatable and supports faster, safer releases.

## Related Comparisons and Processes

### 12. What is the difference between Azure DevOps, Git, GitHub, and GitOps?
- Azure DevOps: A suite of development services that includes boards, repositories, pipelines, test management, and package feeds.
- Git: A distributed version-control system used to track changes to files and collaborate through branches and commits.
- GitHub: A hosted platform for Git repositories, collaboration, code review, and automation, including GitHub Actions.
- GitOps: An operational practice that uses Git-managed declarations as the source of truth for deploying and maintaining systems.

Git is the version-control technology; GitHub and Azure DevOps are platforms that provide services around software development; GitOps is a way of managing delivery and operations.

### 13. What is the difference between Docker and containers? How do they help in DevOps?
A container is an isolated, runnable environment for an application and its dependencies. Docker is a platform and set of tools commonly used to build, distribute, and run container images and containers.

Containers help DevOps by making application environments more consistent across development, testing, and production. They can simplify packaging and deployment, support scaling, and work well with automated pipelines. Containers still rely on the host operating system’s kernel, so they are not the same as virtual machines.

### 14. What is the DevOps process? How does it work, and what are the architectures of Azure DevOps and GitOps?
The DevOps process is a continuous cycle of planning, coding, building, testing, releasing, deploying, operating, and monitoring. Feedback from users and production monitoring informs the next planning and development cycle. Automation, collaboration, version control, and observability support the cycle.

Azure DevOps architecture is commonly organized around services connected to shared repositories and pipelines:

- Azure Boards manages plans and work items.
- Azure Repos stores source code.
- Azure Pipelines builds, tests, and deploys.
- Azure Test Plans supports test planning and execution.
- Azure Artifacts stores and shares packages.

A pipeline can connect these services: for example, a work item is linked to a code change, which triggers a build and tests, then deploys the resulting artifact to an environment.

GitOps architecture usually includes:

1. Git repository: Holds the declared application and/or infrastructure configuration.
2. CI system: Builds and tests code, then publishes artifacts and updates deployment configuration when appropriate.
3. GitOps controller or agent: Watches the repository and reconciles the target environment to match the declared configuration.
4. Target environment: Such as a Kubernetes cluster or cloud infrastructure.
5. Monitoring and feedback: Reports health and drift, prompting follow-up changes through Git.

In short, Azure DevOps is a platform that provides development and delivery services; GitOps is a method of operating systems using Git as the desired-state source of truth.
