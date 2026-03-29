# Hanyang University Course Review System

[中文](./README.md) | [한국어](./README.ko.md)

A course review, timetable, and AI-assisted course selection website for Hanyang University students.

- Live demo: <https://hanyang.eu.cc>
- GitHub metadata: [docs/github-metadata.md](./docs/github-metadata.md)
- Architecture and site logic: [docs/architecture.md](./docs/architecture.md)
- Data processing note: [docs/data-source.md](./docs/data-source.md)
- Data organization overview: [docs/data-model.md](./docs/data-model.md)
- Contributing: [CONTRIBUTING.md](./CONTRIBUTING.md)
- Security: [SECURITY.md](./SECURITY.md)

## Preview

### Desktop

![Desktop Demo](./docs/images/homepage-desktop.png)

### Mobile

![Mobile Demo](./docs/images/homepage-mobile.png)

## Overview

The project currently includes:

- course browsing, search, and filtering
- course detail pages
- timetable management
- class-time conflict detection
- user review and correction submission
- admin review workflow
- AI course assistant

## Core Idea

The point of the project is not to mirror raw Everytime content.

The more important part is turning scattered review signals into stable course-level profiles.

The general approach is:

1. collect course information and user reviews from relevant Everytime pages
2. interpret multiple reviews together at the course level
3. use AI to produce unified course summaries and conclusions
4. use those course profiles for search, recommendation, QA, and frontend presentation

So what users see is not just raw review text. It is a processed and consolidated course layer.

If you have another way to collect or process the data, that is also fine.

## AI Summarization And Retrieval-Augmented QA

This is the most important layer of the project.

AI is not only used for chat. It is first used to summarize reviews, and then used again in the QA flow.

At a high level:

- multiple user reviews are summarized into course-level knowledge
- those summaries are organized into retrievable units
- user questions trigger retrieval before answer generation
- the model integration is built around Google Gemini API

So the AI layer is closer to a retrieval-augmented course intelligence system than a standalone chatbot.

## Timetable And Conflict Detection

The website also includes a timetable feature.

Users can add courses into a timetable, and the system automatically detects schedule conflicts. The timetable view can also be exported as an image.

## Data Note

This public repository keeps the product logic, the public web stack, and the integration-level explanation.

The data organization and processing approach are described at a high level, without expanding every core implementation detail.

See:

- [docs/data-source.md](./docs/data-source.md)
- [docs/data-model.md](./docs/data-model.md)
- [docs/architecture.md](./docs/architecture.md)

## Local Setup

```bash
npm install
cp .env.example .env
npm run dev
```

Default URLs:

- Frontend: `http://localhost:3000/`
- Admin: `http://localhost:3000/admin`

Database setup:

- Run [`supabase_setup.sql`](./supabase_setup.sql) in Supabase SQL Editor

## Adapting It To Other Korean Universities

The current project is built around Hanyang University, but the overall method is not limited to one school.

To adapt it to another Korean university, you would usually need to redesign the school naming, campus model, course taxonomy, data source, and AI summarization strategy.

A more accurate positioning is:

- current product: Hanyang University course review system
- methodology: adaptable to other Korean universities
