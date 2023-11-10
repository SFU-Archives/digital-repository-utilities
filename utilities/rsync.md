###### [Digital Repository Utilities](../README.md)

# rsync
###### Status: under development
`rsync` is a command-line utility for copying files and for syncing files and directories from two different systems.

SFU Archives uses rsync when moving data around across external drives and desktops (e.g. copying a digital transfer to / from an external drive used for temporary storage)

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
Archivists must periodically copy digital objects from external drives to their desktops for validation or processing. `rsync` can be used to ensure timestamps are preserved and checksums are validated.

**Command:**

```
$ rsync --archive --verbose --checksum <path/to/source/> <path/to/destination/>
```
Flags:
- `--archive` = archive mode = -rlptgoD
- `--verbose` = prints output to Terminal screen
- `--checksum` = compares checksums before / after copying

Flags included in the `archive` flag:
- `-r` = recursive; gets all sub-folders.
- `-l` = preserves symlinks (symbolic links to other folders).
- `-p` = preserves permissions
- `-t` = preserves timestamps
- `-g` = preserves group
- `-o` = preserves owner
- `-D` = preserves device files


## Links
- Homebrew rsync page: https://formulae.brew.sh/formula/rsync

- rsync manual page: https://linux.die.net/man/1/rsync

###### Last updated: Nov 10, 2023
