# [WhatjobAI] Phase 2 - Data engineering & storage

## Designing Relational Database (SQL)

| Table name | Primary Key | Key Columns | Purpose |
|----------|----------|----------|----------|
| Companies   | company_id   | name, industry, size |To store unique employers  |
| jobs  | job_id   | title, company_id, data_posted, description   |To store specific role details  |
| Skills | Skill_id   | skill_name, category | To store all tech skills required for jobs|
