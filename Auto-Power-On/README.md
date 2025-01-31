# Generelle Anleitung für den Autostart

Diese Anleitung ist eine generelle Anleitung um die Einstellungen des Bios so anzupassen das der PC Automatisch Startet sobald er mit dem Strom verbunden wird. Achtung nicht alle Hersteller/ Mainbords unterstützen diese Einstellungen

## Wie man in das Bios kommt

Um in das Bios eines Pcs zu gelangen muss dieser zunächst ausgeschaltet sein. Wenn man Ihn nun einschalten und während des Boot Vorgangs eine bestimmte Taste drückt gelangt man in das BIOS. Diese Taste kann sich je nach Hersteller unterscheiden. Oft wird die benötige Taste kurz beim Starten des Pcs angezeigt.

Hier eine Liste häufig verwendete Tasten. Manchmal hilft nur ausprobieren.


| Taste | Hersteller                  |
| ------- | ----------------------------- |
| ENTF  | Asus, MSI, Gigabyte, AsRock |
| F2    | Asus, Acer, Dell, Lenovo    |
| F10   | HP                          |
| F12   | Lenovo                      |
| ESC   | HP, Asus                    |
| F1    | Lenovo                      |

## Welche Einstellungen geändert werden müssen

### Auto Power On

Die Benötigten Einstellungen heißen je nach Hersteller unterschiedlich. Die Einstellung muss es ermöglichen das der PC automatisch booted wenn er Strom über das Netzteil erhält.

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

### Akku Deaktivieren

Es kann sinnvoll sein den internen Akku in Laptops im Bios zu Deaktivieren. Dadurch kann der Pc über das Aus und wieder Einstecken des Stroms neu gestartet werden falls ein normales Herunterfahren nicht möglich ist. Ansonsten müsste man warten bis der Akku komplett entleert ist.

## Speichern und Testen

Nach dem Ändern müssen Einstellungen häufig separat gespeichert werden um wirksam zu sein. Darauf sollte man beim verlassen des BIOS achten.
Anschließend kann Überprüft werden ob die Einstellungen wirksam waren in dem der PC ausgesteckt und wieder eingesteckt wird. Er sollte nun Automatisch Booten
