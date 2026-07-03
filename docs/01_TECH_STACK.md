# Technology Stack

## Purpose

A fixed technology stack is essential for Frontend Academy because it anchors the project in a stable, maintainable, and consistent execution environment. A clearly defined stack reduces friction for new contributors, minimizes the risk of incompatible dependencies, and preserves a shared expectation for architecture and tooling.

Long-term maintenance depends on predictable technology choices. By standardizing frameworks, build tools, and deployment targets, the team can focus on product improvements instead of chasing compatibility issues.

Stability is achieved when every layer of the application is selected for reliability and maturity. The stack should work well together, limiting surprises during development and deployment.

Consistency matters for both code quality and collaboration. When everyone uses the same stack, component ownership, code review, and onboarding are easier. It also enables consistent documentation and helps AI tooling operate effectively across the codebase.

AI-friendly development requires a stack that is simple to reason about and well documented. By choosing established Laravel conventions, Blade templates, and minimal client-side dependencies, the project remains accessible to AI agents and human maintainers alike.

Upgrade management is easier with a fixed stack because the project can adopt new versions in a controlled way. A documented stack defines the upgrade boundaries, making it clear when to update PHP, Laravel, frontend tooling, or database drivers.

---

# Core Stack

The core stack defines the primary technologies that power Frontend Academy. Each technology is chosen for purpose, alignment with the product architecture, and long-term maintainability.

## Laravel 12

Purpose: Laravel is the backend framework and application foundation.

Responsibilities: routing, request lifecycle, database abstraction, authentication, authorization, asset compilation, and service container management.

Advantages: strong convention-over-configuration model, rich ecosystem, integrated testing support, and a large community.

Limitations: more opinionated than microframeworks, and monolithic applications require discipline to keep controllers thin and services organized.

Why selected: Laravel 12 delivers a mature, modern PHP experience with predictable conventions, excellent documentation, and a robust architecture that supports the project’s content-driven, server-rendered application model.

Why alternatives were rejected: Symfony is powerful but more complex for the team’s current scope; lightweight frameworks such as Slim or Lumen sacrifice integrated tooling and convention; full API-first PHP frameworks are not aligned with the platform’s initial server-rendered content focus.

## Blade

Purpose: Blade is the templating engine used for server-rendered UI.

Responsibilities: view rendering, template inheritance, component composition, and safe HTML escaping.

Advantages: lightweight, integrated with Laravel, easy to understand, and supports reusable view components without adding a complex frontend framework.

Limitations: not a reactive client-side framework, so richer interactions require targeted JavaScript enhancement.

Why selected: Blade is native to Laravel and supports progressive enhancement, which aligns with the project’s goal to keep markup meaningful and JS optional.

Why alternatives were rejected: full SPA frameworks would add unnecessary complexity; Twig and other template engines introduce extra dependencies and are not standard for Laravel projects.

## Bootstrap 5

Purpose: Bootstrap provides the core CSS framework and layout utilities.

Responsibilities: responsive grid, typography, forms, components, spacing, and accessible base styles.

Advantages: stable, widely adopted, well-documented, and easy to customize with a consistent visual system.

Limitations: can encourage uniform design if not customized thoughtfully; some advanced UI needs may require custom CSS.

Why selected: Bootstrap 5 is a pragmatic choice for a content-rich platform, offering a balance of utility and ease of use while reducing the need to build foundational styles from scratch.

Why alternatives were rejected: Tailwind CSS introduces a different design approach and higher runtime complexity; custom CSS-only systems would increase maintenance overhead; Bulma or Foundation are less aligned with the team’s familiarity and ecosystem.

## Alpine.js

Purpose: Alpine.js enables lightweight client-side interactivity.

Responsibilities: handling small dynamic behaviors, toggles, modals, dropdowns, and progressive enhancement.

Advantages: minimal footprint, easy integration into Blade templates, low learning curve, and direct mapping to HTML.

Limitations: not suitable for large-scale stateful applications or complex client-side routing.

Why selected: Alpine.js complements Blade by enabling interactive UI patterns without a full JavaScript framework.

Why alternatives were rejected: Vue and React are heavier and create more architectural overhead than required for the current project.

## Vite

Purpose: Vite compiles and bundles frontend assets.

Responsibilities: processing JavaScript, CSS, SCSS, and asset imports for development and production.

Advantages: fast incremental builds, modern module support, and seamless Laravel integration.

Limitations: configuration must be managed carefully for custom build needs.

Why selected: Vite is the current Laravel-recommended asset bundler and provides fast development feedback with modern browser support.

Why alternatives were rejected: Webpack is heavier and slower; older asset pipelines do not match the productivity required by the project.

## MySQL

Purpose: MySQL is the relational database for structured application data.

Responsibilities: persisting users, lessons, courses, progress, assessments, and content metadata.

Advantages: broad hosting support, strong migration tooling, mature reliability, and operational familiarity.

Limitations: requires careful schema design for complex queries and vertical scaling decisions.

Why selected: MySQL provides predictable behavior for the relational data model and aligns with common Laravel hosting environments.

Why alternatives were rejected: PostgreSQL offers advanced features, but MySQL is more widely supported in the target hosting environments and is sufficient for the project’s initial scope; SQLite is only suitable for local development and testing.

## PHP 8.3+

Purpose: PHP is the backend runtime.

Responsibilities: executing Laravel code, handling request processing, and serving server-side logic.

Advantages: modern language features, improved performance, typed properties, and active community support.

Limitations: requires a compatible hosting environment and disciplined dependency management.

Why selected: PHP 8.3+ ensures the project can use the latest Laravel features, maintain compatibility with modern packages, and benefit from improved runtime stability.

Why alternatives were rejected: older PHP versions are unsupported and insecure; non-PHP backends would break the current Laravel-centered architecture.

## Composer

Purpose: Composer manages PHP dependencies.

Responsibilities: dependency resolution, package installation, autoload generation, and version locking.

Advantages: ecosystem integration, semantic versioning support, and support for package discovery.

Limitations: dependency conflicts can be complex when introducing packages without evaluation.

Why selected: Composer is the standard dependency manager for PHP and Laravel projects.

Why alternatives were rejected: there is no viable alternative for PHP dependency management in a Laravel context.

## NPM

Purpose: NPM manages Node.js-based frontend tooling.

Responsibilities: installing frontend packages, scripts, and build tool dependencies.

Advantages: large ecosystem, compatibility with Vite, and broad community adoption.

Limitations: package maintenance varies widely across JavaScript libraries.

Why selected: NPM is the standard package manager for modern front-end build systems and works naturally with Vite.

Why alternatives were rejected: Yarn or pnpm are valid but would add an additional toolchain layer and are not necessary for the current project policy.

## Git

Purpose: Git provides version control for the codebase.

Responsibilities: tracking history, branching, merging, and supporting collaboration.

Advantages: distributed version control, strong tooling support, and a mature workflow.

Limitations: requires discipline to avoid large binary history and merge conflicts.

Why selected: Git is the industry standard for source control.

Why alternatives were rejected: centralized version control systems are not practical for modern collaborative development.

## GitHub

Purpose: GitHub hosts the repository, issue tracking, and collaboration workflows.

Responsibilities: pull requests, reviews, CI/CD integration, and repository management.

Advantages: broad adoption, integrated collaboration features, and ecosystem integrations.

Limitations: reliance on a single hosting provider, though GitHub remains the most practical choice for this project.

Why selected: GitHub enables team workflows, documentation hosting, and code review processes that match the project’s collaborative needs.

Why alternatives were rejected: other platforms provide similar features, but GitHub is the most widely used and suits the project’s expectations.

---

# Backend Stack

Frontend Academy’s backend stack is organized around Laravel conventions and clear separation of responsibilities.

## Laravel

Laravel is the primary application framework. It coordinates the application lifecycle, resolves dependencies, and provides the foundational tools for building a stable backend.

## Routing

Routing maps HTTP requests to controllers, defining the application’s public and protected entry points. Routes should be declared in the appropriate `routes/*.php` files and grouped by middleware and area of responsibility.

Responsibilities: URL mapping, middleware assignment, route naming, and route model binding.

## Middleware

Middleware applies request-level filtering and transformation.

Responsibilities: authentication checks, authorization gates, input sanitization, localization, HTTPS enforcement, and cross-cutting behaviors.

## Controllers

Controllers handle request coordination and response assembly.

Responsibilities: accepting validated data, delegating tasks to services, and returning views or JSON responses.

Controllers should remain thin. They should not contain business logic or complex persistence rules.

## Form Requests

Form requests encapsulate validation and authorization for incoming data.

Responsibilities: defining validation rules, custom messages, and request authorization logic.

Using form requests keeps validation out of controllers and centralizes request-specific rules.

## Services

Services host reusable business logic and workflows.

Responsibilities: orchestrating domain operations, coordinating model interactions, and enforcing business rules.

Service classes are the preferred place for non-trivial application behavior that belongs outside controllers and models.

## Models

Models represent domain entities and persistence behavior.

Responsibilities: defining table relationships, scopes, casts, accessors, and mutators.

Models should express data-centric behavior while avoiding application workflows.

## Policies

Policies centralize authorization decisions.

Responsibilities: defining who can perform actions on models and resources.

Applying policy checks consistently ensures authorization rules are easy to discover and maintain.

## Events

Events provide a way to signal important domain changes.

Responsibilities: representing state transitions such as lesson completion, course enrollment, or certification issuance.

## Jobs

Jobs represent discrete units of work that can run asynchronously.

Responsibilities: sending notifications, processing exports, and performing offline tasks.

## Queues (future)

Queues are part of the future scalability roadmap.

Responsibilities: offloading non-critical work from synchronous requests, improving responsiveness, and enabling background processing.

Queue adoption should be driven by clear performance needs and reliable operational monitoring.

## Caching (future)

Caching is a future optimization layer for query results, rendered fragments, and frequently accessed configuration.

Responsibilities: reducing repeated computation and database load.

Cache should be introduced carefully with clear invalidation rules and only after profiling indicates it is necessary.

---

# Frontend Stack

The frontend stack is designed to be lightweight, accessible, and maintainable while supporting the content-driven nature of the platform.

## Blade

Blade is the primary view layer. It manages template composition, shared layouts, and reusable components.

Responsibilities: page structure, component rendering, and server-side HTML generation.

## Bootstrap

Bootstrap provides the base UI framework.

Responsibilities: responsive layout, component styling, form controls, and spacing utilities.

## Alpine.js

Alpine.js provides small interactive behaviors without a heavyweight JavaScript framework.

Responsibilities: toggling UI state, controlling menus, modals, tabs, and client-side form interactions.

## JavaScript

JavaScript is used sparingly for feature enhancements.

Responsibilities: event handling, DOM updates, and integrations with approved libraries.

Custom JavaScript should remain focused on behavior that cannot be achieved through Blade, Alpine, or CSS alone.

## CSS

CSS defines the visual presentation and custom styling.

Responsibilities: brand-specific styles, layout refinements, typography, and accessibility support.

## SCSS (future possibility)

SCSS is an option for future style modularity.

Responsibilities: organizing styles into variables, mixins, and partials if the project needs more advanced styling structure.

SCSS should only be adopted when the style architecture clearly benefits from nested rules and reusable style primitives.

## Icons

Icons should be selected from a lightweight, consistent set and used to support usability without increasing bundle size unnecessarily.

Responsibilities: visual affordances for buttons, navigation, alerts, and interface elements.

## Fonts

Fonts should be chosen for readability, performance, and accessibility.

Responsibilities: delivering consistent typography across the platform.

## Animations

Animations should be subtle and purposeful.

Responsibilities: enhancing feedback, transitions, and motion without distracting from content.

Animations must degrade gracefully and never interfere with usability.

## Syntax Highlighting

Syntax highlighting is required for code examples and learning materials.

Responsibilities: rendering code blocks clearly and consistently.

Approved highlighting tools should be lightweight and compatible with the static content rendering model.

## Charts

Charts are used only where they provide clear insight into progress or metrics.

Responsibilities: visualizing progress data, activity summaries, and performance indicators.

Charts should be implemented with a minimal, approved charting library and should remain accessible.

---

# Database

MySQL is the selected database for Frontend Academy because it offers mature support for relational data, wide hosting compatibility, and strong migration tooling.

## Why MySQL

Performance: MySQL provides reliable query performance for the expected workload of structured course content, user progress, and reporting data.

Reliability: MySQL is a proven production database with established backup, replication, and recovery practices.

Hosting support: MySQL is universally available across shared, managed, and cloud hosting providers, making deployment easier.

Migration support: Laravel’s migration system integrates naturally with MySQL and simplifies schema versioning.

Scalability: MySQL can scale vertically and can be horizontally partitioned or replicated later if required.

Future upgrade path: if the project outgrows MySQL’s initial configuration, the data model can be migrated to a compatible relational engine or a managed MySQL service.

---

# Development Environment

A consistent local development environment reduces onboarding time and prevents environment-specific issues.

## Recommended tools

- Laragon: preferred on Windows for PHP, MySQL, and web server management.
- Composer: for PHP dependency management.
- Node.js: runtime for frontend build tools.
- NPM: package manager for JavaScript dependencies.
- Git: version control across all development.
- VS Code: recommended editor for code, documentation, and extension support.
- PHPStorm (optional): acceptable when preferred by team members, but not required.

## Recommended versions

- PHP: 8.3 or newer within supported PHP lifecycle.
- Composer: latest stable Composer 2 release.
- Node.js: Active LTS version recommended by the Node.js project.
- NPM: compatible with the selected Node.js version.
- MySQL: version supported by the target deployment environment, ideally MySQL 8.x.

Developers should use the same major tool versions whenever possible to avoid environment drift.

---

# Package Management Policy

Dependencies should be introduced deliberately and only when they clearly improve maintainability, reduce duplicated effort, or solve a real problem in a way that native solutions cannot.

## When a new package may be installed

- When the functionality is not already available in Laravel, Bootstrap, or the existing approved frontend stack.
- When the package clearly improves developer productivity and reduces custom implementation risk.
- When the package is necessary to support a required product feature.

## Approval requirements

- New packages must be reviewed by a team member or maintainer before installation.
- The review should confirm that the package fits the project’s architecture and does not duplicate existing functionality.

## Evaluation criteria

- Security: audit the package for known vulnerabilities.
- Maintenance: check release frequency, issue responsiveness, and current version stability.
- Community adoption: prefer packages with active communities and well-known usage.
- Long-term support: prefer packages that are compatible with Laravel and actively maintained.

## Security considerations

- Prefer trusted sources and packages with clear provenance.
- Avoid packages that require unsafe configuration or broad permissions.

## Maintenance considerations

- Prefer packages that are compatible with the current Laravel version and support the project’s lifecycle.
- Avoid packages that are abandoned, difficult to configure, or likely to be replaced by core framework improvements.

## Community adoption

- Formalize package selection around widely adopted tools that are already common in the Laravel community.
- Avoid edge-case libraries unless they provide unique, essential functionality.

## Long-term support

- Adopt packages that are likely to remain supported for the duration of the feature’s lifecycle.
- Plan package updates during regular maintenance windows rather than ad hoc.

---

# Approved Packages

These packages are the officially approved tools for the project today. Their use should be limited to the purposes described here.

## Bootstrap

Approved for responsive layout and base UI patterns. It is the foundation for forms, grids, and component styling.

## Alpine.js

Approved for light interaction patterns and progressive enhancement. Use it for controlled UI interactions that do not require a full frontend framework.

## Prism.js

Approved for syntax highlighting of code examples and lesson content. It provides lightweight, readable code rendering for the learning experience.

## Chart.js

Approved for simple, accessible charting and progress visualization. It supports the platform’s need for data-driven dashboards without excessive complexity.

## SweetAlert2

Approved for modal alerts, confirmations, and user-facing messaging when a polished dialog experience is needed.

## SortableJS

Approved for drag-and-drop interactions in administrative or content management interfaces.

## Laravel Breeze

Approved for authentication scaffolding that aligns with Laravel conventions and provides a lightweight base for login and registration flows.

## Intervention Image (future)

Approved as a future option for image manipulation if the platform requires server-side image resizing or cropping.

## Laravel Excel (future)

Approved as a future option for import and export workflows involving tabular data.

Each approved package was selected because it fits the application’s architectural model, is well-maintained, and does not introduce unnecessary complexity.

---

# Prohibited Packages

The following package categories should not be introduced into the project without explicit justification and approval.

## Heavy UI Frameworks

Large single-page application frameworks such as React, Angular, or Vue are prohibited unless the project evolves to require a dedicated frontend application.

Why: they add significant complexity, increase bundle size, and conflict with the current server-rendered Blade + Alpine approach.

## Duplicate Libraries

Do not install libraries that duplicate existing capabilities provided by Laravel, Bootstrap, Alpine, or approved packages.

Why: duplicates increase maintenance burden and may create inconsistent behavior.

## Abandoned Packages

Do not introduce packages with no recent releases, stale issue response, or unresolved security vulnerabilities.

Why: abandoned packages become liabilities and can block future upgrades.

## Unmaintained Packages

Avoid packages that are not actively maintained or that have poor community support.

Why: unmaintained dependencies create long-term risk and reduce the predictability of upgrades.

---

# Version Policy

The project follows semantic versioning principles and maintains strict dependency locking.

## Semantic Versioning

- Major upgrades may introduce breaking changes and require a deliberate migration plan.
- Minor upgrades add features and improvements in a backward-compatible way.
- Patch updates provide bug fixes and security patches without changing public APIs.

## Major upgrades

Major dependency upgrades should be treated as project events. They require planning, compatibility checks, and regression testing before deployment.

## Minor upgrades

Minor upgrades may be adopted during regular maintenance cycles if the package is known to be compatible with the current stack.

## Patch updates

Patch updates should be applied promptly for security or bug fixes. They may be included as part of routine dependency maintenance.

## Dependency locking

The project relies on lockfiles to preserve exact dependency versions.

- `composer.lock` must be committed and updated only through approved Composer commands.
- `package-lock.json` must be committed and updated only through approved NPM commands.

Lockfiles ensure reproducible builds, stable deployments, and predictable collaboration across environments.

---

# Dependency Update Strategy

Dependencies should be updated in a controlled manner.

## When dependencies should be updated

- During scheduled maintenance windows.
- When security advisories require immediate remediation.
- When a feature requires a dependency update.

## Testing requirements

- All dependency updates must pass automated tests and manual regression checks for affected areas.
- Frontend build and smoke tests should be run after updating tooling or UI libraries.

## Rollback strategy

- Keep the previous lockfile version available in source control.
- If an update introduces regressions, revert the lockfile and package manifest changes immediately.

## Compatibility checks

- Review changelogs and upgrade guides for major and minor dependency changes.
- Confirm that new package versions are compatible with PHP, Laravel, and existing project conventions.

---

# Coding Environment Standards

The project defines environment standards so all contributors work with compatible tools.

## Recommended platform

- Operating System: Windows with Laragon for local development, or macOS/Linux if preferred.
- PHP Version: 8.3+.
- Composer Version: latest stable Composer 2.
- Node Version: current Active LTS release.
- NPM Version: bundled with Node.js and compatible with the selected version.
- Database Version: MySQL 8.x where available.
- Browser Support: modern evergreen browsers.

Developers should avoid mixing major tool versions without explicit coordination.

---

# Browser Support Policy

Frontend Academy officially supports modern evergreen browsers and a limited set of legacy browser scenarios.

## Supported browsers

- Chrome (current major release)
- Firefox (current major release)
- Safari (current major release)
- Edge (current major release)

## Minimum supported versions

The project supports the latest two major versions of each evergreen browser wherever practical.

## Graceful degradation

The platform should remain functional without advanced browser features. UI may render without advanced animations or enhanced controls, but core content, navigation, and forms must remain accessible.

Feature detection and progressive enhancement should be used instead of browser sniffing.

---

# Performance Considerations

Lightweight technologies were selected to keep the platform fast, responsive, and easy to maintain.

## Bundle size

Minimize frontend bundle size by using only approved packages and by avoiding heavy UI frameworks.

## Rendering speed

Server-side rendering with Blade ensures pages load with meaningful HTML and have a strong baseline performance profile.

## Caching

Cache decisions should be data-driven and introduced only when profiling demonstrates benefit.

## Build process

Vite is the build tool to deliver optimized assets with minimal developer friction.

## Asset optimization

Production builds should include minified CSS and JavaScript, tree-shaken dependencies, and optimized static assets.

---

# Security Considerations

Security is an essential part of package selection and dependency management.

## Composer audit

Run Composer audit checks regularly and address reported vulnerabilities in PHP dependencies.

## NPM audit

Run NPM audit checks before accepting new JavaScript packages and periodically as part of maintenance.

## Dependency vulnerabilities

Avoid dependencies with known vulnerabilities unless there is a patch plan and upgrade path.

## Trusted package sources

Install packages from trusted, well-known repositories and avoid unverified or obscure sources.

## Version pinning

Pin dependency versions in lockfiles. This reduces the risk of unexpected version changes in CI, development, or production deployments.

---

# Future Technology Roadmap

These technologies may be introduced later when the project’s requirements justify them.

## Redis

Use when session management, caching, or queue performance require a dedicated in-memory store.

## Laravel Horizon

Use when queue management requires visibility and operational monitoring.

## Laravel Reverb

Use if native event-driven workflows are adopted and a more opinionated event broadcasting solution is needed.

## PWA

Use when progressive web app support is required for offline capability and mobile-friendly engagement.

## REST API

Use when external integrations, mobile apps, or third-party consumers require programmatic access.

## Nuxt

Use only if the platform evolves to require a separate frontend application with SSR/SPA behavior beyond the current Blade-based experience.

## Mobile App

Use when a native or hybrid mobile experience is required by the product roadmap.

## Cloud Storage

Use when user-generated media or asset storage requires scalable object storage beyond the local filesystem.

## Meilisearch

Use when search requirements demand fast, developer-friendly indexing and filtering beyond database-driven search.

## Elasticsearch

Use when complex search queries, analytics, or full-text ranking require a more powerful search engine.

## Queue Workers

Use when asynchronous processing is needed for notifications, imports, exports, or long-running tasks.

## Docker

Use when development or deployment consistency requires containerized environment standardization.

## CI/CD

Use to automate builds, tests, and deployment pipelines when the project reaches a stable release cadence.

Each future technology should be adopted only when a clear product requirement and operational readiness justify it.

---

# Technology Decision Records

This section documents important technology decisions and their rationale.

## Decision: Laravel 12 as the primary framework

Reason: Laravel 12 provides a stable, well-supported application foundation with a mature ecosystem, strong conventions, and built-in developer tooling.

Benefits: predictable architecture, rapid development, and broad community support.

Trade-offs: requires adherence to Laravel conventions and limits the project to a PHP-centric backend.

Alternatives considered: Symfony, Slim, Lumen.

## Decision: Blade for view rendering

Reason: Blade enables server-side rendering with reusable components and minimal frontend complexity.

Benefits: maintainable templates, secure escaping, and integration with Laravel’s view features.

Trade-offs: not a reactive frontend framework.

Alternatives considered: Vue, React, Twig.

## Decision: Bootstrap 5 for UI styling

Reason: Bootstrap gives a stable responsive framework that accelerates layout and component development.

Benefits: fast design iteration, accessibility support, and consistent UI building blocks.

Trade-offs: requires careful customization to avoid a generic appearance.

Alternatives considered: Tailwind CSS, Bulma, custom CSS.

## Decision: Alpine.js for client interactions

Reason: Alpine.js offers lightweight enhancement for interactive UI patterns without a full SPA.

Benefits: easy integration with Blade, minimal bundle impact, and straightforward usage.

Trade-offs: not suitable for large client-side state management.

Alternatives considered: Vue, React, Stimulus.

## Decision: MySQL for the database

Reason: MySQL matches the project’s data model, hosting expectations, and migration tooling.

Benefits: broad compatibility, predictable performance, and a familiar operational model.

Trade-offs: it does not offer the same advanced indexing features as PostgreSQL.

Alternatives considered: PostgreSQL, SQLite, MariaDB.

---

# AI Development Rules

AI agents must operate within the existing technology stack and established conventions.

- AI agents must never replace existing technologies without explicit approval.
- AI agents must never install new packages without approval from a human maintainer.
- AI agents must always reuse existing libraries and approved packages before introducing new dependencies.
- AI agents must prefer Laravel-native solutions when equivalent functionality exists in the framework.
- AI agents must avoid unnecessary dependencies and minimize technical debt.

---

# Revision History

| Version | Date | Author | Notes |
|---|---|---|---|
| 1.0 | 2026-07-03 | Frontend Academy Team | Initial technology stack reference for Frontend Academy. |
