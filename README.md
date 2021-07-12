# Hi, welcome to my CSGO config.

[My Steam-Profile](https://steamcommunity.com/id/MordorsElite/)

This config will likely get updated from time to time. You can also suggest new additions. To get an easy overview of all the commands, type `info` in console after installing and running the autoexec.

## In this repository you will find:

| File-Name    | Content-Description                      |
|--------------|------------------------------------------|
|knife_configs | Folder filled with a config for each knife-type |
|.gitignore | Only relevant for Github |
|readme.md   | This explanation of the configs |
|autoexec.cfg  | My personal autoexec |

## How to use
Unfortunately, having individual knife-configs is necessary, as the command to drop a knife cannot be writen as an alias command.

To make use of both the autoexec and the knife commands, paste the file and folder into here:
```
C:\Program Files (x86)\Steam\steamapps\common\Counter-Strike Global Offensive\csgo\cfg
```
Please leave the knife files inside the 'knife_configs'-folder, the autoexec expects to find them in there.

To activate them either restart CSGO or enter `exec autoexec` in console. To test if everything's working, just enter `info` in console - a big list should now appear. It will tell you about most of the important stuff the config can do.

# Adjusting settings to your preference

## Simple settings

For most settings (like mouse-sensitivity), just changing the value will be sufficient. If you dont know what a particular setting does, [this website](https://totalcsgo.com/commands) provides a full list including descriptions.

## Complicated settings

Others might need some understanding of how this config works. 

### _Crosshairs and Viewmodels_

Crosshairs and viewmodels are set up in such a way that executing a single command (for example `crosshair_01`) in console changes all crosshair/viewmodel settings at once. To see how it works, these commands are implemented at part 5.1 / 5.2 of the config. 

If you want to put your current viewmodel/crosshair into my config, I have included a blank for both. They can be found at the end of 5.1 and 5.2 respectively (`viewmodel_XX` and `crosshair_XX`). Simply adjust the values under those headers. You can now use them by entering `viewmodel_XX` or `crosshair_XX` in console. To set them as default, swap them into the commands in part 5.0 of the config.

To find your current crosshair settings, paste and execute this command in the csgo-console:
```
con_enable 1; clear; con_filter_enable 1; con_filter_text cl_crosshair; developer 2; con_filter_text_out Achievements; host_writeconfig config; con_filter_text ""; developer 0;
```

To find your current viewmodel settings, paste and execute this command in the csgo-console:
```
con_enable 1; clear; con_filter_enable 1; con_filter_text cl_righthand; developer 2; con_filter_text_out Achievements; host_writeconfig config; con_filter_text viewmodel; host_writeconfig config; con_filter_text cl_bob; host_writeconfig config; con_filter_text ""; developer 0;
```

To implement more than one viewmodel or crosshair, just copy the blank and swap the XX-Parts in the aliases for numbers. I have already used viewmodel 01 and 02, as well as crosshair 01 to 05. But dont worry, you'll figure it out ;)

### _Keybinds_

Changing the keybinds for the most part is a simple matter of changing the commands for each bind in config-part 5.3. You can get a complete list of all keybinds and their functions by entering `allbinds` in the console.

Some explanation might still be needed thought. 
* Per default, the movement keys will remove decals like bloodstains and bulletholes. This is great for deathmatch. However, in competative games you might miss out on some info because of it. In order to disable this feature, just type `mk` in the console. That way only they Q-Key will remove decals. 
* The microphone is bound to P, but I have bound a button on my mouse to P. So if you want to use your keyboard to activate the mic, you should probably change that one
* Jumpbind is set to Z, which for me is another mouse-sidebutton
* The I-Key toggles between the defalt- and nadecrosshair
* The L-Key toggles voice_loopback on or off (good to figure out if your mic works at the start of a game)
* If your teammates stand in front of you, their nametags might get in the way of your vision, with the O-Key you can toggle their nametag- and weaponry-display

## Config Syntax

If you haven't worked with CSGO-Configs before, here is some basic syntax.

| Syntax | Meaning |
|--------|---------|
| `// x` | Comment x will not be seen as a command |
| `alias "x" "y;z;"` | Entering x in console executes command y and z |
| `bind "a" "x"` | Pressing a on your keyboard will execute command x |
| `toggle commandX y z` | Toggles the value for commandX between y and z |

More complicated commands can be achieved, by using one alias to execute several others in succession. For exmaple, the `info` command.

If you want to write a more complex toggle, you can use two aliases to represent each side and one that points at one of them. After each execution of the main alias, it gets redirected to the other toggle as demonstrated below:
```
alias "example"  "+example;"
alias "+example" "say x; alias example -example;"
alias "-example" "say y; alias example +example;"
```

#

# Video-Config

These are my video settings. To my knowledge, these can not be included in the autoexec.

```
"VideoConfig"
{
	"setting.cpu_level"		"0"
	"setting.gpu_level"		"3"
	"setting.mat_antialias"		"2"
	"setting.mat_aaquality"		"0"
	"setting.mat_forceaniso"		"2"
	"setting.mat_vsync"		"0"
	"setting.mat_triplebuffered"		"0"
	"setting.mat_grain_scale_override"		"-1.000000"
	"setauto.gpu_mem_level"		"2"
	"setting.mem_level"		"2"
	"setting.mat_queue_mode"		"-1"
	"setauto.csm_quality_level"		"3"
	"setting.mat_software_aa_strength"		"0"
	"setting.mat_motion_blur_enabled"		"0"
	"setting.mat_texturestreaming"		"0"
	"setting.r_player_visibility_mode"		"1"
	"setauto.mat_enable_uber_shaders"		"1"
	"setting.defaultres"		"1440"
	"setting.defaultresheight"		"1080"
	"setting.aspectratiomode"		"0"
	"setting.fullscreen"		"1"
	"setting.nowindowborder"		"0"
}

```
The video.txt file can be found here
```
C:\Program Files (x86)\Steam\userdata\YOUR-STEAM-ID\730\local\cfg
```
Also located there is the main config.cfg. If the autoexec isn't loaded automatically for some reason, you can add `exec autoexec` as last line into that file.

# Have fun using my config :)
