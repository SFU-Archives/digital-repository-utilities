###### [Digital Repository Utilities](../README.md)

# ClamAV
Check digital transfers for viruses and malware.

**Contents**
- [Description](#description)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Links](#links)

## Description
Use ClamAV to scan transfer packages for malware and remove it before ingest to the repository. If you find infected files in a given transfer, you should contact the producer to advise them of the situation.

## Installation
Install ClamAV with `homebrew` (Mac users).

```
$ brew install clamav
```

**Notes**
- You will need administrator access to your computer to install the software.

## Configuration
You will need to create and edit configuration files to run the software. In order to access these files, set your Mac to view hidden files: `shift + command + .`.

- Navigate to `/usr/local/etc/clamav`.

- Create copies of the sample config files `clam.conf.sample`and `freshclam.conf.sample` as `clam.conf` and `freshclam.conf`.

- Use a text editor (e.g BBEdit) to find and comment out (add `#` to) these lines in both files:

```
# Comment or remove the line below.
# Example
```

## Usage
Always update the virus definitions database before running a scan.

```
$ freshclam
```

There are many variables that can be adjusted. The Archives' standard scan uses the following:

```
$ clamscan -ri --log=<<log_file>> <<transfer_folder>>
```

- `-r` = recursive: scan all sub-folders and items.

- `-i` = infected: print only names of infected files.

- `--log` = output the scan results to a separate log file; give the full path + file extension (e.g. `--log=/Users/richarddancy/Desktop/Clamscan/log.txt`)

- `transfer_folder` = the folder's file path; you can get this by simply dragging the folder into your Terminal window.

**Notes**
- Using file path abbreviations (e.g. `~/Desktop` instead of `/Users/radancy/Desktop`) for the `log` file seems to sometimes cause the program to fail; use the full file path instead.

- Use the `log` file to identify infected files and inspect their context; you will need to manually delete these files.

- You can also run `clamscan` with a `--copy=<<quarantine_folder` or `--move=<<quarantine_folder>>` to facilitate inspection / removal; `copy` by itself will not remove the infected files from their original location.

## Links
- ClamAV website: https://www.clamav.net.

###### Last updated: Nov 16, 2020
