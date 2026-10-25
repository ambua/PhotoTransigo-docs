# PhotoTransigo — how to use it

PhotoTransigo copies photos and videos from a phone or a folder on this PC into daily folders on your PC. Nothing is uploaded anywhere: everything stays on your machine.

## In three steps

1. **Pick a source.** *Select local source* for a folder on this PC, or *Select mobile source* to browse a connected phone and choose a folder such as `DCIM\Camera`. You can also paste a path into the dropdown.
2. **Pick a target.** *Select target* chooses the folder on this PC where the daily folders are created.
3. **Choose what to import, then press Import.**

## Where are my camera files?

The source picker walks through your phone: pick the device, then its storage, then the folder. These are the folders worth knowing:

| Phone | Where to look |
|-------|---------------|
| Android (Samsung, Pixel, …) | `Internal storage\DCIM\Camera`, sometimes `Internal storage\DCIM` |
| Android SD card | `SD card\DCIM\Camera` |
| iPhone / iPad | `Internal Storage\DCIM`, then a folder per month such as `202408_`, or `100APPLE`-style folders depending on the iOS version; some iPhones show the month folders directly under `Internal Storage` |
| Screenshots | Samsung: `DCIM\Screenshots`, otherwise `Pictures\Screenshots` |
| Photos from chat apps | `Android\media\com.whatsapp\WhatsApp\Media\...` or `Pictures\Telegram\`, outside `DCIM` |

Pick the folder that contains the photos themselves: PhotoTransigo lists the files in the folder you choose, not the ones in its subfolders. On most Android phones that means `DCIM\Camera` rather than `DCIM`. On an iPhone it means opening the month folder you want, because `DCIM` itself only holds those folders.

### Before you start

- Unlock the phone, then accept the *Allow* prompt on Android or *Trust This Computer* on iPhone.
- On Android, set the USB connection to **File transfer** (also called MTP); charging-only mode hides the files.
- On iPhone, open *Settings → Photos → Transfer to Mac or PC* and choose **Keep Originals**. With *Automatic*, the phone converts photos to JPEG and videos to H.264 while they are transferred, so the copies are not the originals. *Keep Originals* also avoids the "device is unreachable" copy errors that File Explorer sometimes shows.
- On Windows 11 the iPhone may not appear under *This PC* until Apple's **Apple Devices** app is installed; it provides the USB driver.
- If **iCloud Photos** is on, some full-size originals exist only in iCloud and the phone may not offer them over USB. Choose *Download and Keep Originals* in iCloud settings, or import those photos through iCloud for Windows.
- Photos inside a Samsung **Secure Folder** cannot be read over USB.

## Choosing what to import

- Every file has a checkbox. Tick a few and the button reads `Import (3)` — only those files are copied.
- Tick nothing and the button reads `Import all (42)` — everything in the list is copied.
- The `Images` and `Videos` checkboxes hide one kind of file, and the filter box narrows the list by name: `IMG_*`, `*.jpg`, or plain text such as `20260614`. While a filter hides files, the counter reads `12 of 42 files`.
- **Refresh** reloads the list, for example after you added photos to the folder.

## Where the photos end up

Each file goes into a folder named after the day it was taken:

```text
<target>\2026-09-27\IMG_20260927_120000.jpg
```

The date comes from the photo's EXIF data when it has one, then from the file name, then from the file's date.

## Duplicates

If a file with the same name is already in that day folder, it is **skipped**. Importing the same folder twice is therefore safe: the second run reports the files as skipped instead of copying them again.

## Your originals

- Photos on a phone stay on the phone; PhotoTransigo never changes them.
- Files from a folder on this PC are copied, so the originals stay where they are.

## If something goes wrong

- The **Activity** area at the bottom lists what happened to every file.
- **Open log folder** opens a log file you can attach to a bug report. It contains file paths and device names from your machine and is never sent anywhere by the app.

## Good to know

- Runs on Windows 10 version 20H1 (build 19041) or later, including Windows 11.
- Phone folders can take a while to list; files appear in the list as they are found.
- Only common photo and video formats are imported: `.jpg`, `.jpeg`, `.png`, `.heic`, `.mp4`, `.mov`. Other files are ignored.
