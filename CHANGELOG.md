# 0.2.4.1

## Bug fixes

* Fixed issue that would cause the program to crash when the artwork file was already existing in the target folder.
* Fixed issue [#73](https://github.com/Otiel/BandcampDownloader/issues/73) that would stuck the downloads in an endless loop when downloading a cover art failed.
* Fixed issue that would report an incorrect number of tries when downloading a cover art failed.

# 0.2.4.0

## New features

* Added {album}, {year}, {month} and {day} placeholders to the file name format. [#72](https://github.com/Otiel/BandcampDownloader/issues/72)

## Bug fixes

* {month} and {day} placeholders are now formatted on two digits; for instance: "05" instead of "5".

# 0.2.3.0

## New features

* Added an option to disable notifications sound (off by default). [#71](https://github.com/Otiel/BandcampDownloader/issues/71)

## Bug fixes

* Fixed race condition [#54](https://github.com/Otiel/BandcampDownloader/issues/54) that would make the program crash when downloading two albums with the same name.
* Fixed issue with albums name too long to be supported by Windows.

# 0.2.2.0

## New features

* Added an option to download through a specified proxy. [#70](https://github.com/Otiel/BandcampDownloader/issues/70) You can choose between:
  * No proxy.
  * The system proxy.
  * A manually configured HTTP/SSL proxy.

## Improvements

* Tracks size download is now done asynchronously in order to speed up the process. For instance, when downloading 124 albums, we got the following results:
  * Before: downloading tracks size took 33m30s.
  * Now: downloading tracks size takes 2m30s.

## Bug fixes

* Fixed issue [#65](https://github.com/Otiel/BandcampDownloader/issues/65): the total downloaded size reported when downloads were finished was wrong under some circumstances.
* Fixed the exponential back-off mechanism that forced to wait 200ms (with default settings) before the first download try.
* Fixed issue that would prevent the cover art to be saved in the folder when "☑ Convert to jpg" was unchecked.
* Fixed issue that would prevent the settings file to be correctly saved after clicking on "Browse".
* "☑ Download artist discography" was (un)checkable during downloads. No more.

# 0.2.1.0

_Notes to upgraders:_

* The settings file format has changed, so some of your settings may be reset.

## New features

* Added an option to empty tags from the downloaded files.
* Added an option to disable checking for updates at startup.
* Added a button to check for updates.

## Improvements

* Various UI improvements.
* Log file will be archived to `BandcampDownloader.0.log` if its size exceed 1MB. Only one archive log file will be kept.
* Updated dependencies to their latest version.

## Bug fixes

* Fixed issue [#69](https://github.com/Otiel/BandcampDownloader/issues/69) that prevented from downloading albums that have no cover.
* After selecting a folder via the "Browse" button, the placeholders were lost. The default placeholders will now be added back.

# 0.2.0.0

_Notes to upgraders:_

* The settings file has changed, so your settings will be reset. You can delete your old `BcDlSettings.json` that will be replaced by `BandcampDownloader.ini`.
* DLL files are now packed inside the EXE file. You can delete the DLL files you had next to `BandcampDownloader.exe`.

## New features

* Added separate settings for the cover art downloaded in folder and the one saved in tags. [#64](https://github.com/Otiel/BandcampDownloader/issues/64)
* Lyrics can be saved to tags when available. [#42](https://github.com/Otiel/BandcampDownloader/issues/42) Thanks @ajsnyde!
* You can now choose which tag should be saved (artist, title, album...) or not.
* Added an option to remove comments from tags.
* Added an option to reset settings to their default values.
* The log is now saved to a file: `BandcampDownloader.log`.

## Improvements

* Settings are now displayed on their own window.
* Added advanced settings to the UI. [#46](https://github.com/Otiel/BandcampDownloader/issues/46) No need to edit your settings file anymore. Thanks @ajsnyde!
* Log is now automatically scrolled if position is at the end. "☑ Auto scroll log" option has been removed.
* DLL files are now packed inside `BandcampDownloader.exe`.
* Updated dependencies to their latest version.

## License

* License has changed from [WTFPL](http://www.wtfpl.net) to MIT. See the [LICENSE](https://github.com/Otiel/BandcampDownloader/blob/master/LICENSE) file for details.

# 0.1.9.3

## Improvements

* Updated Json.NET and ImageResizer libraries to their latest version.

## Bug fixes

* Fixed issue [#40](https://github.com/Otiel/BandcampDownloader/issues/40) that prevented downloads of track when their name was too long.
* Fixed issue [#21](https://github.com/Otiel/BandcampDownloader/issues/21) that prevented downloads of one-album artists when "☑Download artist discography" was checked.

# 0.1.9.2

## New features

* Added an option to skip retrieved the track size [#27](https://github.com/Otiel/BandcampDownloader/issues/27). Progress is then based on the downloaded files count. Thanks @ajsnyde for implementing this!
* Added an option to stop scrolling the log [#29](https://github.com/Otiel/BandcampDownloader/issues/29). Thanks @ajsnyde for implementing this!

## Improvements

* UI revamp. Thanks @M4lik for working on this!
* Updated Json.NET and ImageResizer libraries to their latest version.

# 0.1.9.1

## Bug fixes

* Fixed issue [#34](https://github.com/Otiel/BandcampDownloader/issues/34) that prevented to download albums or tracks that contained whitespaces in their name.

# 0.1.9.0

## New features

* Added a confirmation dialog on closing the application when there are active downloads [#28](https://github.com/Otiel/BandcampDownloader/issues/28)

## Bug fixes

* Fixed the issue that prevented the application to download the cover arts [#31](https://github.com/Otiel/BandcampDownloader/issues/31) [#33](https://github.com/Otiel/BandcampDownloader/issues/33)
* Fixed the issue that caused the application to crash when the album name was too long [#22](https://github.com/Otiel/BandcampDownloader/issues/22)

# 0.1.8.0

## New features

* Added placeholder for {year}, {month} and {day} (album release date) that can be chosen for the download location. Thanks @kaktus313 for implementing this!
* Added support for system proxy. Thanks @Aljenci for implementing this!

## Improvements

* The default settings are now using the exponential back-off algorithm in order to prevent Bandcamp to throttle the downloads. Values can be tweaked in the settings file if you encounter some issues.

# 0.1.7.0

## New features

* Added support for track pages (http://[artist].bandcamp.com/track/[track]) [#18](https://github.com/Otiel/BandcampDownloader/issues/18)
* Added option in config file to modify the file naming scheme [#17](https://github.com/Otiel/BandcampDownloader/issues/17)

Thanks again to @ajsnyde!

# 0.1.6.1

## Bug fixes

* Fixed issue [#15](https://github.com/Otiel/BandcampDownloader/issues/15) that prevented BandcampDownloader to correctly save the cover art files.

# 0.1.6.0

## New features

* Added a new functionality to check for updates when starting the application.

# 0.1.5.2

## New features

* Songs can now be downloaded under a artist/album folders architecture.
* An exponential back-off system has been implemented in order to bypass Bandcamp anti-spam filter. By default, this mechanism will not be used, you have to manually edit your settings file.
* BandcampDownloader now checks if files are already present in the download folder in order to prevent to download twice the same files in case an error occurred and the downloaded has been restarted.

## Improvements

* The maximum number of tries when a download fails is now configurable.

Huge thanks to @ajsnyde for implementing all these new features!

# 0.1.5.1

## Bug fixes

* Fixed issue [#9](https://github.com/Otiel/BandcampDownloader/issues/9) that prevented BandcampDownloader to retrieve the artwork file size. Thanks @dashWo for fixing this!

# 0.1.5.0

## New features

* Added option to save the current settings to a file (named BcDlSettings.json, located next to the .exe file). Settings are automatically loaded when starting the application.

# 0.1.4.3

## Bug fixes

* Fixed issue [#1](https://github.com/Otiel/BandcampDownloader/issues/1) that prevented BandcampDownloader to find the correct url to download tracks.

# 0.1.4.2

## Improvements

* Updated Json.NET and ImageResizer libraries to their latest version.

# 0.1.4.1

## Improvements

* The "Description" field of the ID3 tag containing the cover art is now set to "Picture".

# 0.1.4.0

## Improvements

* Added confirmation dialog when user clicks on "Cancel".
* Added option to hide verbose log messages (uncheck ☑ Verbose).
* BandcampDownloader now retries (up to 10 times) to download a track if it previously failed (this seems to happen a lot when downloading a lot of albums in the same session).
* Minor UI changes.

# 0.1.3.0

## New features

* Added functionality to resize cover art.

# 0.1.2.4

## Bug fixes

* Minor fix (tabstops were wrong).

# 0.1.2.3

## Improvements

* The cover art was downloaded even if both checkboxes ☑ Save cover art in tags and ☑ Save cover art in folder were unchecked. Not anymore.

# 0.1.2.2

## Improvements

* Got rid of unneeded references, resulting in one less file in bin files.

# 0.1.2.1

## Improvements

* Cover art is now deleted when it was only temporarily saved.

# 0.1.2.0

## New features

* Added progress in Windows 7 taskbar.

## Bug fixes

* Fixed encoding issue.

# 0.1.1.1

## Bug fixes

* Fixed a bug on the saving of the cover arts.

# 0.1.1.0

## New features

* Added option to download all albums of an artist.

# 0.1.0.1

## Bug fixes

* Fixed a bug that caused the application to crash when the user does not have rights to write in the downloads folder.

# 0.1.0.0

This is the first release of BandcampDownloader.