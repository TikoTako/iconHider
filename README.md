# iconHider

### Simple program that hide/show the icons of Windows desktop.

## Summary
  - [Usage](#usage)
  - [Workaround](#workaround)
  - [Built With](#built-with)
  - [Authors](#authors)
  - [License](#license)

## Usage
The help will show up in case of opening it with dbclick, anyway:
<br />The program require one of the following parameters:

    -test
    -api
    -hax
example:

    iconHider.exe -hax

| Parameter | Description |
|:-:|:-|
|-test|Just print out all the child of the desktop, nothing more.|
|-api|hide/show the icons using the windows api.|
|-hax|workaround to hide/show the icons (for some reason the api don't work)|
<br />

## Workaround
For some reason "SHGetSetSettings" don't work (tested on two windows 10 with different build).<br />
So the workaround is to hide "SysListView32" but as you can see from the two screenshot "SHELLDLL_DefView" can be a child of "Progman" or "WorkerW", there's also more than one "SysListView32" so teh solution was iterate directly all the children window of the desktop to find the only one that has also a title "FolderView".

![Progman](https://raw.githubusercontent.com/TikoTako/TikoTako/main/img/progman-shell-syslist%20%5Bstatic%20wallpaper%5D.JPG)

![WorkerW](https://raw.githubusercontent.com/TikoTako/TikoTako/main/img/workerw-shell-syslist%20%5Bstatic%20and%20slideshow%5D.JPG)


## Built with
* Visual Studio Code
* Microsoft C++ (MSVC) compiler

## Authors
  - **TikoTako** - [TikoTako](https://github.com/TikoTako)

## License
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
