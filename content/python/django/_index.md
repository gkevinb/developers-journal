+++
title = "Django"
date = 2021-04-30T11:24:10+02:00
weight = 10
draft = true
+++

## Database

makemigrations and migrate, migrate the models into the database structure. When making fundamental changes (primary key changes, not null, etc) to the model, you have to delete the old migrations, and then do the makemigrations and migrate.

