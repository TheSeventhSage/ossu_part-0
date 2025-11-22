sequenceDiagram
participant browser
participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server->browser: Single HTML DOC.
    deactivate server

    Note left of browser: Browser loads one HTML file and <br> all linked assets (CSS/JS). After JS initializes, <br> it controls all rendering and routing, with <br> no further HTML requests to the server.
