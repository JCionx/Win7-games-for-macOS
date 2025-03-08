# Win7-games-for-macOS
> A wineskin wrapper for the classic Windows 7 games for macOS

<img width="1000" alt="banner" src="https://github.com/user-attachments/assets/3f006ee0-441d-40ef-9915-dd930262769a" />



## Installing

1. Download the latest release from the [releases page](https://github.com/JCionx/Win7-games-for-macOS/releases)
2. Extract the zip and move the extracted folder to your Applications folder

## Building

### 1. Creating the wrapper
1. Install the [Kegworks app](https://github.com/Kegworks-App/Kegworks)
2. Open the app and download the latest engine and wrapper
3. Click on "Create New Blank Wrapper"
4. Call your wrapper something like "Windows 7 Games"
5. After the wrapper is created find it in Finder
6. Get the original game files from the WinAero website or from a genuine Windows 7 installation image
7. Open the app that was generated
8. Install the WinAero executable or copy the game files over
9. If you get a message asking to choose an executable, quit KegworksConfig from the dock

### 2. Patching the games
Install Resourse Hacker (run it through wine, Whisky or CrossOver).
Right click the generated app and click on Show Package Contents.
Find the directory where the games are installed.
Repeat the following instructions for each game:
1. Open the game.exe file in Resourse Hacker
2. Click on Action > Add from a Resource file
3. In the dropdown "Files of type" select "All files (*.*)"
4. Go inside the en-US folder and select the game.exe.mui file
5. Click on "Overwrite" and select all boxes except for MUI
6. Click on Import and then save
7. Under the MUI folder, delete all entries
8. Finally save again and close
9. In the game folder, delete the game_original.exe file and the en-US folder

### 3. Delete unnecessary files
There are some folders we won't need for our wrapper that can take unnecessary storage. These are some you can delete safely:
1. App/Contents/SharedSupport/wine/share/wine/mono
2. App/Contents/SharedSupport/wine/share/wine/gecko
3. App/Contents/SharedSupport/wine/lib/wine/i386-windows
4. App/Contents/Frameworks/GStreamer.framework
5. App/Contents/Frameworks/renderer

With this process, I got my app from 1.81GB down to just under 800MB

### 4. Create shortcuts for each game
Open the KegworksConfig app under App/Contents.
Then click on the Advanced button and go to the Tools tab.
Repeat the following instructions for each game:
1. Click on "Custom EXE Creator"
2. Insert the name of the game and locate the path to the executable
3. Change the icon if you want to
4. Click on Save

### 5. Create relative symlinks for each game
Create a folder where you will have all of the games.
Move the generated app to that folder.
Now follow these instructions for each game:
1. Open a terminal and navigate to the folder
2. Run this command: `ln -s "generated_app.app/Contents/game_name.app" "game_name"` (be sure to use the parentheses)

## Copyright Disclaimer
The classic Windows 7 games included in the releases are copyrighted by Microsoft Corporation. This project does not claim ownership of the games, nor does it sell or license them. Read the [LICENSE](https://github.com/JCionx/Win7-games-for-macOS/blob/main/LICENSE) file for more information.
