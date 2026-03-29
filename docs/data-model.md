# Data Organization Overview

## Main Idea

This repository keeps the overall data organization visible, but only at the level needed to understand the product.

The important point is that the system is organized around a few core domains:

- course information
- user feedback and moderation
- AI-oriented retrieval support

## Course Layer

The first layer is the course layer.

It holds the course-centered information that the site uses for listing, filtering, detail pages, timetable support, and AI-assisted discovery.

What matters publicly is not each individual field, but the role of this layer:

- it represents courses as stable records
- it carries the summarized understanding of user evaluations
- it acts as the base for search and recommendation

## Feedback Layer

The second layer is the feedback layer.

This is where user-submitted reviews, corrections, and supplements flow through moderation before influencing the public-facing course information.

From a product perspective, this layer exists to keep the visible course information maintainable over time.

## Retrieval Layer

The third layer is the retrieval layer.

This layer supports AI-assisted discovery and question answering by making the processed course knowledge searchable in a semantic way.

The exact structure is not the important part for public documentation.

The important part is the role it plays:

- connecting processed course knowledge to AI retrieval
- improving relevance during course-related questions
- supporting a retrieval-augmented answer flow

## Why This Matters

The system is not organized around raw comments alone.

It is organized around a course knowledge layer built from many user evaluations, plus moderation and retrieval layers around it.

That is the part worth understanding from the public repository.
