**Assignment 7 Reflection **

## Implementation Challenges

1. **Template Selection**:
   - Initially confused between Automated Kanban and Team Planning
   - Resolved by evaluating our need for automation vs. planning features

2. **Customization**:
   - Determining optimal WIP limits required experimentation
   - Deciding on column names needed team input

3. **Tool Comparison**:

| Feature         | GitHub Projects | Trello       | Jira          |
|-----------------|-----------------|--------------|---------------|
| Agile Support   | Good            | Basic        | Excellent     |
| Automation      | Medium          | Limited      | Advanced      |
| Integration     | Best (with GH)  | Good         | Good          |
| Learning Curve  | Easy            | Very Easy    | Steep         |

**Conclusion:** GitHub Projects provides the best balance for our needs with its native integration and sufficient Agile features.






## Assignment 8 Reflection

In-Depth Reflection on Workflow Modeling
1. Granularity Challenges: Striking the Right Balance
State Diagrams: The Abstraction Dilemma
Over-Granularity Pitfall:

Initially modeled every micro-state (e.g., Active.WithUnsyncedData, Active.WithSyncInProgress)

Resulted in cluttered diagrams that obscured core business logic

Example: Early versions of the Wearable Connection diagram had 15+ states

Under-Granularity Risks:

Merged critical states like Suspended and Banned initially

Missed edge cases (e.g., temporary suspensions vs permanent bans)

Solution: Used guard conditions (e.g., violationCount > 3) instead of new states

Sweet Spot:

5-7 core states per object

Detailed transitions/guards only for business-critical flows

## **State Diagrams vs. Activity Diagrams**

| **Aspect**               | **State Diagrams**                          | **Activity Diagrams**                     |
|--------------------------|--------------------------------------------|-------------------------------------------|
| **Primary Purpose**       | Model object lifecycle/behavior            | Model process workflows                   |
| **Core Elements**         | States, transitions, guard conditions      | Actions, decisions, swimlanes, forks      |
| **Best For**             | Showing how a single entity changes over time | Showing interactions between components  |
| **Agile Mapping**        | Maps to object states in user stories      | Maps to acceptance criteria steps         |
| **Key Strengths**        | Enforces business rules via guards         | Reveals process bottlenecks               |
| **Complexity Handle**    | Handles nested states well                 | Manages parallel flows effectively        |
| **Error Handling**       | Explicit error states                      | Decision nodes with error paths           |
| **Example Use Case**     | User account status (Active/Suspended)     | Registration flow across systems          |
| **Mermaid Syntax**       | `stateDiagram-v2`                          | `flowchart TD` or `flowchart LR`          |
| **Traceability**         | Links to entity-focused user stories       | Links to process-oriented requirements    |


Key Insights
Complementary Use:

Used state diagrams for persistent object behavior

Activity diagrams for cross-component processes

Agile Adaptation:

State diagrams helped refine INVEST criteria (Independent, Testable)

Activity diagrams exposed missing edge cases in user stories

Tool Limitations:

GitHub's Mermaid lacks advanced UML features (e.g., composite states)

Manual validation needed to ensure consistency with sprint tasks

Lessons Learned
Start Simple: Begin with minimal viable states/actions, then expand

Trace Early: Link diagram elements to requirements during creation

Validate Visually: Use color-coding (e.g., red for error states) to improve readability
