# FluidNC-Pendant-M5 Example

## Developer Setup Information

Download the appropriate [Visual Studio](https://code.visualstudio.com/download) for your development platform.

### OSX

How to setup OSX based Microsoft Visual Studio Code 2 (vsCode2) for FluidNC Pendant development. This example was tested on a M2 Macbook Air running Sonoma V14.2.1

Download the latest from Microsof [VSCode-darwin-universal.zip](https://code.visualstudio.com/docs/?dv=osx) and unzip it.

Now copy the contents to your applications folder

`cp -r ~/Downloads/Visual\ Studio\ Code\ 2.app /Applications`

Ctl-Click on the applicaton "Visual Studio Code 2" so that you can open a non-verified app.

On the menu bar, click **CODE->Check for Updates...**

If it's stuck in readonly mode, you will likely get a link to a slightly outdated [Read Only Mode Issue](https://github.com/microsoft/vscode/issues/7426#issuecomment-425093469)
To fix this, exit the application and do the following. Note the slight change of the **change extended attributes** (xattr) command to reflect the vsCode2 application name.

`xattr -dr com.apple.quarantine /Applications/Visual\ Studio\ Code\ 2.app`

Restart vsCode2 and ensure it can be updated.

### Windows 10/11

Download the latest from Microsof [VSCodeUserSetup-arm64-*.exe](https://code.visualstudio.com/docs/?dv=win32arm64user) and unzip it.

Launch vsCode2 and ensure it runs.

I have not tested this myself

## Adding the Platform IO IDE Extension to vsCode2

For working with various microprocessors with vsCode2 you need extensions that add the appropriate modules to the base vsCode2.

Proceed to **Code->Settings->Extension** and search for **“PlatformIO IDE”**

More details at [VS code Platform IO ESP32]((https://randomnerdtutorials.com/vs-code-platformio-ide-esp32-esp8266-arduino/#2)

Note: I also installed the "C/C++ Extension Pack".

## Loading code from GitHub
Now use the vsCode2 github integration to load the FluidNC Pendant code base

 `Ctl-Shift-G`

Enter the url for the FluidNC github Pendant code
 `https://github.com/bdring/PendantsForFluidNC.git`

Select a directory to place it into.

 
## M5Dial Pendant Example
 
From the left tab, click on the the PlatformIO button (alien head), then **Pick a Folder** `PendantsForFluidNC`, then select **M5Dial_Pendant**.

From the left tab, click on the the PlatformIO button (alien head) and a new menu with **Project Tasks** should be shown.

When you attempt the first build, the vsCode2 IDE will then use the `platformio.ini` file to configure the rest of the required development items. This is a one-time download.

Select the "Full Clean" then "Build"

On an M2 Macbook Air, a full clean build takes about half a minute.

Plug your M5 Dial into your development machine with a USB-C cable.

It's OK if you have not added the button hardware to the M5 Dial yet, but you will be limited in what you can do.

Select `Upload and Monitor` to connect to the M5 Dial over USB and to flash the newly built image. A new Terminal Window should appear in the IDE
and you should see various package information, dependencies, library and such scroll on the terminal. It will then attempt to connect via USB-C 
to the M5 Dial and flash the file system with the new image. The M5 Dial should reset and flash up the FluidNC logo and then go to the start page.



