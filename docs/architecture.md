# Architecture

## Product Scope

This repository is the web version of a Hanyang University course review, timetable, and AI-assisted course selection system.

The public codebase mainly shows:

- the web frontend
- the admin workflow
- the public API layer
- the AI-assisted user experience

## Core Product Flows

The site is built around several user-facing flows.

### 1. Course Discovery

Users can browse courses, search by key information, apply filters, and inspect course-level summaries.

### 2. Timetable Experience

Users can add courses into a timetable and check for schedule conflicts.

### 3. Feedback And Moderation

Users can submit reviews or corrections, and admins can review and publish updates through the moderation workflow.

### 4. AI-Assisted Q&A

Users can ask course-selection questions, and the system responds against a processed course knowledge layer instead of only raw text.

## AI Layer

The AI layer is built around two connected ideas.

First, course evaluations are aggregated into course-level summaries.

Second, those summaries are reused in retrieval-augmented answering so that the assistant can respond with better context.

The model integration is centered on Google Gemini API.

## Public Documentation Boundary

This repository explains the product logic and the overall technical direction.

It does not try to document every internal implementation choice in detail.

For public understanding, the main takeaway is:

- the product is driven by AI-processed course knowledge rather than raw comments alone
- the web experience, moderation flow, timetable, and AI assistant all depend on that knowledge layer
