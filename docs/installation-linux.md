# Installation unter Linux

Unter Linux läuft der Agent als Kommandozeilen-Programm `fgwt-log-agent`, wahlweise als Dienst im Hintergrund (systemd). Star Citizen selbst läuft dabei wie gewohnt über Wine, Lutris oder Steam/Proton.

## Voraussetzungen

- Linux x64
- **.NET 10 Runtime** (nicht das SDK). Paketname je nach Distribution z. B. `dotnet-runtime-10.0`; Anleitung bei [Microsoft](https://learn.microsoft.com/dotnet/core/install/linux).
- ein Konto auf [fgwt.pforge.de](https://fgwt.pforge.de) und ein API-Token (siehe [Einrichtung](einrichtung.md))

Prüfen, ob die Runtime da ist:

```bash
dotnet --list-runtimes   # muss eine Zeile "Microsoft.NETCore.App 10.x" enthalten
```

## Installieren

```bash
mkdir -p ~/.local/opt/fgwt-log-agent
cd ~/.local/opt/fgwt-log-agent
curl -LO https://github.com/PForgeDE/FGWT-Agent/releases/latest/download/fgwt-log-agent-linux-x64.tar.gz
tar -xzf fgwt-log-agent-linux-x64.tar.gz
```

## Einrichten

Token eingeben, ohne dass er in der Shell-History landet:

```bash
cd ~/.local/opt/fgwt-log-agent
read -rs -p 'FGWT API-Token: ' token; echo
printf '%s\n' "$token" | ./fgwt-log-agent configure --api-url https://fgwt.pforge.de/api --token-stdin
unset token
```

Danach zeigt `status`, ob alles passt und welche `Game.log` gefunden wurde:

```bash
./fgwt-log-agent status
```

### Wo der Agent die Game.log sucht

Automatisch werden diese Orte durchsucht (jeweils für LIVE, PTU, EPTU und HOTFIX):

- Wine-/Lutris-Präfix: `~/Games/star-citizen/drive_c/Program Files/Roberts Space Industries/StarCitizen/<Kanal>/Game.log`
- Steam/Proton: `~/.steam/steam/steamapps/compatdata/<id>/pfx/drive_c/…`
- ein über `$WINEPREFIX` gesetztes Präfix

Liegt deine Installation woanders, gib den Pfad (Datei oder Ordner) einmalig an:

```bash
./fgwt-log-agent configure --log-path "/pfad/zu/StarCitizen/LIVE/Game.log"
```

## Starten

Im Vordergrund (Beenden mit Strg+C):

```bash
./fgwt-log-agent run
```

Als Hintergrunddienst für deinen Benutzer, der beim Anmelden startet:

```bash
./fgwt-log-agent install-service
systemctl --user status fgwt-log-agent      # Status
journalctl --user -u fgwt-log-agent -f       # Ausgaben live ansehen
```

Entfernen mit `./fgwt-log-agent uninstall-service`.

## Alte Logs nachtragen

```bash
./fgwt-log-agent import "/pfad/zu/logbackups/Game Build(…).log"
```

Die Events werden lokal gespeichert und vom laufenden Agent übertragen. Bereits übertragene Ereignisse werden nicht doppelt gezählt.

## Update

```bash
cd ~/.local/opt/fgwt-log-agent
systemctl --user stop fgwt-log-agent 2>/dev/null
curl -LO https://github.com/PForgeDE/FGWT-Agent/releases/latest/download/fgwt-log-agent-linux-x64.tar.gz
tar -xzf fgwt-log-agent-linux-x64.tar.gz
systemctl --user start fgwt-log-agent 2>/dev/null
```

Einstellungen, Token und lokale Datenbank bleiben dabei erhalten.

## Wo die Daten liegen

| Was | Ort |
|---|---|
| Einstellungen | `~/.config/fgwt-log-agent/settings.json` |
| API-Token | eigene Datei in `~/.config/fgwt-log-agent/`, nur für dich lesbar (Rechte 600) |
| lokale Datenbank | `~/.local/share/fgwt-log-agent/log-agent.db` |

Sind `XDG_CONFIG_HOME` bzw. `XDG_DATA_HOME` gesetzt, liegen die Dateien dort.
