``` mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: .
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note left of server: .
    server-->>browser: _
    deactivate server

```
