# Crime Show Quiz: "DOSCHAUHER, EIN MORD!" 🕵️‍♂️🩸

Ein interaktives Echtzeit-Umfragewerkzeug (ähnlich wie Mentimeter) speziell für Live-Krimishows. Die Anwendung läuft komplett serverlos (statisches HTML/JS/CSS), wird auf **GitHub Pages** gehostet und nutzt **Supabase** als kostenlose Echtzeit-Datenbank.

Deine Live-Links:
- **Zuschauer-Voting (Voter)**: [https://tobiasjschreiber.github.io/Crime-Quiz/](https://tobiasjschreiber.github.io/Crime-Quiz/)
- **Moderator-Panel (Admin)**: [https://tobiasjschreiber.github.io/Crime-Quiz/?role=admin](https://tobiasjschreiber.github.io/Crime-Quiz/?role=admin)
- **Beamer-Leinwand (Presenter)**: [https://tobiasjschreiber.github.io/Crime-Quiz/?role=presenter](https://tobiasjschreiber.github.io/Crime-Quiz/?role=presenter)

---

## 🚀 Features

- **3 Ansichten in einer App**:
  - **Zuschauer (Voter)**: Für Smartphones optimiert, zeigt die aktive Frage und ermöglicht das Abstimmen per Klick. Unterstützt eingebaute Silhouetten oder hochgeladene Fotos.
  - **Präsentation (Presenter)**: Für Beamer/Großbildschirm. Zeigt das Live-Diagramm der Stimmen, die Gesamtstimmanzahl und den dynamischen QR-Code.
  - **Moderator (Admin)**: Steuerung der aktiven Frage, Ein-/Ausblenden der Live-Ergebnisse, Zurücksetzen der Stimmen und Fragen-Editor.
- **Echtzeit-Synchronisierung**: Stimmen und Fragenwechsel werden über WebSockets (Supabase Realtime) in Millisekunden an alle Geräte übertragen.
- **Lokale Stimmsperre**: Verhindert doppeltes Abstimmen pro Frage.
- **Krimi-Retro-Design**: Stilvolles Vibe mit Papiertexturen, Schreibmaschinenschrift und markanten Schlagschatten.
- **Custom Fonts & Farben**:
  - **Schriftarten**: Verwendung von **TT Modernoir** (via Adobe Fonts) für Titel und Überschriften sowie **Segoe UI** (mit Inter als Fallback) für Benutzeroberflächen.
  - **Farbpalette**: Ein kontrastreiches Retro-Farbschema basierend auf Orange-Rot (`#E9421F`), warmem Dunkelbraun/Schwarz (`#191311`) und sanftem Creme (`#F7F5EB`).

## 📖 Bedienung während der Show

1. **Fragen vorbereiten (Admin)**: 
   Öffne [https://tobiasjschreiber.github.io/Crime-Quiz/?role=admin](https://tobiasjschreiber.github.io/Crime-Quiz/?role=admin) und erstelle deine Fragen. Du kannst eigene Bilder hochladen (werden automatisch auf 500x500 Pixel skaliert und in der DB gespeichert).
2. **Beamer einrichten (Presenter)**: 
   Öffne [https://tobiasjschreiber.github.io/Crime-Quiz/?role=presenter](https://tobiasjschreiber.github.io/Crime-Quiz/?role=presenter) auf dem Beamer-Bildschirm.
3. **Abstimmen (Voter)**: 
   Die Zuschauer scannen den QR-Code auf der Leinwand und gelangen auf [https://tobiasjschreiber.github.io/Crime-Quiz/](https://tobiasjschreiber.github.io/Crime-Quiz/).
4. **Das Spiel leiten**:
   Aktiviere die Fragen nacheinander im Admin-Panel und schalte die Ergebnisse über **Ergebnisse anzeigen** live frei.

## 🎨 Anpassung von Schriftarten & Farben

### Adobe Fonts (TT Modernoir) einbinden
Damit die Schriftart **TT Modernoir** bei allen Besuchern korrekt angezeigt wird, musst du das Projekt mit deiner Adobe Fonts Kit-ID verknüpfen:
1. Erstelle ein Web-Projekt auf [fonts.adobe.com](https://fonts.adobe.com) für **TT Modernoir**.
2. Ersetze in der `index.html` den Pfad der Kit-ID mit deinem eigenen Projekt-Link (derzeit ist dort dein Link `https://use.typekit.net/yxu7vvd.css` hinterlegt):
   ```html
   <link rel="stylesheet" href="https://use.typekit.net/DEINE_KIT_ID.css">
   ```

### CSS-Design-System
Die Primärfarben und Schriftarten sind als CSS-Variablen in [style.css](style.css) definiert:
```css
:root {
    --color-red: #E9421F;      /* Hauptfarbe (Rot-Orange) */
    --color-dark: #191311;     /* Text- & Schattenfarbe (Warmer Dunkelton) */
    --color-cream: #F7F5EB;    /* Hintergrundfarbe (Warmes Creme) */
    
    --font-display: 'TT Modernoir', 'tt-modernoir', 'Bebas Neue', sans-serif;
    --font-typewriter: 'Special Elite', monospace;
    --font-ui: 'Segoe UI', 'Inter', sans-serif;
}
```
