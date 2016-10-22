#128T Log Viewer

This plugin for Sublime Text 3 will color-highlight log files from 128 Technology routers.

This plugin is heavily based on the [Colorcoder plugin](https://github.com/vprimachenko/Sublime-Colorcoder) by Valerij Primachenko.

##Installation
Download the plugin via [packageControl](https://sublime.wbond.net/).

To properly work 128T Log Viewer needs an appropriately modified color scheme. On the first run plugin will try its best to automatically modify your current scheme. :grey_exclamation: the plugin will not actually modify the scheme but create a modified copy in its own directory and apply it. 
You can use `Tools`▶`Packages`▶`128T Log Viewer`▶` Tweak Log Viewer on current color scheme` (or <kbd>CTRL</kbd><kbd>SHIFT</kbd><kbd>P</kbd> it) to modify the colors a bit (you can change the lightness and saturation).
Colorcoder also needs a "good" language definition, which it does not activate automatically but leaves you the choice to do so, read below for more.


##Options
You can turn the highlighting off per view via `View`▶`128T Log Viewer this view`.

The 128T Log Viewer also might slow down the editor when highlighting huge files, so it will turn itself off once the file has exceeded the `max_size` (the check happens when you save the file or reactivate the view). You can force it to highlight the file nevertheless via said menu item (which will read `Colorcoding may hurt performance, File is large` now)

Default (faster) highlighting method makes the undo work letterwise, you can change this by setting `use_fast_highlighting_but_undo_typing_letterwise` to false. The 128T Log Viewer will then use alternative engine, which does not interfer with undo, but work somewhat slower on large files. You might want to tune `max_size` lower then.

The 128T Log Viewer allows you to specify white- and blacklist for file-types to highlight: the settings are `enabled_for` and `disabled_for`. If `enabled_for` is present in the config only those file-types will be highlighted, `disabled_for` won't be highlighted even if present in whitelist.

Finally :exclamation: if you use some plugins which change the color scheme based on time, or filename, or modify the schemes you better turn the `auto_apply_on_scheme_change` off, or the plugin conflict may result in an endless loop which will lock the editor. You can always change the settings even when Sublime Text is not running.
