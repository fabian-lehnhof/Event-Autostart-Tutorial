[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

These instructions are available in multiple languages

[![en](https://img.shields.io/badge/language-English-green.svg)](https://github.com/fabian-lehnhof/Event-Autostart-Tutorial/blob/main/README.md) [![de](https://img.shields.io/badge/language-German-green.svg)](https://github.com/fabian-lehnhof/Event-Autostart-Tutorial/blob/main/README-de.md)

# Event-Autostart-Tutorial

At trade fairs and events, mini PCs or laptops are often built into furniture or exhibits and are difficult to access. They usually run with a touch display and continuously show a PowerPoint presentation or a website in kiosk mode. Ideally, everything remains stable, but occasionally errors occur. In such cases, it is usually easier to ask the customer by phone or remote instruction to briefly disconnect the device from the power supply instead of laboriously unscrewing wooden panels, connecting the mouse and keyboard and restarting the application.

So far I have simply memorised the setup steps, but at the request of some colleagues I have documented them here. I hope this repository is not only helpful for them, but also for others - and that I learn new methods myself. I also wanted to try out collaboration via GitHub.

This is my first public repository - bear with me! I look forward to contributions, translations and pull requests.

Best regards
Fabian

## Grundlagen

The main steps are as follows:

1. [Automatically start up the PC as soon as it receives power.](#step-1---pc-auto-power-on)
2. [Preparing software or files for autostart](#step-2---software-preparations)
3. [Create a shortcut in the Autostart folder](#step-3---set-up-autostart)

The details and exact settings are documented below.

## Step 1 - PC Auto Power On

This guide explains how to adjust the BIOS settings so that the PC starts automatically as soon as it is connected to the power supply.

> Attention: not all manufacturers/mainboards support these settings!

#### How to access the BIOS

To access the BIOS of a PC, it must first be switched off. If you switch it on and press a specific key during the boot process, you will enter the BIOS. This key may differ depending on the manufacturer. Often, but not always, the required key is briefly displayed when the PC is started.

Here is a list of frequently used keys. If the BIOS is not displayed, often only trial and error will help.


| Taste | Hersteller                  |
| ------- | ----------------------------- |
| ENTF  | Asus, MSI, Gigabyte, AsRock |
| F2    | Asus, Acer, Dell, Lenovo    |
| F10   | HP                          |
| F12   | Lenovo                      |
| ESC   | HP, Asus                    |
| F1    | Lenovo                      |

#### Which settings need to be changed

##### Auto Power On

In order for the PC to start automatically as soon as it is connected to the power, some settings must be changed in the BIOS.
The required settings vary depending on the manufacturer. The setting must configure the PC so that it starts automatically as soon as it receives power.

This setting is often found in categories such as

* **Power Management**
* **Advanced**
* **ACPI Configuration**

The setting itself can also have different names. Here are some examples

* **AC Power Recovery**
* **Restore on AC Power Loss**
* **Power On After Power Loss**
* **Auto Power On**
* **Always Power On**
* **State After Power Failure**
* **Power Failure Recovery**

##### Deactivate Battery

It can be useful to deactivate the internal battery in laptops in the BIOS or to remove it. This allows the PC to be restarted by switching the power off and on again if a normal shutdown is not possible. Otherwise you would have to wait until the battery is completely discharged.

##### Save the changes and check whether they have been applied

After making changes, settings often have to be saved separately to take effect. You should pay attention to this when leaving the BIOS.
You can then check whether the settings were effective by unplugging the PC and plugging it back in. It should now boot automatically

## Step 2 - Software preparations

Here are instructions for various programmes that are frequently used

* [Powerpoint](#power-point)
* [Firefox Kiosk Mode](#firefox-kiosk-mode)
* [Chrome Kiosk Mode](#chrome-kiosk-mode)
* [VLC Single Video Loop](#vlc-single-video-loop)

## Power Point

### Set the PowerPoint so that it repeats itself

Open the PowerPoint presentation

Under the `Screen presentation` tab, click on the `Set up screen presentation` window.

Under `Type of presentation`, change the setting to `View on a kiosk (full screen size)`.

Adjust the settings for `Next slide` under `Transitions`.

* `On mouse click` - Deactivate this setting
* `After` - Set this setting to the desired time for the slide(s).

The transitions can also be changed for all slides together if you set the desired time and then click on `Apply to all`.

Test - Start the screen presentation. The slides should now change automatically and it should repeat after the last slide.

### Save the PowerPoint as a .ppsx File

To save a PowerPoint slide show so that it starts automatically when opened

Select the file format `.ppsx` under `File -> Save as` and save it on the computer.

After making changes to the original file, it must be saved again as a .ppsx file.

The autostart can then be configured

## Firefox Kiosk Mode

### Command for Firefox


| Path to Firefox.exe                            | Parameter                    | URL                     |
| ------------------------------------------------ | ------------------------------ | ------------------------- |
| "C:\Program Files\Mozilla Firefox\firefox.exe" | --kiosk                      | https://www.example.org |
| The path may need to be adjusted               | Starts Firefox in Kiosk mode | The URL to be opened    |

`"C:\Program Files\Mozilla Firefox\firefox.exe" --kiosk https://www.example.org`

> This command can either be created in a normal shortcut or in a `.bat` script file.
> I prefer a small script file because it is more convenient to adjust the link in the text editor afterwards.

The autostart can then be configured

## Chrome Kiosk Mode


| Pfad zu Chrome.exe                                      | Parameter                   | URL                     |
| --------------------------------------------------------- | ----------------------------- | ------------------------- |
| "C:\Program Files\Google\Chrome\Application\chrome.exe" | --kiosk                     | https://www.example.org |
| The path may need to be adjusted                        | Starts Chrome in Kiosk mode | The URL to be opened    |

`"C:\Program Files\Google\Chrome\Application\chrome.exe" --kiosk www.example.org`

> This command can either be created in a normal shortcut or in a `.bat` script file.
> I prefer a small script file because it is more convenient to adjust the link in the text editor afterwards.

The autostart can then be configured

## VLC Single Video Loop

To automatically open and repeat a single video


| Pfad zu VLC Player                       | Pfad zum Video                    | Parameter                      | Parameter                                        | Parameter                                         | Parameter                    |
| ------------------------------------------ | ----------------------------------- | -------------------------------- | -------------------------------------------------- | --------------------------------------------------- | ------------------------------ |
| "C:\Program Files\VideoLAN\VLC\vlc.exe"  | "PATH TO VIDEO"                   | --fullscreen                   | --loop                                           | --no-osd                                          | --no-mouse-events            |
| The path may need to be adjusted   | Path to the desired video file | Starts VLC in fullscreen mode | The video file is started from the beginning at the end | No displays such as the file name on the display | Prevents mouse interaction |

`"C:\Program Files\VideoLAN\VLC\vlc.exe" "PATH TO VIDEO" --fullscreen --loop --no-osd --no-mouse-events`

> This command can either be created in a normal shortcut or in a `.bat` script file.
> I prefer a small script file because it is more convenient to adjust the link in the text editor afterwards.

## Step 3 - Set up autostart

### Windows

#### Windows 11 + 10 + 7

1. Press `Windows + R` to open the Run window.
2. Open the autostart folder with the command `shell:startup`.
3. Create a shortcut to the desired file or application in the folder.

Test
Restart the computer and test whether the file or program opens successfully
