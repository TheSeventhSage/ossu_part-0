sequenceDiagram
participant user
participant browser
participant server

    user->>browser: Inputs note and click
    browser->>user: Saves and renders new list item on page

    browser->server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server->browser: Responds with request status
    deactivate server

    Note right of browser: Browser stays on same page. No more requests.
