# Old Notes on First Android App - From 25-JAN-24

I recorded these notes in my _Computer Log Book_.  It was an attempt to
start figuring out how to do **app** development targeted to **Android**
phones.

I was able to get a simple _hello world_ app installed on my (very?) old
`SAMSUNG Galaxy Express 3`.

Since then I lost my **CentOS 7** installation and installed **Ubuntu**,
because any **CentOS** installations seem to be **deprecated** within
the `Linux` community.  No one seemed to give a reason why.  It seems
the mysterious _powers-that-be_ at Linux decided to stop that effort.

And so I installed the _latest_ **Android SDK** on my Unbunto laptop and
when I run it, it eventually looks up my _laptop_ so I have to do a
hard re-boot.  A query to _www.google.com_ gives a reply that my little
_Dell LATITUDE E6440_ doesn't have enough _resources_ (RAM, CPU, etc)
to handle their (**stupid**) SDK.

So before I give up ... or buy a new system that can handle it ... I want
to capture these notes.  I'm not even sure if there's a point to this
because whatever **SDK** I used in 2024 probably isn't even avaialbe so
that I would even able to duplicate what I did back in _Jan 2024_.

But just in case ...

# Java Runtime Environment (JRE)

Downloaded `Java Runtime Environment` (**JRE**) from **Oracle**.

SDK came from:
```
   https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.rpm
```
Double-clicked on `.rpm` file.

Pop-up was lowest priority (almost missed it?).

jdk-21

Installed to:
```
   /usr/bin/javac
```

## Java 'hello world'

I think what I did is equivalent to what's defined in:
```
   https://github.com/tmacandr/toolbox/tree/main/Java/00_Hello_World
```

Write `build.sh`

Run
```
   Error: A JNI error has occurred, please check you installation and
   try again.

   HelloWorld has been compiled by a more recent version of the Java
   Runtime (class file version 65.0), this version of the Runtime
   only recognizer class file up to 52.0.
```

**Switch JRE ...**

update-alternatives --config java

```
Selection       Command
-------------------------------------------------------------------
+1              java-1.8.0-openjdk.x86_04
                (/usr/lib/java/java-1.8.0-openjdk-1.8.0.312.1.07-2.e18_5.x86_64/jre/bin/java
2              /usr/lib/jvm/jre-1.8-oracle-x64/bin/java
3              /usr/lib/jvm/jdk-21-oracle-x64/bin/java
```

Need to be `root`.

OK ... as `root` ... selected **3**.

Run: `run.sh`

All good.

## Android SDK For Linux

**Android Studio**

```
   https://developer.android.com
```

Download: **Android Studio Hedgehog**

```
   ------------     --------------
   | Install  |     | Build your |
   |    .     |     | first App  |
   |    .     |     |            |
   |    .     |     |            |
   ------------     --------------

   -----------      --------------
   | Configure|     | Training   | 
   | Android  |     | for        |
   | Studio   |     | beginners  |
   |          |     | & pros     |
   ------------     --------------
```
Download **.targ.gz** file
Alternative **.tar** (not selected?)

Use **CentOS** `install` tool or command line?

Installation map

Extract to root `/` or my app?

Wasn't sure to install as `root` or `user`.

Notes:
```
   If libs are owner root, do they get 'executed' as root even if
   run as user?  Best to install as user.  Then anything in there
   will be run only as user ... right?
```

To:
```
   $HOME/Android_Studio
   cd bin
   ./studio.sh

       .
       .
       .

      config location problem(s)
```

EULA - ugly read.

Welcome to `Android Studio`.

## First Android App

```
   https://developer.android.com/codelabs/basic-android-kotlin-compose-first-app#0
```

Need basic knowledge of **Kotlin**.

What the heck is **Kotlin**?

```
   Kotlin is a programming language that is concise and cross-platform.
   It is Google's preferred language for Android app development.

   It is open-source

   Statically typed
```

I think these are notes about the _Wizard_ to create a new project:
```
      .
      .
      .
   Empty Activity
      .
      .
      .
   Finish
      .
    <takes a long time>
      .
      .
    <more long time>
      .
      .
      .
    Split ...
```
some sort of emulation scheme ...
```
   ----------------------------------------
   |          |                  |        |
   |          |                  |        |
   |  Files   |     Code         | Build  |
   |          |                  |        |
   |          |                  |        |
   ----------------------------------------
```
Now it's just a bunch of blah-blah nuances on how to change colors,
borders, UI stuff.

I guess at this point I have an **app**.

Then I wrote:
```
   How do I get it to my phone?
```

Got device (my phone) to connect:
```
   --------
   | ---  |
   | ---  |    <--- their 'main menu' button thing
   | ---  |
   -------- ---> Tools
                   |
                   |
                   ---> Troubleshoot Connection
```

App - `Hello World Lizzy`

Went to some _Japanese_ guy on www.YouTube.com

```
   He built a project of

      EMPTY VIEWS Activity

   and selection Java as language.

   And I selected MINIMUM SDK as:

      API23 ("Marshmellow, Android 6.0")
```

Then this _trick_ on my Phone:

```
   Go to:

      Settings
         |
         |
         ---> System
                |
                |
                ---> About Device
                        |
                        |
                        ---> Android Version

   TRICK:  Press on "Android Version" seven (7) times ... adn this will
           move the phone into the 'DEVELOPER MODE'.

           Then back to SYSTEM ...

           Now there's an option called:

              "DEVELOPER OPTIONS"
```
Developer's Options:
```
   Activate USB DEBUGGING - ON
```
Connect my phone to computer via USB-to-USB link:

```
   -----------
   | ------- |              ________
   | |     | |              |      |
   | |     | |<-----        |      |
   | ------- |     |        |Phone |
   | keyboard|     -------->|      |
   -----------              |------|
```
Back to **Android Studio**

```
   --------
   | ---  |
   | ---  |    <--- their 'main menu' button thing
   | ---  |
   -------- ---> Tools
                   |
                   |
                   ---> Troubleshoot Device Connection
```
Walk thru **connection detector**.

... **activate phone** ... `SAMSUNG ... etc`

**Run**

Press the _loop-with-arrow_ button ...

Builds ... takes a while.

Downloads app to phone ...

Run app on phone

**Installation**

Installed to **Apps**

Had to _push_ to page 2 of **Apps** ... there is icon for **Hello Lizzy**.

Disconnect

Developer Options:
```
   turn off USB debugging
   turn off Developer Options (<-- not sure what I did here)

