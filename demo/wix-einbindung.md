# Spiel in Wix einbinden — Kurzanleitung für SHB

Das Kundentag-Spiel liegt fertig im Netz. Für die Website muss es nur **eingebettet** werden — kein Hosting, kein Upload nötig. Zwei Wege, je nachdem was bequemer ist.

**Spiel-URL (Skin „Straße"):**
```
https://zundanus.github.io/shb-kundentag-game/code/index-bc.html?skin=strasse
```
*(Ohne `?skin=strasse` erscheint die Gerüst-Variante. Der iOS-Zoom-Schutz ist im Spiel eingebaut und bleibt in der Einbettung wirksam.)*

---

## Weg A — am einfachsten: „Website einbetten"

1. In Wix im Editor auf **Hinzufügen (+) → Einbetten → Website einbetten** (Embed a Site).
2. Das Element auf die Seite ziehen, dann **„Website-Adresse eingeben"** anklicken.
3. Die **Spiel-URL** (siehe oben) einfügen und übernehmen.
4. Größe des Elements auf der Seite anpassen — Hochformat, empfohlen ca. **380 × 600 px** (Breite × Höhe).

Fertig. Nichts weiter zu kopieren.

---

## Weg B — mit fixem Rahmen: „HTML einbetten"

Wenn das Spiel in einem sauberen, zentrierten Rahmen sitzen soll:

1. In Wix auf **Hinzufügen (+) → Einbetten → HTML einbetten** (Embed a Widget / HTML-Code).
2. Auf **„Code eingeben"** klicken und den folgenden Block **komplett** einfügen:

```html
<div style="max-width:500px;margin:0 auto;aspect-ratio:40/60;background:#1a1a4e;border-radius:14px;overflow:hidden;touch-action:none;overscroll-behavior:contain;">
  <iframe
    src="https://zundanus.github.io/shb-kundentag-game/code/index-bc.html?skin=strasse"
    style="width:100%;height:100%;border:0;display:block;touch-action:none;"
    title="SHB Kundentag Spiel — LEVEL UP!"
    loading="lazy"
    scrolling="no"
    allowfullscreen></iframe>
</div>
```

> `touch-action:none` am Rahmen sorgt dafür, dass Tippen/Wischen **im Spiel** die Seite nicht mitscrollt (Handy). Siehe auch den Hinweis „Scroll-Verhalten" unten.

3. Übernehmen und das Element auf der Seite auf die gewünschte Größe ziehen.

---

## Hinweise

- **Hochformat:** Das Spiel ist für Smartphones gebaut (Hochkant). Die Rahmenhöhe sollte deutlich größer als die Breite sein (Verhältnis ca. 2:3), sonst wird es gestaucht.
- **Mobil in Wix:** Wix hat eine getrennte Mobil-Ansicht — dort die Element-Größe separat prüfen, damit das Spiel die Bildschirmbreite gut ausfüllt.
- **Scroll-Verhalten (wichtig):** Beim Spielen dürfen ↑/↓/Leertaste bzw. Wischen **nicht die Seite scrollen**. Dafür ist gesorgt: das **Spiel fängt seine Steuertasten selbst ab** (Pfeile/Leertaste/WASD), und der Rahmen im Snippet oben trägt `touch-action:none` gegen Touch-Scrollen. Voraussetzung ist der **aktuelle Spiel-Stand** (der Tasten-Fix ist Teil des laufenden Updates) — bitte nach dem Einbau am Handy **und** am Desktop einmal gegentesten. Sollte in eurer Wix-Umgebung trotzdem gescrollt werden, kurz bei uns melden.
- **Skin wechseln:** `?skin=strasse` = Straßen-Optik, ohne den Parameter = Gerüst-Optik. Einfach in der URL ändern.
- **Domain/Optik:** Besucher sehen nur die SHB-Seite; die Spiel-Adresse taucht nur im Quelltext auf.
- **Vorschau:** Wie es eingebettet aussieht, zeigt die Simulationsseite `embed/shb-dummy-embed.html` (lokal im Browser öffnen).
- **Voraussetzung:** Der genutzte Wix-Tarif muss das Einbetten von Fremdinhalten (iframe/HTML) erlauben — bei den meisten bezahlten Plänen der Fall. Falls Weg B gesperrt ist, funktioniert Weg A fast immer.
