android-quill
=============
This is an attempt to rewive Quill. An old good but abandoned handwriting app.


To build this app you might need:
- Apache ANT `sudo apt install ant`
- Old Android SDK with Ant support. Replicant SDK [replicant-sdk_linux-x86.zip](https://redmine.replicant.us/projects/replicant/wiki/ReplicantSDK) works fine. Alternatively you may try manually downloading [old tools](https://dl.google.com/android/repository/tools_r25.2.5-linux.zip)
- JDK may need replacement. I have used [jdk1.8.0_301](https://www.oracle.com/es/java/technologies/javase/javase8-archive-downloads.html)
- FilePicker library
- I can't get [AmbilWarna](https://github.com/yukuku/ambilwarna) to work. So it is not needed.


Try to run this to compile:
```
RSDK=/path/to/replicant-sdk_linux-x86
OJDK=/path/to/jdk1.8.0_301

mkdir QuillBuild
cd QuillBuild

git clone https://github.com/msoftware/android-file-picker AndroidFilePicker
git clone https://github.com/yarolig/Quill Quill

ANDROID_HOME=$RSDK $RSDK/tools/android update project -p . -t android-17  --subprojects

cd Quill
JAVA_HOME=$OJDK ant debug
```

Now you can install 
```
adb install ./bin/QuillWriterActivity-debug.apk
```
You need to remove the old Quill if it is installed.

If you see this error, you need to change JDK:
```
    [javac] error: Source option 5 is no longer supported. Use 6 or later.
    [javac] error: Target option 1.5 is no longer supported. Use 1.6 or later.
```

### Handwriting note-taking app for Android tablets
The code was forked from code.google.com/p/android-quill.
Then imported from f-droid project and https://github.com/ryanamaral/android-quill

A key design goal is quick response to pen strokes and 100% vector graphics. Developed on a Lenovo ThinkPad Tablet and a Galaxy Note.

### Features
  * Active pen (digitizer) support on ThinkPad Tablet, HTC Jetstream, and HTC Flyer, Galaxy Note.
  * Very fast response to pen strokes.
  * "Fountain pen" mode supports pen pressure data, more pressure = thicker line (requires active pen).
  * Pinch-to-zoom.
  * Double-finger tap to zoom.
  * Two-finger move gesture.
  * Pen strokes are vector art, zoom does not pixelate your writing.
  * "Pen only" mode (optional) disables touch input while writing.
  * Android 3.x hardware accelerated graphics.
  * Open source (GPL), so your notes are not stuck in an opaque file format.
  * PDF export (save to SD card, Evernote, Share).
  * PNG (raster image) export.
  * Can backup/restore your data.
  * Ruled/Quad background paper
  * Tagging for pages so you can group them together.
  * Switch between multiple notebooks.
  * Undo/redo.
  * Requires Honeycomb or later (Ice Cream Sandwich, Jelly Bean)
  * Desktop companion program at https://github.com/vbraun/QuillDesktop to view/convert quill notebooks into svg, pdf, ps.

The n-trig active pen has been tested on the ThinkPad Tablet, HTC Jetstream, and the HTC Flyer (Honeycomb). The Samsung S-pen has been tested on the Galaxy Note (ICS). The basic functionality should work on any Android tablet, but distinguishing pen from finger data and pressure sensitivity might not work on others. Please let me know your results if you try it on another tablet. See http://code.google.com/p/android-quill/wiki/SupportedDevices for more details.

There is a thread on the XDA Developers forum http://forum.xda-developers.com/showthread.php?t=1378625 and at the Lenovo forum http://forum.lenovo.com/t5/ThinkPad-slate-tablets if you want to discuss anything.

Also available on the Android Market (https://play.google.com/store/apps/details?id=com.write.Quill).

### Dependencies
  * [Android Color Picker aka AmbilWarna library](https://github.com/yukuku/ambilwarna)
  * [Android File Picker](http://code.google.com/p/android-file-picker)

### Reviews
http://www.youtube.com/watch?v=k1yxYXMPXA0  
http://the-gadgeteer.com/2011/11/16/lenovo-thinkpad-tablet-review (contains above video)

![LarsWallinDrawing](../master/doc/screenshot-quill-android.png "An amazing drawing by Lars Wallin done in Quill")  
An amazing drawing by Lars Wallin done in Quill.

## LICENSE

Quill is released under the [GNU General Public License v3.0](../master/LICENSE).
