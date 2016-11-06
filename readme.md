#128T Log Viewer

This plugin for Sublime Text 3 will color-highlight log files from 128 Technology routers.

Before:
![128T log file as plain text](https://cloud.githubusercontent.com/assets/3319094/20034510/aa763a28-a396-11e6-9c51-7ea28e8d3405.png)

After:
![128T Log Viewer](https://cloud.githubusercontent.com/assets/3319094/20034513/d46d6702-a396-11e6-9e89-52ed22b70e55.png)

This plugin is very heavily based on the [Colorcoder plugin](https://github.com/vprimachenko/Sublime-Colorcoder) by Valerij Primachenko.

##Installation

Right now: Download the [zipped-file](https://github.com/hadrielk/Sublime-128T-Log-Viewer/archive/master.zip) and unzip it. Name the resulting folder "128T Log Viewer". Copy that folder to your Sublime Text Packages directory - you can find the Packages directory by choosing the `Sublime Text`▶`Preferences`▶`Browse Packages`. On a Mac, this would be `/Users/<username>/Library/Application Support/Sublime Text 3/Packages` directory. I have no idea what it is on Windows/Linux.

Eventually: Download the plugin via [packageControl](https://sublime.wbond.net/).

To properly work 128T Log Viewer needs an appropriately modified color scheme. On the first run the plugin will try its best to automatically modify your current scheme. :grey_exclamation: the plugin will not actually modify the scheme but create a modified copy in a new directory called "128T-Log-Viewer" and apply it - note this directory is not the same as the ony you created if you installed manually using the zip file.

You can use `Tools`▶`Packages`▶`128T Log Viewer`▶` Tweak Log Viewer on current color scheme` (or <kbd>CTRL</kbd><kbd>SHIFT</kbd><kbd>P</kbd> it) to modify the colors a bit (you can change the lightness and saturation).


##Uninstalling

Uninstalling will cause Sublime Text to generate an error about a missing color scheme file. That's because your User settings for Sublime Text have been changed to use the 128T Log Viewer's color scheme instead of you original. So go to `Sublime Text`▶`Preferences`▶`Settings`, and in the User ones remove or comment out the "color_scheme" setting line. Your original color scheme should in that User settings under "original_color_scheme" - you can change the name of this to "color_scheme" and everything should be right as rain.


##Options
You can turn the highlighting off per view via `View`▶`128T Log Viewer this view`.

The 128T Log Viewer also might slow down the editor when highlighting huge files, so it will turn itself off once the file has exceeded the `max_size` (the check happens when you save the file or reactivate the view). You can force it to highlight the file nevertheless via said menu item (which will read `Colorcoding may hurt performance, File is large` now)

Default (faster) highlighting method makes the undo work letterwise, you can change this by setting `use_fast_highlighting_but_undo_typing_letterwise` to false. The 128T Log Viewer will then use alternative engine, which does not interfere with undo, but work somewhat slower on large files. You might want to tune `max_size` lower then.

Finally :exclamation: if you use some plugins which change the color scheme based on time, or filename, or modify the schemes you better turn the `auto_apply_on_scheme_change` off, or the plugin conflict may result in an endless loop which will lock the editor. You can always change the settings even when Sublime Text is not running.
