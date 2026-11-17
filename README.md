# Hofladen & Hofcafé Sonnleiten

Inhalte und Vorlage dieser Website. Verwaltet über das SoftFlop-Serviceportal.

## Struktur

| Pfad | Was |
|---|---|
| `site.json` | Metadaten, Farben, Navigation, Modulreihenfolge |
| `content/*.json` | ein JSON je Modul — das pflegt der Kunde über das Portal |
| `assets/` | Logos und Bilder |
| `tools/build.mjs` | der Renderer als eigenständiges Bündel |

## Build

```bash
node tools/build.mjs . dist
```

Keine Abhängigkeiten, kein `npm install`. Läuft in unter einer Sekunde.
Genau dieser Befehl läuft auch bei Cloudflare Pages.

## Bitte nicht von Hand bearbeiten

Die Dateien unter `content/` schreibt die Veröffentlichungs-Pipeline.
Änderungen von Hand werden bei der nächsten Veröffentlichung überschrieben.

`tools/build.mjs` ist erzeugt — die Quelle liegt im SoftFlop-Hauptrepo.

## Seitenverwaltung

Diese Website wird ueber die Seitenverwaltung im SoftFlop-Portal aufgebaut: Welche Seiten es gibt, ihre
Adressen, das Menue und die Reihenfolge der Bereiche stehen in `content/aufbau.json`.
`site.json` bestimmt ab jetzt nur noch, was gebucht ist (`module`, `seiten`, `navigation` als Buchung) --
wer dort Seiten oder das Menue umbaut, sieht auf der Website keine Wirkung. Umbauen geht im Portal.
