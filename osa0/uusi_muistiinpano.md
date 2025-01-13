``` mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: selain lähettää lomakkeelle syötetyn datan palvelimelle
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note left of server: palvelin lähettää uudelleenohjauspyynnön selaimelle
    server-->>browser: /exampleapp/notes
    deactivate server

    note right of browser: selain hakee uudelleen sivun /exampleapp/notes sisällön
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML dokumentti
    deactivate server

    Note right of browser: HTML-koodi ohjaa selaimen hakemaan uudestaan css -tiedoston
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: css tyylitiedosto
    deactivate server

    Note right of browser: HTML-koodi ohjaa selaimen hakemaan JavaScript -tiedoston
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: JavaScript tiedosto
    deactivate server

    note right of browser: JavaScript-koodi tekee pyynnön osoitteeseen /exampleapp/data.json
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    Note right of browser: selain suorittaa tapahtumankäsittelijän, joka renderöi muistiinpanot ruudulle käyttäen DOM-apia
    server-->>browser: [... , {"content": "Tämä on uusin muistiinpano", "date":"2025-1-1"}]
    deactivate server
    

```
 https://mermaid.js.org/syntax/flowchart.html#beta-flowcharts
