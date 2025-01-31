[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Diese Anleitung gibt es in mehreren Sprachen

[![en](https://img.shields.io/badge/language-English-green.svg)](https://github.com/fabian-lehnhof/Event-Autostart-Tutorial/blob/main/README.md) [![de](https://img.shields.io/badge/language-German-green.svg)](https://github.com/fabian-lehnhof/Event-Autostart-Tutorial/blob/main/README-de.md)

# Event-Autostart-Tutorial

Bei Messen und Veranstaltungen werden Mini-PCs oder Laptops oft in Möbel oder Exponate eingebaut und sind schwer zugänglich. Meist laufen sie mit einem Touch-Display und zeigen durchgehend eine PowerPoint-Präsentation oder eine Webseite im Kiosk-Modus. Idealerweise bleibt alles stabil, doch gelegentlich treten Fehler auf. In solchen Fällen ist es meist einfacher, den Kunden telefonisch oder per Remote-Anweisung zu bitten, das Gerät kurz vom Strom zu trennen, statt mühsam Holzplatten abzuschrauben, Maus und Tastatur anzuschließen und die Anwendung neu zu starten.

Bisher habe ich mir die Einrichtungsschritte einfach gemerkt, doch auf Wunsch einiger Kollegen habe ich sie hier dokumentiert. Ich hoffe, dieses Repository ist nicht nur für sie, sondern auch für andere hilfreich – und dass ich selbst neue Methoden dazulerne. Zudem wollte ich die Zusammenarbeit über GitHub ausprobieren.

Dies ist mein erstes öffentliches Repository – seid nachsichtig! Ich freue mich über Beiträge, Übersetzungen und Pull Requests.

Viele Grüße
Fabian

## Grundlagen

Im wesentlichen gibt es folgende Schritte:

1. [Den PC automatisch Hochfahren lassen sobald er Strom erhält.](##Schritt-1---PC-Auto-Power-On)
2. [Software oder Dateien für den Autostart vorbereiten](##software-vorbereitungen)
3. [Eine Verknüpfung im Autostart Ordner anlegen](##Schritt-3---Autostart-einrichten)

Die Details und genauen Einstellungen sind weiter unten dokumentiert.

## Schritt 1 - PC Auto Power On

Diese Anleitung erklärt wie man die Einstellungen des BIOS anpassen muss, damit der PC automatisch startet sobald er mit dem Strom verbunden wird.

> Achtung nicht alle Hersteller/ Mainbords unterstützen diese Einstellungen!

#### Wie man in das BIOS kommt

Um in das BIOS eines Pcs zu gelangen muss dieser zunächst ausgeschaltet sein. Wenn man Ihn nun einschalten und während des Boot Vorgangs eine bestimmte Taste drückt gelangt man in das BIOS. Diese Taste kann sich je nach Hersteller unterscheiden. Oft aber nicht immer wird die benötige Taste kurz beim Starten des Pcs angezeigt.

Hier eine Liste häufig verwendeter Tasten. Falls das BIOS nicht angezeigt wird, hilft oft nur Ausprobieren.


| Taste | Hersteller                  |
| ------- | ----------------------------- |
| ENTF  | Asus, MSI, Gigabyte, AsRock |
| F2    | Asus, Acer, Dell, Lenovo    |
| F10   | HP                          |
| F12   | Lenovo                      |
| ESC   | HP, Asus                    |
| F1    | Lenovo                      |

#### Welche Einstellungen geändert werden müssen

##### Auto Power On

Damit der PC automatisch startet sobald er mit dem Strom verbunden wird müssen einige Einstellungen im BIOS geändert werden.
Die Benötigten Einstellungen heißen je nach Hersteller unterschiedlich. Die Einstellung muss den PC so konfigurieren, dass er automatisch startet, sobald er Strom erhält.

Diese Einstellung findet sich oft in Kategorien wie zum Beispiel

* **Power Management**
* **Advanced**
* **ACPI Configuration**

Die Einstellung selbst kann ebenfalls verschiedene Namen haben. Hier einige Beispiele

* **AC Power Recovery**
* **Restore on AC Power Loss**
* **Power On After Power Loss**
* **Auto Power On**
* **Always Power On**
* **State After Power Failure**
* **Power Failure Recovery**

##### Akku Deaktivieren

Es kann sinnvoll sein den internen Akku in Laptops im BIOS zu Deaktivieren oder ihn zu entfernen. Dadurch kann der Pc über das Aus und wieder Einstecken des Stroms neu gestartet werden falls ein normales Herunterfahren nicht möglich ist. Ansonsten müsste man warten bis der Akku komplett entleert ist.

##### Speichern und Testen

Nach dem Ändern müssen Einstellungen häufig separat gespeichert werden um wirksam zu sein. Darauf sollte man beim verlassen des BIOS achten.
Anschließend kann überprüft werden ob die Einstellungen wirksam waren in dem der PC ausgesteckt und wieder eingesteckt wird. Er sollte nun Automatisch Booten

## Schritt 2 - Software Vorbereitungen

Hier sind Anleitungen für verschieden Programme hinterlegt die häufig verwendet werden

* [Powerpoint](##Power-Point)
* [Firefox Kiosk Mode](##Firefox-Kiosk-Mode)
* [Chrome Kiosk Mode](##Chrome-Kiosk-Mode)
* [VLC Single Video Loop](##VLC-Single-Video-Loop)

## Power Point

### Die Powerpoint so einstellen das sie sich wiederholt

Die Powerpoint Präsentation öffnen

Unter dem Reiter `Bildschirm Präsentation` das Fenster `Bildschirmpräsentation einrichten` anklicken.

Unter dem Punkt `Art der Präsentation` die Einstellung auf `Ansicht an einem Kiosk (Volle Bildschirmgröße)` ändern.

Unter dem Punkt `Übergänge` die Einstellungen für `Nächste Folie` anpassen

* `Bei Mausklick` - Diese Einstellung deaktivieren
* `Nach` - Diese Einstellung auf die gewünschte Zeit für die Folie(n) einstellen.

Die Übergänge können auch für alle Folien gemeinsam geändert werden wenn man die gewünschte Zeit einstellt und anschließend auf `Auf alle Anwenden` klickt

Testen - Die Bildschirm Präsentation Starten. Die Folien sollten nun automatisch wechseln und sie sollte sich nun nach der letzten Folie wiederholen.

### Die Powerpoint als Powerpoint Slide Show Speichern

Um eine Powerpoint Slide Show so zu speichern das sie beim Öffnen Automatisch Startet

Unter `Datei -> Speichern unter` das Dateiformat `.ppsx` auswählen und auf dem Computer Speichern.

Nach Änderungen an der Original Datei muss diese erneut als .ppsx Datei gespeichert werden.

Anschließend kann der Autostart eingerichtet werden

## Firefox Kiosk Mode

### Befehl für Firefox


| Pfad zu Firefox.exe                            | Parameter                      | URL                               |
| ------------------------------------------------ | -------------------------------- | ----------------------------------- |
| "C:\Program Files\Mozilla Firefox\firefox.exe" | --kiosk                        | https://www.example.org           |
| Der Pfad muss eventuell angepasst werden       | Startet Firefox im Kiosk Modus | Die URL die geöffnet werden soll |

`"C:\Program Files\Mozilla Firefox\firefox.exe" --kiosk https://www.example.org`

> Dieser Befehl kann entweder in einer normalen Verknüpfung angelegt werden oder in einer `.bat` Script Datei.
> Ich bevorzuge eine kleine Skript Datei da ein nachträgliches anpassen des Links im Text Editor komfortabler ist.

Anschließend kann der Autostart eingerichtet werden

## Chrome Kiosk Mode


| Pfad zu Chrome.exe                                      | Parameter                     | URL                               |
| --------------------------------------------------------- | ------------------------------- | ----------------------------------- |
| "C:\Program Files\Google\Chrome\Application\chrome.exe" | --kiosk                       | https://www.example.org           |
| Der Pfad muss eventuell angepasst werden                | Startet Chrome im Kiosk Modus | Die URL die geöffnet werden soll |

`"C:\Program Files\Google\Chrome\Application\chrome.exe" --kiosk www.example.org`

> Dieser Befehl kann entweder in einer normalen Verknüpfung angelegt werden oder in einer `.bat` Script Datei.
> Ich bevorzuge eine kleine Skript Datei da ein nachträgliches anpassen des Links im Text Editor komfortabler ist.

Anschließend kann der Autostart eingerichtet werden

## VLC Single Video Loop

Um ein einzelnes Video Automatisch zu öffnen und zu wiederholen


| Pfad zu VLC Player                       | Pfad zum Video                    | Parameter                      | Parameter                                        | Parameter                                         | Parameter                    |
| ------------------------------------------ | ----------------------------------- | -------------------------------- | -------------------------------------------------- | --------------------------------------------------- | ------------------------------ |
| "C:\Program Files\VideoLAN\VLC\vlc.exe"  | "PATH TO VIDEO"                   | --fullscreen                   | --loop                                           | --no-osd                                          | --no-mouse-events            |
| Der Pfad muss eventuell angepasst werden | Pfad zur gewünschten Video Datei | Startet VLC im Fullscreen Mode | Die Video Datei wird am ende von vorne gestartet | Keine Anzeigen wie den Dateinamen auf der Ausgabe | Unterbindet Maus Interaktion |

`"C:\Program Files\VideoLAN\VLC\vlc.exe" "PATH TO VIDEO" --fullscreen --loop --no-osd --no-mouse-events`

> Dieser Befehl kann entweder in einer normalen Verknüpfung angelegt werden oder in einer `.bat` Script Datei.
> Ich bevorzuge eine kleine Skript Datei da ein nachträgliches anpassen des Links im Text Editor komfortabler ist.

## Schritt 3 - Autostart einrichten

### Windows

#### Windows 11 + 10 + 7

1. Mit `Windows + R` das Ausführen Fenster öffnen.
2. Mit dem Befehl `shell:startup` den Autostart Ordner öffnen.
3. In dem Ordner eine Verknüpfung auf die gewünschte Datei oder das gewünschte Programm anlegen.

Testen
Den Rechner Neustarten und testen ob die Ausführung erfolgreich ist.
