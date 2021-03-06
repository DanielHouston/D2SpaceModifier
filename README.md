# DotA 2 Space Modifier: A Single Hotkey, not a Script

![image](https://cloud.githubusercontent.com/assets/19603023/26280395/13386eb0-3d97-11e7-8611-253684316744.png)

### What is this?
A single hotkey that allows for [this](https://github.com/Karrandalf/D2SpaceModifier/tree/master/1.%20Karrandalf's%20Keyboard%20Layout) (triple keyboard layouts). It unlocks the entire <kbd>WINDOWS</kbd> modifier key in DotA 2 and rebinds it to <kbd>SPACE</kbd>. This allows for a second modifier for use in triple keyboard layouts. Previously, [Loopuleasa's master branch](https://github.com/loopuleasa/Dota2-TheCore-Config-Engine) was broken by Valve's limits to `autoexec.cfg` in the [May 24th, 2016 patch](http://store.steampowered.com/news/22017/). This project is a fork of the former and restores most of its functionality by utilizing just one AHK bind (a few optional ones are available for read in the [" Source code " folder](https://github.com/Karrandalf/D2SpaceModifier/blob/master/Source%20code/D2SpaceModifier.ahk)):

    ~*Space::ControlSend, , {LWin Down}, Dota 2 
    *Space Up::Send {LWin Up}
    
*Simply put, this hotkey hides all down key presses of the left Windows key from the operating system and ALL applications EXCEPT* `dota2.exe`*.* <kbd>SPACE</kbd> retains full functionality. This hotkey is all that is needed to make <kbd>SPACE</kbd> into a modifier just like <kbd>ALT</kbd>. This is because Valve already had the <kbd>WINDOWS</kbd> keys setup to work as modifiers. The only reason they could not be utilized before was because Windows shortcuts would "Alt-tab" the user out of DotA. This single rebind to <kbd>SPACE</kbd> fixes the issue.

## To Install

*Only Supported on Windows Operating Systems*

1. Place `D2SpaceModifier.exe` inside of the " %APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup " folder. Optionally and if [AutoHotKey](https://autohotkey.com/) is installed, use the `.ahk` inside the " Source code " folder instead.

2. Place the `autoexec.cfg` inside of " Steam\steamapps\common\dota 2 beta\game\dota\cfg " and overwrite if necessary.

3. Select a triple keyboard layout from the numbered folders or create a custom one. I recommend [my personal layout](https://github.com/Karrandalf/D2SpaceModifier/tree/master/1.%20Karrandalf's%20Keyboard%20Layout).

4. Place the " 570 " folder inside of " Steam\userdata\[Your 9 digit Steam ID here] " and overwrite.

5. Restart the computer. `D2SpaceModifier.exe` will run in the background but will be inactive unless DotA 2 is running and "Alt-tabbed" into.

6. Launch DotA 2 and customize. I manually tick the following options in-game as they cannot be transfered in config files:
    * Shop Search Gets Focus Upon Open
    * Use Extra Large Minimap
    * Display Network Information
    * Enable console
    * Bring Dota 2 to front when match found
    * Bring Dota 2 to front when pick phase begins
    
    *Note: The <kbd>SPACE</kbd> modifier reads <kbd>WINDOWS</kbd> in-game.*

## To Uninstall

1. Delete the files pasted in the " Game ", " 570 ", and " StartUp " folders.

2. Reset the keybinds.

## Known Bugs

1. Self-cast abilities which are auto-castable are self-casted when the auto-cast hotkey is pressed.
Only affects Ogre Magi, Lich, and neutral troll priests. This is a **Valve bug**.

## Frequently Asked Questions

**Why does double-tap to self-cast or change wards not work?**

That is intended behaviour for this super compact layout inorder to prevent miscasts. <kbd>Alt</kbd>+<kbd>Key</kbd> should do self-cast or switch wards. Furthermore, double-tap self cast is impossible if you are using quick casts.

This was done by reducing the self cast timeout tolerance to zero. The way double-taping works now is by using the *Smart Double-Tap* in-game option (hold <kbd>Alt</kbd> and press an item or ability's hotkey).

**Are the keys rebindable in-game?**

The binds of almost everything can be changed using the default in-game UI.

A few keys require edits to `user_keys.vcfg` in the " Steam\userdata\[Your 9 digit Steam ID here]\570 " folder.

**Does <kbd>CAPSLOCK</kbd> still do what it usually does, even if it's a keybind?**

No, the [fifth line](https://github.com/Karrandalf/D2SpaceModifier/blob/master/Source%20code/D2SpaceModifier.ahk) disables <kbd>CAPSLOCK</kbd>. It can stil be bound using the in-game UI.

**How do I pick a modifier other than <kbd>SPACE</kbd>?**

[AHK](https://autohotkey.com/) must be installed. Edit `D2SpaceModifier.ahk` in the " Source Code " folder by replacing the word "Space" in the [third and fourth lines](https://github.com/Karrandalf/D2SpaceModifier/blob/master/Source%20code/D2SpaceModifier.ahk) with whatever key you want such as "x" (here is a list of some [keys with unique names](https://autohotkey.com/docs/KeyList.htm)). Place the edited script in the " StartUp " folder instead of the `.exe` (or compile a new executable). Restart the computer and finish installation and tweaking as usual.

**Why is Roshan quiet?**

It is easier to hear enemy units whilst killing Rosh. You can change this by editing the [first line](https://github.com/Karrandalf/D2SpaceModifier/blob/master/autoexec.cfg) of `autoexec.cfg` to

    dota_silent_roshan	0

**Why do some of my commands not trigger?**

That must be because of your non-standard keyboard. You should consider changing your keyboard layout to standard English in Windows options.

**Is this bannable?**

Remember, this is not a script. It is one hotkey that allows `dota2.exe` to see the Windows key press whilst blocking it from the OS and every other application. I have played 1000+ games and have not been banned. There exists AHK scripts that are bannable, but those are much more than a hotkey rebind.

**Do you personally use the** `.ahk` **or** `.exe`**?**

I used the `.ahk` during development and the executable in post-development, long-term testing.

**Can the Windows key be disabled using registry edits and then used as a modifier?**

The `dota2.exe` will not be able to see the key press.

## Made a cool keyboard layout and want to share it?

Contact me on reddit at [u/karrandalf](https://www.reddit.com/message/compose/?to=Karrandalf), and I might add it to the main repository, crediting you.
If you know how to use git, just fork this repo and request a merge using a pull request.
