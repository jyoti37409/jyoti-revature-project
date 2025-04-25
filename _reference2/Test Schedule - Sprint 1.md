# Test Schedule
This document contains the Test schedule for the first sprint of the Planetarium project. It is organized by the Standard Testing Life Cycle phases, and includes entry and exit criteria for each phase.

## STLC Phases

### Phase 1: Test Analysis
In this phase, the testing team reviews and analyzes the requirements and provided documentation to determine test basis. They clarify any doubts with stakeholders and create a Requirement Traceability Matrix (RTM) to ensure all requirements will be covered by test cases

**Entry Criteria:**
- Test Documentation is available
- Stakeholder is available for clarification

**Exit Criteria:**
- Requirements are understood
- Requirement Traceability Matrix is created and ready for use
- Acceptance Criteria is created for User Stories

### Phase 2: Test Planning
This phase involves planning the testing activities. Previously determined test basis are used to identiy test conditions, and the RTM is updated to map requirements and acceptance criteria (Happy and Sad Path) with User Stories. The team sets up the Jira Scrum Project, organizes issues into epics, stories, and subtasks, based off the test conditions they determined, and assign story points to each issue to estimate the time effort required

**Entry Criteria:**
- RTM is available
- Test basis determined

**Exit Criteria:**
- Requirements mapped to User Stories in RTM
- Acceptance Criteria created for each User Story in RTM
- Jira Scrum Project created
- Issues organized into epics, stories, and subtasks
- Story points assigned to issues

### Phase 3: Test Case Design
Test cases are designed based on the test conditions determined in the previous phase. The team determines the necessary test data and creates feature files that outline the test scenarios and steps.

**Entry Criteria:**
- RTM updated with mappings
- Scrum Issues organized

**Exit Criteria:**
- Test data determined
- Feature files created

### Phase 4: Test Environment Setup
The test environment is prepared to ensure it mimics the production environment. The team sets up the test application and configures the environment to support the Planetarium application

**Entry Criteria:**
- Feature files available
- Planetarium application available

**Exit Criteria:**
- Test application created
- Environment configured for the Planetarium to function properly

### Phase 5: Test Execution
The final testing is performed in this phase. The team executes the test cases and generates test reports.

**Entry Criteria:**
- Test application present
- Planetarium configured to run

**Exit Criteria:**
- Tests executed successfully
- Test reports generated successfully

### Phase 6: Test Cycle Closure
This final phase involves wrapping up the testing activities. The team reviews the test results and creates defect reports for any issues found, linking them to the appropriate issues.

**Entry Criteria:**
- Test results available

**Exit Criteria:**
- Defect reports created and linked to appropriate issues
- Test results saved in a centralized location
