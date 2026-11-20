# Installation unter Windows

## Voraussetzungen

- Windows 10 oder 11, x64 oder ARM64
- Star Citizen (LIVE, PTU, EPTU oder HOTFIX)
- ein Konto auf [fgwt.pforge.de](https://fgwt.pforge.de)

Die benötigte **.NET 10 Desktop Runtime** installiert das Setup bei Bedarf einmalig selbst mit.

## Installieren

1. Unter [Releases](https://github.com/PForgeDE/FGWT-Agent/releases/latest) die passende Datei laden:
   - `FGWT.LogAgent-win-x64-Setup.exe` für normale PCs
   - `FGWT.LogAgent-win-arm64-Setup.exe` für Windows auf ARM
2. Setup starten. Der Agent wird für deinen Benutzer installiert (keine Administratorrechte nötig) und startet danach.
3. Der Agent erscheint als Symbol im Infobereich der Taskleiste (neben der Uhr).
4. Weiter mit der [Einrichtung](einrichtung.md).

Alternativ gibt es eine **Portable**-Version (`…-Portable.zip`) zum Entpacken ohne Installation. Diese aktualisiert sich nicht automatisch.

## Windows-Warnungen beim ersten Start

Die Installationsdateien sind derzeit **nicht digital signiert**. Deshalb kann Windows warnen:

- **SmartScreen** („Der Computer wurde durch Windows geschützt“): auf *Weitere Informationen* → *Trotzdem ausführen* klicken.
- **Smart App Control** („Herausgeber nicht bestätigt“) blockiert unsignierte Programme vollständig. Laut Microsoft gibt es dafür keine Ausnahme für einzelne Programme; Smart App Control lässt sich nur insgesamt abschalten (Windows-Sicherheit → App- & Browsersteuerung). Ob du das tun möchtest, entscheidest du selbst. Eine Signatur der Releases ist geplant.

## Updates

Der Agent prüft bei jedem Start, ob es eine neue Version gibt, lädt sie herunter und startet neu. Ein Update dauert wenige Sekunden.

## Autostart

In den Einstellungen des Agents lässt sich einstellen, dass er mit Windows startet. Er läuft dann still im Hintergrund und liest mit, sobald du Star Citizen startest.

## Deinstallieren

*Einstellungen → Apps → Installierte Apps → FGWT Log Agent → Deinstallieren*.
Die lokalen Daten (Einstellungen und Datenbank) liegen unter `%LOCALAPPDATA%\FGWT\LogAgent` und können danach von Hand gelöscht werden.
