# BOOKS


## Description
Web app for searching and storing information about your favourite books.

## Entity definition
    
- "ID":
- "Title": string,
- "Author": string,
- "Description": string,
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
- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.
