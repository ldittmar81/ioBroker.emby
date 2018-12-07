![Logo](admin/emby.png)
# ioBroker.emby
=================

This adapter will allow you to connect to your Emby Server and controle it.

Please follow the Steps to ensure the Adapter will work correctly and you can see all Devices.

## Steps 
1. Install the Adapter from Github

2. Edit the Settings and enter the IP, ApiKey and maybe some DeviceIds you want to ignore.

  ```IP **with** Port => 192.168.0.100:8096```
  
3. Save and restart the Adapter.

4. To see the first Items you will have to open a Emby Client to recieve some Data.
  
  ```The Adapter will not get Data if **no** client is open.```


## Objects

### Infos
* x.info.deviceName
  - Shows the Name of the Device


### Media

| Command | Description | Info |
| ------------- | ------------- | ------------- |
| x.media.description | Description of the shown File. |  |
| x.media.isMuted | If Media is Muted. | Not all devices support this and will be False. |
| x.media.isPaused | If Media is Paused. | Will also be True if User closes the client. |
| x.media.title | The Title of the shown File. |  |
| x.media.type | The Type of the shown File. | Episode, Video, Book, etc. |
| x.media.seasonName | The Name of the Season  | Only if .media.type is Episode otherwise it will be empty. |
| x.media.seriesName | The Name of the Serie | Only if .media.type is Episode otherwise it will be empty. |


### Commands
* x.command.dialog
  - Show a dialog on the selected Device.
    You can set Header and Body: Seperate it by '|'
    For example: Alarm|Some one opened the door.
    If no Header is given it will show ioBroker as Header.
* x.command.goHome
  - Sends a command to the selected Device which will return to the Homescreen
* x.command.message
  - Show a message on the selected Device for 5 sec.
* x.command.volume
  - Sets the Volume of the selected Device.
    Doesn't work on the most of devices since it doenst controle the TV Volume.

 
 ## Changelog
 ### 0.0.2
* added more states
* added DisplayMessage

### 0.0.1
* Initial version