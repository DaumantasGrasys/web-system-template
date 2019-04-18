# BOOKS


## Description
Web app for searching and storing information about your favourite books.

## Entity definition
    
- "ID":
- "Title": string,
- "Author": string,
- "Description": string,
- "CoverLink": string,
- "PublishDate": ISO 8601 format date string,
- "Volume": int
- "Content": string (base64 encoded content)

## API definition
### Get "Hostname/Book/{ID}"

- Returns 200 (OK) specific Book by ID
- Returns 404 (NotFound) if book doesn't exist.
- Returns 401 (NotAuthorized) if you are not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

### Get "Hostname/book/{Name}"

- Returns 200 (OK) specific Book by Name
- Returns 404 (NotFound) if book doesn't exist.
- Returns 401 (NotAuthorized) if you are not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution

### Get "Hostname/books?author=author&items=5"

- Returns 200 (OK) returns all books or all books by specific author if it is specified or specified amount of items.
- Returns 200 with empty list if no books matches author.
- Returns 401 (NotAuthorized) if you are not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

### Delete "Hostname/Book/{ID}"

- Returns 200 (OK) if deleted
- Returns 404 (NotFound) if book not found.
- Returns 401 (NotAuthorized) user not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.


### Update "Hostname/book/{id}" with book object

- Returns 200 (OK) if updated
- Returns 404 (NotFound) if book not found.
- Returns 401 (NotAuthorized) user not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

### Post "Hostname/book/{id}" with book object

- Returns 200 (OK) if Inserted
- Returns 409 (NotFound) if same book already inserted.
- Returns 401 (NotAuthorized) user not logged in.
- Returns 500 (Internal Server Error) if Error happens on execution.

## UI definition
### https://wireframe.cc/cR9lpA
