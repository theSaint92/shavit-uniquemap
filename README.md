# shavit-uniquemap
Plugin to support multiple servers for shavit-timer.

### How it works
It connects to the shavit database, and stores name of the current map in it. If map is currently played on another server connected to the same database it forces a mapchange. It prevents possible bugs with replays and player records.

### Installation
If you want to run multiple servers using same database you should :
1. Place `shavit-uniquemap.smx` in all connected servers
2. Make all servers using same shared folder for storing replay data.
    * If servers are running within same machine you can achive this by:
        * Creating joint folder and specifing path to it in your `configs/shavit-replay.cfg`
        For example for folder structure like this:
            ```
            /home/steam
            └───replaydata
            └───server1
            │   └───csgo
            └───server2
                └───csgo
            ```
            You would like to put `"replayfolder" "{SM}/../../../../replaydata"` on both of your servers
        * Creating soft link to `replaybot` folder on main server in according paths on other servers.
            * On Linux Servers by using `ln -s` command.
            * On Windows Servers by using `mklink /D` command or even better by using `mklink /J` which creates directory junction.
            
            For example for folder structure like above on Linux you would run : `ln -s /home/steam/server1/csgo/addons/sourcemod/data/replaybot /home/steam/server2/csgo/addons/sourcemod/data/replaybot`
    * If servers are running on different machines
    NOT TRIED YET! IF YOU KNOW HOW TO ACHIVE IT, PLEASE WRITE AN ISSUE
        