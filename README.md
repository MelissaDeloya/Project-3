# Project 3
Netflix 

## How many movie titles are there in the database? (movies only, not tv shows)

SELECT count(*)
FROM "netflix_titles_info"
WHERE type='Movie';

## When was the most recent batch of tv shows and/or movies added to the database?

select max(date(date_added))
FROM "netflix_titles_info";

### List all the movies and tv shows in alphabetical order.

SELECT title
FROM "netflix_titles_info"
ORDER BY title asc;

## Who was the Director the for move The Starling?

SELECT director
FROM "netflix_titles_info" titles
LEFT JOIN "netflix_people" people
ON titles.show_id=people.show_id
WHERE titles.title='The Starling'

## What is the oldest movie in the database and what year was it made?

SELECT title, release_year
FROM "netflix_titles_info"
WHERE type='Movie'
ORDER BY release_year asc
LIMIT 1;
