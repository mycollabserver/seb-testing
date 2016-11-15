**SEB 2.1.2 for macOS Release Candidate Version**

Here you can find the current pre-release build of the next release of SEB for macOS. You can support us by testing the pre-release version and give feedback in our forum or by creating an issue here on our GitHub page. 

New in SEB 2.1.2 (was first versioned 2.1.1.1) for macOS:
- Fixes a bug when a browser window wasn’t scaled correctly to fit the screen (it was placed in the lower left screen corner, mainly off-screen) when only one screen is connected and the „useBuiltin“ setting is false.
- Fixes a bug when the main browser window stayed open (with setting don’t allow switching to third party apps) when starting SEB by opening a config file (with setting allow switching to third party apps). The window couldn’t be manually closed and stayed in the foreground (as a „zombie“ window, caused by a timing problem when the window gets the close command while it’s still being opened).
- To solve the latter problem and improve usability generally, SEB now doesn’t open the Start URL from its persitent client settings when SEB was started by opening a config file or by opening a seb(s):// link. In this case the opened settings are directly loaded, in case loading or decrypting isn’t successful (load error, canceled by the user, wrong decryption credentials etc.), SEB is quit instead of starting up with the persistent client settings.
- Fixed visible screen area was being wrong calculated, not considering correctly if the SEB dock was visible on that screen. This also caused the temporary browser window for authentication not to be moved up when the user moved it underneath the SEB dock. 
- Fixed this calculation when no main browser window is open yet (when starting SEB by opening a seb(s):// link from a authenticated server and only the temporary browser window is opened).
- Now opening the main browser window, the SEB dock and the temporary browser window when starting SEB by opening a seb(s):// link from a authenticated server always on the main screen as defined by settings (not macOS).
- Fixed a bug when SEB could kill itself when a space switch occurred.

New in SEB 2.1.1 for macOS:
- Compatible with macOS 10.12 Sierra.
- Implements support for embedded TLS/SSL & CA certificates and certificate pinning.
- SEB is now using a private clipboard, so utilities running in the background and Universal Clipboard (on macOS 10.12 Sierra) cannot be used to paste text into exams (can be disabled if using third party applications in a securely managed user account).
- WebAudio API is enabled now. 
- Added blocking panels and windows opened by third party tools running in the background.
- Added detection for ScreenSharing.
- Added deactivating display mirroring and a new setting option for a maximum number of displays which the user is allowed to use. This can prevent wireless displays to be used to cheat or leak exam content.
- Now supporting Basic/Digest and NTLM Authentication.
- Loading seb(s):// linked settings from authenticated servers is possible now, even with indirect links (not containing the config file name with the .seb extension, like for example sebs://example.com/download.php?id=2352). The login session is remembered, therefore students don't have to login twice in SEB if you start SEB/an exam using a seb(s):// link to a config file on an authenticatated server.

Fixed bugs:
- On a trackpad supporting Force Touch, the lookup feature (invoked by strongly pressing the trackpad while the cursor is over a word or text selection) was not blocked with the settings option "Allow dictionary look up" disabled.
- Fixed full screen media player app can take over screen if started with the keyboard play key: If iTunes or another media player app supporting media control keyboard keys is maximized to full screen and quit, pressing the play key on the keyboard starts that app and moves it to the foreground, even if SEB is running. The media player app cannot be operated properly as SEB blocks this, but returning to SEB is a bit tricky: Move the mouse cursor to the upper screen edge. Then the window toolbar appears and shows the green window minimize/exit from full screen button on the left. Pressing the green button exits the media player app from full screen and SEB takes the screen over again.
- Fixed a WebKit related bug which occured in older WebKit versions (if running on an older system than OS X 10.11) and with malformatted DOM elements. For example the navigation buttons in a Moodle 1.8 quiz if running SEB 2.1 on OS X 10.10 or older didn't work properly.
- Fixed various minor issues.