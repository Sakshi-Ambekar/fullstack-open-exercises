```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types a note and clicks "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa with JSON data
    activate server
    server-->>browser: 201 Created (Confirmation)
    deactivate server

    Note right of browser: JavaScript updates the page dynamically without reloading

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json (to get updated notes)
    activate server
    server-->>browser: Updated notes including the new one
    deactivate server

    Note right of browser: JavaScript updates the UI to display the new note instantly
