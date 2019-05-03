# BOOKS


## Description
Web app for searching and storing information about your favourite books.

## Entity definition
    
- "ID" string (exact 12),
- "Title": string (0,255),
- "Author": string(0, 255),
- "Description": string (0,8000),
- "CoverLink": string (0, 1000),
- "PublishDate": ISO 8601 format date string (1,11),

## API definition
### Get "https://www.googleapis.com/books/v1/volumes?q=programming&maxResults=30"

- Returns 200 (OK) List of books
- Returns 401 (NotAuthorized) if you are not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

### Get "https://www.googleapis.com/books/v1/mylibrary/bookshelves/0/volumes"

- Returns 200 (OK) list of your favourite books.
- Returns 404 (NotFound) if book doesn't exist.
- Returns 401 (NotAuthorized) if you are not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution

### Get "https://www.googleapis.com/auth/books"

- Returns 200 (OK) returns code needed to get auth token.
- Returns 401 (NotAuthorized) if you are not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

### post "https://www.googleapis.com/oauth2/v4/token" with authentification code object


- Returns 200 (OK) if body is correct
- Returns 401 (NotAuthorized) user not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.


### post "https://www.googleapis.com/books/v1/mylibrary/bookshelves/0/addVolume?volumeId={id}" 
- Returns 200 (OK) if inserted
- Returns 404 (NotFound) if book not found.
- Returns 401 (NotAuthorized) user not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

### Post "https://www.googleapis.com/books/v1/mylibrary/bookshelves/0/removeVolume?volumeId={id}" 

- Returns 200 (OK) if deleted
- Returns 409 (NotFound) if book not found on your library.
- Returns 401 (NotAuthorized) user not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

## UI definition
### https://wireframe.cc/cR9lpA
