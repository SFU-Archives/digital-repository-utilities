# Digital Repository Utilities

This site lists the various software tools, scripts and utilities SFU Archives uses in its digital repository work. Its purpose is to facilitate public sharing with institutions that may be interested in adapting or using the tools.

Each entry links to a minimal description, with additional links to downloadable files or documentation where applicable. The Archives maintains its fuller SFU-specific documentation on an internal SharePoint site. Pages suitable for public sharing are output as pdf and posted here as [SFU Archives usage guides](sfua-usage-guides); pages may be redacted to remove server names and file paths.

[Recent Changes and Additions](recent-changes.md)

### Access-to-Memory (AtoM)
- SFU Archives' online access platform and catalog of archival descriptions.
- See [SFU AtoM Guidelines and Processing Resources (GitHub)](https://github.com/SFU-Archives/atom-guidelines-processing-resources)

### Archives Information System (AIS) Database
- Custom FileMaker database used to manage information relating to accessions (Archives module) and AIPs (Repository module).
- Documentation maintained internally on Teams site; available on request.

### Archivematica
- SFU Archives' main digital preservation platform.
- Documentation maintained internally on Teams site; available on request.

### Bagger
- Desktop application for packaging and validating transfers.
- [SFU Archives usage guide: Bagger (pdf)](/sfua-usage-guides/bagger-sfua.pdf).

### BagIt Profiles
- BagIt Profiles for creating transfer packages in various contexts.
- [SFU Archives usage guide: BagIt Profiles (pdf)](/sfua-usage-guides/bagit-profiles-sfua.pdf).

### Brunnhilde
- Characterization tool for analyzing files transferred to Archives and to support archival appraisal, arrangement and description.
- [SFU Archives usage guide: Brunnhilde (pdf)](/sfua-usage-guides/brunnhilde-sfua.pdf).

### ClamAV
- Antivirus engine used to check for malware in digital transfers.
- [SFU Archives usage guide: ClamAV (pdf)](/sfua-usage-guides/clamav-sfua.pdf).

### Contact-Sheet Maker
- Python script to create a set of thumbnail images as a pdf document from a folder of digital photographs.
- [SFU Archives usage guide: Contact sheet maker (pdf)](/sfua-usage-guides/contact-sheet-maker-sfua.pdf).
- [Download script (zip file)](/downloads/contact-sheet-maker.zip).

### Digital Archivist's Resource Tool (DART)
- Desktop application for packaging and validating digital transfers.
- [SFU Archives usage guide: DART (pdf)](/sfua-usage-guides/dart-sfua.pdf).

### DIP upload
- Archives developed custom command-line scripts ("DIP Mungers") for retrieving offline DIPs from storage for upload to AtoM; these were retired May 2025 - [documentation of the original scripts here](/sfua-usage-guides/dip-).
- The Archives now uses AtoM's standard [Digital object load task](https://www.accesstomemory.org/en/docs/2.8/admin-manual/maintenance/cli-import-export/#digital-object-load-task).
- [SFU Archives usage guide: DIP upload (pdf)](/sfua-usage-guides/dip-upload-sfua.pdf).

### Emailchemy
- Email migration and conversion software that can convert email to various open formats.

### ePADD
- Open-source software for processing and providing access to email archives.

### Extent Calculator
- Online app for calculating fonds and series extents from box types.
- [SFU Archives usage guide: Extent Calculator (pdf)](/sfua-usage-guides/extent-calculator-sfua.pdf).
- Online calculator on the Archives' [shiny apps site](https://sfuarchives.shinyapps.io/extent_calculator).

### FFmpeg
- Open-source command-line utility for converting audio and video files.
- [SFU Archives usage guide: FFmpeg (pdf)](/sfua-usage-guides/ffmpeg-sfua.pdf).

### Finding Aid Maker
- Custom-built desktop FileMaker app that takes AtoM csv data to create a more printer-friendly pdf finding aid.

### Fixity
- Open-source utility for verifying checksums of stored packages.

### Homebrew
- Open-source software package management system used to install various programs and command-line utilities on a Mac.
- [SFU Archives usage guide: Homebrew (pdf)](/sfua-usage-guides/homebrew-sfua.pdf).

### Imagemagick
- Open-source command-line utility for editing and manipulating images.
- [SFU Archives usage guide: Imagemagick (pdf)](/sfua-usage-guides/imagemagick-sfua.pdf).

### maildir2mbox Script
- Python script for converting email from `maildir` to `mbox` formats.
- [SFU Archives usage guide: maildir2mbox script (pdf)](/sfua-usage-guides/maildir2mbox-script-sfua.pdf).
- [Download the script (py)](/downloads/mailbox2mbox.py)

### msg2eml
- Python script for converting `msg` email files to `eml` format.

### OfflineIMAP
- Command-line utility for exporting email from an active system in `maildir` format.

### Resolution Calculator
- Online app for calculating scanning resolutions for digitizing photographic materials (negatives, slides, prints).
- Documentation on [AtoM Guidelines and Processing Resources site](https://github.com/SFU-Archives/atom-guidelines-processing-resources/blob/main/resources/resolution-calculator.md).
- Online calculator on the Archives' [Shiny App site](https://sfuarchives.shinyapps.io/resolution_calculator/).

### rsync
- Command-line utility for copying and moving digital files.
- [SFU Archives usage guide: rsync (pdf)](/sfua-usage-guides/rsync-sfua.pdf).

### SFU MoveIt
- Desktop packaging utility created by SFU Archives to support digital transfers.
- Retired in the Fall of 2023; replaced by DART.

### SFU Vault
- SFU's cloud service for file sharing and storage; used in digital transfer.

### Tree
- Command-line utility for analyzing the directory structure of digital transfers.
- [SFU Archives usage guide: Tree (pdf)](/sfua-usage-guides/tree-sfua.pdf).

### VLC
- Open-source media player that can also be used for video conversion.
- [SFU Archives usage guide: VLC (pdf)](/sfua-usage-guides/vlc-sfua.pdf).

### WARC creation
- SFU Archives uses wget and the WARCreate Chrome plug-in to create WARC files.
- [SFU Archives usage guide: WARC creation (pdf)](/sfua-usage-guides/warc-creation-sfua.pdf).

```
Last updated: August 19, 2025
```

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

All content in this repository licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](https://creativecommons.org/licenses/by-nc/4.0/)
