# Comprehensive Guide for Effective Collaboration with Cursor

## Table of Contents

1. [Introduction](#introduction)
2. [Context Rules for AI in Cursor](#context-rules-for-ai-in-cursor)
   - [Understanding Context in Cursor](#understanding-context-in-cursor)
   - [What Gets Sent to the AI](#what-gets-sent-to-the-ai)
   - [Context Window Limitations](#context-window-limitations)
3. [Effective Prompting Strategies](#effective-prompting-strategies)
   - [The /code Command](#the-code-command)
   - [The /edit Command](#the-edit-command)
   - [Chat Interface Best Practices](#chat-interface-best-practices)
   - [Task-Specific Prompting Templates](#task-specific-prompting-templates)
4. [Project Context Management](#project-context-management)
   - [Setting Up Project Context](#setting-up-project-context)
   - [Context Manifests](#context-manifests)
   - [Handling Context Overflow](#handling-context-overflow)
5. [Advanced Cursor Techniques](#advanced-cursor-techniques)
   - [File Linking and Referencing](#file-linking-and-referencing)
   - [Working with Multiple Files](#working-with-multiple-files)
   - [Using Chat History Effectively](#using-chat-history-effectively)
   - [Context Prioritization](#context-prioritization)
6. [Session Management](#session-management)
   - [Starting Development Sessions](#starting-development-sessions)
   - [Context Restoration Techniques](#context-restoration-techniques)
   - [Ending Sessions Effectively](#ending-sessions-effectively)
7. [Troubleshooting and Solutions](#troubleshooting-and-solutions)
   - [Common Context Issues](#common-context-issues)
   - [Improving AI Understanding](#improving-ai-understanding)
   - [Redirecting Off-Track Implementations](#redirecting-off-track-implementations)
8. [Templates and Frameworks](#templates-and-frameworks)
   - [Project Context Template](#project-context-template)
   - [Session Management Templates](#session-management-templates)
   - [Code Documentation Templates](#code-documentation-templates)
9. [Example Workflows](#example-workflows)
   - [New Project Development](#new-project-development)
   - [Bug Fixing and Debugging](#bug-fixing-and-debugging)
   - [Feature Implementation](#feature-implementation)

## Introduction

Cursor is an AI-powered code editor that provides intelligent assistance through context-aware code generation, editing suggestions, and in-editor chat capabilities. This guide focuses on maximizing your collaboration with Cursor's AI by understanding its context rules, applying effective prompting strategies, and managing project context effectively.

The primary goal of this guide is to help you work within Cursor's context system, ensuring the AI has the information it needs to provide helpful, accurate assistance while avoiding context overflow and maintaining an efficient workflow.

## Context Rules for AI in Cursor

### Understanding Context in Cursor

Cursor's AI doesn't just respond to your immediate query—it uses multiple sources of context to understand your project and your intent:

1. **Active File Context**: The file you're currently working on provides immediate context
2. **Project Context**: Files within your project that relate to your current task
3. **Editor Context**: Your selected code, cursor position, and visible editor panes
4. **Chat History**: Previous exchanges within the current session
5. **Language and Framework Knowledge**: The AI's built-in understanding of programming

Understanding how Cursor prioritizes and manages these context sources is crucial for effective collaboration.

### What Gets Sent to the AI

By default, Cursor sends the following to the AI:

1. **Current File**: The entire content of the file you're working in
2. **Selected Code**: Any code you've highlighted
3. **Related Files**: Other project files that Cursor determines are relevant
4. **Chat History**: Previous messages in the current chat session
5. **Command Context**: Special commands like `/code` and `/edit` provide additional context

Important considerations:

- Not every file in your project is sent to the AI due to context limits
- The AI prioritizes files directly related to your current work
- You can explicitly reference or link files to include them in context

### Context Window Limitations

Cursor's AI operates within a finite context window, which limits how much information it can process at once:

- Context is measured in tokens (roughly 4 characters per token)
- The context limit varies based on the AI model being used
- When context exceeds limits, Cursor must make decisions about what to keep and what to drop

To avoid context overflow:

1. **Be specific in your queries**
2. **Focus on one task at a time**
3. **Reference only the most relevant files**
4. **Break large tasks into smaller subtasks**
5. **Use context management techniques described later in this guide**

## Effective Prompting Strategies

### The /code Command

The `/code` command is one of the most powerful features in Cursor. It generates code based on your prompt and current context.

Best practices for `/code`:

1. **Be specific and concise**:
   ```
   /code Create a React component that displays a paginated list of users with search functionality. It should use the fetchUsers API from api.js and handle loading and error states.
   ```

2. **Specify language or framework explicitly**:
   ```
   /code Generate a Python function that processes CSV data using pandas, filtering out rows that don't meet the specified criteria
   ```

3. **Provide scope and interfaces**:
   ```
   /code The function should take a filename and filter_criteria dictionary as parameters and return a filtered DataFrame. It should handle file not found errors gracefully.
   ```

4. **Include examples when useful**:
   ```
   /code Example input: filter_criteria = {'age': 30, 'status': 'active'}
   This should filter the CSV to only include rows where age > 30 AND status == 'active'
   ```

### The /edit Command

The `/edit` command allows you to modify existing code. It's powerful for refactoring, bug fixing, and adding features.

Best practices for `/edit`:

1. **Define clear boundaries**:
   ```
   /edit Refactor the processUserData function below to use async/await instead of promises
   ```

2. **Specify the goal, not just the method**:
   ```
   /edit Update this function to include rate limiting to prevent API abuse. Max 5 requests per minute per user.
   ```

3. **Indicate preservation requirements**:
   ```
   /edit Add input validation to this function without changing the core business logic
   ```

4. **Reference existing code patterns**:
   ```
   /edit Update this component following the same error handling pattern used in LoginForm.jsx
   ```

### Chat Interface Best Practices

When using Cursor's chat interface:

1. **Start with context summary**:
   ```
   I'm working on the user authentication module that uses JWT tokens. I need to add password reset functionality.
   ```

2. **Use clear, consistent terminology**:
   ```
   Can you explain how the 'validateUser' function in auth.js interacts with the 'UserSession' class?
   ```

3. **One request per message**:
   Break complex requests into individual messages rather than asking multiple questions at once.

4. **Reference files explicitly**:
   ```
   In src/utils/validation.js, what's the purpose of the sanitizeInput function and where is it being used?
   ```

5. **Provide feedback on responses**:
   Let the AI know when its suggestions are helpful or off-track to improve future interactions.

### Task-Specific Prompting Templates

Adapt these templates for common development tasks:

1. **Feature Implementation**:
   ```
   I need to implement [FEATURE_NAME].
   
   Requirements:
   - [REQUIREMENT_1]
   - [REQUIREMENT_2]
   - [REQUIREMENT_3]
   
   It should interact with these existing components:
   - [COMPONENT_1] in [FILE_PATH_1]
   - [COMPONENT_2] in [FILE_PATH_2]
   
   Please help me plan and implement this feature.
   ```

2. **Bug Fixing**:
   ```
   I'm debugging an issue where [PROBLEM_DESCRIPTION].
   
   Expected behavior: [WHAT_SHOULD_HAPPEN]
   Actual behavior: [WHAT_ACTUALLY_HAPPENS]
   
   Relevant code:
   - The issue appears to be in [FILE_PATH], around line [LINE_NUMBER]
   - It's related to [FUNCTION/COMPONENT_NAME]
   
   What could be causing this issue and how can I fix it?
   ```

3. **Code Review**:
   ```
   Can you review this implementation of [FEATURE/FUNCTION]?
   
   Focus on:
   - Performance optimization
   - Security concerns
   - Edge cases
   - Code readability
   
   [CODE_OR_FILE_REFERENCE]
   ```

## Project Context Management

### Setting Up Project Context

Create a project context document to help Cursor understand your project structure and architecture:

```markdown
# Project Context: [PROJECT_NAME]

## Architecture Overview
- Frontend: [TECHNOLOGIES]
- Backend: [TECHNOLOGIES]
- Database: [TECHNOLOGIES]
- Authentication: [METHOD]

## Key Components
- [COMPONENT_1]: [PURPOSE] - [FILE_PATH]
- [COMPONENT_2]: [PURPOSE] - [FILE_PATH]
- [COMPONENT_3]: [PURPOSE] - [FILE_PATH]

## Data Flow
[BRIEF_DESCRIPTION_OF_DATA_FLOW]

## External APIs/Services
- [API_1]: [PURPOSE]
- [API_2]: [PURPOSE]

## Project Conventions
- [CONVENTION_1]
- [CONVENTION_2]
```

Keep this document in your project root and reference it when starting new sessions with Cursor.

### Context Manifests

For larger projects, create focused context manifests for specific modules or features:

```markdown
# Context Manifest: [MODULE_NAME]

## Purpose
[MODULE_PURPOSE]

## Key Files
- [FILE_1]: [PURPOSE]
- [FILE_2]: [PURPOSE]
- [FILE_3]: [PURPOSE]

## Dependencies
- Internal: [INTERNAL_DEPENDENCIES]
- External: [EXTERNAL_DEPENDENCIES]

## API/Interface
[DESCRIPTION_OF_MODULE_INTERFACE]

## Current State
- [IMPLEMENTED_FEATURES]
- [PENDING_FEATURES]
- [KNOWN_ISSUES]
```

Use these manifests to provide targeted context when working on specific parts of your project.

### Handling Context Overflow

When working with large codebases that exceed context limits:

1. **Create a context hierarchy**:
   - Project-level context (high-level structure and relationships)
   - Module-level context (specific components or features)
   - File-level context (implementation details)

2. **Use targeted context loading**:
   ```
   For this session, we'll focus on the user authentication module. The relevant files are:
   - src/auth/AuthProvider.js
   - src/auth/useAuth.js
   - src/auth/authUtils.js
   - src/api/authApi.js
   
   Let's start by examining AuthProvider.js to understand the authentication flow.
   ```

3. **Create context snapshots**:
   Document the current state of development at key milestones to help restore context later.

## Advanced Cursor Techniques

### File Linking and Referencing

To bring specific files into Cursor's context:

1. **Explicit file references**:
   ```
   I need help understanding how the data flows from api.js to UserProfile.jsx
   ```

2. **File content sharing**:
   When a file isn't automatically included in context, share relevant portions:
   ```
   Here's the utility function from utils/formatting.js that's causing issues:
   
   ```js
   export function formatCurrency(amount, currency = 'USD') {
     // Function implementation
   }
   ```
   ```

3. **Dependency mapping**:
   ```
   The component I'm working on depends on:
   1. The AuthContext from src/context/AuthContext.js
   2. The API client from src/api/client.js
   3. The useForm hook from our custom hooks library
   ```

### Working with Multiple Files

Strategies for multi-file tasks:

1. **Sequential context building**:
   ```
   Let's start by understanding the database schema in models/user.js, then we'll look at the controller in controllers/userController.js, and finally the routes in routes/userRoutes.js
   ```

2. **Relationship focus**:
   ```
   I need to understand how these three files interact:
   - Component.jsx renders the UI
   - useDataHook.js fetches and processes data
   - apiService.js makes the actual API calls
   
   Let's trace a user action from the UI to the API and back.
   ```

3. **Implementation planning**:
   ```
   This feature will require changes to:
   1. The database model (models/product.js)
   2. The API endpoint (controllers/productController.js)
   3. The frontend component (components/ProductForm.jsx)
   
   Let's plan the changes needed for each file.
   ```

### Using Chat History Effectively

Cursor maintains chat history within the session context. Use it effectively:

1. **Reference previous discussions**:
   ```
   As we discussed earlier about the authentication flow, I now need to implement the password reset functionality.
   ```

2. **Incremental development**:
   Build on previous work without repeating context:
   ```
   Now that we've implemented the basic validation, let's add the more advanced rules we discussed.
   ```

3. **Context reinforcement**:
   Periodically summarize progress to reinforce important context:
   ```
   So far we've:
   1. Implemented the data model
   2. Created the API endpoints
   3. Started the UI components
   
   Let's now focus on connecting the UI to the API.
   ```

### Context Prioritization

Help Cursor prioritize the most relevant context:

1. **Explicit prioritization**:
   ```
   The most important file for this task is src/components/DataTable.jsx. It uses helpers from src/utils/tableUtils.js and gets data via src/hooks/useDataFetch.js.
   ```

2. **Function-level focus**:
   ```
   Let's focus specifically on the `processTransactionData` function in dataUtils.js. It's called by the Dashboard and Reports components.
   ```

3. **Interface emphasis**:
   ```
   The key interface we're working with is the `UserService` class in services/userService.js. Let's understand its public methods before we modify it.
   ```

## Session Management

### Starting Development Sessions

Begin each session with proper context initialization:

```
I'm continuing work on [PROJECT_NAME]. 

Current focus: [CURRENT_TASK]

Key files for this session:
- [FILE_1]: [PURPOSE]
- [FILE_2]: [PURPOSE]
- [FILE_3]: [PURPOSE]

Progress so far:
- [COMPLETED_ITEM_1]
- [COMPLETED_ITEM_2]

Today, I want to accomplish:
- [GOAL_1]
- [GOAL_2]

Let's start by [SPECIFIC_STARTING_POINT].
```

### Context Restoration Techniques

When resuming work after breaks or in new sessions:

1. **Project state summary**:
   ```
   We've been developing a user management system. So far, we've implemented:
   - User registration and login
   - Profile management
   - Basic role permissions
   
   We're currently working on the advanced permissions system.
   ```

2. **Recent development recap**:
   ```
   In our last session, we:
   - Created the PermissionGroup model
   - Started implementing the permission assignment UI
   - Identified an issue with permission inheritance
   
   Let's pick up by resolving that inheritance issue.
   ```

3. **Code evolution explanation**:
   ```
   The authentication system has evolved through several iterations:
   1. Basic email/password (completed)
   2. Addition of social login (completed)
   3. Multi-factor authentication (in progress)
   
   We're working on step 3, specifically the verification code handling.
   ```

### Ending Sessions Effectively

Conclude sessions with a structured wrap-up:

```
Let's summarize what we've accomplished today:

1. Implemented:
   - [IMPLEMENTATION_1]
   - [IMPLEMENTATION_2]

2. Issues resolved:
   - [ISSUE_1]
   - [ISSUE_2]

3. Pending items for next session:
   - [PENDING_ITEM_1]
   - [PENDING_ITEM_2]

4. Notes for context:
   - [IMPORTANT_CONTEXT_1]
   - [IMPORTANT_CONTEXT_2]

Is there anything else you'd recommend I focus on in our next session?
```

## Troubleshooting and Solutions

### Common Context Issues

1. **AI Missing Important Context**
   
   Problem: Cursor's AI gives suggestions that don't align with your project's architecture or conventions.
   
   Solution:
   ```
   I notice you might be missing some important context about our project. Key things to know:
   
   1. We're using Repository pattern for data access
   2. Authentication is handled via JSON Web Tokens
   3. We follow the container/component pattern for React components
   
   With this in mind, could you revise your suggestion for the user profile feature?
   ```

2. **Context Overflow**
   
   Problem: You're working on a large project and Cursor is struggling with the context amount.
   
   Solution:
   ```
   Let's narrow our focus for this task. We'll only consider:
   
   1. The payment processing module (src/payments/*)
   2. The specific issue with transaction reconciliation
   
   We can ignore the user management and reporting features for now.
   ```

3. **Inconsistent Understanding**
   
   Problem: Cursor seems to understand some parts of your project but not others.
   
   Solution:
   ```
   Let me clarify our project structure:
   
   Frontend:
   - React components in src/components
   - Redux store in src/store
   - Utilities in src/utils
   
   Backend:
   - Express routes in routes/
   - Controllers in controllers/
   - Models in models/
   
   Does this help establish a clearer understanding?
   ```

### Improving AI Understanding

When Cursor's responses indicate misunderstanding:

1. **Provide concrete examples**:
   ```
   Let me show you how we typically implement API services:
   
   ```js
   // Example from src/services/productService.js
   export class ProductService {
     async getProducts(filters) {
       // Implementation
     }
     
     async createProduct(productData) {
       // Implementation
     }
   }
   ```
   
   Please follow this pattern for the new UserService.
   ```

2. **Contrast with alternatives**:
   ```
   We're using React Query for data fetching, NOT Redux. This means:
   - Data fetching is done with useQuery hooks
   - Mutations use useMutation hooks
   - We don't have actions/reducers for API calls
   
   Please adjust your approach accordingly.
   ```

3. **Feedback on incorrect assumptions**:
   ```
   There are a few misunderstandings in your response:
   
   1. We're using MongoDB, not PostgreSQL
   2. Our authentication is JWT-based, not session-based
   3. Frontend routing is done with React Router, not Next.js
   
   Could you revise your suggestion with these corrections?
   ```

### Redirecting Off-Track Implementations

When Cursor's implementation goes in the wrong direction:

```
Let's redirect our approach. The current implementation won't work because:

1. [ISSUE_1]
2. [ISSUE_2]

Instead, we should:

1. [ALTERNATIVE_APPROACH_1]
2. [ALTERNATIVE_APPROACH_2]

The key requirements to keep in mind are:
- [KEY_REQUIREMENT_1]
- [KEY_REQUIREMENT_2]

Let's try again with this direction.
```

## Templates and Frameworks

### Project Context Template

```markdown
# Project Context: [PROJECT_NAME]

## Overview
[PROJECT_DESCRIPTION]

## Architecture
- Frontend: [FRONTEND_TECH]
- Backend: [BACKEND_TECH]
- Database: [DATABASE_TECH]
- Deployment: [DEPLOYMENT_STRATEGY]

## Key Features
- [FEATURE_1]: [DESCRIPTION]
- [FEATURE_2]: [DESCRIPTION]
- [FEATURE_3]: [DESCRIPTION]

## Project Structure
- [DIRECTORY_1]/: [PURPOSE]
- [DIRECTORY_2]/: [PURPOSE]
- [DIRECTORY_3]/: [PURPOSE]

## Naming Conventions
- [CONVENTION_1]
- [CONVENTION_2]

## Testing Approach
- [TESTING_STRATEGY]

## Important Dependencies
- [DEPENDENCY_1]: [PURPOSE]
- [DEPENDENCY_2]: [PURPOSE]
```

### Session Management Templates

1. **Session Initialization**:
   ```markdown
   # Session: [DATE]
   
   ## Focus Area
   [FEATURE_OR_COMPONENT]
   
   ## Relevant Files
   - [FILE_1]: [PURPOSE]
   - [FILE_2]: [PURPOSE]
   
   ## Context
   [BACKGROUND_INFORMATION]
   
   ## Goals
   1. [GOAL_1]
   2. [GOAL_2]
   
   ## Starting Point
   [SPECIFIC_STARTING_TASK]
   ```

2. **Progress Tracker**:
   ```markdown
   # Progress Update
   
   ## Completed
   - [TASK_1] ✅
   - [TASK_2] ✅
   
   ## In Progress
   - [TASK_3] 🔄
   - [TASK_4] 🔄
   
   ## Not Started
   - [TASK_5] ⏳
   - [TASK_6] ⏳
   
   ## Issues/Blockers
   - [ISSUE_1] ❌
   - [ISSUE_2] ❌
   ```

3. **Session Summary**:
   ```markdown
   # Session Summary: [DATE]
   
   ## Accomplishments
   - [ACCOMPLISHMENT_1]
   - [ACCOMPLISHMENT_2]
   
   ## Code Changes
   - [FILE_1]: [CHANGES]
   - [FILE_2]: [CHANGES]
   
   ## Decisions Made
   - [DECISION_1]
   - [DECISION_2]
   
   ## Next Steps
   1. [NEXT_STEP_1]
   2. [NEXT_STEP_2]
   
   ## Notes for Next Session
   - [NOTE_1]
   - [NOTE_2]
   ```

### Code Documentation Templates

1. **Function Documentation**:
   ```javascript
   /**
    * @function [FUNCTION_NAME]
    * @description [DESCRIPTION]
    * 
    * @param {[TYPE]} [PARAM_NAME] - [DESCRIPTION]
    * @param {[TYPE]} [PARAM_NAME] - [DESCRIPTION]
    * 
    * @returns {[TYPE]} [DESCRIPTION]
    * 
    * @example
    * // Example usage
    * const result = functionName(param1, param2);
    */
   ```

2. **Component Documentation**:
   ```javascript
   /**
    * @component [COMPONENT_NAME]
    * @description [DESCRIPTION]
    * 
    * @prop {[TYPE]} [PROP_NAME] - [DESCRIPTION]
    * @prop {[TYPE]} [PROP_NAME] - [DESCRIPTION]
    * 
    * @example
    * // Example usage
    * <ComponentName prop1="value" prop2={value} />
    * 
    * @notes
    * - [NOTE_1]
    * - [NOTE_2]
    */
   ```

3. **Context Comments**:
   ```javascript
   // [CONTEXT:START]
   // This module handles user authentication
   // It connects to the Auth service and manages user sessions
   // Key responsibilities:
   // - Login/logout functionality
   // - Session persistence
   // - Authentication state management
   // [CONTEXT:END]
   ```

## Example Workflows

### New Project Development

1. **Project Setup Phase**
   - Create project structure
   - Document architecture decisions in the Project Context template
   - Establish coding conventions
   - Set up initial files

2. **Development Phase**
   - Break features into manageable tasks
   - For each task:
     - Provide specific context for the task
     - Use `/code` for initial implementation
     - Review and refine with `/edit`
     - Document code with appropriate templates
   - Update Progress Tracker as you complete tasks

3. **Iteration Phase**
   - Begin each session with Session Initialization
   - End each session with Session Summary
   - Maintain the Project Context document as the project evolves

### Bug Fixing and Debugging

1. **Issue Identification**
   ```
   I'm debugging an issue where [PROBLEM_DESCRIPTION].
   
   Steps to reproduce:
   1. [STEP_1]
   2. [STEP_2]
   3. [STEP_3]
   
   Expected: [EXPECTED_BEHAVIOR]
   Actual: [ACTUAL_BEHAVIOR]
   
   Error message: [ERROR_MESSAGE]
   ```

2. **Context Gathering**
   ```
   The issue appears to be in [COMPONENT_OR_FILE].
   
   Relevant code:
   ```[LANGUAGE]
   [CODE_SNIPPET]
   ```
   
   Related components:
   - [COMPONENT_1] calls this code when [EVENT]
   - [COMPONENT_2] depends on the output of this code
   ```

3. **Problem Analysis**
   ```
   Based on the error and code, I think the issue might be related to:
   
   1. [POSSIBLE_CAUSE_1]
   2. [POSSIBLE_CAUSE_2]
   
   Can you help diagnose which is more likely?
   ```

4. **Solution Implementation**
   ```
   Can you suggest a fix for this issue that:
   
   1. Resolves the immediate error
   2. Prevents similar issues in the future
   3. Maintains compatibility with the rest of the system
   ```

### Feature Implementation

1. **Feature Planning**
   ```
   I need to implement [FEATURE_NAME].
   
   Requirements:
   - [REQUIREMENT_1]
   - [REQUIREMENT_2]
   - [REQUIREMENT_3]
   
   It needs to integrate with:
   - [EXISTING_COMPONENT_1]
   - [EXISTING_COMPONENT_2]
   
   What's the best approach for implementing this?
   ```

2. **Architecture Definition**
   ```
   Based on our discussion, let's use this architecture for the feature:
   
   1. Data model: [DATA_MODEL_DESCRIPTION]
   2. API endpoints: [ENDPOINTS_DESCRIPTION]
   3. Service layer: [SERVICE_LAYER_DESCRIPTION]
   4. UI components: [UI_COMPONENTS_DESCRIPTION]
   
   Let's start by implementing the data model.
   ```

3. **Incremental Implementation**
   ```
   Now that we've implemented the data model, let's move on to the API endpoints.
   
   For context, remember that:
   - The data model has these fields: [FIELDS]
   - We need to support these operations: [OPERATIONS]
   - Authentication is required for all endpoints
   
   Let's implement the CRUD endpoints for this feature.
   ```

4. **Integration and Testing**
   ```
   With the backend components in place, let's implement the UI.
   
   The UI should:
   - Display [DATA] in a [COMPONENT_TYPE]
   - Allow users to [USER_ACTIONS]
   - Handle loading and error states
   - Follow our application's design patterns
   
   Let's start with the main component structure.
   ```

By following these guidelines and using the templates provided, you'll maximize the effectiveness of your collaboration with Cursor, ensuring that the AI has the context it needs to provide helpful, relevant assistance throughout your development process.
