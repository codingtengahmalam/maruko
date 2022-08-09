# Maruko
Simple service to load posts and author data from database 

### Context 
This repo used for demo how to set up CI/CD Go using heroku 

### Database 
There are 2 simple table from database, here is the structure. 

```sql
-- Posts table
create table posts
(
    id          bigserial
        primary key,
    author_id   bigint
        constraint fk_posts_author
            references authors,
    title       text,
    description text,
    content     text,
    date        timestamp with time zone
);

-- authors table
create table authors
(
    id         bigserial
        primary key,
    first_name text,
    last_name  text,
    email      text,
    birth_date timestamp with time zone,
    added      timestamp with time zone
);
```
