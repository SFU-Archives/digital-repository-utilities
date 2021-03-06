###### [Digital Repository Utilities](../README.md)

# ClamAV
<img align="right" width="400" src="../screenshots/clamAV.png">

ClamAV is an open-source antivirus engine that scans files for viruses and malware.

The Archives uses ClamAV in the digital transfer workflow to check transfer packages and remove infected files before ingest to the repository. If you find infected files in a given transfer, you should contact the producer to advise them of the situation.

**Contents**
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Links](#links)

## Installation
Install ClamAV with `homebrew` (Mac users).

```
$ brew install clamav
```

**Notes**
- You will need administrator access to your computer to install the software.

## Configuration
You will need to create and edit configuration files to run the software. In order to access these files, set your Mac to view hidden files: `shift + command + .`

- Navigate to `/usr/local/etc/clamav`

- Create copies of the sample config files `clam.conf.sample`and `freshclam.conf.sample` as `clam.conf` and `freshclam.conf`

- Use a text editor (e.g BBEdit) to find and comment out (add `#` to) these lines in both files:

```
# Comment or remove the line below.
# Example
```

## Usage
Run ClamAV in a Terminal window.

Always update the virus definitions database before running a scan.

```
$ freshclam
```

There are many variables that can be adjusted. The Archives' standard scan uses the following:

```
$ clamscan -ri --log=<<path_to_log/log.txt>> <<transfer_folder>>
```

- `-r` = recursive: scan all sub-folders and items.

- `-i` = infected: print only names of infected files.

- `--log` = output the scan results to a separate log file; give the full path + file name and extension (e.g. `--log=/Users/richarddancy/Desktop/Clamscan/log.txt`)

- `transfer_folder` = the folder's file path; you can get this by simply dragging the folder into your Terminal window.

**Notes**
- Using file path abbreviations (e.g. `~/Desktop` instead of `/Users/radancy/Desktop`) for the `log` file seems to sometimes cause the program to fail; use the full file path instead.

- Use the `log` file to identify infected files and inspect their context; you will still need to manually delete these files.

- You can also run `clamscan` with a `--copy=<<quarantine_folder>>` or `--move=<<quarantine_folder>>` to facilitate inspection / removal; `copy` by itself will not remove the infected files from their original location, but `move` will.

## Links
- ClamAV website: https://www.clamav.net.

###### Last updated: May 6, 2021
