# Welche Daten übertragen werden

Der Agent liest ausschließlich die `Game.log` von Star Citizen. Er liest keine anderen Dateien, keine Tastatureingaben und keine Bildschirminhalte.

## Was übertragen wird

Aus der `Game.log` erkannte Spielereignisse, jeweils mit Zeitpunkt und Spielsitzung:

| Bereich | Beispiele |
|---|---|
| Sitzung | Server/Region, Spielende, Absturz, eigene Spieler-ID und Spielername |
| Handel | Kauf und Verkauf (Ware, Menge, Preis, Terminal) |
| Missionen | angenommen, Ziele, abgeschlossen, Belohnung, Mitspieler in der Mission (als Spieler-ID) |
| Blueprints | erhaltene Baupläne |
| Reisen | Quantum-Ziele, Ankunft, Zonen, Rechtsgebiete, Standort beim Inventar |
| Fahrzeuge | genutzte bzw. aus dem Hangar geholte Schiffe |
| Gesundheit, Kampf | Verletzungen, Tod, Abschüsse |
| Fracht, Bergbau, Inventar | Frachtkisten, Veredelung, Ausrüstungswechsel |
| Recht | CrimeStat, Strafen, beschlagnahmte Fahrzeuge |

Welche Bereiche erfasst werden, lässt sich unter Windows in den Einstellungen des Agents pro Kategorie abschalten.

## Wer die Daten sieht

- **Du selbst:** alle deine Daten auf der Website.
- **Andere Orga-Mitglieder:** nur, was du im Profil freigibst (*Daten mit der Orga teilen*, *Live-Status anzeigen*). Beides ist standardmäßig aus.
- **Fremde Spieler** aus deinen Missionen werden in der Live-Ansicht nie namentlich gezeigt, nur gezählt.

## Wo die Daten liegen

- **Lokal** auf deinem Rechner in einer kleinen Datenbank (Pfade in den Anleitungen für [Windows](installation-windows.md#deinstallieren) und [Linux](installation-linux.md#wo-die-daten-liegen)), damit nichts verloren geht, wenn die Website nicht erreichbar ist.
- **Auf dem FGWT-Server** der Organisation. Details stehen in der [Datenschutzerklärung](https://fgwt.pforge.de/privacy).
