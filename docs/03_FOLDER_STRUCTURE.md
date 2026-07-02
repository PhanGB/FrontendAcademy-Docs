# Folder Structure

## Purpose

A consistent folder structure is essential to the long-term health of Frontend Academy. It improves maintainability, reduces ambiguity, supports scalability, and makes the codebase easier to navigate for both human contributors and AI agents. A well-defined structure also strengthens team collaboration by ensuring that responsibilities are predictable and that new work can be added without introducing scattered or duplicate implementations.

The folder structure should support the following goals:

- Maintainability: Developers should be able to find the right file quickly and understand where new code belongs.
- Scalability: The structure must accommodate growing modules, increasing content, and later expansions without forcing a major rewrite.
- Discoverability: Related concerns should be grouped in a way that makes intent obvious.
- AI-Friendly Development: The layout should be simple, conventional, and easy for automated contributors to interpret.
- Team Collaboration: Shared conventions reduce friction and improve consistency across contributors.

## Laravel Default Structure

Frontend Academy will follow Laravel’s default directory conventions as the foundation of the project structure. The standard directories provide a predictable layout for core application concerns.

### app/

- Purpose: Contains the application’s core business logic, HTTP layer, models, services, policies, and supporting classes.
- Allowed contents: Controllers, Models, Services, Requests, Policies, Middleware, Providers, Console commands, Events, Listeners, Exceptions, Jobs, Notifications, Rules, Traits, Helpers, and related domain logic.
- Things that should never be placed there: Raw database schema files, frontend build output, static user-uploaded assets, or unrelated third-party libraries.

### bootstrap/

- Purpose: Contains framework bootstrapping files and the application initialization path.
- Allowed contents: Framework bootstrapping files and service provider registration logic.
- Things that should never be placed there: Domain business logic, application controllers, or module-specific code.

### config/

- Purpose: Stores application and package configuration values.
- Allowed contents: Environment-specific configuration files, package settings, application options, and feature flags.
- Things that should never be placed there: Runtime-generated data, user content, or business logic.

### database/

- Purpose: Holds database-related definitions and seed data.
- Allowed contents: Migrations, seeders, factories, and schema-related support files.
- Things that should never be placed there: Application controllers, general-purpose services, or view templates.

### public/

- Purpose: Serves as the public web entry point and stores publicly accessible assets.
- Allowed contents: Index file, compiled assets, images, icons, fonts, downloadable files, and other browser-accessible static resources.
- Things that should never be placed there: Source code that should remain inside the application layer, sensitive server-side logic, or private files.

### resources/

- Purpose: Contains views, frontend assets, localization resources, and presentation-layer files.
- Allowed contents: Blade templates, layouts, components, partials, CSS, JavaScript, images used in the UI, and language files if introduced.
- Things that should never be placed there: Business logic, database access code, or application services intended for reuse outside presentation.

### routes/

- Purpose: Defines the application’s request entry points.
- Allowed contents: Web routes, authentication routes, admin routes, and API routes when introduced.
- Things that should never be placed there: Complex domain logic, controller implementations, or database query code.

### storage/

- Purpose: Stores runtime-generated or user-generated content that is not part of the source tree.
- Allowed contents: Logs, cache files, compiled views, uploads, temporary files, and framework-generated state.
- Things that should never be placed there: Source files that should be version-controlled, business logic, or static assets that belong in public/.

### tests/

- Purpose: Contains automated tests that verify platform behavior and guard against regressions.
- Allowed contents: Feature tests, unit tests, and future browser/end-to-end tests.
- Things that should never be placed there: Production application code, generated build artifacts, or runtime data.

### vendor/

- Purpose: Stores Composer and package dependencies.
- Allowed contents: Third-party libraries installed by Composer.
- Things that should never be placed there: Project-owned application code or custom business modules.

## Application Structure

The application layer in app/ should remain organized and module-aware. The structure should reflect the platform’s responsibilities while staying consistent with Laravel conventions.

### Controllers

- Purpose: Receive requests, delegate to services, and return responses.
- Responsibilities: Route handling, request orchestration, and response preparation.
- Should contain: Minimal flow control, simple data mapping, and response decisions.
- Should not contain: Business rules, long validation logic, or direct database queries beyond simple retrieval when absolutely necessary.

### Models

- Purpose: Represent entities and encapsulate persistence behavior.
- Responsibilities: Relationships, scopes, casts, accessors, mutators, and persistence-related logic.
- Should contain: Data structure definitions and model-level behavior.
- Should not contain: Full application workflows or presentation logic.

### Services

- Purpose: Encapsulate business logic and domain operations.
- Responsibilities: Orchestrating workflows, performing calculations, coordinating modules, and enforcing business rules.
- Should contain: Reusable logic shared across controllers or commands.
- Should not contain: Presentation-only concerns or direct HTML rendering.

### Requests

- Purpose: Contain validation and authorization logic for incoming data.
- Responsibilities: Rules, messages, authorization checks, and request-specific validation behavior.
- Should contain: Form requests for validated input and protected actions.
- Should not contain: Business logic unrelated to request handling.

### Policies

- Purpose: Centralize authorization rules.
- Responsibilities: Authorize actions based on role, ownership, or policy logic.
- Should contain: Permission checks and access rules.
- Should not contain: Data retrieval logic unrelated to authorization.

### Traits

- Purpose: Share small, reusable behaviors across multiple classes.
- Responsibilities: Cross-cutting behavior such as common helper methods or shared logic.
- Should contain: Small, focused building blocks.
- Should not contain: Large domain services or unrelated abstractions.

### Helpers

- Purpose: Provide utility functions for common repeated operations.
- Responsibilities: Small support functions that are useful across the application.
- Should contain: Stateless helpers with narrow purpose.
- Should not contain: Large orchestration logic or stateful objects.

### Observers

- Purpose: Respond to model lifecycle events.
- Responsibilities: Handle actions on create, update, delete, or save events.
- Should contain: Side effects triggered by model changes.
- Should not contain: High-level workflow logic that should be placed in services.

### Providers

- Purpose: Register services, bindings, and application bootstrapping behavior.
- Responsibilities: Service container registration, custom boot logic, and integration wiring.
- Should contain: Framework and application registration logic.
- Should not contain: Domain-specific workflow implementation.

### Exceptions

- Purpose: Define custom exceptions for domain or application-specific error handling.
- Responsibilities: Represent expected failure conditions clearly.
- Should contain: Custom exception classes with meaningful names and context.
- Should not contain: General utility code or unrelated error handling.

### Console

- Purpose: Host artisan commands used for maintenance or administration.
- Responsibilities: Batch operations, data maintenance, import/export tasks, and administrative commands.
- Should contain: Console commands with limited scope.
- Should not contain: Complex user-facing web logic.

### Jobs

- Purpose: Represent queued or asynchronous work.
- Responsibilities: Offload work that should not block the user experience.
- Should contain: Small, serializable units of work.
- Should not contain: Large service logic that should remain in services.

### Events

- Purpose: Define meaningful domain events.
- Responsibilities: Signal important changes within the system.
- Should contain: Event classes and payloads.
- Should not contain: Side effects or application behavior.

### Listeners

- Purpose: Respond to events by performing follow-up actions.
- Responsibilities: Notification dispatch, integration triggers, or reaction workflows.
- Should contain: Event reaction logic.
- Should not contain: Core business rules that belong in services.

### Mail

- Purpose: Define mailables for system emails.
- Responsibilities: Assemble email content and metadata.
- Should contain: Mail class definitions and related presentation.
- Should not contain: Business logic unrelated to message composition.

### Notifications

- Purpose: Define in-platform or email notifications.
- Responsibilities: Channel-based notification delivery and content formatting.
- Should contain: Notification classes for user-facing events.
- Should not contain: Core state-changing business operations.

### Rules

- Purpose: Encapsulate reusable validation rules.
- Responsibilities: Cleanly express custom validation behavior.
- Should contain: Validation rule classes with focused purpose.
- Should not contain: Large domain logic.

## Controller Organization

Controllers should be organized by feature and audience so that the structure reflects the application’s functional domains. The controller layer should remain thin and focused on request handling.

Recommended organization:

- Controllers/
  - Admin/
  - Student/
  - Auth/
  - Profile/
  - Course/
  - Lesson/
  - Quiz/
  - Project/
  - Progress/
  - Settings/

State naming conventions should follow the user-facing role or functional context of the controller. For example:

- AdminCourseController
- StudentLessonController
- AuthLoginController
- ProfileSettingsController

Controller responsibilities:

- Accept input from the request.
- Delegate to services.
- Return views or redirects.
- Handle response composition and status codes.

Controllers should never:

- Contain business logic.
- Perform complex validation directly.
- Query the database in a way that encodes business rules.
- Render presentation details beyond the final response shape.

## Service Layer

Services exist to keep business logic out of controllers and to make domain behavior reusable and testable. This separation is one of the core architectural rules of the project.

A service should encapsulate logic such as:

- Enrollment workflows.
- Progress calculation.
- Certificate issuance.
- Quiz grading.
- Lesson completion tracking.
- Achievement evaluation.
- Notification dispatch coordination.

Services should be used when a task:

- Involves rules beyond a simple CRUD operation.
- Needs to be reused across multiple controllers or commands.
- Requires coordination between models and supporting modules.
- Should be tested independently from the HTTP layer.

## Request Validation

Form requests should be used for validating incoming data and authorizing actions. They provide a structured and reusable approach to keeping request-specific concerns outside controllers.

Form requests should be used for:

- Creating or updating courses, lessons, quizzes, profiles, and settings.
- Enforcing validation rules for user-submitted input.
- Expressing authorization conditions before the action is processed.

Best practices:

- Keep validation rules explicit and focused.
- Use custom messages when the default wording is insufficient.
- Separate validation concerns from domain business logic.
- Use authorization methods in requests when access rules depend on the action or resource.
- Avoid overloading controllers with validation logic.

## Models

Models are responsible for representing domain entities and encapsulating persistence-related behavior. They should stay focused on the data shape and relationships of the application.

Responsibilities:

- Define table mappings and attributes.
- Declare relationships such as hasMany, belongsTo, belongsToMany, and morph relationships when applicable.
- Encapsulate simple query scopes for reusable filters.
- Define accessors and mutators for attribute transformation.
- Define casts for structured values such as booleans, arrays, or JSON.

Best practices:

- Keep models readable and focused.
- Avoid embedding large application workflows in models.
- Use scopes for common query patterns.
- Keep relationship definitions clear and explicit.
- Prefer model-level behavior only when it is truly part of the data abstraction.

## Resources Directory

The resources directory holds presentation and frontend asset files. It should be organized so that templates, styles, and scripts remain easy to maintain.

### resources/views

- Purpose: Contains Blade templates and presentation structure.
- Organization: Group by page type, feature, or role.
- Should contain: Layouts, pages, components, partials, and error views.

### resources/css

- Purpose: Stores application stylesheets.
- Organization: Keep global styles separate from component-specific or page-specific styles where possible.

### resources/js

- Purpose: Stores frontend JavaScript sources.
- Organization: Keep scripts modular and aligned with progressive enhancement principles.

## Blade Structure

Blade views should follow a consistent structure that separates global layout from page-specific content and role-specific experiences.

### layouts/

- Purpose: Shared page shells and global layout structure.
- Naming convention: Use descriptive names such as app.blade.php and admin.blade.php.
- Usage: Define the main page wrapper, navigation, and common chrome.

### components/

- Purpose: Reusable UI units.
- Naming convention: Use kebab-case component names and organize by responsibility.
- Usage: Buttons, cards, forms, badges, lesson summaries, and navigation elements.

### partials/

- Purpose: Reusable fragments of markup.
- Naming convention: Use descriptive names such as flash-messages.blade.php.
- Usage: Shared sections that are inserted into multiple views.

### pages/

- Purpose: Feature-specific pages.
- Naming convention: Use a folder per feature and descriptive view names.
- Usage: Page-level templates for primary user flows.

### admin/

- Purpose: Administrative interface views.
- Naming convention: Use admin/ for administrative sections and subfolders by feature.
- Usage: Dashboard pages, moderation tools, and content-management interfaces.

### student/

- Purpose: Student-facing pages.
- Naming convention: Use student/ for learner-specific views.
- Usage: Course pages, lesson content, progress views, and learning dashboards.

### errors/

- Purpose: Error-related views.
- Naming convention: Use descriptive error view files such as 404.blade.php and 500.blade.php.
- Usage: User-facing error pages and fallback states.

### auth/

- Purpose: Authentication-related views.
- Naming convention: Use auth/ for login, registration, password reset, and session-related pages.
- Usage: Sign-in, registration, recovery, and related flows.

## Blade Components

Reusable Blade components should be used to avoid duplicated markup and to keep the UI consistent. The component strategy should favor small, composable pieces over large one-off templates.

### Anonymous Components

- Purpose: Best for small, self-contained UI fragments.
- Use when: The component is simple and does not require custom logic.

### Class Components

- Purpose: Best for components that need behavior, attributes, or more advanced rendering control.
- Use when: The component needs logic or reusable data handling beyond simple markup.

### Component Slots

- Purpose: Allow content to be injected into a component.
- Use when: A component should act as a wrapper while preserving flexibility.

### Attributes

- Purpose: Support configurable component behavior and styling.
- Use when: A component needs optional props, classes, or rendering variations.

Reusable UI philosophy:

- Build small building blocks that can be composed together.
- Keep components focused and predictable.
- Avoid embedding business logic into components.
- Prefer consistent formatting, props, and naming across the UI.

## Public Directory

The public directory should contain only assets that are directly exposed to the browser.

### assets/

- Purpose: Store compiled or source frontend assets that are served by the application.
- Organization: Keep generated and static assets separated where appropriate.

### images/

- Purpose: Store public images used by the interface or content.
- Organization: Group by type or feature when needed.

### icons/

- Purpose: Store static icons used by the application.
- Organization: Keep a consistent naming scheme and avoid duplicate icon variants.

### fonts/

- Purpose: Store web fonts when the project requires custom typography.
- Organization: Keep font files in a dedicated location and reference them from the asset pipeline.

### downloads/

- Purpose: Store files intended for direct user download.
- Organization: Keep file types and categories clearly separated.

## Routes

Routes should remain clear and organized by purpose. The structure should mirror the system’s major user experiences while keeping the routing layer straightforward.

### web.php

- Purpose: Main application routes for the website experience.
- Contains: Standard public and authenticated pages and general user flows.

### auth.php

- Purpose: Authentication-related routes.
- Contains: Login, registration, password reset, and logout flows.

### admin.php (future)

- Purpose: Administrative routes when the admin interface grows beyond a single file.
- Contains: Dashboard and management routes grouped by responsibility.

### api.php (future)

- Purpose: API routes for future integrations or client applications.
- Contains: Endpoint definitions for external or programmatic access.

Route naming conventions:

- Use descriptive, resource-oriented names.
- Prefer lowercase, kebab-case, or dot-based naming consistent with Laravel conventions.
- Keep route names aligned with the feature or module they serve.

## Database Structure

The database directory should hold persistence definitions in a clean and versioned way.

### migrations

- Purpose: Track schema changes over time.
- Naming convention: Use descriptive names such as create_courses_table.php or create_lesson_progress_table.php.
- Rules: Keep migrations focused and reversible where possible.

### seeders

- Purpose: Populate the database with initial or test data.
- Naming convention: Use descriptive names such as UserSeeder or CourseSeeder.
- Rules: Keep seeders clear, minimal, and safe to run repeatedly when appropriate.

### factories

- Purpose: Generate realistic test data for development and testing.
- Naming convention: Use model-based names such as CourseFactory or UserFactory.
- Rules: Keep factories aligned with the model they support.

## Storage

The storage directory is for generated and runtime-managed content. It should not be treated as a place for source files or core application code.

### logs

- Purpose: Store application logs.
- Usage: Error logs, debug output, and operational messages.

### uploads

- Purpose: Store user-uploaded or generated files.
- Usage: Profile media, lesson assets, and other content that is not part of the source tree.

### cache

- Purpose: Store cached data and compiled artifacts.
- Usage: Framework caches, route caches, and application cache files.

### framework

- Purpose: Store framework-managed runtime files.
- Usage: Sessions, cache metadata, and compiled framework artifacts.

## Tests

Tests should be organized by scope and purpose. The structure should support both rapid feature validation and deeper unit-level verification.

### Feature Tests

- Purpose: Validate end-to-end behavior through the application layer.
- Use for: Routes, controllers, authentication, and user workflows.

### Unit Tests

- Purpose: Validate business logic and isolated components.
- Use for: Services, helpers, validation rules, and model behavior.

### Future Browser Tests

- Purpose: Validate interactive browser behavior when the UI grows more dynamic.
- Use for: Rich interactions, complex flows, and user experience regressions.

Testing philosophy:

- Prefer behavior-focused tests over implementation-focused tests.
- Keep tests readable and tied to real user workflows where possible.
- Use tests to protect architectural boundaries and business rules.

## Naming Conventions

Naming conventions should be consistent and predictable throughout the codebase.

### Directories

- Use lowercase, descriptive names.
- Prefer singular names for domain-focused folders where appropriate.
- Use hyphenated or lowercase names only when a directory name requires a separator.

### Files

- Use PascalCase for classes and camelCase for helper or utility files where appropriate.
- Use descriptive names that reflect the file’s responsibility.
- Keep file names aligned with the class or feature they represent.

### Controllers

- Use PascalCase.
- Suffix with Controller.
- Example: CourseController, StudentLessonController.

### Models

- Use PascalCase.
- Use singular names that reflect the domain entity.
- Example: Course, Lesson, QuizAttempt.

### Services

- Use PascalCase.
- Use descriptive names that reflect the business capability.
- Example: CourseEnrollmentService, ProgressTrackerService.

### Blade Views

- Use lowercase and descriptive naming.
- Use dot notation or folder-based organization where appropriate.
- Example: courses.index.blade.php.

### Blade Components

- Use kebab-case for component names.
- Example: lesson-card.blade.php or course-progress.blade.php.

### CSS

- Use lowercase and descriptive names.
- Prefer a single entry point for global styles and smaller feature-specific files when needed.

### JavaScript

- Use camelCase or kebab-case consistently.
- Keep files focused by responsibility.

### Images

- Use lowercase, descriptive names.
- Prefer consistent naming for asset variants.

### Database Tables

- Use lowercase snake_case.
- Use plural names for tables.
- Example: users, course_lessons, quiz_attempts.

### Migration Files

- Use a timestamped prefix followed by a descriptive suffix.
- Example: 2026_07_02_000001_create_courses_table.php.

### Routes

- Use descriptive route names and keep them role- or feature-oriented.
- Example: courses.index, student.lessons.show.

### Variables

- Use camelCase.
- Keep names descriptive and domain-oriented.

### Methods

- Use camelCase.
- Use verbs that describe the action clearly.

### Classes

- Use PascalCase.
- Keep names meaningful and specific.

### Constants

- Use uppercase snake_case.
- Example: MAX_ATTEMPTS, DEFAULT_ROLE.

### Environment Variables

- Use uppercase snake_case.
- Example: APP_ENV, DB_CONNECTION, MAIL_HOST.

## Module Organization

Future modules should be added in a way that preserves the existing structure and remains easy to locate. Each module should be represented consistently across the application layers.

### Course Module

- app/Http/Controllers/Course/
- app/Services/Course/
- app/Models/Course.php
- resources/views/pages/courses/
- routes/web.php or a future feature-specific route file

### Lesson Module

- app/Http/Controllers/Lesson/
- app/Services/Lesson/
- app/Models/Lesson.php
- resources/views/pages/lessons/

### Quiz Module

- app/Http/Controllers/Quiz/
- app/Services/Quiz/
- app/Models/Quiz.php
- resources/views/pages/quizzes/

### Progress Module

- app/Http/Controllers/Progress/
- app/Services/Progress/
- app/Models/ProgressRecord.php
- resources/views/pages/progress/

### Project Module

- app/Http/Controllers/Project/
- app/Services/Project/
- app/Models/Project.php
- resources/views/pages/projects/

### Achievement Module

- app/Http/Controllers/Achievement/
- app/Services/Achievement/
- app/Models/Achievement.php
- resources/views/pages/achievements/

### Certificate Module

- app/Http/Controllers/Certificate/
- app/Services/Certificate/
- app/Models/Certificate.php
- resources/views/pages/certificates/

## File Placement Rules

Every new file should be placed according to its responsibility. The following rules should be used as the default decision guide:

- Put controllers in app/Http/Controllers/.
- Put domain logic in app/Services/.
- Put request validation in app/Http/Requests/.
- Put authorization rules in app/Policies/.
- Put models in app/Models/.
- Put reusable UI in resources/views/components/.
- Put page-level templates in resources/views/pages/.
- Put shared layout files in resources/views/layouts/.
- Put reusable fragments in resources/views/partials/.
- Put frontend scripts in resources/js/.
- Put styles in resources/css/.
- Put migrations in database/migrations/.
- Put routes in routes/.
- Put tests in tests/.

Examples:

- A new lesson creation form request belongs in app/Http/Requests/Lesson/.
- A new course enrollment workflow belongs in app/Services/Course/.
- A new reusable lesson card component belongs in resources/views/components/lesson-card.blade.php.
- A new admin dashboard page belongs in resources/views/admin/dashboard.blade.php.

## Directory Do's and Don'ts

### Do

- Keep the structure conventional and predictable.
- Group related files by responsibility.
- Reuse existing folders before creating new ones.
- Keep nested folders shallow and readable.
- Keep naming consistent with the surrounding codebase.
- Document meaningful changes to structure.

### Don't

- Create new top-level directories without approval.
- Scatter feature code across unrelated folders.
- Place business logic inside views.
- Put controllers in the wrong layer.
- Duplicate logic in multiple modules.
- Hide important domain logic inside non-obvious locations.

## AI Development Rules

AI agents must follow the documented folder structure and naming conventions exactly. They must not introduce ad hoc directory layouts or create parallel implementations when an established location already exists.

AI agents must:

- Never create new top-level directories without approval.
- Reuse existing folders whenever possible.
- Respect naming conventions and module boundaries.
- Keep the directory structure clean and maintainable.
- Avoid duplicate implementations.
- Ensure that documentation remains aligned with the actual structure.

## Future Expansion

The folder structure should remain stable as the project grows. Future expansion should be handled by adding new modules and subfolders within the existing architectural layers rather than by replacing the layout with a different convention.

Possible future expansion paths include:

- Additional module-specific folders under app/Http/Controllers/ and app/Services/.
- More specialized Blade view areas for instructor, moderator, or analytics workflows.
- Additional route files for admin, API, or other dedicated surfaces.
- New storage subfolders for different content categories or file types.

The structure should evolve incrementally and remain backward compatible with the initial Laravel-based layout.

## Revision History

| Version | Date | Description |
| --- | --- | --- |
| 1.0 | 2026-07-02 | Initial folder structure document established as the official directory and naming reference for the project. |
