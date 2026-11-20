# Häufige Fragen und Probleme

### Der Agent findet meine Game.log nicht
- **Windows:** Der Agent sucht in den üblichen Installationsordnern von Star Citizen. Bei abweichendem Pfad im Reiter *Konfiguration* den Ordner deiner Installation (z. B. `D:\Games\StarCitizen\LIVE`) eintragen.
- **Linux:** `./fgwt-log-agent configure --log-path "<Pfad>"`, siehe [Linux-Anleitung](installation-linux.md#wo-der-agent-die-gamelog-sucht).

### „Verbindung testen“ meldet 401
Der Token ist falsch, abgelaufen oder widerrufen. Neuen Token in der [Token-Verwaltung](https://fgwt.pforge.de/tools/token-management) anlegen und eintragen.

### „Verbindung testen“ meldet 403
Dem Token fehlt eine Berechtigung. Für das Senden ist `events:write` nötig, für Gaming-Sessions zusätzlich `sessions:read` und `sessions:write`. Token mit den richtigen Scopes neu anlegen.

### Windows blockiert den Agent („Herausgeber nicht bestätigt“)
Das ist Smart App Control, weil die Dateien noch nicht signiert sind. Details in der [Windows-Anleitung](installation-windows.md#windows-warnungen-beim-ersten-start).

### Ich erscheine nicht in der Live-Ansicht
- Auf der Website unter *Profil* „Live-Status für Orgamitglieder anzeigen“ einschalten.
- Der Agent muss laufen, während du spielst. Nur aktuelle Ereignisse zählen; Nachträge alter Logs ändern den Live-Status nicht.
- Dein Ort erscheint, sobald das Spiel ihn ins Log schreibt – z. B. beim Öffnen des lokalen Inventars an einer Station oder beim Planen eines Quantum-Sprungs.

### Eine Mission bleibt als „aktiv“ stehen
Missionen, die du nicht abschließt, gelten beim regulären Ausloggen als abgebrochen, nach einem Absturz spätestens nach 24 Stunden. In der Live-Ansicht verschwinden sie, sobald niemand von der Mission mehr online ist.

### Ich habe offline gespielt bzw. die Website war nicht erreichbar
Kein Problem: Der Agent speichert alles lokal und überträgt es, sobald die Verbindung wieder steht. Doppelte Übertragungen werden auf der Website erkannt.

### Kann ich alte Logs nachtragen?
Ja. Windows: Reiter *Datei-Import*. Linux: `./fgwt-log-agent import <Datei>`. Alte Logs liegen im Star-Citizen-Ordner unter `logbackups`.

### Wie deinstalliere ich den Agent?
Siehe [Windows](installation-windows.md#deinstallieren) bzw. unter Linux `uninstall-service` und den Programmordner löschen.
