# homeAssistent_tools – Radio (lokal im Browser)

Dieses Repo enthält eine kleine, lokale HTML-Seite für Home Assistant, um Radio-Streams (mp3/aac/m3u8) direkt im Browser (z.B. Android) abzuspielen.

## Dateien

- `www/radio.html`  
  Einfache UI: Dropdown (Sendernamen), Play/Stop, `<audio>` Player.

- `www/radios.json`  
  Senderliste als JSON-Mapping: `"Sendername": "Stream-URL"`.

## Installation in Home Assistant (HA OS)

1. Kopiere die Dateien nach deinem Home Assistant `config/www/` Verzeichnis:
   - `config/www/radio.html`
   - `config/www/radios.json`

   Hinweis: In Home Assistant entspricht `config/www/` der URL `/local/`.

2. Öffne die Seite nach dem Login in Home Assistant:

   `/local/radio.html`

   Beispiel (je nach Host/IP):
   - `http://homeassistant.local:8123/local/radio.html`

## Sender hinzufügen / ändern

Bearbeite `www/radios.json` (im HA z.B. mit dem File editor Add-on oder Studio Code Server) und lade die Seite neu.

Beispiel:
```json
{
  "Oldie Antenne": "https://s1-webradio.oldie-antenne.de/oldie-antenne/stream/aacp"
}
```

## Hinweise

- Autoplay ist meist gesperrt; Play startet per Button-Klick, das ist ok.
- Wenn ein bestimmter m3u8/HLS Stream nicht im Browser läuft, kann eine HLS-Fallback-Lösung nötig sein.
