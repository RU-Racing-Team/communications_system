![Team Sleipnir](http://teamsleipnir.is/wp-content/uploads/2018/02/Logo_svartir-stafir_2017-1.png "Team Sleipnir")

## Formula Student dashboard, telemetry and communications controller.

### Description

Multiple controllers are combined into one Visual Studio 2017 solution. Class references are depended on the main solution file. The microcontroller code is written in Arduino standard for the Teensy 3.x boards. For the build, Visual Micro extension for Visual Studio, Arduino IDE patched with Teensyduino needs to be installed. See readme for individual projects for detailed information.

## Getting Started:
## Step 1: Installation of Arduino and teensyduino
### Linux:
### Arduino IDE:
Simply download the current arduino version from the [Arduino Download Page](https://www.arduino.cc/en/Main/Software).

After downloading the arduino IDE move it to a new folder, e.g. ~/Arduino:
```
mkdir ~/Arduino
mv ~/Downloads/<file-name> ~/Arduino
```

Extract the files:
```
tar xvf <file-name>
```
This should create a new folder in the Arduino folder. cd into it:
```
cd folder-name
```
And finally execute the installation script:
```
sudo ./install.sh
```

If you have problems with the installation see the [official installation guide](https://www.arduino.cc/en/guide/linux)
### Teensyduino:
All information can be found [here](https://www.pjrc.com/teensy/td_download.html#linux_issues).

To install Teensyduino you need to generate udev rules. The udev rule is in this repository called 49-teensy.rules. You can either copy the file manually from the repository or clone the repo before proceeding (See Step 2). Assuming you created the file (in whichever way) copy it to your udev rules folder:
```
cp 49-teensy.rules /etc/udev/rules.d/
```
Download your os matching file from [here](https://www.pjrc.com/teensy/td_download.html#linux_issues).

To install teensyduino you need to make the downloaded file executable first and then execute it:
```
cd ~/Downloads
sudo chmod +x <file-name>
./<file-name>
```
This should start the installer. After finishing the installation (this should go pretty quick) continue to the next steps.

### Windows
# Here somebody else should write something up since I have not the slightest clue ;)

## Step 2: Set Up Workspace and Arduino IDE:
### Linux:
### Create Workspace (If you already have a ws skip this):
```
mkdir ru_racing_ws && cd ru_racing_ws
```
### Clone repository to ws:
```
git clone https://github.com/RU-Racing-Team/communications_system.git
```
### Submodules:
```
git submodule init
git submodule update
```

This clones the FlexCAN_Library to the workspace. The library is needed to replace the original FlexCAN Library of your teensyduino installation.
### Copy FlexCAN_Library to your arduino:
First we need to remove the original FlexCAN Library:
```
rm -r ~/<your-arduino-path>/hardware/teensy/avr/libraries/FlexCAN/*
```

Then we need to copy the new library to the old folder (assuming you are in the ws folder):
```
cp FlexCAN_Library/* ~/<your-arduino-path>/hardware/teensy/avr/libraries/FlexCAN/
```

Now you should be able to upload your code using the arduino IDE. It is currently not possible to upload directly from Visual Studio Code.

### Windows:
# Would be great if a windows user could write something up!
