# Android

Apps for my Android phone

# Setup

Google:
```
   Q : "What are the Software Development Kits for Android?"
   A : The main Software Development Kit (SDK) for Android is
       the Android SDK, a toolbox from Google containing APIs,
       libraries, debuggers, emulators, and sample code, primarily
       managed within the official Android Studio IDE for building,
       testing, and debugging apps.

       Key components include the Android NDK (Native Development Kit
       for C/C++), platform tools like ADB, and libraries for various
       features, all designed to support app development across diverse
       Android devices and versions
```
When I first started this I downloaded something called "Android SDK
Hedgehog" (from Google).  I pushed my way through to make a "hello-world"
app and loaded it on my old `SAMSUNG Galaxy Express 3`.

I'm trying to repeat that and then start writing more apps.

However, this was all done on my CentOS 8, which bombed out during an
update.  And CentOS was being tombstoned (for some unknown reason) so
I switched over to Ubuntu.

## Android SDK

Ther's no Ubunto `sudo apt install` command.  Instead:
```
Installing the full Google Android SDK with all its components (including the
sdkmanager for installing platforms and other tools) is not typically done
through a single sudo apt install command.

The recommended method for a complete and up-to-date Android SDK installation
on Ubuntu is to download Android Studio from the official Android Developers
website.
```
OK ... these steps:
```
1) https://developer.android.com/studio

   Bypass:
   (a) "Gemini" - AI assisted SDK
   (b) "Cloud" - SDK via Web connection

   Down at the bottom of the page:

   Select:

   Linux (64-bit) 1.5 GB
   SHA - a6f9d40d87856f13a7c3674ff4178a16eb219d31e6a43ac1c269cd583c7ca5b4

   NOTE
   They have a "Command line tools only".  What's that?

   (a) Download

       Download Android Studio Otter 2 Feature Drop | 2025.2.2

   (b) File "explorer" to $HOME/Downloads

       Double click on: android-studio-2025.2.2.7-linux.tar.gz

       Extract to $HOME/bin

       3.5 GB

   (c) Read:

       cd $HOME/bin/android-studio

       Install-Linux-tar.txt

   (d) Expand $PATH in .bashrc

       export PATH=$PATH:$HOME/bin:$HOME/bin/android-studio/bin:.

   (c) Run 'studio.sh' for first time

       Note - it looks for a Java Runtime Env (JRE).

       Does a massive declaration of $CLASSPATH
```

