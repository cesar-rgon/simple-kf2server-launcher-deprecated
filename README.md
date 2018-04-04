Simple Killing Floor 2 Server Launcher ![Logo](images/icon.png)
===============================================================

Application to easily customize and launch a Killing Floor 2 Server through a visual interface instead of edditing batch files or server's config files. It has been developed with Autoplay Media Studio 8.

```
Version: 1.1
Last modified date: 2018/04/03
Author: César Rodríguez González
Language: English, Spanish
```

![Screenshot1](images/screenshot1.png)

![Screenshot2](images/screenshot2.png)

The file "Simple-KF2server-launcher.zip" contains binary files to execute the application.

The file "Simple-KF2server-launcher.apz" is the source project (It needs to be edit with Autoplay Media Studio if you want to make changes on it).

### Pre-requisites
- Download and install a Killing Floor 2 Server. Instructions can be found [here](https://wiki.tripwireinteractive.com/index.php?title=Dedicated_Server_%28Killing_Floor_2%29). For this document, we supose that the installation folder is: C:\kf2server (but can be any other).
- Open needed ports in your router and firewall if you want your server be visible on internet.

### Installing and running the launcher
- Download binary file from [here](https://github.com/cesar-rgon/simple-kf2server-launcher/raw/master/Simple-KF2server-launcher.zip).
- Extract the content of the Simple-KF2server-launcher.zip file in your Killing Floor 2 server folder.
For example, the result would be:
```
C:\kf2server\Autoplay
C:\kf2server\autorun.exe
C:\fk2server\icon.ico
C:\kf2server\lua5.1.dll
C:\kf2server\lua51.dll
etc (Files and folders of Killing Floor 2 server)
```
- Create a direct link on your desktop to "autorun.exe" file.
- Execute direct link to "autorun.exe" file.

### Understanding the launcher
**Profile**: This field is optional. It allows to save field values (filter values) by profile name. If no profile is selected, field values can not be saved. You can add a new profile or delete the selected one.

**Game Type**: This field is mandatory. To manage (add/modify/delete) Game Type list, just edit text file: AutoPlay\Docs\en\GameTypes.properties. At least one game type must exist.

**Map**: This field is mandatory. To manage (add/modify/delete) Map list, just edit text file: AutoPlay\Docs\en\Maps.properties. At least one map must exist.

**Difficulty**: This field is mandatory if game type is not equal to Weekly, disabled in other case. To manage (add/modify/delete) Difficulty list, just edit text file: AutoPlay\Docs\en\Difficulty.properties

**Length**: This field is mandatory if game type is not equal to Weekly or Endless, disabled in other case. To manage (add/modify/delete) Length list, just edit text file: AutoPlay\Docs\en\Length.properties

**Server name**: This field is mandatory. It must contain at least one character.

**Server password**: This field is optional

**Max. players**: This field is mandatory. To manage (add/modify/delete) Max. players list, just edit text files: AutoPlay\Docs\en\MaxPlayers.properties and AutoPlay\Docs\en\MaxPlayersVersus.properties

**Web page**: If web page check is enabled you can manage the server through it. Killing Floor 2 server must be launched before you can access web page. Authentication:
```
User: admin
Password: <Web Password>
```

**Web password**: This field is mandatory only is web page is enabled

**Ports**: Ports are mandatory. You need to open ports in your router and firewall. If more than one server is launched, ports must be different between them (one profile per server configuration).

**URL image server**: This field is optional. This link must return an uploaded image to internet and it will be used as a preview image in your Killing Floor 2 server. Resolution must be 512x256 pixels.

**Messages**: These fields are optional. They are welcome messages in starting screen of the server.

**Language**: This field is mandatory. To manage (add/remove/delete) Language list, just edit text file: AutoPlay\Docs\Language.properties

**Launch server**: Launch a Killing Floor 2 server with the specified filters. All mandatory fields must be specified.
If there is not a profile, server config files are placed in folder: KFGame\Config\\\_NoneProfile. If a profile is selected, server config files are placed in folder: KFGame\Config\PROFILENAME. So, the original config files placed in folder: KFGame\Config are never modified.

### Anex
#### A1. Command line arguments
The accepted command line arguments are:
 ```
 autorun.exe --profiles PROFILENAME1 {PROFILENAME2 PROFILENAME3 ...}
```
{} means: Optional

When you specify these command line arguments, the launcher will be no interactive, that means, load and execute each profile automatically, with no need of user interaction.

For example:
```
autorun.exe --profiles MYPROFILE
```
The launcher, on startup, will load the profile MYPROFILE and execute the server automatically.

#### A2. How to execute more than one KF2 server on same computer
You need one profile per server. Each profile should contain a different server name to be identified. Further more, each profile must have different ports eachother.

For example: Two Servers on same computer
- PROFILE1: Server name: My Server 1; Ports: 8080, 7777, 27015
- PROFILE2: Server name: My Server 2; Ports: 8081, 7778, 27016

_Steps (interactive way)_:
- Start the launcher
- Load profile PROFILE1
- Launch server
- Load profile PROFILE2
- Launch server

_Steps (no interactive way)_:
- Create a shortcut with destiny:
```
autorun.exe --profiles PROFILE1 PROFILE2
```
- Execute the shortcut

#### A3. Play music when the launcher is executed
The launcher will play, on startup, music files placed in folder AutoPlay\Music. Accepted formats are: .mp3, .ogg, etc.
The music will be played in random order and in a loop.

### Author notes
I hope you can find useful this application.

By a gamer for gamers :)
