``` mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: Selain lataa sivun samalla tavalla palvelimelta
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML dokumentti
    deactivate server

    Note right of browser: HTLM-koodi ohjaa hakemaan css-tiedoston
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: css tyylitiedosto
    deactivate server

    Note right of browser: HTLM-koodi ohjaa hakemaan JavaScript -tiedoston
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: JavaScript tiedosto
    deactivate server

    Note right of browser: Selaimen JavaScript-koodi hakee muistiinpanot 
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON raakadata
    deactivate server
    Note right of browser: Muistiinpanot renderöidään selaimessa
```
