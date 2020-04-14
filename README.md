Inspired by: [diehardsk/Volumio-OledUI](https://github.com/diehardsk/Volumio-OledUI)

## This is the Python3 version of [Maschine2501/Volumio-OledUI](https://github.com/Maschine2501/Volumio-OledUI/)

# NR1-UI

Im building a Network Hifi Receiver from scratch.
An old Braun T2 Tuner serves as case for the player.
To keep as much as possible from the look of the device i needed an Interface for Volumio.
And especialy one that supports a 3,2" ssd1322 SPI Oled with 256x64Pixel.
After doing some research i found diehrdsk/Volumio-OledUI.
It fullfills many points on my "wishlist" but not nearly all.
As we all know, the way is the destination, i spent some time (much time....) in modifying the original code.
Unfortuneatly luma.oled does not support Python2 anymore.
So this ist the new version, now depending on python 3.5.2

The project is not finished yet... but close the the goal!

## Features of Maschine2501/NR1-UI:

* 4 Button Interface (Button function depends on "State" of the screen, e.g. playback, menu...)
* 1 Rotary with button (function also depends on "State")
* Playback Screen with Artist, Song, file-format, samplerate and bitdepth
* Standby-Screen with Time, Date and IP-Adress
* 3 Menu Screens (Media-Library, Playlists, Queue)
* Button-Layout-Icons on each Screen (depending on "State")
* Media-Library-Information Screen (Statistics about your Media-Library -> Artists, Albums, Songs, total Playtime)
* Boot and Shutdown Logo
* maybe more features will come... ^^

* Some bugs will (not often) happen. Will debug it soon.

## To-Do: 

* Tune the whole UI (fonts, positions... etc.)
* Maybe integrate "CAVA" to display a bargraph spectrum? (hot topic!!!)

## Allready Done:

* Standby-Screen (when Playback is stoped, Time, Date and IP is Displayed)
* Automatic stop when playback is paused (value could be defined / declared)
* display Fileformat/Samplerate/Bitdepth in the NowPlayingScreen
* Scroll Text stops before shown completly -> text was defined as scrollText, which makes "black"-boxes arround the text
* one rotary removed
* 4 more Buttons via GPIO (needs some fine tuning)
* MediaInformationScreen (volumio.local/api/v1/collectionstats)
* Icons for the function of each button, depending on "state"
* migration to Python 3.5.2

## Demo Video from nightly-build (05.03.2020):

[![Video-Sample](http://img.youtube.com/vi/9TtgO0_KqNk/0.jpg)](http://www.youtube.com/watch?v=9TtgO0_KqNk "Video-Sample")

## Why is the first part of the display empty?

The cutout in the front of the device is smaller as the ssd1322 display -> so the display actually don't use the first 42 pixels.

![hifi-tuner case](https://i.ibb.co/WpsSd5z/Entwurfszeichnung-NR1-500px.jpg)

## [Project on Volumio-Forum](https://forum.volumio.org/256x64-oled-ssd1322-spi-buttons-rotary-interface-t14098.html#p72945)

## But you want it on the whole Display?

Simply change the value's from "42" to "0" (self.text1Pos = (42, 2))... that's it! (Tutorials/Guides will follow...)

## [installation steps (stable release)](https://github.com/Maschine2501/Volumio-OledUI/wiki/Installation-steps-(stable-release))

## [installation steps (nightly build)](https://github.com/Maschine2501/Volumio-OledUI/wiki/Installation-steps-(nightly))

## Check the logs

#### for the stable build

sudo journalctl -fu nr1ui.service

#### for the nightly build:

sudo journalctl -fu nr1ui-nightly.service

## [Hints](https://github.com/Maschine2501/Volumio-OledUI/wiki/hints---tricks---nice-to-know)

## [wiring / button-layout / truthtable](https://github.com/Maschine2501/Volumio-OledUI/wiki/Wiring---Button-Truthtable)

### [hardware](https://github.com/Maschine2501/Volumio-OledUI/wiki/Hardware)

### [dependencies](https://github.com/Maschine2501/Volumio-OledUI/wiki/Dependencies)

### [Sources & font-info](https://github.com/Maschine2501/Volumio-OledUI/wiki/Sources---font-information)

