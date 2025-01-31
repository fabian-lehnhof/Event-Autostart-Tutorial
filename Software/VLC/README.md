# Webbrowser Kiosk Mode

Dieser Befehl kann entweder in einer normalen Verknüpfung angelegt werden oder in einer `.bat` Script Datei.
Ich bevorzuge eine kleine Skript Datei da ein nachträgliches anpassen im Text Editor komfortabler ist.

Um ein Video Automatisch zu öffnen und zu Wiederholen


| Pfad zu VLC Player                                          | Pfad zum Video                    | Parameter                      | Parameter                                        | Parameter                                         | Parameter                    |
| ------------------------------------------------------------- | ----------------------------------- | -------------------------------- | -------------------------------------------------- | --------------------------------------------------- | ------------------------------ |
| vlc.exe                                                     | "PATH TO VIDEO"                   | --fullscreen                   | --loop                                           | --no-osd                                          | --no-mouse-events            |
| Pfad zu VLC Player.exe<br />Muss eventuell angepasst werden | Pfad zur gewünschten Video Datei | Startet VLC im Fullscreen Mode | Die Video Datei wird am ende von vorne gestartet | Keine Anzeigen wie den Dateinamen auf der Ausgabe | Unterbindet Maus Interaktion |

`"C:\Program Files\VideoLAN\VLC\vlc.exe" "PATH TO VIDEO" --fullscreen --loop --no-osd --no-mouse-events`
