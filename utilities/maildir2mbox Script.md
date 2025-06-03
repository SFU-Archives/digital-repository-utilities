**maildir2mbox** is an command line Python script adapted by SFU Archives ca. 2013 from an [existing project](http://yergler.net/blog/2010/06/06/batteries-included-or-maildir-to-mbox-again/) originally created by Nathan Yergler in June 2010 and ported to Python 3 by Philippe Fremy. SFU's Alex Garnett made additional modifications in 2019.

The Archives has used the script to take `maildir` email exported from SFU Mail by [[OfflineImap]] and convert it to `mbox` format for ingest into [[Archivematica]] and [[ePADD]].

Note that as of June 2022, SFU Archives also uses the proprietary software [[Emailchemy]] to perform conversions. Emailchemy's user interface makes it somewhat easier to use, and it also supports conversions to and from other email formats.

## Download
The script is stored on the Archives' shared drive at `ITM002-40`. The code is directly available from this GitHub repository at [this link](https://github.com/SFU-Archives/digital-repository-utilities/blob/master/downloads/maildir2mbox2.py).

Once downloaded, the script can be run from any location on your computer.

## Configuration
None required.

## Usage
To run, open a Terminal window and run the following command

```
python3 /path/to/script path/to/maildir/input/folder/ /path/to/mbox/output/folder`
```

There are three script arguments:
- `script`: the file path of the `maildir2mbox.py` file.
- `input folder`: the folder containing the **maildir** email to be converted.
- `output folder`: the folder that will take the email converted to **mbox**.

```
Last updated: Nov 28, 2023
```
