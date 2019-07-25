# Setting the up the Environment for Flutter

## Windows Install

{% hint style="info" %}
### System Requirements

* **Operating System**: Windows 7 SP1 or Later \(64-bit\)
* **Disk Space**: 400MB \(Does not include the disk space for IDE\)
* **Tools**: Flutter depends on these tools being available in your environment.
  * Windows PowerShell 5.0 or newer
  * Git for Windows 2.x 

_If Git for Windows is already installed, make sure you can run `git` commands from the command prompt or PowerShell._
{% endhint %}

### Get the Flutter SDK  <a id="get-the-flutter-sdk"></a>

* Download an installation bundle [**here**](https://storage.googleapis.com/flutter_infra/releases/stable/windows/flutter_windows_v1.2.1-stable.zip) to get the latest stable release of the Flutter SDK
* Extract the zip file and place the contained flutter in the desired installation location for the Flutter SDK \(eg. **`C:\src\flutter`** do not install Flutter in a directory like **`C:\Program Files\`** that requires elevated privileges \).
* Locate the file **`flutter_console.bat`** inside the flutter directory. Start it by double-clicking.

Congratulations! You are now ready to run Flutter commands in the Flutter Console!

{% hint style="warning" %}
NOTE: Should you at anytime require an upgrade to a latest Flutter version? [Use this link](https://flutter.dev/docs/development/tools/sdk/upgrading)
{% endhint %}

#### \(Optional Step\)

If you wish to run Flutter commands in the regular Windows console, take these steps to add Flutter to the PATH environment variable:

* From the Start search bar, type **`‘env’`** and select Edit environment variables for your account
* Under User variables check if there is an entry called Path\(If it exist append the full path **`to flutter\bin`** using **`;`** as a separator from existing values else create a new user variable named Path with the full path to **`flutter\bin`** as its value\)

### Run Flutter Doctor

The following command to see if there are any platform dependencies you need to complete the setup:

```text
 c:\src\flutter sdk>flutter doctor
```

This command checks your environment and displays a report of the status of your Flutter installation. Check the output carefully for other software you might need to install or further tasks to perform \(shown in **bold** text\).

For example:

```text
[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    • Try re-installing or updating your Android SDK,
      visit https://flutter.dev/setup/#android-setup for detailed instructions.
```

Ensure you check the output carefully for other software you may need to install or further tasks to perform \(shown in bold text\).

{% hint style="danger" %}
The `flutter` tool uses Google Analytics to anonymously report feature usage statistics and basic crash reports. This data is used to help improve Flutter tools over time. Analytics is not sent on the very first run or for any runs involving `flutter config`, so you can opt out of analytics before any data is sent. To disable reporting, type `flutter config --no-analytics` and to display the current setting, type `flutter config`. See Google’s [Privacy Policy](https://policies.google.com/privacy).
{% endhint %}

### Android Setup

Wondering why we need android studio setup?Here is why: Flutter relies on a full installation of Android Studio to supply its Android platform dependencies.You can however write flutter apps on other IDEs such as Visual studio code.

#### Install Android Studio

{% hint style="info" %}
* Download and install Android Studio from [here](https://developer.android.com/studio/?gclid=Cj0KCQjwsZ3kBRCnARIsAIuAV_RMbMDTLk-O1LOvm7MXD_o2diOYLqz4KPIBrpfUnw_2fAuE44y5K5waAt5EEALw_wcB).
* Start Android Studio, and go through the ‘Android Studio Setup Wizard’. This installs the latest Android SDK, Android SDK Platform-Tools, and Android SDK Build-Tools, which are required by Flutter when developing for Android.
{% endhint %}

**Set up your Android device**

One of the coolest thing about Flutter is that you can run your Flutter app on android device without writing complex commands. Here is how I did it.

First thing first, to prepare to run and test your Flutter app on an Android device, you’ll need an Android device running **Android 4.1 \(API level 16\) or higher**.

**Other necessary steps to follow:**

* Enable Developer options and USB debugging on your device. **Go to Settings &gt; Developer options &gt;USB debugging**.
* Windows-only: Install the Google USB Driver
* Using a USB cable, plug your phone into your computer. If prompted on your device, authorise your computer to access your device.
* In your android studio terminal or command prompt, run the `flutter devices` command to verify that Flutter recognizes your connected Android device.

**Set up the Android emulator**

To prepare to run and test your Flutter app on the Android emulator for some reasons :\), follow these steps:

* Enable VM acceleration on your machine.
* Launch **Android Studio &gt; Tools &gt; Android &gt; AVD Manager** and select Create Virtual Device. \(The Android submenu is only present when inside an Android project.\)
* Choose a device definition and select **Next**.
* Select one or more system images for the Android versions you want to emulate, and select **Next**. An x86 or x86\_64 image is recommended.
* Under Emulated Performance, select **Hardware - GLES 2.0** to enable hardware acceleration.
* Verify the AVD configuration is correct, and select Finish.

In Android Virtual Device Manager, click **Run** in the toolbar. The emulator starts up and displays the default canvas for your selected OS version and device.

## **Mac** Install

{% hint style="info" %}
### System Requirement

* **Operating System:** macOS \(64-bit\)
* **Disk Space**: 400MB \(Does not include the disk space for IDE\)
* **Tools**: Flutter depends on these command-line tools being available in your environment.
  * `bash`
  * `curl`
  * `git` 2.x
  * `mkdir`
  * `rm`
  * `unzip`
  * `which`
{% endhint %}

### Get the Flutter SDK  <a id="get-the-flutter-sdk"></a>

* Download an installation bundle [here](https://storage.googleapis.com/flutter_infra/releases/stable/macos/flutter_macos_v1.2.1-stable.zip) to get the latest stable release of the Flutter SDK
* Extract the file in the desired location.

```text
 cd ~/development
 unzip ~/Downloads/flutter_macos_v1.2.1-stable.zip
```

* Add the flutter tool to your path.

     export PATH="$PATH:`pwd`/flutter/bin"

This command sets your PATH variable for the current terminal window only.

To permanently add Flutter to your path, follow the steps below:

* Determine the directory where you placed the Flutter SDK.
* Open \(or create\) **`$HOME/.bash_profile.`** The file path and filename might be different on your machine.
* Add the following line and change **`[PATH_TO_FLUTTER_GIT_DIRECTORY]`** to be the path where you cloned Flutter’s git repo:

```text
 export PATH="$PATH:[PATH_TO_FLUTTER_GIT_DIRECTORY]/flutter/bin"
```

* Run source **`$HOME/.bash_profile`** to refresh the current window.
* Verify that the **`flutter/bin`** directory is now in your PATH by running:

```text
 echo $PATH
```

Congratulations! You are now ready to run Flutter commands in the Flutter Console!

{% hint style="warning" %}
NOTE: Should you at anytime require an upgrade to a latest Flutter version? [Use this link](https://flutter.dev/docs/development/tools/sdk/upgrading)
{% endhint %}

### Run Flutter Doctor

The following command to see if there are any platform dependencies you need to complete the setup:

```text
 c:\src\flutter sdk>flutter doctor
```

This command checks your environment and displays a report of the status of your Flutter installation. Check the output carefully for other software you might need to install or further tasks to perform \(shown in **bold** text\).

For example:

```text
[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    • Try re-installing or updating your Android SDK,
      visit https://flutter.dev/setup/#android-setup for detailed instructions.
```

Ensure you check the output carefully for other software you may need to install or further tasks to perform \(shown in bold text\).

{% hint style="danger" %}
The `flutter` tool uses Google Analytics to anonymously report feature usage statistics and basic crash reports. This data is used to help improve Flutter tools over time. Analytics is not sent on the very first run or for any runs involving `flutter config`, so you can opt out of analytics before any data is sent. To disable reporting, type `flutter config --no-analytics` and to display the current setting, type `flutter config`. See Google’s [Privacy Policy](https://policies.google.com/privacy).
{% endhint %}

### Update the environment path

You can update your PATH variable for the current session only at the command line, as shown in [Get the Flutter SDK](https://flutter.dev/docs/get-started/install/macos#get-sdk). You’ll probably want to update this variable permanently, so you can run **`flutter`** commands in any terminal session.

_The steps for modifying this variable permanently for all terminal sessions are machine-specific._

* Determine the directory where you placed the Flutter SDK.
* Open \(or create\) `$HOME/.bash_profile`. The file path and filename might be different on your machine.
* Add the following line and change `[PATH_TO_FLUTTER_GIT_DIRECTORY]` to be the path where you cloned Flutter’s git repo:content\_copy

```text
$ export PATH="$PATH:[PATH_TO_FLUTTER_GIT_DIRECTORY]/flutter/bin"
```

* Run `source $HOME/.bash_profile` to refresh the current window.
* Verify that the `flutter/bin` directory is now in your PATH by running:content\_copy

```text
$ echo $PATHIos Setup
```

### iOS Setup

#### Install Xcode

To develop Flutter apps for iOS, you need a Mac with Xcode 9.0 or newer:

1. Install Xcode 9.0 or newer \(via [web download](https://developer.apple.com/xcode/) or the [Mac App Store](https://itunes.apple.com/us/app/xcode/id497799835)\).
2. Configure the Xcode command-line tools to use the newly-installed version of Xcode by running the following from the command line:content\_copy

   ```text
   $ sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
   ```

   This is the correct path for most cases, when you want to use the latest version of Xcode. If you need to use a different version, specify that path instead.

3. Make sure the Xcode license agreement is signed by either opening Xcode once and confirming or running **`sudo xcodebuild -license`** from the command line.

With Xcode, you’ll be able to run Flutter apps on an iOS device or on the simulator.

#### Set up the iOS simulator <a id="set-up-the-ios-simulator"></a>

To prepare to run and test your Flutter app on the iOS simulator, follow these steps:

1. On your Mac, find the Simulator via Spotlight or by using the following command:content\_copy

   ```text
   $ open -a Simulator
   ```

2. Make sure your simulator is using a 64-bit device \(iPhone 5s or later\) by checking the settings in the simulator’s **Hardware &gt; Device** menu.
3. Depending on your development machine’s screen size, simulated high-screen-density iOS devices might overflow your screen. Set the device scale under the **Window &gt; Scale** menu in the simulator

## Setup an editor

{% tabs %}
{% tab title="Visual Studio Code" %}
### Install VS Code <a id="install-vs-code"></a>

VS Code is a light-weight editor with Flutter app execution and debug support.

* [VS Code](https://code.visualstudio.com/), latest stable version

### Install the Flutter and Dart plugins <a id="install-the-flutter-and-dart-plugins-1"></a>

1. Start VS Code.
2. Invoke **View &gt; Command Palette…**.
3. Type “install”, and select **Extensions: Install Extensions**.
4. Type “flutter” in the extensions search field, select **Flutter** in the list, and click **Install**. This also installs the required Dart plugin.

### Validate your setup with the Flutter Doctor <a id="validate-your-setup-with-the-flutter-doctor"></a>

1. Invoke **View &gt; Command Palette…**.
2. Type “doctor”, and select the **Flutter: Run Flutter Doctor**.
3. Review the output in the **OUTPUT** pane for any issues. 
{% endtab %}

{% tab title="Android Studio / IntelliJ" %}
### Install Android Studio <a id="install-android-studio"></a>

Android Studio offers a complete, integrated IDE experience for Flutter.

* [Android Studio](https://developer.android.com/studio), version 3.0 or later

Alternatively, you can also use IntelliJ:

* [IntelliJ IDEA Community](https://www.jetbrains.com/idea/download/), version 2017.1 or later
* [IntelliJ IDEA Ultimate](https://www.jetbrains.com/idea/download/), version 2017.1 or later

### Install the Flutter and Dart plugins <a id="install-the-flutter-and-dart-plugins"></a>

To install these:

1. Start Android Studio.
2. Open plugin preferences \(**Preferences &gt; Plugins** on macOS, **File &gt; Settings &gt; Plugins** on Windows & Linux\).
3. Select **Browse repositories**, select the Flutter plugin and click **Install**.
4. Click **Yes** when prompted to install the Dart plugin.
5. Click **Restart** when prompted.
{% endtab %}
{% endtabs %}



