# Milestone 2

This document should be completed and submitted during **Unit 6** of this course. You **must** check off all completed tasks in this document in order to receive credit for your work.

## Checklist

This unit, be sure to complete all tasks listed below. To complete a task, place an `x` between the brackets.

- [ ] In `planning/wireframes.md`: add wireframes for at least three pages in your web app.
  - [ ] Include a list of pages in your app
- [ ] In `planning/entity_relationship_diagram.md`: add the entity relationship diagram you developed for your database.
  - [ ] Your entity relationship diagram should include the tables in your database.
- [ ] Prepare your three-minute pitch presentation, to be presented during Unit 7 (the next unit).
  - [ ] You do **not** need to submit any materials in advance of your pitch.
- [X] In this document, complete all three questions in the **Reflection** section below

## Reflection

### 1. What went well during this unit?

Our group successfully identified all the core entities needed for QuestTwyst and mapped out a complete list of tables, including users, stories, genres, passages, choices, reading_progress, and path_history. We were able to break down complex relationships, such as the many-to-many connection between stories and genres

### 2. What were some challenges your group faced in this unit?

One of the biggest challenges was understanding cardinality, especially cases where two separate relationships existed between the same two tables, like the "owning" and "destination" relationships between passages and choices. 

### 3. What additional support will you need in upcoming units as you continue to work on your final project?

As we move forward, we will need more guidance on translating our finalized ERD into actual PostgreSQL table schemas and writing the corresponding migrations. We would also benefit from support on building out the Express API routes that handle the branching logic between passages and choices, as well as best practices for structuring our React components for the story reader interface. 
