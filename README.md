PebbleKit Android
=================

Welcome to Pebble's official Android SDK!

## Communication with Pebble

On Android, all communication between apps and Pebble go through the official
Pebble Android application via intents.

PebbleKit Android provides a convenience layer on top of those intents.

## Documentation

 - [Using PebbleKit
   Android](http://developer.pebble.com/guides/communication/using-pebblekit-android) describes
   how to use PebbleKit Android in your application.
 - [PebbleKit Android API
   Reference](http://developer.getpebble.com/docs/pebblekit-android)

## Examples

All Pebble examples are now [available on
GitHub](https://github.com/pebble-examples).

We provide several examples of Android application communicating with Pebble:

 - The [Sports
   demo](https://github.com/pebble-examples/pebblekit-sports-api-demo/tree/master/Android/PebbleKitSportsAPIDemo)
   shows how to build an Android application that starts and communicates with
   the Sports app embedded in all Pebbles.
 - The [PebbleKit Android Example](https://github.com/pebble-examples/pebblekit-android-example)
   shows how to perform basic use of AppMessage between a Pebble watchapp and an Android companion app.

## Using PebbleKit Android

As of version 2.5, PebbleKit Android is distributed as a library on the
[Sonatype OSS Repository](https://oss.sonatype.org/).  Source code and Android
library (`.aar`) are also available.

A specific library is available for Eclipse users (Eclipse does not support the
`.aar` library format).`

You must install the official [Pebble Android
application](https://play.google.com/store/apps/details?id=com.getpebble.android)
to use PebbleKit Android.

PebbleKit Android requires Android SDK version 14 or higher (4.0 and above).

### Using PebbleKit Android with Android Studio and Gradle

In Android Studio, or on any Gradle project, you can add PebbleKit Android in
your `app/build.gradle` file:

    dependencies {
        compile 'com.getpebble:pebblekit:4.0.1@aar'
    }

Make sure that you also include a reference to the Sonatype OSS Repository:

    repositories {
        mavenCentral()
        maven { url "https://oss.sonatype.org/content/groups/public/" }
    }

### Using Eclipse

To use PebbleKit in the Eclipse IDE you must import the `.jar` file that
contains the PebbleKit Android SDK. To install, follow the instructions below:

1. Download the `pebblekit-4.0.1-eclipse.jar` file from
[Sonatype][jar-download].

2. Add the file to your Android project in the `libs` folder alongside the
`AndroidManifest.xml` file. This should automatically add it to your build path
after refreshing the Android project. If not (or you saved it elsewhere)
right-click the file and choose Build Path->Add to Build Path.

You can now use PebbleKit in your Eclipse Android project!

### Using PebbleKit Android with Maven

If you are using Maven, you can add the following dependency in your `pom.xml`:

    <dependency>
        <groupId>com.getpebble</groupId>
        <artifactId>pebblekit</artifactId>
        <version>4.0.1</version>
        <type>aar</type>
    </dependency>

### Using PebbleKit Android library directly

Finally you can also [download the AAR file][aar-download] for PebbleKit Android
and add it directly into your project.

*Note: The AAR file format is currently not supported by Eclipse.*

## Changelog

### 4.0.1 - November 2016
- Fixed bug that could cause apps to not properly update the speed/pace label
  when using the `SportsState` helper in the Sports API.

### 4.0.0 - November 2016
- Added new APIs for sending custom HR data and a custom label/value from a
  mobile companion app, using the Sports API.
- Added a helper object that will automatically manage state and message
  construction for updates to the Sports app on a Pebble watch.
- Updated the Constant ``ICON_MAX_DIMENSIONS`` to be 25px, to be consistent
  with watches running 4.0 firmware. If your provided icon exceeds 25px x 25px,
  you will encounter a runtime error when calling ``customizeWatchApp``.

### 3.1.0 - April 2016

- Fixes a crash which could happen in some Locales
- Makes `PebbleTuple` public and non-`final`

### 3.0.0 - March 2015

This version provides support for the upcoming Pebble Time and Pebble Time Steel
watches. You must re-compile your application with this version of PebbleKit
otherwise you will not be able to detect (`PebbleKit.isWatchConnected()`) the
new Pebble watches.

There are no other changes in this version.

### 2.6.0 - November 2014

 - The datalogging API has changed in this version. `receiveData()` now takes
   `java.lang.Long` instead of `com.google.common.primitives.UnsignedInteger`.
   Otherwise the API has not changed.
 - Guava is no longer a dependency of PebbleKit.
 - Distribute a JAR version of PebbleKit Android for Eclipse users.
 - Fixed a bug where PebbleKit Android could leak cursors.
 - Fixed bug that caused duplicate launcher icons.

**Important:** In this version, DataLogging is only compatible with the Pebble
mobile app 2.1+ ([currently available in the Android Beta
channel](http://developer.getpebble.com/blog/2014/06/12/Android-Beta-Channel/)).

### 2.5.0 - August 2014

 - (Bumped version to 2.5 to follow firmware updates)
 - Automatic publication to Sonatype OSS Repo

## 2.0 - January 2014

 - First release of 2.0 SDK with the new DataLogging API

[jar-download]: https://oss.sonatype.org/service/local/repositories/releases/content/com/getpebble/pebblekit/4.0.1/pebblekit-4.0.1-eclipse.jar
[aar-download]: https://oss.sonatype.org/service/local/repositories/releases/content/com/getpebble/pebblekit/4.0.1/pebblekit-4.0.1.aar
