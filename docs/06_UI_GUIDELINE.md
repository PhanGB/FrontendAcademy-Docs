# UI Guideline

## Purpose

This document defines the official UI design system for Frontend Academy. It exists to ensure that every experience across the platform feels coherent, purposeful, and easy to learn from. A unified UI guideline is essential because educational products depend on clarity, trust, and predictability more than novelty.

A strong UI system supports:

- Consistency: Users should recognize patterns instantly across courses, dashboards, forms, and administrative views.
- Usability: Interfaces should reduce friction and help learners focus on content rather than on figuring out the interface itself.
- Accessibility: Learners, educators, and administrators with different abilities must be able to use the platform comfortably and effectively.
- Maintainability: Shared rules reduce duplicated design decisions and make future updates easier to implement safely.
- Scalability: The system must remain coherent as new lessons, features, and modules are introduced over time.
- AI-friendly interface development: Designers, developers, and AI coding agents should be able to build interfaces that align with the same standards without inventing conflicting patterns.

This guideline is the official reference for product design decisions, implementation planning, and UI review.

---

# Design Philosophy

Frontend Academy should feel calm, intelligent, and focused on learning. The design philosophy is grounded in clarity, confidence, and educational effectiveness.

The platform should embody:

- Simplicity: Interfaces should be direct and free from unnecessary ornamentation.
- Clean Interface: Every visual element should serve a purpose and support comprehension.
- Content First: Educational content must remain the primary focus, with UI supporting rather than competing with it.
- Learning-focused Experience: The interface should guide users through progression, feedback, and practice without distractions.
- Minimal Distraction: Unnecessary motion, clutter, and competing visual signals should be avoided.
- Responsive by Default: The experience should adapt gracefully to mobile, tablet, desktop, and large-screen environments.
- Accessibility First: Inclusive design is not an afterthought; it should shape decisions from the beginning.
- Consistency: Repeated patterns should feel familiar, predictable, and dependable.
- Modern Educational Platform: The visual language should feel contemporary, constructive, and credible for a professional learning environment.

These principles should influence every interface, from a lesson page to an administrative dashboard. The user should always feel that the system is helping them learn, not obstructing them.

---

# Design Principles

## Visual Hierarchy

Visual hierarchy should guide attention in a deliberate order. Important actions, headings, and key information should be emphasized through scale, placement, contrast, and grouping. The interface should make it obvious what matters most at a glance.

## Whitespace

Whitespace is a structural design tool. It helps organize content, improve readability, and reduce cognitive load. Ample spacing should be used around blocks of text, form fields, cards, and sections to create calm and visual clarity.

## Alignment

All interface elements should align systematically. Alignment creates order, strengthens credibility, and makes interfaces easier to scan. Content blocks, text, form controls, and navigation should follow consistent alignment rules.

## Contrast

Contrast should be used to separate important elements, highlight actions, and ensure readability. It should be applied carefully to preserve accessibility while maintaining balance and visual elegance.

## Consistency

Consistency is a core product value. Repeated patterns should behave similarly across the application. Users should not need to relearn interaction rules when moving between sections.

## Feedback

Interfaces should provide visible feedback for user actions. Loading states, success states, validation messages, hover states, focus states, and confirmation feedback should be clear and timely.

## Recognition over Recall

The interface should minimize memory load. Users should be able to identify actions and options easily rather than relying on memorized paths or hidden conventions.

## Progressive Disclosure

Complex information should be revealed gradually. Interfaces should surface essential content first and reserve advanced or optional information for later interaction when appropriate.

## Affordance

Each interactive element should suggest its purpose clearly. Buttons, links, toggles, inputs, and navigation items should look and behave as users expect.

---

# Color System

The color system should communicate clarity, trust, and energy without becoming visually noisy. The palette should support education, progress, and calm focus.

## Primary

Primary colors should be used for the most important actions, key accents, and primary brand signals. They should appear sparingly and intentionally so they retain impact.

## Secondary

Secondary colors should support the primary color without competing with it. They are useful for less dominant emphasis, supporting states, or secondary actions.

## Success

Success colors should indicate completed states, positive outcomes, and favorable feedback. They should be used for achievements, correct answers, and completed progress.

## Warning

Warning colors should communicate caution, pending attention, or important but non-critical information. They should not be used excessively.

## Danger

Danger colors should signal destructive actions, errors, or critical warnings. They should be reserved for high-severity issues and confirmation flows.

## Info

Info colors should communicate helpful context, neutral updates, or informative messages. They should support discoverability and guidance without implying urgency.

## Neutral

Neutral tones create calm structure and balance. They are essential for surfaces, borders, text, and supporting UI elements.

## Background

Background colors should provide visual comfort and maintain strong contrast with content. They should support readability and reduce visual fatigue.

## Surface

Surface tones distinguish cards, panels, modals, navigation containers, and other elevated UI patterns from the page background.

## Border

Border colors should create separation without being visually heavy. They should help define structure, grouped content, and input boundaries.

## Text

Text colors should prioritize readability and contrast. The system should ensure that body text remains legible in both light and dark themes.

## Muted Text

Muted text should be used for secondary information such as captions, helper text, metadata, and less prominent labels.

## Dark Mode Considerations

Dark mode should preserve the same hierarchy, meaning, and contrast as the light theme. Color roles should remain consistent while adjusting luminance and contrast for comfortable viewing.

## Usage Guidelines

- Use color to reinforce meaning, not as the only indicator of meaning.
- Avoid overusing saturated colors.
- Maintain strong contrast for text and interactive controls.
- Keep color choices consistent across components and states.
- Do not rely on color alone for essential instructions or validation.

---

# Typography

Typography is one of the most important elements in an educational interface. Good typography increases readability, supports learning, and strengthens trust in the platform.

## Primary Font

The primary font should be modern, highly legible, and suitable for long-form reading. It should feel polished but approachable, avoiding excessive personality.

## Fallback Fonts

Fallback fonts should be reliable system-based options that preserve readability if the primary font is unavailable. Fallbacks should maintain a similar tone and spacing behavior.

## Heading Hierarchy

Headings should create a clear content structure. The hierarchy should be visually distinct and semantically meaningful. Heading levels should guide scanning and reinforce curriculum organization.

## Paragraphs

Paragraph text should be easy to read and comfortable to scan. Lines should not be overly long, and blocks should be visually separated by spacing.

## Line Height

Line height should support readability, especially for long-form content. Educational content benefits from generous spacing between lines to reduce visual fatigue.

## Letter Spacing

Letter spacing should be subtle and purposeful. It should support legibility without creating an artificial or overly decorative appearance.

## Readability

Readability should remain the highest priority. Text should be comfortable to read across screen sizes and device types.

## Maximum Content Width

Long reading content should be constrained to a comfortable maximum width to avoid lines that feel too long or visually tiring.

## Learning Content Typography

Lesson content should use typography that supports focus and clarity. Key concept blocks, examples, equations, and callouts should remain visually distinct while fitting the overall system.

## Code Typography

Code text should be visually distinct from body text and should preserve readability in both inline and multiline contexts. Code typography should remain consistent across lesson content, examples, and documentation surfaces.

## Blockquote Typography

Blockquotes should be visually differentiated without overpowering the surrounding content. They should be used sparingly for emphasis or guidance.

## Tables

Tables should use clear typography and strong structure so data remains easy to read and compare.

## Lists

Lists should be easy to scan. Bullet and numbered list styling should be consistent and appropriate to the content type.

---

# Spacing System

The spacing system should be consistent, rational, and easy to apply. Spacing is a foundational part of layout clarity and interface rhythm.

## Margins

Margins should create separation between content blocks, sections, and major layout regions. They should be used consistently to avoid clutter and preserve alignment.

## Padding

Padding should be used to create comfortable internal spacing within components, cards, forms, and containers. It should support legibility and make interaction areas feel generous.

## Section Spacing

Section spacing should define the distance between major content areas on a page. It should be generous enough to create visual breathing room without disconnecting related content.

## Component Spacing

Spacing within components should be evenly applied and aligned with the overall scale. Buttons, inputs, labels, icons, and cards should have predictable spacing relationships.

## Grid Spacing

Grid spacing should be consistent across layouts to maintain alignment and reduce visual unevenness. Content should align to a clear rhythm rather than appear arbitrarily placed.

## Content Width

Content width should be controlled so reading experiences remain comfortable. Text blocks should not stretch too wide on large screens.

## Container Width

Containers should create a balanced reading experience while preserving enough room for supporting content and navigation.

## Vertical Rhythm

Vertical rhythm is essential for long-form educational pages. Headings, paragraphs, lists, and component blocks should align to a consistent spacing rhythm.

---

# Layout System

The layout system should support predictable page composition across the full product. It should balance content focus, navigation, and action surfaces.

## Container

Containers should provide a stable horizontal frame for content. They should organize page structure without creating excessive visual constraint.

## Grid

The grid should support alignment, responsive adaptation, and thoughtful grouping of content. The layout should feel structured rather than improvised.

## Sidebar

Sidebars should support navigation, course structure, or supplementary context. They should remain clear and unobtrusive while providing useful access to related actions.

## Top Navigation

Top navigation should be simple, stable, and easy to understand. It should support primary pathways without overwhelming the page.

## Footer

The footer should provide secondary navigation, legal or support information, and platform context. It should not compete with the primary content experience.

## Learning Layout

Learning layouts should prioritize lessons, examples, progress indicators, and related resources. The interface should make it easy to move through educational material.

## Dashboard Layout

Dashboard layouts should emphasize overview, progress, and quick action. They should present information in a structured way that promotes orientation and decision-making.

## Admin Layout

Admin layouts should support operational clarity and efficiency. They should provide structured access to management features while remaining visually aligned with the broader product system.

## Authentication Layout

Authentication layouts should remain simple, focused, and low-friction. The experience should reduce uncertainty and feel trustworthy.

## Responsive Breakpoints

The system should define clear responsive behavior for small, medium, large, and very large screens. Layout changes should preserve hierarchy and usability at each breakpoint.

## Content Width

Content width should adapt gracefully across screen sizes while preserving comfortable reading and interaction areas.

## Maximum Width

Maximum content width should prevent text from stretching too far on wide screens and should preserve a balanced composition.

---

# Responsive Design

Responsive design should be treated as a default requirement, not an optional enhancement. The platform must work comfortably across mobile, tablet, desktop, and large-display contexts.

## Mobile First

The experience should begin with mobile constraints in mind. Core functionality and content should remain available and understandable on smaller screens before expanding to larger layouts.

## Tablet

Tablet layouts should balance touch-friendly spacing and efficient use of screen real estate. Navigation and content should remain easy to browse without feeling cramped.

## Desktop

Desktop layouts should make use of more horizontal space while preserving clarity and focus. Multi-column arrangements should remain consistent and readable.

## Large Desktop

Large desktop layouts should avoid excessive stretching and should maintain strong content boundaries. The system should use space thoughtfully rather than filling it unnecessarily.

## Landscape

Landscape layouts should preserve usability for wider screens without sacrificing content structure or touch ergonomics.

## Touch Devices

Touch targets should be large enough to be comfortably tapped. Interactive elements should provide enough spacing to reduce accidental input.

## Orientation

Orientation changes should not break the experience. Layout adjustments should preserve continuity and meaning.

## Responsive Navigation

Navigation should adapt to available space without hiding essential paths from users. The system should maintain clarity across collapsed and expanded navigation states.

## Responsive Tables

Tables should remain usable on smaller screens through careful structure and readable behavior. Content should not become impossible to interpret when space is limited.

## Responsive Cards

Cards should adapt gracefully to smaller screens while keeping actions, headings, and supporting content legible.

## Responsive Forms

Forms should remain easy to complete on any device. Inputs, labels, help text, and validation messaging should scale appropriately for smaller screens.

---

# Component Design Guidelines

All components should be designed as reusable parts of a coherent interface system. They should be understandable, adaptable, and accessible.

## Buttons

Purpose: Encourage important actions and support task completion.

Visual hierarchy: Primary actions should be visually stronger than secondary actions.

Usage: Use buttons for explicit actions and avoid using them for navigation when links are more appropriate.

Interaction: Buttons should provide visible hover, focus, and active states.

Accessibility: Labels must be clear, and button groups should be structured logically.

Best practices: Keep labels concise and action-oriented.

Common mistakes: Overloading a page with too many primary actions or using buttons where links would be clearer.

## Cards

Purpose: Group related information into visually distinct containers.

Visual hierarchy: Cards should organize content while keeping emphasis on the most important information.

Usage: Use cards for lessons, courses, progress summaries, project highlights, and feature groupings.

Interaction: Cards may support hover, focus, and click behaviors when appropriate.

Accessibility: Ensure that card content remains readable and that interactive cards are keyboard accessible.

Best practices: Avoid overcrowding cards with too many competing elements.

Common mistakes: Using cards as a generic layout container without clear purpose.

## Alerts

Purpose: Communicate important information, warnings, or feedback.

Visual hierarchy: Alerts should be clearly distinguishable from surrounding content.

Usage: Use alerts for validation messages, important updates, or required attention.

Interaction: Alerts should not interrupt unexpectedly and should allow users to understand the message quickly.

Accessibility: Use appropriate roles and ensure content remains readable and clearly associated with the relevant message.

Best practices: Keep alert copy concise and actionable.

Common mistakes: Using alerts for routine information that would be better handled elsewhere.

## Badges

Purpose: Show status, labels, categories, or achievements quickly.

Visual hierarchy: Badges should be compact and visually secondary to main content.

Usage: Use badges for progress states, labels, difficulty, or completion status.

Interaction: Badges are generally non-interactive unless used as filters or tags.

Accessibility: Ensure badges are not the sole means of conveying meaning.

Best practices: Keep badge labels short and meaningful.

Common mistakes: Overusing badges so they lose distinction and meaning.

## Breadcrumbs

Purpose: Show the user’s location within a structured experience.

Visual hierarchy: Breadcrumbs should remain secondary to the main content while clearly supporting orientation.

Usage: Use breadcrumbs for layered content, course navigation, and lesson sequences.

Interaction: Breadcrumb items should remain simple and predictable.

Accessibility: Make breadcrumb trails keyboard accessible and semantically clear.

Best practices: Keep the path short and meaningful.

Common mistakes: Using breadcrumbs where a simple page title or navigation would suffice.

## Pagination

Purpose: Divide large sets of content into manageable pages.

Visual hierarchy: Pagination should be clear and unobtrusive.

Usage: Use pagination for resource lists, course indexes, and search results when large content sets are involved.

Interaction: Active and current page states should be obvious.

Accessibility: Ensure page controls are labeled and keyboard accessible.

Best practices: Use simple, clear labels and avoid excessive page numbers when possible.

Common mistakes: Overcomplicating pagination with too many options or unclear current-state indicators.

## Forms

Purpose: Collect information clearly and efficiently.

Visual hierarchy: Forms should guide the user through each field logically, with labels and structure that reduce ambiguity.

Usage: Use forms for account setup, profile updates, search, quiz responses, and content submission.

Interaction: Forms should provide clear validation, progress indicators, and feedback.

Accessibility: Every field should have an associated label, clear instructions, and a clear validation story.

Best practices: Group related fields and avoid unnecessary complexity.

Common mistakes: Creating dense or ambiguous forms that force the user to guess what is required.

## Inputs

Purpose: Capture user text and data.

Visual hierarchy: Inputs should be easy to scan and clearly associated with labels.

Usage: Use inputs for short textual responses and simple data entry.

Interaction: Inputs should show focus states and validation behavior clearly.

Accessibility: Input fields should include labels, purpose, and guidance for assistive technologies.

Best practices: Keep input labels concise and context-specific.

Common mistakes: Using placeholder text as a replacement for labels.

## Textarea

Purpose: Gather longer-form free text.

Visual hierarchy: Textareas should be visually distinct from simple input fields.

Usage: Use textareas for notes, reflections, descriptions, and longer responses.

Interaction: Support resizing behavior appropriately and ensure text remains readable.

Accessibility: Provide labels, instructions, and sufficient contrast.

Best practices: Keep text areas easy to understand and sized appropriately.

Common mistakes: Using textareas where a shorter input would be more appropriate.

## Checkbox

Purpose: Allow selection of multiple options.

Visual hierarchy: Checkboxes should be visually clear and aligned with their labels.

Usage: Use checkboxes for multi-select choices, consent, and optional preferences.

Interaction: Selection states should be obvious and consistent.

Accessibility: Ensure cues are understandable without relying on color alone.

Best practices: Keep labels short and unambiguous.

Common mistakes: Mixing checkbox behavior with single-choice semantics.

## Radio

Purpose: Allow a single choice from a defined set.

Visual hierarchy: Radio options should be grouped clearly and visually balanced.

Usage: Use radios for mutually exclusive choice sets.

Interaction: Selected and unselected states should be easy to distinguish.

Accessibility: Group related radios with clear labels and instructions.

Best practices: Avoid overly long option sets when possible.

Common mistakes: Using radios where checkboxes would be more appropriate.

## Switch

Purpose: Toggle between two states quickly.

Visual hierarchy: Switches should feel lightweight and obvious.

Usage: Use switches for preferences and settings that can be enabled or disabled.

Interaction: Switching should feel immediate and provide feedback.

Accessibility: Provide clear labels and state descriptions.

Best practices: Use switches sparingly and only for simple binary choices.

Common mistakes: Using switches for actions that require confirmation or more context.

## Dropdown

Purpose: Present a compact set of choices.

Visual hierarchy: Dropdowns should be visually compact but clearly interactive.

Usage: Use dropdowns for lists of options where space is limited.

Interaction: The selected state and available options should be easy to interpret.

Accessibility: Dropdown labels and available choices should be clear and keyboard operable.

Best practices: Keep option lists manageable and ordered logically.

Common mistakes: Overusing dropdowns for simple yes/no or short choices that would be better as radio buttons.

## Accordion

Purpose: Hide and reveal related content progressively.

Visual hierarchy: Accordion items should remain simple and clearly distinguished.

Usage: Use accordions for optional details, FAQs, and grouped content sections.

Interaction: Expansion states should be obvious.

Accessibility: Ensure each trigger is keyboard accessible and clearly labeled.

Best practices: Keep content sections concise and meaningful.

Common mistakes: Using accordions for essential information that users should not miss.

## Tabs

Purpose: Organize related content into clearly separated views.

Visual hierarchy: Tabs should create a clear sense of sectioning and navigation.

Usage: Use tabs when switching between related views or categories.

Interaction: The active tab should be immediately recognizable.

Accessibility: Tabs should be keyboard navigable and correctly labeled.

Best practices: Keep tab labels short and descriptive.

Common mistakes: Using too many tabs or placing unrelated content in the same tab group.

## Modal

Purpose: Focus attention on a specific task, message, or interaction.

Visual hierarchy: Modals should visually anchor the user’s attention without overwhelming the experience.

Usage: Use modals for important confirmations, short forms, or task-specific interactions.

Interaction: Modal behavior should be predictable and easy to dismiss.

Accessibility: Modal content should be keyboard accessible and properly announced to assistive technologies.

Best practices: Keep modals focused and avoid overusing them.

Common mistakes: Using modals for routine content that can be presented directly on the page.

## Toast

Purpose: Deliver lightweight feedback after an action.

Visual hierarchy: Toasts should be brief and unobtrusive.

Usage: Use toasts for success, warning, or informational feedback after an interaction.

Interaction: Toasts should appear temporarily and be easy to dismiss.

Accessibility: Toasts should not rely solely on color and should be announced appropriately.

Best practices: Keep messages short and specific.

Common mistakes: Using toasts for critical or long-form information.

## Tooltip

Purpose: Provide brief contextual help.

Visual hierarchy: Tooltips should be concise and appear close to the related element.

Usage: Use tooltips for small clarifications or additional instruction.

Interaction: Tooltips should appear on demand and not block workflow.

Accessibility: Avoid using tooltips as the only way to convey essential information.

Best practices: Keep tooltip content short and timely.

Common mistakes: Using tooltips for content that should be visible and persistent.

## Progress Bar

Purpose: Show task completion or progress.

Visual hierarchy: Progress bars should communicate current status clearly and simply.

Usage: Use progress bars for course completion, form steps, uploads, and assessments.

Interaction: Progress should update predictably and be understandable at a glance.

Accessibility: Progress indicators should include appropriate labels and state meaning.

Best practices: Use progress bars when progress is meaningful and visible.

Common mistakes: Using a progress bar for a process that does not have clear stages or meaningful progress.

## Skeleton Loader

Purpose: Show placeholder structure during content loading.

Visual hierarchy: Skeletons should reflect the expected layout without demanding attention.

Usage: Use skeletons for cards, dashboards, lesson content, and profile sections.

Interaction: Skeletons should feel calm and not appear as actual content.

Accessibility: Avoid making loading states visually confusing or overly animated.

Best practices: Use skeletons only when content load times are noticeable.

Common mistakes: Using skeletons for trivial or nearly instant interactions.

## Empty State

Purpose: Guide users when there is no content yet.

Visual hierarchy: Empty states should be helpful, calm, and encouraging.

Usage: Use empty states for courses with no lessons, empty projects, or no recent activity.

Interaction: Empty states should offer clear next steps.

Accessibility: Text should be readable and actionable.

Best practices: Pair empty states with a clear path forward.

Common mistakes: Leaving users with a blank screen and no guidance.

## Loading Indicator

Purpose: Communicate that work is in progress.

Visual hierarchy: Loading indicators should be unobtrusive and understandable.

Usage: Use them for network operations, page transitions, and data fetching.

Interaction: Loading states should not create uncertainty about whether the system is working.

Accessibility: Loading indicators should not block or confuse assistive technology users.

Best practices: Keep loading indicators brief and informative.

Common mistakes: Using indefinite loading without a clear fallback or timeout approach.

## Tables

Purpose: Present structured data clearly.

Visual hierarchy: Tables should be easy to scan and should distinguish headers, rows, and actions.

Usage: Use tables for progress reports, user lists, content management, and analytics summaries.

Interaction: Table actions should be clearly associated with the relevant rows.

Accessibility: Use clear headers, logical ordering, and accessible navigation patterns.

Best practices: Keep tables focused and avoid unnecessary visual complexity.

Common mistakes: Displaying dense data without structure or readable row spacing.

## Search Bar

Purpose: Help users find relevant content quickly.

Visual hierarchy: Search input should be easy to locate and visually simple.

Usage: Use search bars across course catalogs, lessons, and project discovery flows.

Interaction: Search should provide immediate clarity and feedback.

Accessibility: Ensure search inputs have labels and keyboard accessibility.

Best practices: Keep the search experience lightweight and predictable.

Common mistakes: Hiding search or making it visually inconsistent with the rest of the interface.

## Sidebar

Purpose: Provide navigation, context, and quick access to related areas.

Visual hierarchy: Sidebars should support scanning without overpowering the page.

Usage: Use sidebars for course structure, dashboard navigation, and administrative tools.

Interaction: Sidebar items should clearly communicate their state and purpose.

Accessibility: Sidebar navigation should be keyboard navigable and clearly structured.

Best practices: Keep the sidebar focused and avoid excessive nesting.

Common mistakes: Overloading the sidebar with unrelated actions and confusing labels.

## Navigation

Purpose: Help users move through the platform efficiently.

Visual hierarchy: Navigation should be simple, stable, and easy to scan.

Usage: Use navigation for primary sections, course paths, and user account actions.

Interaction: Active states and current position should be obvious.

Accessibility: Navigation should remain understandable with keyboard and screen reader support.

Best practices: Keep navigation consistent and logically grouped.

Common mistakes: Creating multiple competing navigation patterns within the same experience.

## Footer

Purpose: Provide supporting links and platform context.

Visual hierarchy: Footers should support but not compete with the core experience.

Usage: Use footers for policies, support information, and secondary paths.

Interaction: Footer links should remain straightforward and predictable.

Accessibility: Footer content should be structured and readable.

Best practices: Keep footer content concise and purposeful.

Common mistakes: Turning the footer into an overloaded repository of unrelated links.

## Profile Card

Purpose: Present a user’s identity, key status, or account context.

Visual hierarchy: Profile cards should emphasize the person or account while keeping supporting context readable.

Usage: Use profile cards in dashboards, learner summaries, and account sections.

Interaction: Profile cards may support actions such as editing or viewing details.

Accessibility: Ensure the card remains clear for assistive technologies and keyboard navigation.

Best practices: Keep the card focused and avoid too much secondary information.

Common mistakes: Overloading profile cards with unrelated information.

## Course Card

Purpose: Introduce a course in a scannable and motivating way.

Visual hierarchy: Course cards should highlight title, level, and key progress indicators.

Usage: Use course cards in catalogs, learning paths, and recommendation areas.

Interaction: Course cards should support clear selection and preview states.

Accessibility: Use meaningful labels and avoid relying on visual cues alone.

Best practices: Keep course information concise and easy to compare.

Common mistakes: Making course cards visually identical even when their purpose differs.

## Lesson Card

Purpose: Summarize an individual lesson or learning unit.

Visual hierarchy: Lesson cards should clearly communicate lesson status and progression.

Usage: Use lesson cards inside course pages and lesson lists.

Interaction: Lesson cards should indicate completion, current position, or action availability.

Accessibility: Ensure cards remain readable and navigable without losing context.

Best practices: Keep lesson metadata concise and useful.

Common mistakes: Using large cards for simple content that could be represented more compactly.

## Quiz Card

Purpose: Introduce an assessment experience clearly.

Visual hierarchy: Quiz cards should present readiness and expected effort clearly.

Usage: Use quiz cards for assessment entry points and review surfaces.

Interaction: Quiz cards should convey whether an assessment is active, completed, or locked.

Accessibility: Validation and instructions should remain understandable to all users.

Best practices: Use clear labels for difficulty, duration, or prerequisites.

Common mistakes: Making quiz states ambiguous or visually inconsistent.

## Project Card

Purpose: Highlight practical learning work or portfolio-oriented projects.

Visual hierarchy: Project cards should emphasize outcomes and project purpose.

Usage: Use project cards in learning libraries, portfolios, and milestone views.

Interaction: Project cards should support exploration and selection.

Accessibility: Keep descriptions simple and actionable.

Best practices: Use concise project summaries and clear progress information where relevant.

Common mistakes: Overloading project cards with overly technical or vague descriptions.

## Statistics Card

Purpose: Present metrics or summary information elegantly.

Visual hierarchy: Statistics cards should highlight the most important number or trend clearly.

Usage: Use them within dashboards, progress views, and admin summaries.

Interaction: Statistics cards should remain static unless additional detail is offered.

Accessibility: Numerical values and labels should be clearly associated.

Best practices: Keep metrics understandable and avoid unnecessary decorative emphasis.

Common mistakes: Displaying too many metrics in a single card so the core message is lost.

## Dashboard Widgets

Purpose: Surface useful or time-sensitive information in a structured way.

Visual hierarchy: Widgets should organize content without competing with primary page actions.

Usage: Use widgets for recent activity, progress summaries, reminders, and system updates.

Interaction: Widget actions should be clear and consistent.

Accessibility: Widgets should be readable, navigable, and not overly dense.

Best practices: Keep widget content relevant and update it meaningfully.

Common mistakes: Turning widgets into cluttered collections of unrelated information.

---

# Iconography

Icons should support comprehension without becoming decorative noise. They should be simple, consistent, and easy to recognize.

## Icon style

Icons should be clear, modern, and minimal. They should fit the overall visual tone of the platform and remain legible at small sizes.

## Icon size

Icons should use a consistent size system so they align well with text and controls.

## Consistency

Icons should be used consistently across the product. If a symbol represents a concept in one area, it should represent the same concept elsewhere.

## Meaning

Each icon should communicate a clear meaning. Icons should not be used merely for decoration.

## Usage rules

Icons should support the user’s understanding of actions, sections, and states. They should not replace text where meaning could be ambiguous.

## Accessibility

Icons should not be relied upon as the sole indicator of meaning. Where needed, they should be paired with text or labels and used in a way that remains understandable to assistive technology.

---

# Illustrations

Illustrations should reinforce the educational tone of the platform and make complex or abstract concepts easier to understand.

## Educational illustrations

Illustrations should be clear, friendly, and instructive. They should support learning rather than distract from it.

## Empty states

Empty-state illustrations should feel encouraging and helpful. They should guide users toward the next step without feeling bleak or confusing.

## Onboarding

Onboarding illustrations should be approachable and informative. They should make the platform feel accessible from the start.

## Achievements

Achievement visuals should feel rewarding and motivating while remaining consistent with the overall design language.

## Certificates

Certificate and completion visuals should feel formal, credible, and polished without becoming overly ornate.

---

# Images

Images should be used thoughtfully to support content, motivation, and learning. They should never overwhelm the experience or distract from the educational purpose.

## Aspect Ratio

Images should use consistent aspect ratios that preserve composition and fit the layout gracefully.

## Optimization

Images should be optimized for performance and clarity. Large or unnecessary assets should be avoided.

## Lazy Loading

Images should be loaded efficiently, especially on content-heavy pages or lower-bandwidth connections.

## Alt Text

Images must include meaningful alternative text when they communicate information. Decorative images should be handled appropriately.

## Responsive Images

Images should adapt to different screen sizes without losing quality or breaking the layout.

## Compression

Images should be compressed carefully to balance quality and performance.

## Accessibility

Images should support accessibility through appropriate descriptions and meaningful use. They should not be the only carrier of important information.

---

# Code Presentation

Source code should be presented in a way that is clear, readable, and easy to scan. The goal is to support learning and technical understanding without creating visual friction.

## Syntax Highlighting

Code should use clear and consistent syntax highlighting that improves readability without being overly dramatic.

## Code Blocks

Code blocks should be visually separate from surrounding text and should allow the content to breathe. They should not feel cramped or difficult to read.

## Inline Code

Inline code should be used sparingly for technical terms, file names, or short snippets. It should remain visually distinct but not intrusive.

## Copy Button

Where appropriate, code examples may include a copy action to improve usability, especially for learners practicing implementation.

## Line Numbers

Line numbers may be used in longer code examples to improve navigation and reference.

## Code Themes

Code themes should remain readable and consistent with the overall system. They should not compete with the surrounding interface.

## Overflow Handling

Long code content should be displayed in a way that preserves readability and avoids layout breakage. Horizontal scrolling or wrapping should be handled thoughtfully depending on the context.

---

# Learning Content Design

The visual structure of lessons should support comprehension, progression, and retention. The layout should make educational content feel organized and approachable.

## Lesson Header

Each lesson should have a clear, purposeful header that establishes the topic and context.

## Objectives

Lesson objectives should be explicit and easy to scan. They help learners understand what they are expected to gain.

## Theory

Theory sections should be presented clearly and in a readable structure. They should not overwhelm learners with dense blocks of text.

## Examples

Examples should stand out visually and appear close to the related explanation. They should be easy to compare with the surrounding concept.

## Tips

Tips should be visually differentiated and should feel supportive rather than distracting.

## Warnings

Warnings should be distinct and easy to notice without causing unnecessary anxiety.

## Exercises

Exercises should be visually structured to encourage participation and clarity.

## Quiz

Quiz experiences should be simple, focused, and easy to complete. Feedback should be immediate and constructive.

## Summary

Lesson summaries should help learners consolidate key points and prepare for the next step.

## Next Lesson

The next lesson should be clearly signposted so that progression feels guided and motivating.

## Estimated Reading Time

Estimated reading time, where present, should help learners plan their study session and manage expectations.

## Difficulty Indicator

Difficulty should be communicated clearly and consistently, especially for learners choosing a path through the curriculum.

---

# Dashboard Design

Dashboards should help learners and administrators orient quickly and act efficiently. The design should make progress, priorities, and next steps obvious.

## Statistics

Statistics should be presented in a scannable, meaningful way. They should emphasize relevance rather than simply displaying raw data.

## Progress Cards

Progress cards should help users understand where they are and what remains. They should feel motivating without becoming overly gamified.

## Charts

Charts should be readable, minimal, and useful. They should support understanding rather than visual decoration.

## Quick Actions

Quick actions should be prominent and clearly grouped. They should help users move efficiently to common tasks.

## Recent Activity

Recent activity should be presented in a compact and informative format. It should remain useful without becoming noisy.

## Notifications

Notifications should be short, helpful, and easy to act on.

## Widgets

Widgets should be structured and consistent, with clear labels and meaningful information hierarchy.

---

# Animation Guidelines

Animation should feel intentional, subtle, and supportive. It should help users understand change without becoming distracting.

## Micro Interactions

Micro interactions should provide feedback for actions such as hover, focus, selection, and completion.

## Hover Effects

Hover effects should be subtle and useful. They should reinforce affordance without becoming excessive.

## Transitions

Transitions should be smooth and consistent. They should support orientation and perceived continuity.

## Loading Animations

Loading animations should be calm and unobtrusive. They should indicate activity without creating unnecessary visual noise.

## Page Transitions

Page transitions should be gentle and purposeful. The interface should not feel abrupt or disorienting.

## Reduced Motion Support

Animations should respect reduced-motion preferences and remain usable without motion.

## Performance Considerations

Animations should be lightweight and efficient. They should not degrade the experience on lower-powered devices.

---

# Accessibility Guidelines

Accessibility is a product requirement, not a secondary concern. The interface should be usable by as many people as possible, including those using assistive technologies or alternative input methods.

## WCAG Principles

The interface should align with the core principles of WCAG: perceptible, operable, understandable, and robust.

## Keyboard Navigation

All interactive elements should be reachable and operable through keyboard navigation.

## Focus States

Focus states should be visible, consistent, and easy to follow.

## Screen Readers

Content should be structured semantically so screen readers can interpret it correctly.

## Contrast Ratio

Text and important UI elements should maintain sufficient contrast to remain readable.

## ARIA

ARIA should be used only when semantic HTML alone is insufficient. It should support clarity rather than add unnecessary complexity.

## Semantic HTML

The interface should rely on semantic structure wherever possible. This improves accessibility and maintainability.

## Reduced Motion

Interfaces should support reduced-motion preferences and avoid relying on motion for essential meaning.

## Accessible Forms

Forms should clearly communicate labels, instructions, errors, and required states.

## Accessible Tables

Tables should include clear headers and understandable structure.

## Accessible Navigation

Navigation should remain understandable and usable with keyboard and assistive technologies.

## Accessible Modals

Modals should be focus-trapped, dismissible, and appropriately announced to assistive technology.

---

# Dark Mode Strategy

Dark mode should be supported as a future enhancement rather than a one-off visual variant. It should preserve the same hierarchy, clarity, and usability as the light theme.

## Color Tokens

The design system should define color roles that can be reused across light and dark themes.

## Contrast

Contrast must remain strong in dark mode so that content remains readable and clear.

## Images

Images and illustrations should remain legible and appropriate in dark contexts.

## Icons

Icons should retain clarity and recognizability in dark mode.

## Code Blocks

Code blocks should remain readable and visually consistent in both themes.

## Charts

Charts should preserve meaning and legibility in dark mode.

## Consistency

Dark mode should not introduce a different design language. It should feel like the same system adapted for different lighting conditions.

---

# Performance Guidelines

Performance should be treated as part of the UI experience. Interfaces that feel slow or visually heavy can undermine trust and learning flow.

## Image Optimization

Images should be optimized for the web and sized appropriately for their display context.

## Lazy Loading

Lazy loading should be used for non-critical media and offscreen content.

## Deferred Loading

Non-essential UI content should be loaded only when needed.

## Responsive Assets

Assets should be appropriate for the device and viewport in use.

## Minimal Animations

Animations should be limited to meaningful transitions and feedback.

## Rendering Performance

The interface should remain smooth and responsive, especially on lower-powered devices.

---

# UI Consistency Rules

Consistency is maintained through shared rules and disciplined reuse. The design system should be applied across all surfaces of the product.

## Spacing

Spacing should follow a consistent scale throughout the interface.

## Colors

Color usage should remain aligned with the defined system and semantic meaning.

## Typography

Typography should be applied consistently across headings, body text, labels, and content blocks.

## Component Reuse

Components should be reused rather than recreated for each new feature.

## Naming

UI patterns, states, and variants should use clear and consistent naming.

## Layout

Layout patterns should remain recognizable across pages and modules.

## Interactions

Interactive behavior should feel predictable and coherent across the product.

## Feedback

Feedback states should be standardized and easy to understand.

---

# Common UI Mistakes

The following mistakes should be avoided because they reduce usability, clarity, or maintainability.

- Overusing color to communicate meaning without supporting text or structure.
- Creating inconsistent spacing that makes layouts feel uneven or accidental.
- Using too many competing visual styles in the same screen.
- Making buttons, links, and form controls visually ambiguous.
- Hiding important actions in low-contrast or hard-to-find places.
- Using excessive animation that distracts from learning.
- Building one-off components that duplicate existing patterns.
- Neglecting keyboard and screen-reader support.
- Making content too dense for comfortable reading.
- Introducing visual novelty that weakens clarity and product coherence.

---

# AI Development Rules

AI agents must follow this design system.

AI agents must reuse existing UI components rather than introducing parallel patterns.

AI agents must never invent new visual styles without approval from the product and design direction.

AI agents must prioritize accessibility in all interface work.

AI agents must prioritize consistency over creativity when the two conflict.

AI agents must preserve the educational focus of the interface and avoid adding unnecessary visual complexity.

---

# Revision History

| Version | Date | Description | Author |
| --- | --- | --- | --- |
| 1.0 | 2026-07-04 | Initial UI guideline and design system documentation. | Frontend Academy Team |
