# Mr. QB

## Introduction

Mr. QB is a light-weight SQL query builder. It can be used with any Go SQL driver that take a string query.

## Features

- Select

## Installation

```
go get github.com/nickmro/mrqb
```

## Usage

```go
import "github.com/nickmro/mrqb"

stmt := mrqb.Select(
		"film.film_id",
		"film.title",
		"film.description",
		"film.release_year",
		"film.language_id",
		"film.original_language_id",
		"film.rental_duration",
		"film.rental_rate",
		"film.length",
		"film.replacement_cost",
		"film.rating",
		"film.special_features",
		"film.last_update",
	).
		From("film").
    Where("film.film_id = %v", 1)

query, args := stmt.Build()

row := db.QueryRow(query, args...)
```

## Todo

- Insert
- Update
- Delete
- Tests
- Documentation
- PostgreSQL
