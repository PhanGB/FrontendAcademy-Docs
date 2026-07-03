# Coding Standards

## Purpose

Coding standards are essential for Frontend Academy because they ensure that the codebase remains readable, maintainable, and predictable as the project grows. A shared standard allows developers and AI agents to contribute with confidence, reduces regressions, and minimizes unnecessary debate over formatting or structure.

Readability improves when code is organized consistently and uses clear naming. Maintainability increases when responsibilities are separated and architectural boundaries are respected. Consistency helps the team move faster because conventions become familiar rather than arbitrary.

Scalability depends on code that is easy to extend without introducing tangled dependencies. AI-assisted development also benefits from strong standards because automated contributors produce better results when the expected structure is explicit.

Team collaboration improves when everyone follows the same rules for layout, architecture, documentation, and review. This standard exists to protect the long-term health of the application.

---

# General Principles

The project follows a practical, disciplined engineering philosophy centered on clarity and maintainability.

## Clean Code

Code should be easy to read, easy to reason about, and easy to modify. It should express intent clearly and avoid unnecessary complexity.

## SOLID

The system should follow the core principles of object-oriented design where they are meaningful:

- Single Responsibility Principle: each class should have a narrow and clear purpose.
- Open/Closed Principle: extend behavior without modifying core logic unnecessarily.
- Liskov Substitution Principle: implementations should remain compatible with their abstractions.
- Interface Segregation Principle: avoid forcing consumers to depend on irrelevant methods.
- Dependency Inversion Principle: depend on abstractions where appropriate.

In Laravel, these principles should be applied through well-defined services, request classes, policies, and value objects rather than by over-engineering the codebase.

## DRY

Do not repeat logic when it can be expressed once in a reusable location. Reuse services, traits, helpers, components, and view partials where appropriate.

## KISS

Prefer simple solutions that solve the problem directly. Avoid introducing abstractions before they are justified by real needs.

## YAGNI

Do not build features or abstractions that are not required by the current scope. Keep the solution aligned with the product roadmap and current requirements.

## Separation of Concerns

Presentation, validation, business logic, and persistence must remain distinct. A controller should not contain business rules, and a model should not contain rendering logic.

## Single Responsibility Principle

Every class, service, and component should have a clear purpose and a single reason to change.

## Convention over Configuration

Laravel conventions should be preferred over bespoke solutions unless a strong architectural reason exists. The project should use native Laravel patterns and defaults whenever they are appropriate.

## Explicit over Implicit

The code should make its intent obvious. Prefer clear names and direct logic over hidden behavior, magic, or clever shortcuts.

---

# PHP Standards

The project follows the relevant PHP community standards where applicable.

## PSR-1

Code must follow the basic coding style rules defined by PSR-1, including:

- Files should use only `<?php` opening tags.
- Class names should use PascalCase.
- Method names should use camelCase.
- Constants should use uppercase snake case.

## PSR-12

Code should follow PSR-12 formatting guidance for:

- Indentation and whitespace.
- Opening braces and control structures.
- Method declarations and visibility keywords.
- Line length and organization of imports.

Formatting expectations:

- Use 4 spaces for indentation.
- Keep code readable and avoid overly dense expressions.
- Use consistent spacing around operators and control structures.
- Keep one logical statement per line where it improves readability.
- Avoid unnecessary complexity in conditionals.

---

# Laravel Standards

Laravel conventions are the baseline for this project. The architecture should remain native to Laravel and should not drift into custom patterns unless the need is justified.

## Controllers

Controllers receive requests, delegate to services, and return responses. They should remain thin and focused on orchestration.

They should not:

- Contain complex business rules.
- Perform direct database logic that belongs in services.
- Render presentation logic beyond response composition.

## Models

Models should represent domain entities and encapsulate persistence-related behavior.

They may contain:

- Relationships.
- Scopes.
- Accessors and mutators.
- Casts.

They should not:

- Contain full application workflows.
- Encapsulate unrelated business rules.
- Perform heavy view rendering logic.

## Services

Services contain business logic and reusable workflows. They should be the primary location for non-trivial application behavior.

Responsibilities include:

- Coordinating multiple models or modules.
- Encapsulating business rules.
- Enforcing domain logic.
- Supporting controllers and commands.

Services should be named clearly and designed around a specific responsibility.

## Form Requests

Form requests are used for validation and authorization. They should be used whenever input needs to be validated or permission-checked.

They should not:

- Contain broad business logic.
- Replace service-layer orchestration.

## Policies

Policies centralize authorization logic based on user roles, ownership, and permissions.

They should not:

- Perform data mutation unrelated to authorization.
- Contain presentation logic.

## Observers

Observers should handle model lifecycle events such as create, update, delete, or save. They should remain lightweight and avoid containing large workflows.

## Events

Events represent meaningful domain transitions. They should describe what happened, not contain all the logic for handling it.

## Jobs

Jobs represent queued or asynchronous work. They should be small and focused and should delegate to services when additional logic is required.

## Notifications

Notifications are used for user-facing or system-facing messages. They should format and deliver messages, not carry unrelated business rules.

## Mail

Mail classes should assemble email content and metadata. They should not contain domain logic unrelated to message composition.

## Console Commands

Console commands should encapsulate administrative or maintenance tasks. They should coordinate services and external actions without mixing unrelated responsibilities.

## Traits

Traits should be small, focused, and reusable. They should solve a narrow concern and not replace service classes.

## Helpers

Helpers should be limited to small, stateless utilities. They should not contain domain workflows or large orchestration logic.

---

# Controller Standards

Controllers must remain thin.

A controller should:

- Receive an incoming request.
- Validate or delegate validation to form requests.
- Delegate business logic to services.
- Return a response, redirect, view, or JSON payload.

Controllers must never contain:

- Complex business logic.
- Repeated domain calculations.
- Direct persistence logic beyond minimal orchestration.
- Large amounts of conditional branching that represent business rules.

When a controller becomes crowded, it should be refactored into services or request classes.

---

# Service Layer Standards

Services exist to keep business logic out of controllers and models. They provide a stable location for reusable, testable domain behavior.

## Responsibilities

A service should represent a specific domain capability such as enrollment, course publishing, lesson completion, or certificate issuance.

## Method Design

Methods should be clear, focused, and reusable. A service method should do one meaningful thing and expose that intent through a descriptive name.

## Reusability

If logic is used by multiple controllers, commands, or jobs, it should be moved to a service.

## Dependencies

Services may depend on other services, models, repositories, or integrations. Dependencies should be explicit and avoid hidden coupling.

## Best Practices

- Keep services cohesive and dedicated to one domain concern.
- Avoid writing "god services" that handle unrelated responsibilities.
- Prefer small, well-named methods over large procedural blocks.
- Use exceptions and clear return values rather than hidden side effects.

Examples of good service boundaries include authentication workflows, course publishing workflows, progress calculation, achievement evaluation, and notification dispatch.

---

# Model Standards

Models should stay focused on domain representation and persistence behavior.

## Relationships

Relationships should be defined clearly and reflect the domain model. Relationships must be readable and named according to the project’s conventions.

## Scopes

Scopes should encapsulate reusable query constraints and keep controllers and services from repeating filtering logic.

## Accessors and Mutators

Use accessors and mutators for formatting and transforming model values when the behavior belongs to the model.

## Casts

Use casts to transform database values into meaningful PHP types.

## Mass Assignment

Mass assignment should be handled carefully. The model should define guarded or fillable fields explicitly and avoid broad assignment policies unless the use case is intentional.

## Business Logic Limitations

Models should not become dumping grounds for application workflows. Business logic that spans multiple models or concerns should be moved to services.

## Best Practices

- Keep model methods focused and domain-relevant.
- Avoid complex branching inside model methods.
- Keep model classes readable and predictable.

---

# Validation Standards

Validation should be explicit and centralized.

## Form Requests

Use form requests for request validation and authorization whenever possible. This keeps validation logic out of controllers and makes the intent visible.

## Validation Rules

Validation rules should be concise, explicit, and reusable. Use custom rules when rules are domain-specific or repeated.

## Custom Validation

If validation logic is complex, it should be expressed through dedicated validation rules or service-level checks rather than embedded in controllers.

## Authorization

Authorization belongs in policies, not in validation rules. Validation should focus on input correctness, while policies enforce what a user may do.

## Error Messages

Error messages should be clear, user-friendly, and consistent. Avoid vague or overly technical language.

## Validation Responsibilities

- Frontend validation can improve UX but must not replace server-side validation.
- Database constraints protect data integrity.
- Business rules belong in services and domain logic.

---

# Blade Standards

Blade is the primary presentation layer for the application and should be kept clean and maintainable.

## Blade Layouts

Layouts should define the common shell of the page and should not contain feature-specific markup.

## Blade Components

Reusable UI should be built as Blade components rather than duplicated across templates.

## Blade Partials

Partials should be used for repeated markup fragments when they provide clarity and reuse.

## View Organization

Views should be organized by feature and role, with clear folder structures that match the domain.

## Presentation Logic

Simple presentation logic may exist in Blade, but complex logic should be moved to services or view data preparation.

## Reusable Components

Prefer reusable components for repeated patterns such as cards, alerts, forms, navigation, and lesson content wrappers.

## Accessibility

Templates must support accessible markup, semantic HTML, and keyboard-friendly behavior.

## Responsiveness

Layouts and components should be designed to work across screen sizes using Bootstrap utilities and accessible responsive patterns.

Templates should never contain:

- Complex business logic.
- Raw database queries.
- Heavy inline JavaScript that should be extracted to the frontend layer.
- Duplicate markup that should be shared via components.

---

# Bootstrap Standards

Bootstrap is the official UI foundation and should be used consistently.

## Grid

Use the Bootstrap grid system for responsive layouts.

## Utilities

Use Bootstrap utility classes for spacing, alignment, display, and responsive behavior wherever practical.

## Spacing

Use consistent spacing scales to maintain visual harmony.

## Flex

Use flex utilities for alignment and layout decisions when they improve clarity.

## Responsive Classes

Responsive classes should be used intentionally, not excessively, and should support the platform’s support policy.

## Custom CSS Policy

Custom CSS should be minimal and purposeful. Avoid unnecessary overrides of Bootstrap defaults.

## Component Reuse

Reuse Bootstrap components and patterns rather than creating one-off implementations.

## Avoid Unnecessary Overrides

Do not override Bootstrap styles without a clear design reason. Custom styles should be scoped and documented.

---

# JavaScript Standards

JavaScript should remain lightweight and purposeful.

## Vanilla JavaScript

Use vanilla JavaScript for simple, focused behaviors.

## Alpine.js

Use Alpine.js for small interactive behaviors that enhance Blade-rendered interfaces.

## DOM Manipulation

DOM manipulation should be clear, minimal, and easy to follow. Avoid sprawling inline scripts.

## Events

Use event listeners intentionally and keep them scoped to the relevant component or page.

## Modules

If JavaScript grows beyond small enhancements, organize it into modules rather than monolithic scripts.

## Naming

Use descriptive names for functions and variables. Avoid vague names such as `x` or `temp`.

## Organization

JavaScript should be organized by feature or component where practical.

## Avoid Global Variables

Do not introduce unnecessary global state. Prefer local scope and explicit data flow.

---

# CSS Standards

Custom CSS should be structured, intentional, and low in complexity.

## Custom CSS

Use custom CSS for project-specific styling that cannot be expressed cleanly with Bootstrap utilities.

## Naming

Use clear, semantic class names. Prefer descriptive names that reflect purpose rather than implementation details.

## Organization

Keep styles grouped logically by component, page, or layout concern.

## Specificity

Avoid unnecessary specificity. Prefer simple selectors and clear structure.

## Variables

Use CSS variables for repeated design values such as spacing, colors, and typography.

## Responsiveness

Ensure styles remain functional and readable across supported devices and breakpoints.

## Avoid Duplicated Styles

Do not duplicate styles across files or components when a shared class or utility can be used.

---

# Naming Conventions

The project uses consistent naming across the codebase.

## Classes

Use PascalCase for classes.

Examples:

- `CourseService`
- `LessonProgressPolicy`
- `UserProfileController`

## Methods

Use camelCase for methods.

Examples:

- `getActiveCourses()`
- `markLessonCompleted()`
- `canAccessCourse()`

## Variables

Use camelCase for variables.

Examples:

- `$courseCount`
- `$lessonProgress`
- `$isPublished`

## Constants

Use uppercase snake case.

Examples:

- `STATUS_PUBLISHED`
- `ROLE_ADMIN`

## Routes

Use lowercase, descriptive route names.

Examples:

- `courses.index`
- `lessons.show`
- `admin.dashboard`

## Blade Views

Use lowercase, descriptive names with folder grouping where helpful.

Examples:

- `resources/views/courses/index.blade.php`
- `resources/views/lessons/show.blade.php`

## Blade Components

Use PascalCase component names and kebab-case file names.

Examples:

- `AlertCard`
- `course-card.blade.php`

## Services

Use PascalCase and a clear domain suffix.

Examples:

- `CourseService`
- `AchievementService`

## Models

Use singular PascalCase names.

Examples:

- `Course`
- `Lesson`
- `QuizAttempt`

## Controllers

Use PascalCase and a domain-specific suffix.

Examples:

- `CourseController`
- `AdminCourseController`

## Requests

Use PascalCase and descriptive names.

Examples:

- `StoreCourseRequest`
- `UpdateLessonRequest`

## Policies

Use PascalCase and a domain-focused name.

Examples:

- `CoursePolicy`
- `LessonPolicy`

## Database Tables

Use lowercase snake case, plural where appropriate.

Examples:

- `courses`
- `lesson_progress`
- `quiz_attempts`

## Migration Files

Use timestamped names that describe the change.

Examples:

- `create_courses_table`
- `add_published_at_to_lessons`

## Seeders

Use PascalCase or descriptive class names.

Examples:

- `CourseSeeder`
- `AdminUserSeeder`

## Factories

Use singular PascalCase names.

Examples:

- `CourseFactory`
- `UserFactory`

## Events

Use PascalCase and a clear domain event name.

Examples:

- `LessonCompleted`
- `CoursePublished`

## Jobs

Use PascalCase and action-oriented names.

Examples:

- `SendLessonReminderJob`
- `GenerateCertificateJob`

## Notifications

Use PascalCase and a clear purpose.

Examples:

- `LessonReminderNotification`
- `CoursePublishedNotification`

---

# Error Handling

Errors should be handled deliberately and predictably.

## Exceptions

Use exceptions for exceptional conditions rather than for routine control flow. Custom exceptions should be used when a domain-specific failure needs to be expressed clearly.

## Validation Errors

Validation errors should be returned in a structured and user-friendly form.

## 404

Not-found errors should be handled consistently and should present a clear experience to the user.

## 403

Permission-related failures should return a clear authorization response and should be enforced through policies.

## 500

Unexpected failures should be logged and surfaced safely without exposing internal details to end users.

## Logging

Logs should capture sufficient context to diagnose issues without exposing passwords or tokens.

## User-friendly Messages

User-facing error messages should be short, human-readable, and actionable.

---

# Logging Standards

Logging should be used sparingly and with purpose.

## When to Log

Log significant events such as authentication failures, failed background jobs, permission errors, import issues, and unexpected exceptions.

## What to Log

Log enough context to understand what happened: the event, affected entity, user context, and relevant identifiers.

## Sensitive Information

Never log passwords, tokens, API keys, or other sensitive values.

## Log Levels

Use log levels appropriately:

- `debug` for non-production diagnostics.
- `info` for meaningful but expected events.
- `warning` for recoverable issues.
- `error` for failures that require attention.

## Production Considerations

Avoid noisy logging in production. Keep logs structured, relevant, and suitable for monitoring.

---

# Security Standards

Security must be treated as a design concern, not an afterthought.

## Validation

All user input must be validated on the server side.

## Authorization

Every protected action must be authorized through policies, gates, or middleware.

## Escaping

Output must be escaped properly in Blade templates and views to prevent cross-site scripting issues.

## CSRF

CSRF protection is required for state-changing requests.

## XSS

Prevent XSS by escaping dynamic content and avoiding unsafe inline rendering.

## SQL Injection

Use Laravel query builder or Eloquent rather than raw database queries when possible. Never concatenate user input into SQL statements.

## Mass Assignment

Avoid unsafe mass assignment and define explicit fillable or guarded properties.

## Sensitive Data

Store sensitive data carefully and limit access to the minimum required roles.

## Secrets

Secrets and credentials must be stored in environment variables and never committed to source control.

## Environment Variables

Environment-specific configuration should use `.env` values and documented configuration patterns.

---

# Performance Standards

Performance should be considered from the beginning of each feature.

## Eager Loading

Use eager loading for relationships that will be accessed together to prevent N+1 query issues.

## Pagination

Use pagination for large lists and search results.

## Caching

Use caching for repeated, expensive, or read-heavy operations when the cache invalidation strategy is clear.

## Database Queries

Write efficient queries and prefer relationships over repeated manual lookups.

## N+1 Prevention

Avoid N+1 query patterns by loading related records intentionally.

## Lazy Loading

Lazy loading is acceptable only when the amount of data is small and the query path is simple.

## Asset Optimization

Frontend assets should be optimized for production, including minification and efficient bundling.

## Reusable Components

Use reusable Blade components and shared frontend assets to avoid redundant work and unnecessary complexity.

---

# Documentation Standards

Code must be documented well enough to support both human developers and AI agents.

## PHPDoc

Use PHPDoc for complex classes, methods, and service responsibilities where beneficial.

## Method Comments

Add comments to explain intent when the implementation is non-obvious. Do not comment obvious code.

## Complex Business Logic

Complex business rules should be documented in service classes or dedicated architecture notes rather than hidden in controllers.

## README Updates

Any meaningful new feature or architectural change should be reflected in the documentation set.

## Architecture Updates

If the solution changes the application structure, the relevant architecture documents should be updated.

## Database Documentation

Database changes should be reflected in the relevant database documentation to keep the design reference accurate.

---

# Git Standards

The project uses disciplined version control practices.

## Branch Names

Use descriptive branch names that reflect the change.

Examples:

- `feature/course-management`
- `fix/lesson-progress-bug`
- `docs/update-coding-standards`

## Commit Messages

Use clear, descriptive commit messages.

Examples:

- `feat: add course publishing workflow`
- `fix: correct lesson progress calculation`
- `docs: update coding standards`

## Pull Requests

Pull requests should include a clear summary, scope, and testing or verification notes.

## Merge Strategy

Prefer merge commits or squash merges that preserve a clear development history. Avoid unnecessary merge noise.

## Version Tags

Use semantic versioning for release milestones when appropriate.

## Semantic Versioning

Use version numbers that reflect the impact of changes:

- Major: breaking changes.
- Minor: backward-compatible feature additions.
- Patch: bug fixes and maintenance updates.

---

# Code Review Checklist

Every change should be reviewed against the following checklist.

- Readability: Is the code easy to understand?
- Architecture: Does it respect the service, controller, and model boundaries?
- Performance: Does it avoid unnecessary queries or large asset overhead?
- Security: Does it validate input and protect sensitive behavior?
- Testing: Is the change covered by tests or a clear validation path?
- Documentation: Are documentation and architecture notes updated when needed?
- Naming: Are names descriptive, consistent, and aligned with standards?
- Duplication: Is logic reused instead of copied?
- Responsiveness: Does the UI remain usable across supported devices?
- Accessibility: Does the implementation support accessible behavior and semantics?

---

# AI Development Rules

AI agents must follow this document before writing code.

- AI agents must not introduce new coding styles that conflict with this document.
- AI agents must reuse existing architecture rather than creating parallel patterns.
- AI agents must avoid duplicated implementations when a shared service, component, or utility already exists.
- AI agents must keep controllers thin and place business logic inside services.
- AI agents must document architectural changes that affect the project’s structure or conventions.

---

# Common Mistakes

The following mistakes should be avoided.

## Putting business logic in controllers

This makes the application harder to test and harder to maintain. Business logic belongs in services.

## Creating duplicate implementations

Duplicated logic leads to drift and inconsistent behavior over time.

## Mixing presentation and business logic in Blade templates

This makes views difficult to maintain and weakens separation of concerns.

## Overusing JavaScript for simple interactions

The project should prefer Blade and Alpine for lightweight interactions rather than introducing unnecessary frontend complexity.

## Ignoring validation and authorization

Skipping validation and authorization creates security issues and inconsistent behavior.

## Introducing packages without review

Unreviewed packages increase maintenance risk and may conflict with the established stack.

## Writing unclear names

Vague names make code harder to read and increase the cost of future changes.

---

# Revision History

| Version | Date | Author | Notes |
|---|---|---|---|
| 1.0 | 2026-07-03 | Frontend Academy Team | Initial coding standards reference for Frontend Academy. |
