# Claude Code MCP Guide: Enhancing Memory and Sequential Thinking

## Table of Contents

1. [Introduction](#introduction)
2. [Understanding the MCP Framework](#understanding-the-mcp-framework)
   - [Memory](#memory)
   - [Context](#context)
   - [Planning](#planning)
3. [Setting Up Claude Code for MCP](#setting-up-claude-code-for-mcp)
   - [Installation and Configuration](#installation-and-configuration)
   - [Project Structure for Sequential Thinking](#project-structure-for-sequential-thinking)
4. [Memory Enhancement Techniques](#memory-enhancement-techniques)
   - [State Tracking Files](#state-tracking-files)
   - [Session Journals](#session-journals)
   - [Contextual Breadcrumbs](#contextual-breadcrumbs)
5. [Sequential Thinking Frameworks](#sequential-thinking-frameworks)
   - [Task Decomposition Strategies](#task-decomposition-strategies)
   - [Step-by-Step Execution Model](#step-by-step-execution-model)
   - [Verification Checkpoints](#verification-checkpoints)
6. [Practical MCP Implementation](#practical-mcp-implementation)
   - [Starting an MCP Session](#starting-an-mcp-session)
   - [Maintaining State Between Interactions](#maintaining-state-between-interactions)
   - [Context Restoration After Interruptions](#context-restoration-after-interruptions)
7. [Advanced Techniques](#advanced-techniques)
   - [Structured Reasoning Chains](#structured-reasoning-chains)
   - [Long-Running Tasks with Checkpointing](#long-running-tasks-with-checkpointing)
   - [Multi-Stage Problem Solving](#multi-stage-problem-solving)
8. [MCP Templates and Patterns](#mcp-templates-and-patterns)
   - [Project State Template](#project-state-template)
   - [Sequential Task Template](#sequential-task-template)
   - [Reasoning Chain Template](#reasoning-chain-template)
9. [Case Studies and Examples](#case-studies-and-examples)
   - [Multi-Step Refactoring Project](#multi-step-refactoring-project)
   - [Sequential Feature Implementation](#sequential-feature-implementation)
   - [Debugging Complex Issues](#debugging-complex-issues)
10. [Troubleshooting MCP Issues](#troubleshooting-mcp-issues)
    - [Handling Context Loss](#handling-context-loss)
    - [Recovering from Reasoning Errors](#recovering-from-reasoning-errors)
    - [Optimizing Context Usage](#optimizing-context-usage)

## Introduction

Claude Code is an AI-powered command-line tool that assists with software development tasks. While powerful, AI assistants naturally face challenges with maintaining long-term memory and thinking sequentially across multiple steps. This guide introduces the Memory, Context, and Planning (MCP) framework—a methodology designed to enhance Claude Code's ability to handle complex, multi-stage tasks through structured approaches to memory management and sequential thinking.

The MCP framework helps Claude Code overcome inherent limitations of AI assistants by creating explicit memory structures, managing context efficiently, and implementing deliberate planning strategies. This approach transforms Claude Code from a reactive tool into a more effective partner for complex software development projects.

## Understanding the MCP Framework

### Memory

Memory in the MCP framework refers to the deliberate recording and referencing of information, decisions, and state across interactions. Unlike human memory, Claude Code doesn't inherently "remember" previous work, so the MCP framework creates explicit memory structures:

- **Short-term memory**: Information needed within the current task sequence
- **Long-term memory**: Project-wide knowledge that persists across sessions
- **Working memory**: The active set of considerations for the current step

Enhancing Claude Code's memory isn't about technical modifications to the AI, but rather implementing workflows and documentation practices that simulate memory.

### Context

Context refers to the relevant information Claude Code needs to understand the current state of work:

- **Project context**: Overall project goals, architecture, and standards
- **Task context**: The specific task at hand, its requirements, and constraints
- **Historical context**: Previous decisions and their rationales
- **Technical context**: Language-specific, framework-specific, or domain-specific considerations

Managing context effectively means strategically controlling what information is provided to Claude Code at any given time, ensuring it has the right information without exceeding context window limitations.

### Planning

Planning involves breaking down complex tasks into manageable sequences and establishing a clear path forward:

- **Task decomposition**: Breaking large problems into smaller, sequential steps
- **Dependency management**: Identifying which tasks must precede others
- **Verification strategies**: Defining how to validate successful completion of each step
- **Adaptive planning**: Adjusting plans based on intermediate results

Effective planning allows Claude Code to focus on one step at a time while maintaining awareness of the overall goal.

## Setting Up Claude Code for MCP

### Installation and Configuration

1. **Install Claude Code**:
   - Follow the standard installation instructions for Claude Code
   - Ensure you have the latest version for best performance

2. **Create an MCP Project Directory Structure**:
   ```
   project/
   ├── .claude/
   │   ├── state.md            # Tracks current project state
   │   ├── memory/             # Directory for persistent memory files
   │   │   ├── decisions.md    # Records key decisions
   │   │   ├── progress.md     # Tracks overall progress
   │   │   └── tasks/          # Individual task memory files
   │   ├── sessions/           # Session journals
   │   └── templates/          # MCP templates
   ├── src/                    # Your actual project code
   ├── docs/                   # Project documentation
   └── README.md               # Project overview
   ```

3. **Configure Shell Integration** (optional):
   - Create aliases for common MCP patterns
   - Set up environment variables for project paths

### Project Structure for Sequential Thinking

Organize your project to support sequential thinking:

1. **Task Breakdown Files**:
   Create a `tasks.md` file that explicitly breaks down large features into sequential steps:

   ```markdown
   # Feature: User Authentication System

   ## Sequential Implementation Plan

   1. [  ] Define user data model
      a. [  ] Design database schema
      b. [  ] Create model classes
      c. [  ] Implement validation

   2. [  ] Implement authentication logic
      a. [  ] Password hashing and verification
      b. [  ] Session management
      c. [  ] Token generation

   3. [  ] Create API endpoints
      a. [  ] Registration endpoint
      b. [  ] Login endpoint
      c. [  ] Password reset flow

   4. [  ] Frontend integration
      a. [  ] Create authentication forms
      b. [  ] Implement client-side validation
      c. [  ] Add auth state management
   ```

2. **Stage-Based Directories**:
   For complex projects, consider organizing code by development stages:

   ```
   feature/
   ├── stage1-data-model/
   ├── stage2-auth-logic/
   ├── stage3-api-endpoints/
   └── stage4-frontend/
   ```

   This organization reinforces sequential development and makes it easier for Claude Code to understand the current stage.

## Memory Enhancement Techniques

### State Tracking Files

Create and maintain state files that Claude Code can reference:

```markdown
# Project State: User Authentication System
Last Updated: 2025-03-15

## Current Stage: 2b - Session Management

## Completed Steps:
- ✅ 1a: Designed user schema with fields: id, username, email, password_hash, created_at, last_login
- ✅ 1b: Created User model with basic attributes
- ✅ 1c: Implemented validation for email and password strength
- ✅ 2a: Implemented bcrypt password hashing and verification

## Current Work:
- 🔄 2b: Implementing session management
  - Created session table in database
  - Implemented session creation
  - TODO: Session expiration handling
  - TODO: Implement remember-me functionality

## Next Steps:
- 2c: Token generation for API authentication
- 3a: User registration endpoint

## Key Decisions:
- Using JWT for API authentication
- Sessions stored in database rather than Redis (revisit if scale requires)
- Password reset tokens valid for 24 hours

## Known Issues:
- Need to add rate limiting for login attempts
```

Update this file after each significant development step and reference it at the beginning of new Claude Code sessions.

### Session Journals

Maintain detailed session journals to track work done with Claude Code:

```markdown
# Session Journal: 2025-03-15

## Session Goals
- Complete session management implementation
- Begin token generation functionality

## Work Completed
- Implemented session expiration handling
  - Added `expires_at` column to sessions table
  - Created cleanup cron job
  - Added forced expiration on password change
- Started remember-me functionality
  - Added persistent token storage
  - Implemented auto-renewal of sessions

## Challenges Encountered
- Edge case with multiple active sessions per user
  - Solution: Added session listing and management UI

## Next Session Plan
- Complete remember-me functionality
- Begin implementation of JWT token generation

## Code Changes
- Modified `SessionManager.php`: Added expiration logic
- Created `SessionCleanup.php`: Implemented cron job
- Updated `LoginController.php`: Added remember-me checkbox handling
```

Share relevant parts of these journals when resuming work with Claude Code to help it understand what was previously accomplished.

### Contextual Breadcrumbs

Leave explicit breadcrumbs in your code for Claude Code to follow:

```php
// [MCP:MEMORY] 2025-03-15: Implemented basic session creation
// [MCP:MEMORY] 2025-03-15: Added session expiration handling
// [MCP:MEMORY] 2025-03-16: Implemented remember-me functionality
// [MCP:TODO] Add session invalidation on password change

public function createSession(User $user, bool $rememberMe = false): Session
{
    // Implementation...
}
```

These breadcrumbs create a timeline within the code itself, helping Claude Code understand the evolution of the codebase.

## Sequential Thinking Frameworks

### Task Decomposition Strategies

1. **Hierarchical Decomposition**:
   Break tasks down into a hierarchy of steps and substeps:

   ```
   Task: Implement User Authentication
   ├── Step 1: Design Data Models
   │   ├── Step 1.1: Define user schema
   │   ├── Step 1.2: Define session schema
   │   └── Step 1.3: Define relationships
   ├── Step 2: Implement Core Logic
   │   ├── ...
   ```

2. **Pipeline Decomposition**:
   Organize tasks as data flowing through a pipeline:

   ```
   Raw User Input → Validation → Authentication → Session Creation → Response
   ```

3. **State-Based Decomposition**:
   Define tasks in terms of state transitions:

   ```
   Anonymous → Credentials Provided → Validated → Authenticated → Session Established
   ```

When working with Claude Code, explicitly describe which decomposition strategy you're using and the current position within it.

### Step-by-Step Execution Model

Implement a clear execution model for working through sequential tasks:

1. **Setup Phase**:
   ```
   I'm implementing user authentication following our sequential plan.
   We're currently at Step 2b: Session Management.
   
   Previous steps completed:
   - Designed database schema
   - Created models
   - Implemented password hashing
   
   In this step, we need to:
   1. Create session storage
   2. Implement session creation on login
   3. Add session validation
   4. Handle session expiration
   
   Let's start with subtask 1: Creating session storage.
   ```

2. **Execution Phase**:
   For each subtask:
   
   ```
   Let's implement subtask 1: Creating session storage.
   
   We need to:
   - Define a sessions table
   - Create a Session model
   - Add methods for session CRUD operations
   
   Let's begin with the database schema.
   ```

3. **Verification Phase**:
   After completing each subtask:
   
   ```
   We've now implemented the session storage with:
   - Sessions table with fields: id, user_id, token, expires_at, ip_address, user_agent
   - Session model with creation and validation methods
   - Repository pattern for session management
   
   Let's verify this implementation:
   
   1. The schema includes all necessary fields for tracking and security ✅
   2. The model properly encapsulates session logic ✅
   3. We've included methods for creating, validating, and expiring sessions ✅
   
   This subtask is complete. Let's move to subtask 2: Implementing session creation on login.
   ```

4. **Transition Phase**:
   Explicitly transition to the next subtask:
   
   ```
   Now that we've completed session storage, let's implement session creation during user login.
   
   For context, here's our login flow:
   1. User submits credentials
   2. We validate credentials (already implemented)
   3. We need to create a session (current task)
   4. Return session token to user
   
   Let's focus on step 3...
   ```

### Verification Checkpoints

Implement explicit verification at multiple levels:

1. **Subtask Verification**:
   After each small step, verify correctness:
   
   ```
   I've implemented the session creation method. Let's verify it:
   
   Requirements:
   - Must create a unique token ✅
   - Must set appropriate expiration ✅
   - Must store IP and user agent ✅
   - Must invalidate old sessions if limit reached ✅
   
   The implementation meets all requirements.
   ```

2. **Task Verification**:
   After completing a major task:
   
   ```
   We've now completed the entire session management system. Let's verify against our requirements:
   
   1. Sessions are securely created with random tokens ✅
   2. Sessions expire appropriately ✅
   3. Users can have multiple sessions ✅
   4. Remember-me functionality extends sessions ✅
   5. Sessions are properly validated on each request ✅
   
   All requirements are met. Let's update our project state to mark this task complete and move to the next step: JWT token generation.
   ```

3. **Integration Verification**:
   Verify that completed components work together:
   
   ```
   Now that we've implemented both session management and JWT token generation, let's verify they work together properly:
   
   Test scenario: User logs in
   1. Credentials validated ✅
   2. Session created in database ✅
   3. JWT token generated with correct payload ✅
   4. Token returned to user ✅
   5. User can access protected resources with token ✅
   
   The integration is working as expected.
   ```

## Practical MCP Implementation

### Starting an MCP Session

When starting a new Claude Code session, include comprehensive context:

```
I'm continuing development on our user authentication system using the MCP framework for sequential development.

Here's our current project state:
<paste content of state.md>

Today, we'll be working on Stage 2c: JWT token generation.

Specifically, we need to:
1. Set up a secure key for JWT signing
2. Implement token generation with proper claims
3. Create token validation middleware
4. Add token refresh functionality

Let's start with step 1: Setting up a secure key for JWT signing.
```

### Maintaining State Between Interactions

Between Claude Code interactions in the same session:

1. **Summarize Progress**:
   ```
   We've now completed the JWT key setup by:
   - Generating a secure key
   - Storing it in environment variables
   - Adding a configuration provider
   
   Next, let's move to step 2: Implementing token generation with proper claims.
   ```

2. **Provide Transition Context**:
   ```
   For token generation, we need to consider:
   - What user data should be included in the token
   - Token expiration time
   - Refresh token strategy
   
   Let's implement the JWTService class that will handle token generation.
   ```

3. **Update State Documents**:
   After significant progress, update your state tracking file and reference the changes:
   
   ```
   I've updated our project state file to reflect the completion of JWT key setup.
   
   Current state:
   <paste updated state section>
   
   Now, let's continue with token generation.
   ```

### Context Restoration After Interruptions

If your Claude Code session is interrupted or you need to start a new session:

1. **Explicit Restoration Point**:
   ```
   I need to restore our previous Claude Code session on the authentication system.
   
   We were working on JWT token generation and had completed:
   - Setting up the secure signing key
   - Defining the token structure
   
   We were in the middle of implementing the token generation method in JWTService.php.
   
   Here's the code we had so far:
   
   ```php
   public function generateToken(User $user): string
   {
       // Define standard claims
       $issuedAt = new DateTimeImmutable();
       $expire = $issuedAt->modify('+15 minutes');
       
       // TODO: Add custom claims
       // TODO: Implement signing
   }
   ```
   
   Let's continue by implementing the custom claims and token signing.
   ```

2. **Session Journal Reference**:
   ```
   According to our session journal from yesterday:
   
   <paste relevant section of session journal>
   
   We need to pick up by implementing the token refresh functionality.
   ```

3. **State Reestablishment**:
   ```
   Before continuing, let's make sure we're aligned on the current state of the authentication system:
   
   <paste current state.md content>
   
   Given this state, we'll now focus on implementing the token refresh endpoint.
   ```

## Advanced Techniques

### Structured Reasoning Chains

Implement explicit reasoning chains for complex decisions:

```
Let's think through our token refresh strategy step by step:

1. Problem: JWT tokens need to be short-lived for security, but we want to avoid forcing users to log in frequently.

2. Options:
   A. Single refresh token with long expiry
   B. Rotating refresh tokens
   C. Sliding expiration window
   
3. Analysis:
   - Option A is simplest but has security implications if the refresh token is compromised
   - Option B is more secure as refresh tokens change after each use
   - Option C provides good UX but requires more server-side state
   
4. Trade-offs:
   - Security vs. Implementation Complexity
   - User Experience vs. Security
   
5. Decision criteria:
   - We need high security for this financial application
   - Implementation complexity is acceptable for security benefits
   - User experience should be good but security takes priority
   
6. Decision:
   We'll implement Option B: Rotating refresh tokens, because:
   - Provides best security by limiting the lifetime of any single token
   - Allows us to invalidate specific refresh token chains if needed
   - Acceptable implementation complexity for the security benefits
   
7. Implementation approach:
   - Store refresh tokens in the database with reference to the parent token
   - Implement token rotation on each refresh
   - Add token family concept to prevent replay attacks
   
Let's proceed with implementing this approach.
```

### Long-Running Tasks with Checkpointing

For tasks that span multiple sessions, implement checkpointing:

1. **Define Checkpoints**:
   ```
   We're implementing the entire authentication system, which will take multiple sessions. Let's define checkpoints:
   
   - Checkpoint 1: Data models and basic validation ✅
   - Checkpoint 2: Core authentication logic
     - 2.1: Password handling ✅
     - 2.2: Session management ✅
     - 2.3: JWT implementation 🔄
   - Checkpoint 3: API endpoints
   - Checkpoint 4: Frontend integration
   
   We're currently at Checkpoint 2.3: JWT implementation.
   ```

2. **Checkpoint State Files**:
   Create dedicated state files for each checkpoint in `.claude/memory/checkpoints/`

3. **Checkpoint Verification**:
   Before moving to a new checkpoint:
   
   ```
   Before moving to Checkpoint 3, let's verify Checkpoint 2 is complete:
   
   2.1 Password handling:
   - Secure hashing implemented ✅
   - Password validation rules established ✅
   - Password reset flow created ✅
   
   2.2 Session management:
   - Session creation and storage implemented ✅
   - Session validation working ✅
   - Remember-me functionality working ✅
   
   2.3 JWT implementation:
   - Secure key management implemented ✅
   - Token generation with proper claims working ✅
   - Token validation middleware created ✅
   - Refresh token rotation implemented ✅
   
   All items in Checkpoint 2 are complete. We can now proceed to Checkpoint 3: API endpoints.
   ```

### Multi-Stage Problem Solving

For complex problems, implement a formal multi-stage approach:

1. **Understanding Stage**:
   ```
   We need to implement a secure password reset flow. Let's start by understanding the problem:
   
   Requirements:
   - Users should be able to request a password reset via email
   - Reset links should be secure and time-limited
   - Users should set a new password that meets our requirements
   - Old sessions should be invalidated after password change
   
   Security considerations:
   - Token must be sufficiently random and unguessable
   - Process should be resistant to enumeration attacks
   - Rate limiting should prevent abuse
   
   Let's make sure we fully understand the problem before proceeding to design.
   ```

2. **Design Stage**:
   ```
   Now that we understand the password reset requirements, let's design the solution:
   
   Components needed:
   1. Password reset request endpoint
   2. Token generation and storage mechanism
   3. Email service integration
   4. Token verification endpoint
   5. Password update mechanism
   6. Session invalidation logic
   
   Data model changes:
   - Add password_reset_token field to user table
   - Add password_reset_expires field to user table
   
   Flow design:
   [User requests reset] → [Generate token, store, send email] → [User clicks link] → [Verify token] → [User sets new password] → [Update password, invalidate token and sessions]
   
   Let's validate this design before implementation.
   ```

3. **Implementation Stage**:
   Break down and implement each component sequentially using step-by-step execution.

4. **Verification Stage**:
   ```
   Now that we've implemented the password reset flow, let's verify it against our requirements:
   
   Functional verification:
   - Request endpoint returns success and sends email ✅
   - Email contains correct reset link ✅
   - Invalid or expired tokens are rejected ✅
   - Password update enforces validation rules ✅
   - Old sessions are invalidated after password change ✅
   
   Security verification:
   - Tokens are cryptographically secure (32 bytes random) ✅
   - Tokens are time-limited (1 hour expiry) ✅
   - Rate limiting prevents brute force (5 attempts per hour) ✅
   - Success/failure messages don't leak account existence ✅
   
   The implementation meets all functional and security requirements.
   ```

## MCP Templates and Patterns

### Project State Template

```markdown
# Project State: [Project Name]
Last Updated: [Date]

## Overview
[Brief description of the project]

## Current Stage
[Current implementation stage or feature]

## Progress Tracking
- [Category 1]:
  - ✅ [Completed task 1]
  - ✅ [Completed task 2]
  - 🔄 [In-progress task]
  - ⏳ [Planned task 1]
  - ⏳ [Planned task 2]

- [Category 2]:
  - ✅ [Completed task 1]
  - 🔄 [In-progress task]
  - ⏳ [Planned task]

## Current Focus
[Detailed description of the current task]

### Subtasks
- [  ] [Subtask 1]
- [  ] [Subtask 2]
- [  ] [Subtask 3]

## Key Decisions
- [Decision 1]: [Rationale]
- [Decision 2]: [Rationale]

## Dependencies
- [Dependency 1]: [Status]
- [Dependency 2]: [Status]

## Known Issues
- [Issue 1]: [Workaround or plan]
- [Issue 2]: [Workaround or plan]

## Next Steps
1. [Next step 1]
2. [Next step 2]
3. [Next step 3]
```

### Sequential Task Template

```markdown
# Sequential Task: [Task Name]

## Objective
[Clear statement of what needs to be accomplished]

## Prerequisites
- [Prerequisite 1]
- [Prerequisite 2]

## Sequential Steps

### 1. [Step 1 Name]
- Description: [Step description]
- Inputs: [What this step needs]
- Expected output: [What should be produced]
- Verification criteria:
  - [Criterion 1]
  - [Criterion 2]

### 2. [Step 2 Name]
- Description: [Step description]
- Inputs: [What this step needs]
- Expected output: [What should be produced]
- Verification criteria:
  - [Criterion 1]
  - [Criterion 2]

### 3. [Step 3 Name]
- Description: [Step description]
- Inputs: [What this step needs]
- Expected output: [What should be produced]
- Verification criteria:
  - [Criterion 1]
  - [Criterion 2]

## Integration Verification
- [Verification step 1]
- [Verification step 2]

## Completion Criteria
- [Criterion 1]
- [Criterion 2]
```

### Reasoning Chain Template

```markdown
# Reasoning Chain: [Decision Topic]

## Problem Statement
[Clear definition of the problem or decision needed]

## Context
- [Relevant context 1]
- [Relevant context 2]
- [Relevant context 3]

## Options
1. [Option 1]
   - Description: [Description]
   - Pros: [List of pros]
   - Cons: [List of cons]

2. [Option 2]
   - Description: [Description]
   - Pros: [List of pros]
   - Cons: [List of cons]

3. [Option 3]
   - Description: [Description]
   - Pros: [List of pros]
   - Cons: [List of cons]

## Evaluation Criteria
- [Criterion 1]: [Weight/Importance]
- [Criterion 2]: [Weight/Importance]
- [Criterion 3]: [Weight/Importance]

## Analysis
[Step-by-step analysis of options against criteria]

## Decision
[The chosen option]

## Rationale
[Detailed explanation of why this option was chosen]

## Implementation Plan
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Future Considerations
- [Consideration 1]
- [Consideration 2]
```

## Case Studies and Examples

### Multi-Step Refactoring Project

**Scenario**: Refactoring a legacy authentication system to a modern implementation using the MCP framework.

1. **Initial State Assessment**:
   ```
   We're refactoring the legacy authentication system. Let's analyze its current state:
   
   Current implementation:
   - Plain MD5 password hashing (security issue)
   - Single-file procedural code (maintainability issue)
   - No separation of concerns (architectural issue)
   - Sessions in PHP's default session store (scalability issue)
   
   Our refactoring will follow this sequence:
   1. Create proper data models and repositories
   2. Implement secure password hashing with migration strategy
   3. Add proper session management
   4. Implement JWT for API authentication
   5. Refactor UI components to use new system
   
   Let's start with step 1: Creating proper data models.
   ```

2. **Sequential Execution**:
   For each step, follow the Step-by-Step Execution Model with clear transitions.

3. **Maintaining MCP Framework**:
   - Update state tracking after each major step
   - Maintain session journals
   - Use reasoning chains for architectural decisions
   - Implement verification at each stage

4. **Example Transition**:
   ```
   We've now completed the user model and repository refactoring. Let's verify:
   
   - User data structure properly encapsulated ✅
   - Repository pattern implemented for data access ✅
   - Unit tests added for core functionality ✅
   - Legacy code can still function during transition ✅
   
   Step 1 is complete. Let's update our project state and move to step 2: Implementing secure password hashing with a migration strategy.
   
   For this step, we need to:
   a. Choose a secure hashing algorithm (bcrypt)
   b. Create a strategy for migrating existing passwords
   c. Implement transparent password upgrade during login
   
   Let's start with 2a: Choosing and implementing a secure hashing algorithm.
   ```

### Sequential Feature Implementation

**Scenario**: Implementing a new feature using the MCP framework for sequential thinking.

1. **Feature Decomposition**:
   ```
   We're implementing a new "Team Permissions" feature. Let's break it down sequentially:
   
   1. Data model phase:
      a. Create team entity
      b. Create team membership model
      c. Create permission definition model
      d. Create role model with permissions
   
   2. Core logic phase:
      a. Implement team CRUD operations
      b. Implement team membership management
      c. Implement permission checking logic
      d. Implement role assignment
   
   3. API phase:
      a. Create team management endpoints
      b. Create membership endpoints
      c. Create role and permission endpoints
   
   4. UI phase:
      a. Implement team management interfaces
      b. Implement member management
      c. Implement permission configuration UI
   
   Let's start with phase 1a: Creating the team entity.
   ```

2. **Phase Progression**:
   Use explicit phase transitions with verification:
   
   ```
   We've now completed the data model phase (1a-1d). Let's verify:
   
   - Team entity with proper attributes ✅
   - Team membership model with user relationships ✅
   - Permission definitions with scopes ✅
   - Role model with permission assignments ✅
   
   All data models are properly implemented with migrations, validations, and tests.
   
   Now let's move to phase 2: Core logic implementation, starting with 2a: Team CRUD operations.
   ```

3. **Cross-Reference Previous Work**:
   ```
   As we implement the permission checking logic (2c), we need to reference the permission model we created in step 1c.
   
   The permission model has these attributes:
   - name: String (e.g., "create_project")
   - description: String
   - scope: String (e.g., "team", "global")
   
   Now, let's implement the permission check method that will determine if a user has a specific permission within a team context.
   ```

### Debugging Complex Issues

**Scenario**: Using MCP framework for debugging a complex issue.

1. **Problem Decomposition**:
   ```
   We're debugging an issue where users occasionally lose access to their teams after password reset. Let's apply sequential thinking:
   
   1. Understanding phase:
      a. Define the exact symptoms
      b. Identify the conditions under which it occurs
      c. Determine affected components
   
   2. Investigation phase:
      a. Analyze the password reset flow
      b. Analyze the team access mechanism
      c. Examine the session handling
   
   3. Root cause identification phase
   
   4. Solution implementation phase
   
   Let's start with 1a: Defining the exact symptoms.
   ```

2. **Sequential Investigation**:
   ```
   Having completed the understanding phase, we now know:
   - Only affects users who belong to multiple teams
   - Only happens after password reset, not regular login
   - User sessions are properly invalidated, but team access is inconsistent
   
   Now moving to investigation phase 2a: Analyzing the password reset flow.
   
   Let's trace through the exact code execution during password reset:
   1. User requests password reset
   2. Reset token is generated and stored
   3. User clicks email link and sets new password
   4. Password is updated
   5. All user sessions are invalidated
   6. User is logged in with new session
   7. Team access is loaded
   
   Let's examine each step...
   ```

3. **Root Cause Analysis**:
   Use structured reasoning chains to identify the root cause:
   
   ```
   After investigation, we've identified three potential root causes:
   
   1. Session invalidation issue:
      - The new session may not have all required data
      - Evidence: Session data differs between regular login and post-reset login
   
   2. Team cache problem:
      - Team memberships may be cached and not refreshed
      - Evidence: Database shows correct memberships but application doesn't
   
   3. Race condition:
      - Team data might be loaded before user data is fully initialized
      - Evidence: Timing differences in log timestamps
   
   Let's analyze each hypothesis...
   
   [Analysis details]
   
   Based on our analysis, the root cause is #3: A race condition where team data is loaded before user data is fully initialized after password reset.
   ```

4. **Solution Implementation**:
   ```
   Now that we've identified the race condition, let's implement the solution sequentially:
   
   1. First, let's add proper synchronization between user initialization and team data loading
   2. Then, let's add explicit refresh of team memberships after login
   3. Finally, let's add logging to verify the fix
   
   Starting with step 1...
   ```

## Troubleshooting MCP Issues

### Handling Context Loss

When Claude Code loses important context:

1. **Recovery Strategy**:
   ```
   I notice that we may have lost some context about our current task. Let's restore:
   
   We're implementing the team permissions feature and were working on the role assignment API endpoint. 
   
   Key context:
   - We've already implemented the data models and core logic
   - The role model has: id, name, team_id, and permissions (JSON)
   - We're using middleware for authentication and permission checking
   - We need to implement the role-user assignment endpoint
   
   Let's continue with implementing this endpoint.
   ```

2. **Context Prioritization**:
   ```
   Since we have limited context space, let's focus only on the most relevant information for the current task:
   
   For the role assignment endpoint, we need:
   1. The role assignment controller method
   2. Request validation
   3. Permission checking
   4. Database transaction handling
   
   Let's implement these components sequentially.
   ```

3. **Context Refresh**:
   Periodically refresh key context:
   
   ```
   Before moving to the next API endpoint, let's refresh our understanding of the authentication flow:
   
   1. Request contains JWT in Authorization header
   2. Auth middleware validates the token
   3. User is loaded and attached to request
   4. Permission middleware checks specific permissions
   
   This context will be important as we implement the next endpoint.
   ```

### Recovering from Reasoning Errors

When Claude Code makes errors in sequential reasoning:

1. **Error Identification**:
   ```
   I notice a problem in our reasoning about the role permission checking. The current implementation:
   
   ```php
   public function hasPermission(User $user, string $permission): bool
   {
       return $user->roles->contains(function($role) use ($permission) {
           return in_array($permission, $role->permissions);
       });
   }
   ```
   
   The error is that permissions are stored as a JSON string in the database, but we're treating them as an array. Let's correct this reasoning.
   ```

2. **Backtracking**:
   ```
   Let's backtrack to where we designed the permission storage:
   
   We decided to store permissions as a JSON array in the database:
   
   ```php
   $table->json('permissions')->default('[]');
   ```
   
   This means we need to decode the JSON before checking permissions. Let's correct our implementation.
   ```

3. **Forward Correction**:
   ```
   With the corrected understanding, let's fix the implementation:
   
   ```php
   public function hasPermission(User $user, string $permission): bool
   {
       return $user->roles->contains(function($role) use ($permission) {
           $permissions = json_decode($role->permissions, true);
           return in_array($permission, $permissions);
       });
   }
   ```
   
   Now let's verify this corrected implementation...
   ```

### Optimizing Context Usage

Strategies for managing limited context windows:

1. **Targeted Context Loading**:
   ```
   For this session, we'll focus specifically on the team invitation system. The relevant components are:
   
   1. InvitationController.php: Handles invitation creation and acceptance
   2. InvitationService.php: Core business logic for invitations
   3. Invitation.php: The invitation model
   4. mail/team-invitation.blade.php: Email template
   
   Let's limit our discussion to these components to optimize context usage.
   ```

2. **Progressive Context Building**:
   ```
   Let's progressively build our understanding of the notification system:
   
   First, let's examine the notification model and database structure...
   [Implement and discuss]
   
   Now that we understand the data layer, let's look at the notification service...
   [Implement and discuss]
   
   With both the data layer and service understood, let's implement the controllers...
   ```

3. **Deliberate Context Dropping**:
   ```
   Now that we've completed the team management API, we can set aside that context and focus on the notification system.
   
   Let's explicitly transition our focus to the notification components:
   
   1. Notification models and database structure
   2. Notification service for creating and managing notifications
   3. Real-time notification delivery via WebSockets
   
   Let's start with the notification models.
   ```

By implementing the MCP framework with Claude Code, you can significantly enhance its ability to manage complex, multi-step development tasks. The structured approach to memory, context, and planning transforms Claude Code from a reactive assistant into a more effective development partner with improved sequential reasoning capabilities.
