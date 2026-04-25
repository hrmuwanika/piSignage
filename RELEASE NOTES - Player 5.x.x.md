# Release Notes for piSignage Player2 (4.x.x and 5.x.x)

This document covers Player2 — the rewritten player line that started at version 4.6.0. It spans the 4.x.x series and the current 5.x.x series.

For the original (legacy) player notes, see [RELEASE NOTES - Player 3.x.x.md](<RELEASE NOTES - Player 3.x.x.md>).
For server-side notes, see [RELEASE NOTES - Server.md](<RELEASE NOTES - Server.md>).

---

## Player2 (version 4.x.x onwards)  

### 5.4.2/5.4.3   

1. Fixed - Issue of Wifi credentials with special characters not working in 5.4.1
2. Disable pi-player for now and map "mpv" to vlc with no-gap support
2. Upgrade pdf.js to 5.5.207(latest) and use that to show PDF slide show instead of evince player(which is based on X)
3. In lower models of Pi, HDMI interface was not detected after video -> image transition - Fixed
4. Screenshot support for GNOME-WAYLAND configuration of Debian/Ubuntu players
5. Added 32 bit Trixie support for lower models of Pi as 64 bit was running into resource issues

### 5.4.0/5.4.1

1. Bookworm OS upgrade to latest version for player images 5.1.2/5.2.0/5.3.2 and fixing broken updates
2. New 5.4.1 image based on Trixie (**needs SD card re-imaging**)
3. Playlist plays once instead of looping in certain cases - fixed
4. Crontab issues while group settings TV on/off selected - fixed
5. Audio
   - Fixed audio volume setting and default audio issues
   - Audio player for lounge music and audio assets changed to VLC from mpv
   - Issue of playing radio streams - fixed
6. Rewritten network-config using nmcli commands
   - Fixed network-config issues for static IP, DNS and wifi power management
   - Improved UI for Ctrl+N menu
   - Better reporting of network checks
   - Fallback AP behaviour when known wifi is not available to connect
   - Fixed unreliable wifi in some cases (wifi power management off)
7. Player2 scripts update
   - Fix issues while detecting Window Manager, Display Manager, Display Server
   - Wider support for Debian/Ubuntu versions
   - Hide panels to avoid white/black strips on top and bottom of the screen
   - Disable keyring popups
8. Weblinks fixes
   - Not getting closed in some cases after the duration - fixed
   - Page zoom issue - fixed
   - Added Translate flag to avoid Chromium popups
   - Support for adding custom Chromium flags - refer https://help.pisignage.com/hc/en-us/articles/54869730944537-How-to-Add-Custom-Chromium-Flags-on-Raspberry-Pi-PiSignage
9. YouTube play
   - Avoiding popups for allow camera by disabling portal services
   - Update yt-dlp for VLC YouTube support
   - Fixed known YouTube play issues
10. PDF play
    - Avoid crashes
    - Slide show support issues in Trixie - fixed
11. Performance improvements
    - State logic occupying too much memory in lower models - fixed
    - VLC flag issue fixes for different versions on Wayland
    - Non-play of certain videos - fix color-space issue after downloading videos
    - VLC play issues for Pi 3/Pi Zero 2W - fixed
    - Introduced a new GStreamer-based pi-player (when mpv is selected), still under beta
12. New image format support
    - Support for AVIF and WebP image formats
13. Licensing/download issues when the server name contains "/" at the end or installation name - fixed
14. Log flooding issues for RSS error and CEC mismatch - fixed
15. Send hardware info to the server


### 5.3.5
1. Fixed - After YouTube video playlist stops advancing
2. Fixed - Popups for translate and camera access sometimes appearing

### 5.3.4
1. Fixed - CEC not working after HDMI enable on TV on event, restarting the player to enable CEC upon TV on event

### 5.3.3
1. Fixed - certain case TV on/off not working

### 5.3.2
1. SD Card image supporting all models of Pi (*32 bit only for Pi 0,Pi 0 W,Pi 0,2W, 1,2*)
1. BETA - Introduce non-chromium linux players for Image, Text, Video and PDF players for Pi zero, Pi 1, Pi 2 models (32 bit Raspberry OS only)
1. Remove gap between PDF slides in presentation mode (evince player)
2. Fixed - RSS feed of few sites was not working
3. Fixed - Issue with Access point not working

Known issue

- While playing youtube video a camera allow popup may appear on the srreen. Issue following command on piShell/terminal &
reboot to avoid this(will be fixed in the next release)   
  `echo '--use-fake-device-for-media-stream' > /home/pi/.config/chromium-flags.conf` 
### 5.3.1
1. Fixed - 5.3.0 update causing screen not occupying full screen and toolbar being seen
2. Fixed - HDMI interface on/off issue present in 5.3.0 version
3. Ability to change boot log - copy splash.png to /boot folder
4. player-config.txt based configuration support on every boot (not just first boot)
5. Fixes for image generation

### 5.3.0
**Please note, this updates all bookworm OS based players(5.x.x platform version) to latest OS release dated Nov 2024 
and to a new Window Manager labwc, update may take 15-30 minutes**

1. New Window Manager labwc - supports widgets on front of the screen like ticker, logo, emergency message, clock etc.
2. Wayland windowing system support for Raspberry Pi 3 and Pi Zero models
2. Brings back support to kiosk, webpage link confined to zones and hardware widget support
3. Tile mode for 2 screens support is enabled for 5.x.x players
4. Autodetection of HDMI interfaces and reconfigures within 30 seconds
5. Support for SD card based configuration in player-config.txt file in the boot partition on every boot (not just 
   first boot)
6. Fixed - player update failing in some cases and player becoming unuseable
7. Fixed - Rare race condition causing repeated downloads
8. Fixed - cast icon showing up in videos

### 5.2.4
1. Update to latest OS release dated 28 Oct 2024
2. Remove labwc-prompt from autostart after upgrade

### 5.2.3
1. Fixed - Older version of bookworm players showing blank screen on poweron or stuck on pi logo 

### 5.2.2
1. Videos not playing when VLC is selected under group - Fixed
2. Applying OS updates

### 5.2.1
1. SD card image release support using Raspberry OS Debian 12 (bookworm) dated 4 July 2024
2. Supports both 64bit OS and 32bit OS with support for Pi 5,4 and 3 models
3. Support for both wayfire and X11 window managers
4. This release supports 4 zone weblink,PIO and interactive feature support on legacy relases based on bullseye OS(4.
   9.x, 5.1.0-legacy) 

### 5.2.0
1. Added support for 64bit bookworm OS (needs a new SD card image of 5.2.0)
1. Weblink positioning in case of multi-zone playlist - fixed (use zoom factor of 1 only)
1. Player webUI - start the last playing playlist on poweron
1. Mirrored the second HDMI port in case of 2 displays connected
1. More robust display detection and resolution detection
1. Support for GPIO based playlist play and media control keys (fwd,prev,pause/play)
   - More details at [GPIO media control instructions](https://github.com/colloqi/piSignage/blob/master/GPIO%20media%20control%20Instructions.md)
1. Support added for the Interactive features to be introduced soon

### 5.1.5
1. piSignage using lower resolution when switched on when TV is OFF - fixed
   - Fixed resolution at 1080p when TV settings are not readable, for more details please refer to 
     [TV Resolution issues](https://help.pisignage.com/hc/en-us/articles/32635692383641-piSignage-screen-displays-at-a-lower-resolution-or-incorrect-resolution-on-TV)
### 5.1.4
1. Login screen/piSignage restarting issue in case of weblinks - fixed 
   - bookworm OS upgrade as per https://forums.raspberrypi.com/viewtopic.php?p=2211369#p2211361

### 5.1.3
1. In case of session crash auto-restart, not all previous pisignage related programs were getting closed - fixed
2. When emergency message is empty, small rectangle is shown on center of screen - fixed
3. Added chromium flags to avoid browser metrics collection

### 5.1.2
1. Login screen appearing after some time while displaying weblinks - fixed using workaround of autologin
2. Disable AP issues for image 5.0.5 - fixed
3. Unable to set DNS and Static IP from player webUI - fixed
4. Added "vc4.force_hotplug=1" to cmdline.txt to emulate HDMI always connected
5. Removed unnecessary gtk.css 
6. Startup logo changed to more subtle one
7. When default playlist is combined with a multi-zone playlist, other zones are copied from scheduled playlist 1 to 
   default playlist zone so that non-main zones start playing from the beginning

### 5.1.1
1. Uopdates Raspberry OS  - sudo apt update && sudo apt full-upgrade
   - Fixes login screen issue when monitor is siwtched off (https://github.com/raspberrypi/bookworm-feedback/issues/217) 

### 5.1.0
1. Fixed - Wifi needing second configuration after connecting to server
1. Bookworm (5.0.5) release - CEC functionalities improved and screen off support added
1. Bookworm (5.0.5) release - force browser widgets only  
1. Fixed - Player name change was not reflected in hostname of device
1. Unlimited Browser crash messages in log - fixed
1. Recent OS updates for both bookworm and legacy releases pushed to player
1. Other bug fixes

### 5.0.6
1. Ticker not working properly - fixed
2. Hardware widgets for clock, logo and emergency message disabled to avoid flickering while changing assets

### 5.0.5
1. Wifi AP not reflecting player ID - fixed
2. Welcome screen to update connection status and IP address periodically

### 5.0.4
1. Wifi AP name was not reflecting last 4 digits of player ID - fixed
2. Auto connect to wifi was not working on poweron - fixed

### 5.0.3
1. cursor was showing up in 5.0.1 image - fixed

### 5.0.2
1. Player continuous crash (and not starting) in case of video file being added using "Add asset to playlist" feature
   under assets tab and the playlist is played in non-main zone - Fixed

### 5.0.1
1. New image based on Raspberry Bookworm release to support Pi 5 and Pi 4
   - Bookworm OS/wayland architecture
   - Upgraded nodejs to v20 and npm packages to latest(security updates)
   - ES6 module support
   - Hardware ticker and widgets moved to wayland/wayfire from X/mutter window manager
   - Network Manager added instead of dhcpcd for network management
   - Browser based PDF reader instead of evince program
   - Moved TV control (CEC) program to cec-ctl from cec-client
   - See [known issues](https://help.pisignage.com/hc/en-us/articles/26593998005785)
2. Fixed - webpage link show getting stuck and slide show not progressing
3. Fixed - ticker message showing "null"
4. Fixed - certain crashes making display black 
5. Fixed - issue of download in progress message appearing when hide system messages option was selected

### 4.9.5
1. Fixed issue of ticker not scrolling

### 4.9.4
1. Imported fixes from Android app branch for the issues faced
   - Video play/stop issues
   - Use screen parameters instead of innerHeight and innerWidth for resolution in templates
   - Fixes for stop Video for adverts
2. Fixed rare issue of two players having the same ID
3. API for showing Emergency message in full screen for player
4. Change server command from server to facilitate server name change of player from server
5. Force TV ON disable was not working - fixed
6. Added app install logic for player2 for customer app installation
   - Write code and upload as pisignage-app.zip to assets folder
   - This gets copied to /home/pi/pisignage-app folder after unzip
   - Entry point is start-app.sh which is executed on every poweron 

### 4.9.3
1.Avoid download of the file to player when timestamp is not new and content length is same

### 4.9.2
1. fix for download error (MEDIA_SETTINGS_SLICE not defined)

### 4.9.1
1. Including .htm extension for html files

### 4.9.0
1. Make greater resolution of the 2 (HDMI-1, HDMI-2) connected TVs as promary display
2. YouTube play support when the default player is selected using YouTube API
3. Reading TV power status and sending ON/OFF command as needed - added
4. Reporting CEC TV status as well CEC support status to server - added
5. Support for play-once option for keyboard playlists
6. Audio getting restarted every cycle - fixed
7. Auto-detect https/http protocol for server when not specified
8. Kiosk mode -propagate mouse events from inside iframe
9. custom_layout issue fixes
10. Playlist name missing in player tab during TV_OFF - fixed
11. Added 5 week scheduling support
12. wifi:  support for space character in SSID
12. Update install script for more platforms and fixed non-starting of piSignage on power on in few platforms
13. OS and yt-dlp upgrades along with software upgrade
14. Fixed few crashes, scroll bar in few cases

### 4.8.2/4.8.3
1. Making https as default for pisignage server for wget download
2. Fixing the issue of wifi Access Point disable as selected from Group settings
3. Support for both horizontal and vertical flip
4. Flickering due to double playlist change being called on power-on
5. Black screen when asset does not exist instead of skipping - fixed 

### 4.8.1
1. Advertizement video playling issue - resolved
2. Issue with break video duration to play adverts in between - resolved
3. Domination playlist duration incorrect - issue resolved
4. RTSP transport defaults to UDP for mpv option
5. Gap between CEC command "as" after "on"

### 4.8.0
1. Updates the Raspberry OS with apt full-upgrade command(takes around 10 minutes)
2. Disable auto-fill in kiosk and other forms
3. Added temperature and uptime support
4. Support VLC for You-tube videos as well
5. Several bug fixes

### 4.7.5
1. Handling of more cases to get available resolution like disconnected displays, resolution not available from
   xrandr etc.
2. Fixed issues related to TV ON/TV OFF and monitor resolution change operations
3. Browser crash in  cases where resolution is not available from screen - fixed
4. Avoid continuos pings to websocket of crashed browser
5. Continuous mediaCompletionPromise errors in forever_err.log - fixed 
6. Scheduling issue when start and stop time span across days - fixed
7. Playlist not getting scheduled sometimes during player poweron and tv on - fixed
8. Modified piShell history (up-arrow button) to include new commands like xrandr
9. Added adavanced settings for player webUI
10. Set system volume using Pulse Audio utilities
11. Use System audio output and volume for all audio and video players  (mpv,vlc,chromium)
12. Reboot everyday feature not working - fixed 
13. VLC video play - 5sec file caching added to avoid gaps between videos

### 4.7.4
1. webpage link and kiosk launch issue with 4.7.3 - fixed
2. Player webUI, wifi access points were not detected - fixed
3. Always use VLC player for mkv extensions(H.265) irrespective of video player selection
4. Zone size corrections for mpv,vlc for portrait mode
5. Welcome screen, emergency message and clock sizes based on screen resolution

### 4.7.3
1. Scheduling issue when start and stop times cross midnight - fixed
2. White label support for ticker message in case of non-license added
3. mpv option not playing in Rsspberry Pi - fixed

### 4.7.2/4.7.1
1. Dual display support 
   - Use 2c/2d/2bp layout, side or bottom layout is mapped to the second screen 
   - Use 4K for single screen mode to play 4K videos
   - Use mirror in case of 2 displays and need to duplicate the content
2. Video play a long gap - fixed
3. screenshot not working in Intel platforms - fixed
4. Side zone weblink not killed in some cases - fixed
5. Added resolution change watch to take care of TV resolution change after poweron

### 4.7.0
1. Support for 2 display in Pi 4 - mirror mode (content is replicated in both screens) and 4K mode (adds 4kp60 and 
   turbo_mode flag for vlc,single display only) 
2. Support for http headers in weblink (webpage type) for authentication support
3. Monitor resolution change, cable insertions and auto resolution adjustment 
4. Non-main zone asset flickering when main zone asset changes - fixed
5. After TV_OFF, playlist will not start - fixed
6. Fixed issues like playlist restart after API play, sleep times etc., logo title visibility
7. mpv -  audio fixes and added hwdec=auto flag for other platforms
8. Logo - text display issue fixed
9. Better handling of primary display when more than single display exist

### 4.6.5  
1. Black screen on boot-up in devices which do not have Ethernet interface
2. Few Keystrokes not working for weblink - fixed 

### 4.6.4  
1. YouTube Streaming support for mpv player using yt-dlp
2. Support for spaces in wi-fi access point name
3. keypress playlists support for player2, fixes in keycode for x86 architecture
4. Fixed issues with nodejs exit for license loading/settings change, event playlist, online playlists

### 4.6.3
1. Sleep and reboot were not resetting after set - Fixed

### 4.6.2
1. Checking and opening http websocket connections (in place of https websocket) for local servers when needed
2. Reducing unnecessary delay during upgrade process (using old node module packages wherever possible)
3. YouTube URL normalization for fullscreen autoplay from various share URLs
4. Download returning error if robot.txt is not present - Avoided & Fixed 
5. Locking of application and dark screen if browser load event was not  received - fixed

### 4.6.0
1. This player uses new code base, based on learnings of all these years and to take care of newer technologies of 
   Raspberry Pi OS.
2. Also, portable across various Linux Single Board computers, web platforms and Android PWA.
3. First version released for general availability with feature set of 3.1.1 as reference (there are few features 
   missing like keyboard playlists which will be documented soon)
