# Webbrowser Kiosk Mode

Dieser Befehl kann entweder in einer normalen Verknüpfung angelegt werden oder in einer `.bat` Script Datei.
Ich bevorzuge eine kleine Skript Datei da ein nachträgliches anpassen des Links im Text Editor komfortabler ist.

## Befehl für Firefox


| Pfad zu Firefox.exe                            | Parameter                      | URL                               |
| ------------------------------------------------ | -------------------------------- | ----------------------------------- |
| "C:\Program Files\Mozilla Firefox\firefox.exe" | --kiosk                        | https://www.example.org           |
| Der Pfad muss eventuell angepasst werden       | Startet Firefox im Kiosk Modus | Die URL die geöffnet werden soll |

`"C:\Program Files\Mozilla Firefox\firefox.exe" --kiosk https://www.example.org`

## Befehl für Chrome


| Pfad zu Chrome.exe                                      | Parameter                     | URL                               |
| --------------------------------------------------------- | ------------------------------- | ----------------------------------- |
| "C:\Program Files\Google\Chrome\Application\chrome.exe" | --kiosk                       | https://www.example.org           |
| Der Pfad muss eventuell angepasst werden                | Startet Chrome im Kiosk Modus | Die URL die geöffnet werden soll |

`"C:\Program Files\Google\Chrome\Application\chrome.exe" --kiosk www.example.org`
