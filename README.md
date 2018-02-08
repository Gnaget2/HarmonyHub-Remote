# HarmonyHub-Remote
Control your Harmony hub from Home Assistant

## Description
Designed for and tested with Home Assistant hassio version 0.62.1

 #### Functions:

Its created as a [Home Assistant package](https://home-assistant.io/docs/configuration/packages/) and assume you already have your [harmony hub](https://home-assistant.io/components/remote.harmony/) connected to HASS, it should be discovered by the [Discovery: component](https://home-assistant.io/components/discovery/)

## Screenshot from HASS GUI
<img src="https://github.com/Gnaget2/HarmonyHub-Remote/blob/master/Images/Screenshot.png" alt="Screenshot" />

## Installation
- If your installation doesn’t already support the use of [packages](https://home-assistant.io/docs/configuration/packages/) please activate it.
- Place `harmony_remote.yaml` in your package folder
- Edit `harmony_remote.yaml` and replace all instances of the name of the remote to match your remote, in the example its called `Hub1`, your name you can find by looking at the file `harmony_XXXXXXX.conf` in your `<Config dir>` where XXXXXXX is your name. tip is to search and replace all hub1 valus to your name.
- Open `harmony_XXXXXXX.conf` in your `<Config dir>` and make a note of all your activity names and activity IDs. The example have the following.
  ```
  Activities
  13507786 - TV
  13507990 - ATV3
  30143777 - AirPlay
  -1 - PowerOff
  13845019 - WII
  29039108 - Film
  23688854 - Xbox
  ```
  -Edit the `harmony_remote.yaml`and the section `input_select:`so that the options match your activitys, add or remove lines if needed.
- Edit the `input_select_harmony` script so that the names and activitys match your names and IDs
- Edit the rest if the scripts with ID for the device the command should be sent to and what command to send, see your `harmony_XXXXXXX.conf` file for ID for each device and its commands.
- Download `/www/custom_ui/state-card-tiles.html` to `<config-dir>/www/custom_ui/`
- Add to your `configuration.yaml`:
```yaml
frontend:
  extra_html_url:
    - /local/custom_ui/state-card-tiles.html
  extra_html_url_es5:
    - /local/custom_ui/state-card-tiles.html
```
- Restart HASS and start using it.



## Change log

#### 1.0
First release
Can start several activitys but only control one, support for several activitys will come in next version




