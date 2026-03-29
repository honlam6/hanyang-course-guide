# Data Processing Note

## Main Idea

The key point is not raw collection itself.

The more important part is turning scattered review signals into a stable course-level knowledge layer.

In practice, the workflow can be understood like this:

1. collect course information and user review signals from relevant Everytime pages
2. read multiple reviews together at the course level
3. use AI to consolidate them into consistent course summaries
4. turn those summaries into a form that can support search, recommendation, and QA
5. reuse that processed layer across the frontend and AI flows

The result is not a direct dump of source text. It is a transformed course representation.

## Why AI Summarization Matters

Raw review text is uneven, noisy, and repetitive.

AI summarization makes it possible to move from scattered opinions to a clearer course-level understanding.

That matters because the product needs a stable information layer that can support:

- readable course presentation
- better retrieval quality
- more consistent AI answers

## About Model Integration

This project integrates Google Gemini API in the AI layer.

At a high level, the model is used in two places:

- summarizing course reviews into a more coherent knowledge layer
- supporting retrieval-augmented answers when users ask course-selection questions

The exact implementation can vary, but the overall design principle is the same: AI first organizes the information, then helps answer against that organized layer.
