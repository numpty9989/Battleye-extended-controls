# BattlEye-Extended-Controls

BattlEye-Extended-Controls (BEC) is a program created by nuxil/Stian Mikalsen. This utility was
created for ArmA 2 and ArmA 3 to take advantage of the Rcon protocol and provide tools for game
server owners and administrators. BEC while originally made for ArmA 2 and ArmA 3 still works just
fine for DayZ SA since the Rcon protocol has not changed much.

# Installation

Download Repo, Add to TCA.Mods in master game fles of Dayz. 
Once done go to your config and setup the mod. you need to create the mod with 3 editable files

```
Bans.txt (BEC Added Bans).
Config.cfg (BEC Config) Make sure you add the relevant variables for IP and port (game port, not    query).
Scheduler.xml (Default one sets up 4 hour restarts with messages  before the at 15 mins 10 mins 5 mins and 1 min before the restart and auto shuts down the server.. Tcadmin then starts it back up)
```

you will need to add these to your hosts file located in 

```
C:\Windows\system32\drivers\etc 
```
###open with notepadd ++ or any relevent program NOT WORDPAD or Notepad 

```
127.0.0.1 ibattle.org
127.0.0.1 www.ibattle.org
```

# Scheduler

The Scheduler is an extremely powerful tool that comes with BEC. This tool allows you to schedule
tasks such as automated messages, automated shutdown, ETC. The Scheduler is configured via the
Scheduler.xml file.

The Stock File is Setup to Restart the server Every 4 Hours using the #SHUTDOWN Command (perfect for Hosting COmapnies)

If you Host your server yourself you can just change shutdown to >LOCATION OF START BATCH FILE<

and ensure that the start bat has a Kill script EG 

```
START BAT

start kill.bat
CD Server Location 
start DZSALModServer.exe -ip= -port=2302 "-config=serverdz.cfg" "-bepath=\Battleye" -profiles=\instance" "-mod=" - "-autoinit" -dologs -adminlog


KILL.BAT

taskkill /IM DZSALModServer.exe

```


# UPDATE BATCH FILE

Update your batch file with the installation of BEC, you MUST UPDATE your start bat by adding 
```
-F
```

If the BEC Crashed bofore actually connecting to your server EG Mods take too long to load server as BEC wil only connect when it get s to reading mission part of UI. for server.. add 

```
--dsc
```

