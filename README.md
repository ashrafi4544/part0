codes mermaid 0.4,0.5,0.6
Codes that I used to make exercise diagram 0.4 for Mermaid


sequenceDiagram
    participant browser
    participant server
    
    browser->>server:HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    note over browser:the browser will send the user input to the server
    server-->>browser:do a new HTTP GET request to /notes
    deactivate server
    note over server:The server responds with HTTP status code 302
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser:HTML-code
    deactivate server
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser:file main.css
    deactivate server
    note over browser:browser starts executing js-code that requests json data from server
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser:file main.js
    deactivate server
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser:[{content: "A", date: "2024-06-02T16:59:34.861Z"}, {content: "", date: "2024-06-02T17:00:58.599Z"},…]
    deactivate server
    note over browser:browser executes the event handler that renders notes to display


Codes that I used to make exercise diagram 0.5 for Mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser:HTML document
    deactivate server
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser:main.css file
    deactivate server
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser:spa.js file
    deactivate server
    note over browser:the browser start executing the javascript code that fetches the json from the server
    browser->>server:HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser:[{content: "testing", date: "2024-06-03T19:10:04.031Z"},…]
    deactivate server
    note over browser:browser executes the event handler 


Codes that I used to make exercise diagram 0.6 for Mermaid


sequenceDiagram
    participant browser
    participant server

    browser->>server:https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    note over browser:Content-Type:application/json <br/> {content: "LLH", date: "2024-06-04T06:49:44.487Z"}
    server-->>browser:{"message":"note created"}
    note over browser:browser executes the event handler 