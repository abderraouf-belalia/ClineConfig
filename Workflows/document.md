---
description: "A detailed workflow for Cline (the AI assistant) to generate and enhance documentation within codebases based on a provided specification."
author: "Ergod"
version: "1.0"
tags: ["documentation", "code quality", "ai workflow", "agentic coding"]
globs: ["**/*.*"]
---
You are tasked with generating and enhancing documentation for source code files according to the provided `SPEC` (Documentation Workflow Prompt). Your goal is to produce consistent, agent-friendly documentation by identifying public APIs, adhering to core principles, and implementing standard conceptual sections mapped to language-specific syntax. Do not alter any functional code; only add or modify documentation comments.

<detailed_sequence_of_steps>

# Documentation Generation and Enhancement Process - Detailed Sequence of Steps

## 1. Identify Target Files and Scope

1.  **Receive Input:** The user will provide a list of source code files (e.g., `.ts`, `.py`, `.rs`, `.sol`) or a directory to scan.
2.  **Determine Language:** Identify the programming language of each file to apply the correct documentation syntax.
    * If uncertain, ask the user for clarification.
        ```xml
        <ask_followup_question>
        <question>I need to determine the programming language of the following file(s) to apply the correct documentation syntax: [list of files]. Could you please confirm the language (TypeScript, Python, Rust, Solidity)?</question>
        <options>["TypeScript", "Python", "Rust", "Solidity", "Other (Please specify)"]</options>
        </ask_followup_question>
        ```
3.  **Read File Content:** Read the full content of the target source code file(s).
    ```xml
    <read_file>
    <path>path/to/source_code.ts</path>
    </read_file>
    ```

## 2. Analyze Code for Public APIs and Existing Documentation

1.  **Parse Code Structure:** Internally, analyze the Abstract Syntax Tree (AST) or use regex/pattern matching (if AST parsing is not directly available) to identify:
    * All public (exported) functions, classes, methods, and significant data structures.
    * Their parameters, return types, and potential throws/errors.
    * Any existing documentation comments (JSDoc, docstrings, Rustdoc, NatSpec).
2.  **Extract Existing Docs:** If documentation exists, extract it and parse it into conceptual sections (`@summary`, `@description`, `@param`, etc.) for potential enhancement or migration to the standardized format.
3.  **Identify Missing Docs:** Determine which public APIs lack documentation or have incomplete documentation according to the `SPEC`.

## 3. Draft Documentation (Iterative for Each Component)

1.  **Focus on Component:** For each identified public API or significant data structure requiring documentation:
2.  **Generate Conceptual Sections:** Based on the code's functionality, generate content for the following conceptual sections, adhering to the principles of "Why," "What," and "How":
    * `@summary`: A concise one-liner describing its primary function.
    * `@description`: A detailed explanation of its functionality, logic, and any complexities.
    * `@param {Type} name - Description`: For each parameter, including type and detailed description.
    * `@returns {Type} - Description`: If applicable, including type and detailed description.
    * `@throws {ErrorType} - Description`: If applicable, documenting potential errors.
    * `@precondition`: Conditions that must be true before invocation.
    * `@postcondition / @sideEffects`: State changes or observable effects after completion.
    * `@example`: A concise code block demonstrating typical usage.
    * `@notes`: **CRUCIAL**: Include explicit guidance for AI agents (Recommended Usage, Performance, Security, Concurrency, Dependencies, Alternatives, Prioritization, Error Recovery).
        * **Self-Correction/Refinement for `@notes`**: After generating initial notes, critically review them. Are they truly useful for an AI? Do they offer more than what's obvious from the code? Are there any hidden pitfalls or common misuses an AI should be aware of? If not, refine or add more specific guidance.

3.  **Map to Language-Specific Syntax:** Translate the generated conceptual sections into the precise syntax for the identified language (JSDoc/TypeDoc, Google Style Docstrings, Rustdoc, NatSpec). Ensure correct formatting, indentation, and comment delimiters.

4.  **Integrate with Code:** Insert the newly drafted or enhanced documentation comments into the appropriate locations within the source code file, directly above the documented component.
    * **Maintain Existing Code:** Ensure *no functional code* is altered. Only documentation comments should be added or modified.

## 4. Review and User Confirmation

1.  **Present Changes for Review:** Once all documentation has been drafted and integrated into the file(s), present the proposed changes to the user in a diff format or clearly highlighted sections.
    ```xml
    <ask_followup_question>
    <question>I have drafted documentation for the following file(s) based on your specifications. Please review the proposed changes. Would you like me to apply these changes to the file(s)?</question>
    <options>["Yes, apply changes", "No, let me review the changes more closely and provide feedback", "No, revert all changes"]</options>
    </ask_followup_question>
    ```
2.  **Iterate on Feedback:** If the user selects "No, let me review the changes more closely and provide feedback," wait for their specific instructions or further questions. Be prepared to refine documentation based on their input.
    * If specific line-by-line feedback is provided, use `<edit_file>` with the provided changes.
    * If general instructions are given (e.g., "make the examples more concise"), re-enter step 3 focusing on that feedback.

## 5. Apply Changes

1.  **Write Documented File:** If the user approves, write the modified content back to the original file(s).
    ```xml
    <write_file>
    <path>path/to/source_code.ts</path>
    <content>
    [Fully documented source code content]
    </content>
    </write_file>
    ```
2.  **Confirmation:** Confirm to the user that the documentation has been updated.

</detailed_sequence_of_steps>