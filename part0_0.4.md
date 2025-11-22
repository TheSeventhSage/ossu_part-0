sequenceDiagram
participant browser
participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes on click button 'Save'
    activate server
    server-->>browser: Asks browser to perform a new HTTP GET to /notes
    deactivate server

    Note right of server: Executes code at location new_notes

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server->browser: HTML Doc
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    Note left of browser: Browser parses css file <br> and applies ruleset

    browser -> server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server -> browser: the js file
    deactivate server

    Note left of browser: Executes js code that makes next request to fetch a JSON from the server.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Learnt mermaid fresher", "date": "2025-11-21" }, ... ]
    deactivate server

    Note left of browser: Runs th callback fn. that renders that notes list to the page.
