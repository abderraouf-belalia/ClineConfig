## Global Rules for Cline's Operation

These rules apply across all modes and guide Cline's general behavior and output.

### 1. Documentation Standards and Methodology

* **Clarity and Conciseness:** "All documentation, whether in-code comments, markdown files, or design documents, must be clear, concise, and unambiguous."
* **Structured Content:** "Utilize Markdown effectively with headings, bullet points, and code blocks to ensure well-structured and readable documentation."
* **Objective-Driven:** "Every piece of documentation should have a clear objective, stating its purpose at the beginning."
* **Accuracy and Up-to-dateness:** "Ensure documentation accurately reflects the current state of the codebase and is updated whenever relevant code or processes change."
* **Audience Awareness:** "Tailor the level of detail and technical jargon to the intended audience (e.g., developers, users, other agents)."
* **Self-Referencing:** "If a rule builds upon or relates to another, reference it by its filename to create a connected knowledge base."
* **Automated Documentation:** "Whenever possible, leverage tools and practices that support automated documentation generation to maintain consistency and reduce manual effort."

### 2. Approach to Version Control and Implementation of Features and Fixes

* **Frequent and Atomic Commits:** "Commit changes often, in small, logical chunks, with clear and descriptive commit messages that explain the purpose of the change."
* **Branching Strategy:** "Utilize feature branches for new functionalities or bug fixes to isolate work and prevent disruption to the main codebase. Use descriptive branch names (e.g., `feature/add-user-profile`, `bugfix/login-issue`)."
* **Branch Protection Rules:**
   - "Never commit directly to main branch - all changes must come through branches"
   - "Main branch must remain deployable at all times"
   - "Only human users may merge to main branch after review"
   - "All merges must be done via pull requests with approval checks"
* **Regular Merging/Rebasing:** "Regularly pull updates from the main branch into feature branches to minimize merge conflicts and integrate changes early."
* **Pull Request (PR) Workflow:** "All significant changes must go through a pull request review process to ensure code quality, adherence to standards, and to facilitate knowledge sharing."
* **Testing Integration:** "Integrate automated tests (unit, integration) into the CI/CD pipeline to ensure that new features and fixes do not introduce regressions and maintain code quality."
* **Test-Driven Development (TDD) Preference:** "Whenever applicable, favor a Test-Driven Development (TDD) approach: write tests based on expected inputs/outputs, ensure they fail, then write the code to make them pass, and finally refactor."
* **Backward Compatibility:** "Prioritize backward compatibility for public APIs and interfaces unless a major version bump is explicitly planned."

### 3. Exploration and Discovery of APIs, Documentation Gathering During Planning

* **Systematic API Exploration:** "When tasked with integrating or interacting with an API, systematically explore its functionalities. This includes identifying endpoints, understanding HTTP methods, examining parameters, and analyzing response structures."
* **Prioritize Official Documentation:** "Always refer to official API documentation as the primary source of truth for understanding API functionality and usage."
* **Demonstration Learning:** "In cases where documentation is missing, outdated, or unclear, attempt to learn API functionality directly from demonstrations or examples provided within the codebase or external resources."
* **Schema Understanding:** "Focus on understanding the input parameter schema and the expected output schema for each API function."
* **Authentication and Authorization:** "Identify and understand the authentication and authorization mechanisms required to access protected API resources."
* **Error Handling (API):** "Examine the API's error responses to understand how errors and exceptions are communicated and how to handle them gracefully."
* **Contextualization:** "When gathering API information, contextualize it within the current planning task, extracting only the most relevant details."

### 4. Feature/Fix Planning and Formulation of Testing Strategies

* **Requirement Analysis:** "Thoroughly analyze project requirements, user workflows, and business needs to define clear and measurable objectives for features and fixes."
* **Scope Definition:** "Clearly define the scope of the feature or fix, breaking it down into manageable sub-tasks. For fixes, identify the root cause of the issue before proposing solutions."
* **Solution Brainstorming:** "Explore multiple possible approaches to a problem, considering their trade-offs (e.g., efficiency, simplicity, maintainability, scalability)."
* **Comprehensive Test Planning:** "Formulate a comprehensive testing strategy for each feature or fix, considering various testing types:
    * **Unit Tests:** Focus on testing individual components or functions in isolation.
    * **Integration Tests:** Verify the interactions between different modules or services.
    * **Functional Tests:** Ensure the software meets specified functional requirements, simulating real-world usage.
    * **Performance Tests:** Assess system responsiveness, stability, and scalability under various loads.
    * **Security Tests:** Identify vulnerabilities and ensure the system is protected against common attacks.
    * **Regression Tests:** Ensure that new changes do not break existing functionalities."
* **Test Case Formulation:** "Develop clear test cases with expected inputs and outputs for each test type."
* **Prioritization:** "Prioritize test cases based on criticality and risk."
* **Automation Focus:** "Design tests with automation in mind to facilitate continuous testing in the CI/CD pipeline."
* **Post-Implementation Verification:** "Include steps for post-implementation verification, such as monitoring logs and user feedback, to ensure the deployed solution performs as expected."
