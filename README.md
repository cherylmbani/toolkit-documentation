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

1. Open terminal and run:**
```bash
 sudo apt update
sudo apt install curl git unzip xz-utils zip libglu1-mesa
```
- zip/unzip/xz-utils are needed to extract the Flutter SDK.
- libglu1-mesa provides graphics support required for the app to display on your screen

2. In your home directory, clone Flutter:
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
 - The "." at the end tells Flutter to create the project in the current folder. **Note:** The project folder contains everything needed to run the app, like the Linux setup, Web setup and libraries, config files. Codes are however written in the lib/main.dart file.

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

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    // Dynamic text display
    Text(
      text,
      style: TextStyle(
        fontSize: changed ? 32 : 24,
        color: changed ? Colors.blue : Colors.black,
      ),
    ),
    
    // Spacing
    const SizedBox(height: 20),
    
    // Button that triggers state change
    ElevatedButton(
      onPressed: changeText,  // Calls method when pressed
      child: const Text("Press Me"),
    ),
  ],
)
```

### Expected output

**Initial:** “Hello Flutter!” in black, font size 24, button below.
**After pressing button:** Text changes to “Flutter is interactive!”, color becomes blue, font size 32. Pressing again toggles back.

## AI Prompt Journal
### Prompt 1: 

I am a junior software engineer with strong proficiency in JavaScript, React, Python, and Flask. I want to learn Flutter for mobile app development from scratch.

Please provide a comprehensive beginner's guide that covers:

1. What Flutter is and how it differs from React/React Native
2. The Dart programming language basics (syntax, data types, functions, classes) with comparisons to JavaScript
3. Core Flutter concepts: Widgets, Widget Tree, StatelessWidget vs StatefulWidget
4. The Flutter development environment setup (SDK installation, IDE setup, creating first project)
5. Project structure explanation (what each folder/file does)
6. How state management works in Flutter (setState, lifecycle methods)
7. Common Flutter widgets I'll use frequently (Text, Container, Column, Row, Button, etc.)

For each concept, please:
- Explain it in simple terms
- Show code examples
- Compare to React/JavaScript concepts where applicable
- Highlight what's different from web development

My goal is to understand the fundamentals before building my first app.

**AI's Response:**

Flutter is Google's framework for building mobile apps using the Dart language. It compiles directly to native code, making it faster than React Native. Everything in Flutter is a Widget, which is equivalent to React components.
Dart syntax is similar to JavaScript but with types. Here's how variables work:
```dart
String name = 'John';
var age = 25;
final city = 'NYC';
```
Functions use type annotations:
```dart
int add(int a, int b) => a + b;
```
Lists work like arrays:
```dart
List<String> fruits = ['apple', 'banana'];
```
There are two main widget types. StatelessWidget is like a functional React component:
```dart
class Hello extends StatelessWidget {
  Widget build(context) => Text('Hello');
}
```
StatefulWidget is like using useState. Here's a counter:
```dart
class _CounterState extends State<Counter> {
  int count = 0;
  
  Widget build(context) {
    return ElevatedButton(
      onPressed: () => setState(() => count++),
      child: Text('$count'),
    );
  }
}
```
Common widgets include Text, Container, Column, Row, and buttons.
To start, run flutter create my_app then flutter run. Your code lives in lib/main.dart and dependencies go in pubspec.yaml. State management uses setState to trigger re-renders. The main difference from web is no separate HTML or CSS, everything is nested Widget classes with styling in code.

### Prompt 2:

Please help me build a "Hello Flutter" app with these requirements:

FUNCTIONALITY:
- Display text that says "Hello Flutter!"
- Have a button labeled "Press Me"
- When the button is clicked:
  * The text changes to "Flutter is interactive!"
  * The font size increases from 24 to 32
  * The text color changes from black to blue
- Clicking again toggles back to the original state

LEARNING REQUIREMENTS:
Please provide:
1. Complete, working Flutter code (main.dart)
2. Step-by-step explanation of how the code works
3. Clean inline comments in the code
4. Detailed breakdown after the code
5. Relate concepts to React where possible (e.g., "setState is like calling the setter from useState")

Make sure the code is beginner-friendly, follows Flutter best practices, and helps me understand both Dart and Flutter simultaneously.

### AI's Response:

The app has three parts. MyApp is the root widget that wraps everything in MaterialApp, similar to your top-level App component in React.
HelloScreen is a StatefulWidget, which means it can change over time. Think of it like a React component that uses useState. It creates a separate State class to hold the actual data.
The State class (_HelloScreenState) holds a boolean variable isPressed that tracks if the button was clicked. This is like declaring const [isPressed, setIsPressed] = useState(false) in React.
The toggleText function changes the state by calling setState, which is exactly like calling setIsPressed in React. It flips the boolean and triggers a re-render.
The build method returns the UI. Scaffold provides the app structure with an AppBar at the top. The body uses Center and Column to arrange widgets vertically in the middle of the screen.
The Text widget displays different content based on isPressed using a ternary operator. It also changes fontSize and color dynamically. This is like conditional rendering in React with inline styles.
SizedBox adds vertical spacing between widgets, similar to adding margin in CSS. ElevatedButton is a material design button that calls toggleText when pressed, just like onClick in React.
When you click the button, setState runs, Flutter re-renders the widget, and you see the text, size, and color change instantly. Click again and it toggles back.

### Prompt 3:

I've learned Flutter basics and built a simple interactive "Hello Flutter" app. Now I need help with proper project setup and documentation.

Please provide:

1. A comprehensive README.md file that includes:
   - Project description and what the app does
   - Learning objectives
   - Prerequisites (Flutter SDK, IDE, etc.)
   - Detailed installation instructions for Windows, macOS, and Linux
   - Step-by-step guide on how to run the app (command line, VS Code, Android Studio)
   - Project structure explanation
   - How the app works (flow diagram or explanation)
   - Troubleshooting section for common errors
   - Customization ideas for practice
   - Resources for next steps
   - Special section for React developers transitioning to Flutter

2. Git setup guidance:
   - What files/folders to include in .gitignore for Flutter projects
   - Suggested commit message for the initial commit
   - Best practices for Flutter project version control

3. Development workflow tips:
   - How to use hot reload effectively
   - Debugging techniques
   - Testing the app on different platforms (Android, iOS, Web)
   - Performance optimization basics

### AI's Response

Simple Flutter app demonstrating state management and user interaction.
What It Does
Button toggles text between "Hello Flutter!" and "Flutter is interactive!" with size and color changes.
Prerequisites
Flutter SDK 3.0+, VS Code or Android Studio, Android emulator or iOS simulator.
Installation
Download Flutter SDK from flutter.dev. Extract and add to PATH. Run flutter doctor and fix issues.
Run the App
```bash
flutter pub get
flutter run
```

Or press F5 in VS Code.

**roject Structure**

- `lib/main.dart` - Your code
- `pubspec.yaml` - Dependencies
- `android/` and `ios/` - Platform configs

**How It Works**

StatefulWidget holds boolean state. Button press calls setState to toggle. Text widget reads state and updates styling.

**Troubleshooting**

- Command not found: Add Flutter to PATH
- No devices: Start emulator or connect device
- Build failed: Run `flutter clean` then `flutter pub get`

## Common Issues & Fixes

**Issue:**

Text changed from "Hello Flutter!" to "Flutter is interactive!" upon pressing the **Press Me** button but color stayed the same instead of turning blue.

**Errors:**

No error message, just unexpected behavior. Button works but styling doesn't update.

The TextStyle color property was written incorrectly or the ternary operator had wrong logic.  It was hardcorded like this, "
```dart
Text(
  changed ? 'Flutter is interactive!' : 'Hello Flutter!',
  style: TextStyle(
    fontSize: isPressed ? 32 : 24,
    color: Colors.black,  
  ),
)
```

**Resolution:**

Make sure color also uses the ternary operator based on isPressed state:
```dart
Text(
  changed ? 'Flutter is interactive!' : 'Hello Flutter!',
  style: TextStyle(
    fontSize: isPressed ? 32 : 24,
    color: changed ? Colors.blue : Colors.black,  
  ),
)
```

**Helpful Resource**
[Flutter TextStyle documentation](https://stackoverflow.com/questions/58232078/how-to-change-the-color-of-text-dynamically-in-flutter)


## References

Flutter Official Docs: https://flutter.dev/docs
Dart Language Tour: https://dart.dev/guides/language/language-tour
Flutter Widget Catalog: https://docs.flutter.dev/ui/widgets
StatefulWidget Documentation: https://api.flutter.dev/flutter/widgets/StatefulWidget-class.html
setState Method: https://api.flutter.dev/flutter/widgets/State/setState.html