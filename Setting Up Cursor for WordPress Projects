# Setting Up Cursor for WordPress Projects: A Comprehensive Guide

## Table of Contents

1. [Introduction](#introduction)
2. [Installing and Configuring Cursor](#installing-and-configuring-cursor)
   - [Basic Installation](#basic-installation)
   - [WordPress-Specific Configuration](#wordpress-specific-configuration)
3. [Setting Up Rules for AI](#setting-up-rules-for-ai)
   - [Creating a Rules File](#creating-a-rules-file)
   - [WordPress-Specific Rules Template](#wordpress-specific-rules-template)
   - [Explanation of Rules](#explanation-of-rules)
4. [Project Structure Organization](#project-structure-organization)
   - [WordPress Plugin Structure](#wordpress-plugin-structure)
   - [Including Key Files in Context](#including-key-files-in-context)
5. [Workflow Best Practices](#workflow-best-practices)
   - [Plugin Development Workflow](#plugin-development-workflow)
   - [Gutenberg Block Development](#gutenberg-block-development)
   - [REST API Endpoint Development](#rest-api-endpoint-development)
6. [Context Management for WordPress](#context-management-for-wordpress)
   - [Managing WordPress Core Context](#managing-wordpress-core-context)
   - [Theme vs Plugin Context](#theme-vs-plugin-context)
7. [Prompting Techniques for WordPress Development](#prompting-techniques-for-wordpress-development)
   - [Plugin Feature Development](#plugin-feature-development)
   - [Debugging WordPress Issues](#debugging-wordpress-issues)
   - [Code Optimization and Refactoring](#code-optimization-and-refactoring)
8. [Advanced Techniques](#advanced-techniques)
   - [Working with Multiple Plugins](#working-with-multiple-plugins)
   - [Theme Development in Cursor](#theme-development-in-cursor)
   - [WooCommerce Integration](#woocommerce-integration)
9. [Troubleshooting and Solutions](#troubleshooting-and-solutions)
   - [Common WordPress-Specific Issues](#common-wordpress-specific-issues)
   - [Context Window Limitations with Large Plugins](#context-window-limitations-with-large-plugins)
10. [Resources and Templates](#resources-and-templates)
    - [WordPress Project Context Template](#wordpress-project-context-template)
    - [Plugin Development Session Template](#plugin-development-session-template)

## Introduction

This guide will help you set up Cursor, an AI-powered code editor, specifically for WordPress development. We'll focus on plugin development with modern features like Gutenberg blocks and REST API endpoints, ensuring your AI assistant understands the WordPress context and coding standards. By following this guide, you'll establish an efficient workflow that combines the power of AI assistance with WordPress best practices.

## Installing and Configuring Cursor

### Basic Installation

1. **Download and Install Cursor**:
   - Visit [cursor.sh](https://cursor.sh) to download the appropriate version for your operating system
   - Follow the installation instructions for your platform
   - Launch Cursor to complete initial setup

2. **Initial Configuration**:
   - Connect Cursor to your preferred AI provider if required
   - Configure your preferred theme and editor settings
   - Set up Git integration for version control

### WordPress-Specific Configuration

1. **PHP Language Support**:
   - Ensure PHP language support is enabled in Cursor
   - Configure PHP formatting settings to align with WordPress coding standards
   - Consider installing the WordPress extension if available

2. **JavaScript/TypeScript Configuration**:
   - Configure TypeScript support for Gutenberg block development
   - Set up ESLint with WordPress configuration

3. **Environment Integration**:
   - Configure Cursor to work with your local WordPress development environment
   - Set up paths to your WordPress installation

## Setting Up Rules for AI

### Creating a Rules File

Cursor's AI can be guided by a rules file that provides context and coding preferences. Create a new file in your project directory named `.cursor/rules.md` to establish guidelines for the AI.

### WordPress-Specific Rules Template

Here's an extended version of the sample rules provided, optimized for WordPress plugin development:

```markdown
# Rules for AI in WordPress Development

- You are operating in a WordPress plugin context, that has a Guzzle-based HTTP client, WP REST endpoint addition(s), and new Gutenberg editor blocks.
- Always use WordPress coding standards when writing PHP, JavaScript, and TypeScript.
- Always type hint PHP code.
- Prefer writing TypeScript over JavaScript.
- Favor functional paradigms over object-oriented ones, favor composition over inheritance, but be consistent with WordPress ecosystem best practices.
- Optimize for readability.

## WordPress-Specific Guidelines

- Use WordPress hooks (actions and filters) appropriately rather than modifying core files.
- Follow the WordPress security best practices including proper data sanitization, validation, and escaping.
- Use WordPress' built-in functions when available instead of writing custom ones.
- Use WordPress' database abstraction layer ($wpdb) for database operations.
- Use WordPress' nonce system for form submissions.
- Follow WordPress plugin directory guidelines for all public plugins.
- Prefer wp_enqueue_script and wp_enqueue_style for asset management.

## Coding Standards

- PHP: Follow PSR-12 with WordPress adaptations.
- JavaScript/TypeScript: Follow WordPress JavaScript coding standards.
- CSS: Follow WordPress CSS coding standards.
- Keep functions focused and small when possible.
- Add appropriate documentation for hooks, functions, and classes.

## Development Focus

- Ensure code is compatible with PHP 7.4+ and follows modern PHP practices.
- Create responsive and accessible Gutenberg blocks.
- Implement proper error handling for API requests.
- Use WordPress transients or object cache for performance optimization when appropriate.
- Follow REST API best practices for endpoint creation.
```

### Explanation of Rules

Let's break down the key elements of these rules:

1. **Context Specification**: Establishes that we're working on a WordPress plugin with specific technologies (Guzzle, REST API, Gutenberg).

2. **Coding Standards**: Sets expectations for following WordPress coding standards while incorporating modern practices like type hinting.

3. **Technology Preferences**: Establishes TypeScript preference over JavaScript for new code.

4. **Architecture Approach**: Guides the AI toward functional paradigms and composition while remaining consistent with WordPress practices.

5. **WordPress-Specific Guidelines**: Provides detailed guidance on WordPress-specific practices like hooks, security, and the database layer.

6. **Development Focus**: Sets expectations for modern PHP practices, accessibility, error handling, and performance considerations.

## Project Structure Organization

### WordPress Plugin Structure

For optimal Cursor AI understanding, ensure your plugin follows a clear, organized structure:

```
my-plugin/
│
├── .cursor/
│   └── rules.md              # AI rules file
│
├── assets/
│   ├── js/                   # JavaScript files
│   ├── css/                  # CSS files
│   └── images/               # Image files
│
├── build/                    # Compiled Gutenberg blocks
│
├── src/
│   ├── Blocks/               # Gutenberg block source files
│   ├── REST/                 # REST API endpoint implementations
│   ├── Http/                 # Guzzle HTTP client implementations
│   └── Utils/                # Utility functions and classes
│
├── templates/                # Template files
│
├── vendor/                   # Composer dependencies
│
├── tests/                    # Test files
│
├── composer.json             # Composer configuration
├── package.json              # npm configuration
├── my-plugin.php             # Main plugin file
├── uninstall.php             # Uninstall handler
└── README.md                 # Project documentation
```

### Including Key Files in Context

To help Cursor understand your project better:

1. **Create a project summary file** at the root of your project that explains the plugin's purpose and architecture.

2. **Maintain a plugin documentation file** that outlines:
   - Plugin hooks provided
   - Available filters
   - REST API endpoints
   - Shortcodes
   - Gutenberg blocks

3. **Include a WordPress core reference** file that lists common WordPress functions and hooks your plugin uses.

## Workflow Best Practices

### Plugin Development Workflow

1. **Project Initialization**:
   ```
   I'm developing a WordPress plugin called [PLUGIN_NAME] that [PLUGIN_PURPOSE].
   
   The main components are:
   - [COMPONENT_1]: [PURPOSE]
   - [COMPONENT_2]: [PURPOSE]
   - [COMPONENT_3]: [PURPOSE]
   
   Let's start by setting up the plugin's main file.
   ```

2. **Feature Implementation**:
   ```
   Now I need to implement [FEATURE_NAME] for our WordPress plugin.
   
   Requirements:
   - [REQUIREMENT_1]
   - [REQUIREMENT_2]
   - [REQUIREMENT_3]
   
   It should integrate with WordPress by using [HOOKS/APIS].
   
   Let's plan and implement this feature.
   ```

3. **Testing and Debugging**:
   ```
   I need to test the [FEATURE] functionality in our WordPress plugin.
   
   Can you help me create:
   1. A list of test cases to verify functionality
   2. Debug code to help troubleshoot issues
   3. A WordPress-specific logging approach for this feature
   ```

### Gutenberg Block Development

For Gutenberg block development with Cursor:

1. **Block Planning**:
   ```
   I need to create a new Gutenberg block called [BLOCK_NAME] that allows users to [BLOCK_FUNCTIONALITY].
   
   The block should:
   - Have these attributes: [ATTRIBUTES]
   - Support these alignment options: [ALIGNMENTS]
   - Have these custom controls: [CONTROLS]
   
   Let's start by defining the block registration.
   ```

2. **Block Implementation**:
   ```
   Now that we've defined the block registration, let's implement:
   
   1. The edit component in TypeScript/JSX
   2. The save component
   3. The necessary styles
   
   The block should follow WordPress accessibility standards and be responsive.
   ```

3. **Block Testing**:
   ```
   Now let's create test cases and verification steps for our Gutenberg block:
   
   1. Manual testing procedures
   2. Integration with the WordPress editor
   3. Compatibility with other blocks
   ```

### REST API Endpoint Development

For developing WordPress REST API endpoints:

1. **Endpoint Planning**:
   ```
   I need to create a custom WordPress REST API endpoint for [PURPOSE].
   
   The endpoint should:
   - Be registered at [ROUTE]
   - Support these methods: [METHODS]
   - Require these permissions: [PERMISSIONS]
   - Accept these parameters: [PARAMETERS]
   
   Let's plan the implementation.
   ```

2. **Endpoint Implementation**:
   ```
   Let's implement the REST API endpoint we planned.
   
   We need to:
   1. Register the route
   2. Create callback functions for each method
   3. Implement proper request validation
   4. Add response handling with appropriate status codes
   5. Implement WordPress nonce validation
   
   Let's start with the route registration.
   ```

3. **Endpoint Testing**:
   ```
   Now let's create a testing plan for our REST API endpoint:
   
   1. Manual testing with appropriate tools (like Postman)
   2. Authentication testing
   3. Error handling testing
   4. Performance testing considerations
   ```

## Context Management for WordPress

### Managing WordPress Core Context

Since WordPress has a massive codebase, you need strategies to provide relevant context without overflow:

1. **Core Function References**:
   Create a reference file for commonly used WordPress functions that includes:
   
   ```markdown
   # WordPress Core Functions Reference
   
   ## Content Functions
   - `get_post()`: Retrieves post data given a post ID or post object
   - `get_posts()`: Retrieves a list of recent posts
   
   ## User Functions
   - `current_user_can()`: Checks if the current user has a certain capability
   - `wp_get_current_user()`: Gets the current user object
   
   ## Database Functions
   - `$wpdb->get_results()`: Retrieves multiple database rows
   - `$wpdb->prepare()`: Prepares a SQL query for safe execution
   
   ## Hook System
   - `add_action()`: Hooks a function to a specific action
   - `add_filter()`: Hooks a function to a specific filter
   ```

2. **Just-in-time Context**:
   When working on specific WordPress features, provide targeted context:
   
   ```
   For this REST API endpoint, we need to understand these WordPress concepts:
   
   1. `register_rest_route()` function for registering endpoints
   2. WordPress permission callback system
   3. WordPress request parameter sanitization
   
   Let's focus specifically on these aspects for now.
   ```

### Theme vs Plugin Context

Be explicit about whether you're working on a theme or plugin:

```
Note that we're developing a plugin, not a theme. This means:

1. We should use plugin activation/deactivation hooks
2. We should not include theme-specific functions
3. Our code needs to work independently of the active theme
4. We should use plugin-specific loading patterns

Let's keep this context in mind as we develop.
```

## Prompting Techniques for WordPress Development

### Plugin Feature Development

Use structured prompts for plugin features:

```
I need to implement a [FEATURE_TYPE] for my WordPress plugin.

Specifically, I want to:
- [FEATURE_FUNCTIONALITY]
- It should integrate with [WP_COMPONENT]
- It needs to store data in [DATA_STORAGE_APPROACH]

WordPress-specific requirements:
- Must use appropriate hooks: [HOOK_EXAMPLES]
- Should follow WordPress security practices for [SECURITY_CONCERN]
- Needs to be compatible with [WP_VERSION] and above

Let's implement this feature following WordPress best practices.
```

### Debugging WordPress Issues

For debugging WordPress-specific problems:

```
I'm debugging an issue in my WordPress plugin where [PROBLEM_DESCRIPTION].

Environment details:
- WordPress version: [WP_VERSION]
- PHP version: [PHP_VERSION]
- Relevant plugins: [PLUGINS]

Error information:
- Error message: [ERROR_MESSAGE]
- Error location: [ERROR_LOCATION]

What I've tried:
- [TROUBLESHOOTING_STEP_1]
- [TROUBLESHOOTING_STEP_2]

How can I diagnose and fix this WordPress-specific issue?
```

### Code Optimization and Refactoring

For optimizing WordPress code:

```
I need to optimize this WordPress [CODE_TYPE]:

```php
[CODE_SNIPPET]
```

Specifically, I'm concerned about:
- [PERFORMANCE_ISSUE]
- [MAINTAINABILITY_ISSUE]
- [WORDPRESS_SPECIFIC_CONCERN]

Can you help me refactor this following WordPress best practices while maintaining functionality?
```

## Advanced Techniques

### Working with Multiple Plugins

When developing multiple plugins or managing plugin interactions:

```
I'm working on two WordPress plugins that need to interact:

Plugin 1: [PLUGIN_1_NAME]
- Purpose: [PURPOSE]
- Key functions: [FUNCTIONS]

Plugin 2: [PLUGIN_2_NAME]
- Purpose: [PURPOSE]
- Key functions: [FUNCTIONS]

I need to implement a way for Plugin 1 to [INTERACTION_DESCRIPTION] with Plugin 2 using WordPress best practices.

What's the best approach for this plugin interaction?
```

### Theme Development in Cursor

For theme development context:

```
Note that for this session, I'm working on a WordPress theme, not a plugin.

Theme-specific context:
- Using template hierarchy
- Implementing theme support features
- Working with template parts
- Supporting Gutenberg editor styles

Let's develop this theme component with these considerations in mind.
```

### WooCommerce Integration

For WooCommerce-specific development:

```
I'm developing a WordPress plugin that integrates with WooCommerce.

WooCommerce-specific requirements:
- Needs to hook into [WOOCOMMERCE_HOOK]
- Extends [WOOCOMMERCE_COMPONENT]
- Modifies [WOOCOMMERCE_FUNCTIONALITY]

Let's develop this integration following WooCommerce best practices.
```

## Troubleshooting and Solutions

### Common WordPress-Specific Issues

1. **Hook Priority Issues**:
   ```
   I'm having an issue where my plugin's hook isn't executing at the right time.
   
   Current code:
   ```php
   add_action('init', 'my_function');
   ```
   
   What I need:
   - Function needs to run after [OTHER_PLUGIN] but before theme setup
   - Need to understand hook priority system better
   
   How can I fix this WordPress hook timing issue?
   ```

2. **Database Query Performance**:
   ```
   I'm having performance issues with this WordPress database query:
   
   ```php
   $results = $wpdb->get_results("SELECT * FROM {$wpdb->posts} WHERE post_type = 'product'");
   ```
   
   The site has over 10,000 products and this query is slow.
   
   How can I optimize this query following WordPress best practices?
   ```

### Context Window Limitations with Large Plugins

For managing context in large WordPress plugins:

```
I'm working on a large WordPress plugin with over 50 files. For this session, let's focus specifically on:

1. The payment gateway integration in:
   - src/Payments/Gateway.php
   - src/Payments/Processor.php

2. The specific issue with [FEATURE]

Let's ignore other plugin components for now to stay within context limits.
```

## Resources and Templates

### WordPress Project Context Template

Use this template to provide project context for Cursor:

```markdown
# WordPress Project Context: [PLUGIN_NAME]

## Plugin Purpose
[BRIEF_DESCRIPTION]

## WordPress Integration Points
- Hooks used: [HOOKS]
- Filters provided: [FILTERS]
- Shortcodes: [SHORTCODES]
- Gutenberg blocks: [BLOCKS]
- REST endpoints: [ENDPOINTS]

## Data Storage
- Custom tables: [TABLES]
- Post types: [POST_TYPES]
- Options: [OPTIONS]
- Transients: [TRANSIENTS]

## External Services
- [SERVICE_1]: [PURPOSE]
- [SERVICE_2]: [PURPOSE]

## Plugin Architecture
[BRIEF_ARCHITECTURE_DESCRIPTION]

## Current Development Focus
[CURRENT_FOCUS]
```

### Plugin Development Session Template

Use this template to start development sessions:

```markdown
# Development Session: [DATE]

## Current Focus
[FEATURE_OR_COMPONENT]

## WordPress Context
- This is a [PLUGIN/THEME] development task
- WordPress version target: [WP_VERSION]+
- Related core components: [WP_COMPONENTS]

## Relevant Files
- [FILE_1]: [PURPOSE]
- [FILE_2]: [PURPOSE]

## Session Goals
1. [GOAL_1]
2. [GOAL_2]

## WordPress-Specific Considerations
- [CONSIDERATION_1]
- [CONSIDERATION_2]

## Starting Point
[SPECIFIC_STARTING_TASK]
```

By following this guide and using these templates, you'll create an effective development environment in Cursor that understands the WordPress context and can assist you in building high-quality plugins following WordPress best practices.
