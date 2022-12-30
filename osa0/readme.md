0.4: uusi muistiinpano
selain->palvelin: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
palvelin-->selain: staus code 302
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
palvelin-->selain: HTML-koodi
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
palvelin-->selain: main.css
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
palvelin-->selain: main.js

note over selain:
selain alkaa suorittaa js-koodia
joka pyytää JSON-datan palvelimelta
end note

selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
palvelin-->selain: [{ content: "HTML on helppoa", date: "2019-01-01" }, ...]

note over selain:
selain suorittaa tapahtumankäsittelijän
joka renderöi uuden rivin näytölle
end note

--------------------------------------------------
0.5: Single Page App
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
palvelin-->selain: HTML-koodi
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
palvelin-->selain: main.css
selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
palvelin-->selain: spa.js

note over selain:
selain alkaa suorittaa js-koodia
joka pyytää JSON-datan palvelimelta
end note

selain->palvelin: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
palvelin-->selain: [{ content: "HTML on helppoa", date: "2019-01-01" }, ...]

note over selain:
selain suorittaa tapahtumankäsittelijän
joka renderöi uuden rivin näytölle
end note

-------------------------------------------------
0.6: Uusi muistiinpano
selain->palvelin: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
palvelin-->selain: status code 201

note over selain:
Status 201 ilmoittaa, 
että pyyntö on suoritettu menestyksekkäästi
 ja uusi "note" on luotu ennen palautteen
 lähettämistä. Spa.js ohjaa uuden "noten" renderöintiä näytölle. Selain suorittaa tahtumankäsittelijän, 
joka renderöi uuden rivin näytölle
end note
