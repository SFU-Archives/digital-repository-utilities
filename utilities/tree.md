###### [Digital Repository Utilities](../README.md)

# Tree
Tree is an open-source, command-line utility that generates a text representation of a directory structure.

SFU Archives uses Tree in the digital transfer workflow to document the original structure of a transfer package to support later accessioning, appraisal, and description. The archivist typically captures only the folder structure and uploads the report to the [AIS database](ais.md) Validator module for further analysis.

**Contents**
- [Installation](#installation)
- [Usage](#usage)
- [Links](#links)

## Installation
Install with `homebrew`.

```
$ brew install tree
```

**Notes**
- You will need administrator access to your computer to install the software.

## Usage
You can use Tree to capture the full transfer down to the file level or (more typical for the Archives' workflow) to get a higher level representation of the folder structure.

Run Tree in a Terminal window.

```
$ tree -d -o <<file_path_for_output_report/tree.txt>> <<target_folder>>
```

- `-d` = Get directories only.

- `-o` = File path for output report; include file extension (e.g. `~/Desktop/tree.txt`)

- `target_folder` = Folder to be analyzed; you can get the file path by dragging the folder into your Terminal window.

**Notes**
- If you want the full listing (including files), omit the `-d` flag.

- Use the `-L <<number>>` flag to specify the level of folders to include; e.g. `-L 1` would print only the top-level folders and files.

## Links
- Full list of Tree variable flags: https://linux.die.net/man/1/tree.

###### Last updated: Jan 8, 2021
