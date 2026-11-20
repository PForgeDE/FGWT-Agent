# Einrichtung

## 1. API-Token erstellen

Der Agent meldet sich nicht mit deinem Passwort an, sondern mit einem **API-Token**, den nur er benutzt.

1. Auf [fgwt.pforge.de](https://fgwt.pforge.de) anmelden.
2. Oben rechts im Benutzermenü **Token-Verwaltung** öffnen (direkt: [/tools/token-management](https://fgwt.pforge.de/tools/token-management)).
3. Neuen Token anlegen, z. B. mit dem Namen „Log Agent PC“, und diese Berechtigungen (Scopes) auswählen:
   - `events:write` – Spielereignisse senden (**Pflicht**)
   - `sessions:read` und `sessions:write` – Gaming-Sessions automatisch starten und beenden
4. Den angezeigten Token **sofort kopieren**. Er wird nur dieses eine Mal angezeigt. Geht er verloren, einfach einen neuen anlegen und den alten widerrufen.

Behandle den Token wie ein Passwort: nicht teilen, nicht in Screenshots zeigen.

## 2. Token im Agent eintragen

- **Windows:** Agent-Fenster öffnen (Doppelklick auf das Symbol im Infobereich) → Reiter **Konfiguration** → Token einfügen → **Verbindung testen** → **Speichern**. Die API-Adresse ist bereits `https://fgwt.pforge.de/api`.
- **Linux:** siehe [Linux-Anleitung, Abschnitt Einrichten](installation-linux.md#einrichten).

Der Token wird verschlüsselt (Windows) bzw. in einer nur für dich lesbaren Datei (Linux) gespeichert.

## 3. Spielen

Star Citizen ganz normal starten. Der Agent erkennt die neue Sitzung selbst, liest mit und überträgt die Ereignisse im Hintergrund. Ist die Website kurz nicht erreichbar, sammelt er alles lokal und schickt es später nach – es geht nichts verloren.

## Freigaben auf der Website

Was andere Orga-Mitglieder von dir sehen, stellst du **auf der Website** unter *Profil* ein, nicht im Agent:

| Einstellung | Wirkung |
|---|---|
| **Daten mit der Orga teilen** | deine Funde erscheinen z. B. in der Blueprint-Sammlung der Orga |
| **Live-Status für Orgamitglieder anzeigen** | du erscheinst in der Live-Ansicht mit Ort, Schiff und laufenden Missionen, solange du spielst |

Beides ist standardmäßig **aus**.

## Gaming-Sessions

Wenn der Token die Session-Berechtigungen hat, legt der Agent beim Spielstart automatisch eine Gaming-Session an. Der Startbetrag ist der Endbetrag deiner letzten Session; den Endbetrag schlägt die Website aus Handel, Missionsbelohnungen und Strafen vor – du kannst ihn beim Beenden übernehmen oder korrigieren.
