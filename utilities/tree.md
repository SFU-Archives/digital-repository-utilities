**Tree** is an open-source, command-line utility that generates a text representation of a directory structure.

SFU Archives uses Tree in the digital transfer process to document contents transferred (typically only at the folder level). It is also used during archival processing to analysis, appraisal, arrangement and description.

**Contents**
- [Installation](#installation)
- [Usage](#usage)
- [Links](#links)

## Installation
Install with [[Homebrew]].

```
brew install tree
```

**Notes**
- You will need administrator access to your computer to install the software.

## Usage
You can use Tree to capture the full transfer down to the file level or (more typical for the Archives' workflows) to get a higher level representation of the folder structure.

Run Tree in a Terminal window.

```
$ tree -d -o /path/to/log/tree.txt>> /path/to/target/folder
```

- `-d` = Get directories only.

- `-o` = File path for output report; include file extension (e.g. `~/Desktop/tree.txt`)

- `target folder` = Folder to be analyzed; you can get the file path by dragging the folder into your Terminal window.

**Notes**
- If you want the full listing (including files), omit the `-d` flag.

- Use the `-L <<number>>` flag to specify the level of folders to include; e.g. `-L 1` would print only the top-level folders and files.

## Links
- Full list of Tree variable flags: https://linux.die.net/man/1/tree.

```
Last updated: Nov 28, 2023
```
