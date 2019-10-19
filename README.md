![Team Sleipnir](http://teamsleipnir.is/wp-content/uploads/2018/02/Logo_svartir-stafir_2017-1.png "Team Sleipnir")

## Formula Student dashboard, telemetry and communications controller.

### Description

Multiple controllers are combined into one Visual Studio 2017 solution. Class references are depended on the main solution file. The microcontroller code is written in Arduino standard for the Teensy 3.x boards. For the build, Visual Micro extension for Visual Studio, Arduino IDE patched with Teensyduino needs to be installed. See readme for individual projects for detailed information.

Getting Started:
Linux:
Step 1: Create Workspace (If you already have a ws skip this):
mkdir ru_racing_ws && cd ru_racing_ws
Step 2: Clone repository to ws:
git clone https://github.com/RU-Racing-Team/communications_system.git
Step 3: Submodules:
git submodule init
git submodule update

This clones the FlexCAN_Library to the workspace. The library is needed to replace the original FlexCAN Library of your teenyduino installation.
Step4: Copy FlexCAN_Library to your arduino:
First we need to remove the original FlexCAN Library:
rm -r ~/<your-arduino-path>/hardware/teensy/avr/libraries/FlexCAN/*

Then we need to copy the new library to the old folder (assuming you are in the ws folder):
cp FlexCAN_Library/* ~/<your-arduino-path>/hardware/teensy/avr/libraries/FlexCAN/

Now you should be able to upload your code using the arduino IDE. It is currently not possible to upload directly from Visual Studio Code.