# Learn Flutter By Building a Simple Interactive App

## Title and Objectives

**Tech used:** The chosen technology for this project is Flutter, a framework that uses the Dart programming language. A programming language provides the words used to write code, while a framework provides the structure that uses those words to build applications.

**Reason for choice:** I chose Flutter because it allows the use of a single codebase to build the same app across Android, iOS, web, and desktop platforms, which saves time, effort, and cost. 

**Objective:** The objective of this project is to use AI as a learning aid to understand Flutter and build a simple app that displays the text “Hello Flutter” on the screen.


## Quick Summary of the Technology

Flutter is an open-source framework that was developed by Google and first released in 2018 to help developers create applications for various platforms such as mobile, web, and desktop using a single codebase.. Flutter has its own programming language named Dart, where developers can create all their application logic. All that is rendered on the screen using widgets.

Flutter is fast, easy to use even for beginners, and has a uniform appearance regardless of the device being used. Also, it has a feature called hot reload, so whatever is being coded can be seen instantly. It is popularly used by applications such as Google Pay and Alibaba.


## System Requirements

**Operating System:**  
- Ubuntu 24.04 LTS (Linux)

**Tools / Editors:**  
- Flutter SDK  
- VS Code (or any code editor)  
- Web browser (Chrome)

**Packages Installed:**  
- curl  
- git  
- unzip  
- xz-utils  
- zip  
- libglu1-mesa


## Installation & Setup Instructions

1. Open terminal and run:
```bash
 sudo apt update
sudo apt install curl git unzip xz-utils zip libglu1-mesa
```
- zip/unzip/xz-utils are needed to extract the Flutter SDK.
- libglu1-mesa provides graphics support required for the app to display on your screen

2. In your home directort, clone Flutter:
```bash
cd ~
git clone https://github.com/flutter/flutter.git
```
- This creates a folder called flutter that contains the Flutter SDK.

3. Open the .bashrc  file which runs everytime the terminal is opened:
```bash
nano ~/.bashrc
```

4. Add the flutter path:
```bash
export PATH="$PATH:$HOME/flutter/bin"
```

5. 4.Save using CTRL + O then enter. Then exit using CTRL + X

6. Reload terminal settings to acknowledge Flutter commands: 
```bash
source ~/.bashrc
```

7. Verify installation:
```bash
flutter doctor
```
- The command checks what tools are installed, missing or OK.
- Key installations:  Flutter SDK, Android Studio, Linus desktop, and web.
- For a simple flutter app, only Flutter SDK and Web installations are required..

8. Navigate to your project folder: 
```bash
cd Development_1/code/phase-5/flutter_beginne_-toolkit
```
**Note:** Flutter does not support - in folder names. Use _ instead

9. Create the flutter project:
```bash
 flutter create
 ```
 - The "." at the end tells Flutter to create the project in the current folder. Note that the project folder contains everything needed to run the app, like the Linux setup, Web setup and libraries, config files. Codes are however written in the lib/main.dart file.

10. To confirm that the project folder is successfully created, run:
 ```bash
 flutter run -d chrome
 ```
 - It opens the default Flutter counter app in the browser with a number increasing when the  plus button is pressed. 

11. Open the VSCode. Navigate into lib folder and open the main.dart file

12. 11.Delete the default countet app code

13. Replace with the code that runs your application

14. Save the file and run:
 ```bash
  flutter run -d chrome
  ```
  - The browser should display the **Hello Flutter!** text  with a button **Press Me** which when pressed, the text changes to **Flutter is interactive!** in bigger font and blue color. 

## Minimal Working Example

### Description

  A simple Flutter app that shows text “Hello Flutter!” and a button. Pressing the button changes the text, its color, and size to demonstrate basic interactivity and UI customization.
  
### Code
```bash
  // Widget that displays the text in the center of the screen
  Text(
  text, // Current text: "Hello Flutter!" initially, changes when button is pressed
  style: TextStyle(
    fontSize: changed ? 32 : 24, // Font size 24 initially, 32 when changed
    color: changed ? Colors.blue : Colors.black, // Black initially, blue when changed
    ),
  ),
```

### Expected output

**Initial:** “Hello Flutter!” in black, font size 24, button below.
**After pressing button:** Text changes to “Flutter is interactive!”, color becomes blue, font size 32. Pressing again toggles back.

## AI Prompt Journal
### Prompt 1

**Prompt used:**


