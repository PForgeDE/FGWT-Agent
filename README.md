# FGWT Agent

Der **FGWT Agent** liest während du Star Citizen spielst die `Game.log` mit und überträgt deine Spielereignisse an die Organisations-Website **[fgwt.pforge.de](https://fgwt.pforge.de)**: Handel, Missionen, Blueprints, Reisen, Kämpfe, Bergbau und mehr. Daraus entstehen dort deine Gaming-Sessions mit Kontostand, die Missionsübersicht, die Blueprint-Sammlung und – wenn du es freigibst – der Live-Status für die Orga.

Dieses Repository enthält **nur die Installationsdateien, Updates und die Anleitung**. Der Quellcode liegt nicht hier.

## Download

➡️ **[Neueste Version herunterladen](https://github.com/PForgeDE/FGWT-Agent/releases/latest)**

| System | Datei | Anleitung |
|---|---|---|
| Windows 10/11 (x64) | `FGWT.LogAgent-win-x64-Setup.exe` | [Installation unter Windows](docs/installation-windows.md) |
| Windows auf ARM (z. B. Snapdragon) | `FGWT.LogAgent-win-arm64-Setup.exe` | [Installation unter Windows](docs/installation-windows.md) |
| Linux (x64, Star Citizen über Wine/Lutris/Proton) | `fgwt-log-agent-linux-x64.tar.gz` | [Installation unter Linux](docs/installation-linux.md) |

Die genauen Dateinamen können je nach Version leicht abweichen; maßgeblich ist die Liste unter *Assets* der jeweiligen Version.

## In drei Schritten startklar

1. **Agent installieren** – siehe Anleitung für dein System.
2. **API-Token erstellen** – auf [fgwt.pforge.de/tools/token-management](https://fgwt.pforge.de/tools/token-management), siehe [Einrichtung](docs/einrichtung.md).
3. **Token im Agent eintragen** und Star Citizen starten. Der Agent findet die `Game.log` selbst.

## Updates

- **Windows:** Der Agent prüft beim Start auf neue Versionen und installiert sie automatisch. Du musst nichts tun.
- **Linux:** Neue Version herunterladen und über die alte entpacken, siehe [Linux-Anleitung](docs/installation-linux.md#update).

Was sich geändert hat, steht bei der jeweiligen Version unter [Releases](https://github.com/PForgeDE/FGWT-Agent/releases).

## Weitere Hilfe

- [Einrichtung: Token, Einstellungen, Freigaben](docs/einrichtung.md)
- [Häufige Fragen und Probleme](docs/faq.md)
- [Welche Daten übertragen werden](docs/daten.md)

Probleme oder Wünsche? Bitte als [Issue](https://github.com/PForgeDE/FGWT-Agent/issues) melden oder im Orga-Discord ansprechen.
