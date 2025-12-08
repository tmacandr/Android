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

## Download/Install

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
```

## Run (first time)

Invoke the `studio.sh' script per the direction in the
`Install-Linux-tar.txt`.
```
   (a) Run 'studio.sh' for first time

       Note - it looks for a Java Runtime Env (JRE).

       Does a massive declaration of $CLASSPATH

   (b) allow Google to collect info = NO

   (c) Configure

       (i) Welcome

       (ii) Install Type: Standard

       (iii) Verify Settings

             1) Android Emulator                            306 MB
             2) Android SDK Build-Tools 36.1               61.2 MB
             3) Android SDK Platform 36                    62.8 MB
             4) Android SDK Platform-Tools                  7.54 MB
             5) Google Play Intel x86_64 Atom System Image  1.86 GB
             6) Sources for Android 36                     49.3 MB

       (iv) EULA

       (v) Emulator Settings:

           "We have detected that your system can run the Android emulator
            in an accelerated performance mode.

            Linux-based systems support virtual machine acceleration through
            the KVM (Kernel-bsed Virtual Machine) software package.

            Follow <Configure hardware acceleration for the Android Emulator>
            to enable KVM and achieve better performance."

            What?

            Goes to:

       https://developer.android.com/studio/run/emulator-acceleration?utm_source=android-studio-app&utm_medium=app#vm-linux

            No ... don't like the looks of this.  Various `sudo apt install`
            commands, etc.

      (vi) Downloading ....
           start 17:40
           End   ~17:50

      (vii) Finish

      NOTE - (from Install-Linux-tar.txt) Config information for
             SDK IDE, etc goes to:

                 $HOME/.config/Google

      (viii) Welcome to Android Studio

             What are these (warnings)?

             (a) The IDE seems to be launched with a script launcher
                 ('bin/studio.sh').  Please consider switching to a
                 native launcher ('bin/studio') for better experience.

                     <More>    <Don't Show Again>

                 What?  It's their own dang script?

                 Select don't show again

             (b) Input methods disabler
                 The IDE is running with enabled input methods that can
                 cause freezes.  Please consider to disable input
                 methods if you don't really use them.

                 <Disable input methods>

                 What the heck is "Input Methods" ... and why do I think
                 someone not from the US wrote that pop-up?

                 Google search ... how ironic ... using Google to find
                 what the heck Google is doing.

                 Q: "Android Studio what is an "Input Method" and why
                     should it be disabled? 
                 A: Something about users entering text, etc into
                    applications.

                    Well, dang it! ... that's what I want.

                    And something about how it might conflict with
                    other input and shortcuts (what's that?) during
                    debugging.

                    What?

                 :.\   Did NOT disable.

    (ix) Ug ... there must be some sort of time out.  Now it plowed
         right over to "Welcome to Android Studio" with no warnings.
```

## First (new) Project

Begin writing a "hello world" ... I guess.

```
1) New Project

2) "Phone and Tablet"

3) "Empty Activity"

4) "Create a new empty activity with Jetpack Compose" <-- What is that?

   Name: hello_world
   Package Name: com.example.hello_world
   Save location: $HOME/Programming/Android/00_hello_world
   Minimum SDK: API 23 ("Marshmallow"; Android 6.0)

            RE: my Samsung Galaxy Express 3 is Android version 6.0.1
                Date: October 1, 2017

      "Your app will run on approximately 99.3% of devices".

    Build configuration language:
                 (a) Kotlin DSL (build.gradle.kts) Recommended
              or (b) Groovy DSL (build.gradle)

    DSL := Domain Specific Language

    I want to write Java.

    -------------------------------------------------------
    When developing Android applications using Java, the Domain
    Specific Language (DSL) primarily encountered is the Groovy DSL
    for configuring your Gradle build scripts. While Kotlin is
    now the recommended and default language for new Gradle builds,
    Groovy DSL remains fully supported and is widely used in existing
    Java-based Android projects.
    -------------------------------------------------------

    Pick:  Groovy

    Some weird note:  "i The application name for most apps begins with
                       an uppercase letter."

5) Finish ...

   Start-up screen disappears and some "Add Configuration ..." window
   comes up ... long time ... progress bar saying:
               "Generating sources"

   There were three pop ups saying "add source" ... I didn't know what
   to do.  Selected "cancel".  Could be trouble.

   Ug!  It's a "kotlin" file, "MainActivity.kt" even though I didn't
   say so.  I want Java!

```
