## Global Workflows for Repeatable Processes

These workflows outline step-by-step procedures for common development tasks, promoting deterministic execution and consistency.

### 1. Feature Development Workflow

This workflow guides Cline through the process of developing a new feature from conception to deployment.

1.  **Understand Feature Requirements (Architect Mode):**
    * Analyze user stories, use cases, and business requirements.
    * Ask clarifying questions to ensure a complete understanding of the feature.
    * Identify dependencies and potential external integrations.
2.  **Architectural Design (Architect Mode):**
    * Propose high-level design, component breakdown, and data flow.
    * Select appropriate technologies and libraries.
    * Formulate a high-level implementation plan and define milestones.
    * Outline initial testing strategy for the feature.
    * Document the architectural design.
3.  **Setup Development Environment (Engineer Mode):**
    * Create a new feature branch from the main development branch.
    * Ensure all necessary dependencies are installed.
    * Verify the development environment is correctly configured.
4.  **Implement Feature (Engineer Mode):**
    * Write unit tests for individual components (TDD approach preferred).
    * Implement code based on the architectural design and coding standards.
    * Run unit tests and ensure they pass.
    * Perform frequent, atomic commits with descriptive messages.
5.  **Integration and Testing (Engineer Mode):**
    * Write integration tests to verify component interactions.
    * Run integration tests and resolve any issues.
    * Perform local functional testing to ensure the feature works as expected.
    * Ensure code passes linting and type checking.
6.  **Code Review and Refinement (Engineer Mode):**
    * Create a pull request for the feature branch.
    * Address any feedback from code reviews.
    * Refine code and tests as necessary.
7.  **Merge and Deploy:**
    * Once approved, merge the feature branch into the main development branch.
    * Trigger CI/CD pipeline for automated builds, tests, and deployment.
    * Monitor deployment and initial performance.

### 2. Bug Fix Workflow

This workflow provides a structured approach for Cline to identify, fix, and verify bugs.

1.  **Reproduce Bug (Engineer Mode):**
    * Analyze bug report and steps to reproduce.
    * Attempt to reproduce the bug in a controlled environment.
    * If unable to reproduce, request more information.
2.  **Diagnose Root Cause (Engineer Mode):**
    * Examine relevant code, logs, and system state.
    * Utilize debugging tools and techniques.
    * Identify the exact cause of the bug.
3.  **Propose Fix (Architect/Engineer Mode):**
    * Based on the root cause, propose a fix.
    * Consider potential side effects or regressions.
    * If the fix is complex, switch to Architect mode for a mini-design phase.
4.  **Implement Fix (Engineer Mode):**
    * Create a new bugfix branch.
    * Write a new test case that specifically reproduces the bug and fails before the fix.
    * Implement the code changes to fix the bug.
    * Run the new test and ensure it passes.
    * Run all relevant existing tests (unit, integration, regression) to ensure no new issues are introduced.
    * Commit the fix with a descriptive message referencing the bug.
5.  **Code Review and Verification (Engineer Mode):**
    * Create a pull request for the bugfix branch.
    * Address feedback from reviewers.
    * Ensure the fix is verified in a testing environment by human testers if applicable.
6.  **Merge and Deploy:**
    * Merge the bugfix branch into the main development branch.
    * Trigger CI/CD pipeline.
    * Monitor post-deployment for recurrence of the bug.

### 3. API Integration Workflow

This workflow guides Cline through the process of integrating a new external API or extending existing API usage.

1.  **Understand API Requirements (Architect Mode):**
    * Identify the purpose of the API integration and the data to be exchanged.
    * Determine which specific API endpoints and methods are needed.
2.  **API Discovery and Documentation (Architect Mode):**
    * Access and review the official API documentation.
    * Identify authentication/authorization mechanisms, rate limits, and error handling.
    * Explore API functionality using available tools (e.g., Postman, `curl`).
    * Gather necessary API keys or credentials.
3.  **Design Integration Strategy (Architect Mode):**
    * Propose how the new API will integrate with existing system components.
    * Define data mapping and transformation logic.
    * Outline error handling and retry mechanisms for API calls.
    * Consider caching strategies if applicable.
4.  **Implement API Client (Engineer Mode):**
    * Create a dedicated API client or service layer for the external API.
    * Implement methods for each required API endpoint.
    * Handle authentication and authorization.
    * Implement robust error handling and logging for API interactions.
5.  **Testing API Integration (Engineer Mode):
    * Write unit tests for the API client methods, mocking external calls.
    * Write integration tests that make actual (or sandboxed) API calls to verify connectivity and data exchange.
    * Perform functional tests to ensure the end-to-end integration works as expected.
6.  **Refine and Document (Engineer Mode):**
    * Optimize API calls for performance and efficiency.
    * Update internal documentation on API usage, limitations, and common issues.
    * Ensure secure handling of API credentials.