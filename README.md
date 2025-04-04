Hackintosh Chime Boot Sound

Carillon is an open source OS X app, specifically for Hackintosh machines, that plays the classic "Chime" boot sound on startup that real Macs have.
A new launch daemon will be added that triggers the sound, meaning, unlike most similar apps, this one runs much earlier during the boot process, even before the login screen appears. No crappy AppleScript solution that triggers when you're already on the Desktop, no outdated PrefPane
It has currently been tested on macOS 15 Sequoia and macOS 14 Sonoma but it should work on previous and future versions as well. Please report any issues you may have.

VIEW HIDDEN MAC FILES

defaults write com.apple.Finder AppleShowAllFiles true
killall Finder

defaults write com.apple.Finder AppleShowAllFiles false
killall Finder


MANUAL INSTALLATION

/System/Library/LaunchDaemons/com.hackintosh.sound.plist

/System/Library/Sounds/


MANUAL ACTIVATION

sudo chown root:wheel /usr/local/bin/Chime.aiff

sudo chown root:wheel /Library/LaunchDaemons/com.hackintosh.sound.plist


UNINSTALL

To uninstall Carillon, remove the following files from your system:

/System/Library/LaunchDaemons/com.hackintosh.sound.plist

/System/Library/Sounds/Chime.aiff.

————————

/usr/bin/afplay

afplay is an audio playback library for Rust, based on the psst.core audio playback implementation.

ThrottleInterval: 2

StartInterval means that the program should be started after x seconds (more or less precisely). macOS Sonoma o macOS Sequoia

————————


NOTES
This should work for everyone using USB audio adapters and/or AppleHDA.kext for the sound. If you're using another kext to get your sound working, please let me know.

To edit the Package installer, you need PackageManager, which comes in the Auxiliary Tools bundle, which you can download here PlistEdit Pro
While this should work just fine on a real Mac, I would not suggest installing it on one.

I'm aware that "chime" doesn't exactly classify as "carillon", but I liked the name, so deal with it. 

