*Project no longer maintained*

This project was for ST2.  It appears ST3 has changed to http://www.sublimetext.com/docs/3/syntax.html for syntax definitions so you may not need to edit the built in language definitions anymore, yay!

License: WTFPL

Old readme below:

Sublime Whitespace Coloring
===========================
This is based on the advice from facelessuser & nick on the [Sublime Forums][1] and will give you greater control over the look of your whitespace.

Below are 3 examples in Monokai: 

1. The default Sublime theme of Monokai
2. An example illustrating the colors
3. The included theme

![Whitespace examples][example]

To use this theme you will need to modify each of your syntax language files such as `Packages/Ruby/Ruby.tmLanguage`. To get to your packages folder in Sublime goto Preferences -> Browse Packages and search for your language. You will need to do this for each language you wish to customize (CSS, HTML, JavaScript, etc).  In your tmLanguage file search for the following `patterns` block, it should be close to the top:

    ...
    <string>Ruby</string>
    <key>patterns</key>
    <array>
      <dict>
        ...

Insert the following between `<array>` and the first `<dict>`:

    <dict>
      <key>match</key>
      <string>^[\s\t]+</string>
      <key>name</key>
      <string>meta.whitespace.leading</string>
    </dict>
    <dict>
      <key>match</key>
      <string>[\s\t]+$</string>
      <key>name</key>
      <string>meta.whitespace.trailing</string>
    </dict>
    <dict>
      <key>match</key>
      <string>[\s\t]+</string>
      <key>name</key>
      <string>meta.whitespace</string>
    </dict>

Next copy the `Monokai Whitespace.tmTheme` to your `User` folder.  In Sublime goto Preferences -> Browse Packages -> open the `User` folder in your file system.  Finally select the new theme with Preferences -> Color Scheme -> User -> Monokai Whitespace.tmTheme

If you wish to customize your own theme with whitespace coloring/transparency add the following in the .tmTheme of your choice:

    <dict>
      <key>scope</key>
      <string>meta.whitespace.leading</string>
      <key>settings</key>
      <dict>
        <key>foreground</key>
        <string>#75715E00</string>
      </dict>
    </dict>
    <dict>
      <key>scope</key>
      <string>meta.whitespace.trailing</string>
      <key>settings</key>
      <dict>
        <key>foreground</key>
        <string>#FF0000</string>
      </dict>
    </dict>
    <dict>
      <key>scope</key>
      <string>meta.whitespace</string>
      <key>settings</key>
      <dict>
        <key>foreground</key>
        <string>#75715E75</string>
      </dict>
    </dict>

This is using the Monokai Comment color of `#75715E` with transparency settings on the end of `00` and `75`.  For trailing whitespace it is using a simple red.  Adjust as desired.

[1]: http://www.sublimetext.com/forum/viewtopic.php?f=3&t=6161
[example]: https://github.com/ckovey/sublime-whitespace-coloring/raw/master/example.png
