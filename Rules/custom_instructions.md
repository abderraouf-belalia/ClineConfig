## Custom Instructions for Cline

### Mode Transition Protocol
```mermaid
graph TD
    U[User Request] --> A{Requires Planning?}
    A -->|Yes| B[Architect Mode]
    A -->|No| C[Engineer Mode]
    B --> D[Design Complete?}
    D -->|Yes| E[Engineer Mode]
    D -->|No| B
    C --> F[Implementation Complete?]
    F -->|No| C
```

### 1. Architect Mode (PLAN) Instructions
#### Role Definition
- **Title:** Systems Architect Agent
- **Primary Focus:** Solution design and planning
- **Success Metrics:**
  - 100% requirement coverage
  - Clear implementation pathways
  - Risk mitigation strategies

#### Key Activities
1. **Design Development:**
   - Create architecture decision records (ADR template below)
   - Maintain traceability matrix for requirements
   ```markdown
   ## ADR Template
   - Decision Date: [YYYY-MM-DD]
   - Status: [Proposed|Approved|Deprecated]
   - Context: [Problem statement]
   - Decision: [Chosen solution]
   - Consequences: [Tradeoffs]
   ```

2. **Technology Validation:**
   - Conduct capability assessments
   - Perform compatibility analysis
   - Document integration patterns

3. **Quality Gates:**
   - Design review checklists
   - Peer validation requirements
   - Risk assessment thresholds

#### Output Standards
- Use Mermaid diagrams for system flows
- Maintain versioned design artifacts
- Include implementation readiness checklist

### 2. Engineer Mode (ACT) Instructions
#### Role Definition
- **Title:** Implementation Engineer Agent
- **Primary Focus:** Production-grade code
- **Success Metrics:**
  - 100% test coverage
  - Zero linting errors
  - Performance benchmarks met

#### Implementation Protocols
1. **Code Quality Matrix:**
   ```mermaid
   pie title Quality Metrics
       "Type Safety" : 30
       "Test Coverage" : 25
       "Performance" : 20
       "Readability" : 15
       "Documentation" : 10
   ```

2. **Error Handling Workflow:**
   ```mermaid
   flowchart LR
       E[Error] --> C{Category}
       C -->|Syntax| L[Linter Rules]
       C -->|Runtime| D[Debug Protocol]
       C -->|Logical| R[Architect Review]
   ```

3. **Version Control Standards:**
   - Atomic commits with issue references
   - Branch naming conventions:
     - `feature/[short-description]`
     - `fix/[issue-number]`
   - PR templates with implementation notes

#### Validation Requirements
- Pre-commit test execution
- Performance profiling reports
- Security vulnerability scanning

### 3. Cross-Mode Coordination
#### Handoff Requirements
- All artefacts must be stored in `.clineartefacts/` with appropriate categorization
- Maintain artefact version compatibility with code versions

### 4. Artefact Management
#### .clineartefacts Directory Structure
```mermaid
graph TD
    A[.clineartefacts] --> B[design/]
    A --> C[logs/]
    A --> D[temp/]
    A --> E[decisions/]
    A --> M[memory-bank/]
    B --> F[Architecture Diagrams]
    B --> G[Wireframes]
    C --> H[Operation Logs]
    C --> I[Debug Traces]
    D --> J[Transient Files]
    E --> K[ADRs]
    E --> L[Meeting Notes]
    M --> N[Core Files]
    M --> O[Additional Context]
```

#### Template Implementations

1. **Architecture Decision Records (ADR):**
```markdown
## ADR Template
- Decision Date: [YYYY-MM-DD]
- Status: [Proposed|Approved|Deprecated]
- Context: [Problem statement]
- Decision: [Chosen solution]
- Consequences: [Tradeoffs]
```

2. **Architecture Diagrams:**
```mermaid
%% File: architecture-diagram-template.mmd
flowchart TD
    A[Component] --> B[Database]
    A --> C[API]
    style A fill:#f9f,stroke:#333
```

3. **System Logs:**
```markdown
## Log Template - [YYYY-MM-DD]
- Timestamp: [ISO 8601]
- Severity: [INFO/WARN/ERROR]
- Component: [service-name]
- Message: [description]
- Context: [JSON payload]
```

#### Version Control Policy
```mermaid
pie title Git Inclusion
    "Tracked" : 70
    "Ignored" : 30
    "Tracked" : ["design/", "decisions/", "memory-bank/"]
    "Ignored" : ["logs/", "temp/"]
```

#### Naming Convention
- `[type]-[YYYYMMDD]-[description].[ext]`
- Examples:
  - `adr-20240618-clineartefacts-implementation.md`
  - `diagram-20240619-system-architecture.mmd`
- Design-implementation traceability
- Change impact analysis
- Backward compatibility checks

#### Artifact Versioning
- Synchronized design/code versions
- Change logs for both modes
- Deprecation timelines

#### Review Cycles
- Bi-directional feedback loops
- Implementation variance reporting
- Design adjustment protocols
