# dynmap-snapshotter
Use this script to assemble one large *snapshot* of your minecraft dynmap.



## Features 
- Automatic uploads of snapshot to discord server
- Set new background color with hex code
- Resize the output image 


## Usage
### **Taking a snapshot**
Capture a snapshot from the commandline
1. Download dynmap-snapshotter

2. Install dependencies<br/>
    `pip install pillow`

3. Run the script<br/>
    EITHER in interactive mode<br/>
    `python dynmap-snapshotter.py --interactive`
    
    OR set required arguments yourself<br/>
    `python dynmap-snapshotter.py --folder plugins/dynmap/web/tiles --world world --map flat`


4. Enjoy your snapshot <br/>
	Find your snapshot in the `snapshots` folder where `dynmap-snapshotter.py` was saved


### **Daily snapshots with crontab**
Use crontab to setup daily snapshots 
1. Open the crontab editor<br/>
    `crontab -e`

2. Create a new entry<br/>
	This will create a snapshot of world:flat every day at 00:00<br/>
	```
    0 0 * * * python /home/user/dynmap-snapshotter.py --folder /srv/minecraft/plugins/dynmap/web/tiles --world the_nether --map flat
    ```
    remeber to set your own arguments and flags

### **All arguments**
This is the help message for the script
```
> python dynmap-snapshotter.py --help

usage: dynmap-snapshotter.py [-h] [--folder FOLDER] [--world WORLD] [--map MAP] [--interactive] [--scale SCALE] [--fixed-tile-size FIXED_TILE_SIZE]
                           [--color-hex COLOR_HEX] 

optional arguments:
  -h, --help            show this help message and exit
  --folder FOLDER       specify the absolute path for folder where dynmap tiles are stored. this is usually [server folder]/plugins/dynmap/web/tiles.
  --world WORLD         world to take snapshot of
  --map MAP             map to take snapshot of
  --interactive         helps user decide arguments trough prompts
  --scale SCALE         resize the snapshot with a decimal point number
  --fixed-tile-size FIXED_TILE_SIZE
                        resize the snapshot with setting a new tile size
  --color-hex COLOR_HEX
                        hex value of color to apply to background.
```


## Credit

Thanks to https://github.com/GuyInGrey for helping me understand the dynmap api :)

Project inspired by https://github.com/xtotdam/dynmap-assemble