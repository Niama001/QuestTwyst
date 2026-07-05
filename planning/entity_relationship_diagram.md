# Entity Relationship Diagram
Reference the Creating an Entity Relationship Diagram final project guide in the course portal for more information about how to complete this deliverable.


## Create the List of Tables
- users
- stories
- genres
- story_genres (join table)
- passages
- choices
- reading_progress
- path_history


## Add the Entity Relationship Diagram
### users
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| name | text | user's display name |
| email | text | user's email, unique |
| password_hash | text | hashed password for login |
| created_at | timestamp | account creation date |

### stories
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| title | text | title of the story |
| description | text | short summary of the story |
| creator_id | integer | foreign key → users.id (one-to-many: a user can create many stories) |
| created_at | timestamp | date story was created |

### genres
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| name | text | genre name (e.g., mystery, sci-fi, comedy) |

### story_genres (join table — many-to-many)
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| story_id | integer | foreign key → stories.id |
| genre_id | integer | foreign key → genres.id |

### passages
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| story_id | integer | foreign key → stories.id (one-to-many: a story has many passages) |
| content | text | the passage text the reader sees |
| is_ending | boolean | true if this passage ends the story |

### choices
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| passage_id | integer | foreign key → passages.id (one-to-many: a passage has two choices) |
| choice_text | text | label for the choice (e.g., "Ask the driver") |
| next_passage_id | integer | foreign key → passages.id (which passage this choice leads to) |

### reading_progress
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| user_id | integer | foreign key → users.id |
| story_id | integer | foreign key → stories.id |
| current_passage_id | integer | foreign key → passages.id (where the reader left off) |

### path_history
| Column Name | Type | Description |
|-------------|------|-------------|
| id | integer | primary key |
| user_id | integer | foreign key → users.id |
| story_id | integer | foreign key → stories.id |
| passage_id | integer | foreign key → passages.id |
| choice_id | integer | foreign key → choices.id |
| timestamp | timestamp | when this choice was made |
