###### [Digital Repository Utilities](../README.md)

# rsync
###### Status: under development
<img align="right" width="400" src="../screenshots/rsync.png">

`rsync` is a command-line utility for copying files and for syncing files and directories from two different systems.

SFU Archives uses rsync in its digital transfer workflow: use rsync to upload validated transfer packages to the Archives' staging server for ingest to Archivematica.

## Contents
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Links](#links)

## Installation
The easiest way to install on a Mac (most Archives' machines are Macs) is via `homebrew`.

```
$ brew install rsync
```

**Notes**
- You will need administrator access to your computer to install the software.

## Configuration
No special configuration needed.

## Usage
In the Archives' workflow, an archivist validates a transfer package, re-packages it with [Bagger](bagger.md) to include accession and validation metadata, copies it to a staging server on SFU Cloud, then ingests it to Archivematica backlog.

Prior to June 2021, archivists could upload packages directly to the staging server, either via `rsync` or with an FTP client like Cyberduck. With the migration to SFU Cloud, however, you must first `ssh` into the Archives' bastion server, then from there copy the package using `rsync`. Both operations require use of command line; you can no longer use an FTP client.

**Command:**

```
$ rsync -vhrlt --checksum <<transfer-package>> <<user-name>>@<<staging-server>>/var/transfersource/ | tee <<log-file.txt>>
```

- `-v` = verbose: results for each file printed to your Terminal window

- `-h` = human-readable output

- `-r` = recursive: gets all sub-folders and their contents

- `-l` = symlinks

- `-t` = timestamps: preserves files' original timestamps

- `--checksum` = generates checksums

- `transfer-package` = full directory path of the package to be copied;

- `staging-server` = VM on SFU Cloud; you will be prompted for your SFU computing password

- `tee` = name of log file (optional)

**Notes**
- If you use a log file (`tee` flag), rsync will output results for each file copied in both your Terminal window and on the log file; you need to create the log file **before** running the command (i.e. it needs to exist).

## Links
- Homebrew rsync page: https://formulae.brew.sh/formula/rsync

- rsync manual page: https://linux.die.net/man/1/rsync

###### Last updated: Jun 2, 2021
