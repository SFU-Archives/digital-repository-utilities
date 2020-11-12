###### [Digital Repository Utilities](../README.md)

# AIP and DIP Scripts
Retrieve stored AIPs and DIPs, upload DIPs or DIP metadata to AtoM.

**Contents**
- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
  - [AIP retrieve](#aip-retrieve)
  - [DIP retrieve](#dip-retrieve)
  - [DIP upload](#dip-upload)
  - [DIP metadata upload](#dip-metadata-upload)
- [Links](#links)

## Description
These are command-line scripts or commands to support ad-hoc retrieval and upload of packages from / to Archivematica or AtoM outside the interfaces provided by those applications. In some cases, they provide a faster alternative to the application interface; in others, there is no application interface for the required action and the command-line provides the only method.

## Installation
[AIP retrieve](#aip-retrieve) is an `scp` (secure copy) command that can be run from Terminal and does not need to be installed.

The DIP scripts are compiled Python scripts that should be installed on your computer so that they can be run as line commands in Terminal. Download copies from the shared drive at `ITM002-40 > DRUtilities > DIPUploadCLIScripts`. Unzip the files and move to your `/usr/local/bin/` directory.

```
$ mv <file_path_of_downloaded_copy> /usr/local/bin/
```

**Notes**
- You will need administrator access to your computer to move the files to your `/usr/local/bin/` folder.

- Your SFU user name must be added to the `vm-admin` maillist in order to access the VMs on which AIPs and DIPs are stored.

- You must have passwordless key-based authentication, i.e. your computer's RSA key must be added to the VMs as an authorized key.

## Usage
###AIP retrieve
Use the AIP retrieve command as an alternative to downloading AIPs through your web browser from the Archivematica or Storage Service interface, which can be slow when the AIP is large. The target file path is different depending on whether the package is a fully processed AIP or still in backlog.

**Use cases**
- General: you need to download a large AIP and transfer via the web browser is slow.

There are various scenarios in which an archivist needs to download an AIP:
- Reference: researcher request for access to files in their original or preservation formats.
- Processing: manually redact an access copy (AIP must be restructured and re-ingested).
- Processing: manually re-normalize files outside Archivematica.

**To download an AIP**
```
$ scp -r <<user_name>>@cherry.archives.sfu.ca:'/data/<<pipeline>>/aips/**/<<aip_name>>*' .
```

**To download a backlog package**
```
$ scp <<user_name>@cherry.archives.sfu.ca:'/data/<<pipeline>>/transfer_backlog/originals/<<aip_name>>*'
```

**Notes**
- You cannot use `scp` to download AIPs stored in the encrypted directory; it will only work with standard, unencrypted AIPs.

- Packages will download to your `home` directory on your computer.

### DIP retrieve
This script downloads a stored DIP. Stored DIPs can also be downloaded from the Storage Service interface, but not all Archives' staff have access to Storage Service.

**Use cases**
- Reference: provide access (deliver a copy) to materials not available in AtoM (e.g. high-risk copyright protected works; restricted materials only available under a Research Agreement).

- Processing: quality control Archivematica processing, i.e. verify that the DIP copy is functional (e.g. video plays properly).

- Accessioning: get the size of the DIP to record in the AIS database AIP record.

**Command**
```
$ dip-retrieve <pipeline> <user_name> <aip_name>
```

**Notes**
- You may need to do some work to find the AIP name: e.g. get the AIP UUID from AtoM, search the Archivematica `Archival storage` tab, then copy the AIP name to your clipboard.

- There is a field in the AIS database AIP record for `AIP name`, but we have only recently begun capturing this (in the past we just recorded the UUID with a descriptive note); always update this field when possible to facilitate future retrievals.

- The DIP will download to your desktop.

- The DIP will include all the DIP digital objects plus a csv file listing all file names; the csv file is used in the [DIP upload](#dip-upload) and [DIP metadata upload](#dip-metadata-upload) scripts.

### DIP upload
This script uploads DIP objects to existing description records in SFU AtoM, using a csv file to map objects to descriptions.

**Use cases**
- Digitization: digitize previously described analog materials and upload the digital copies to the existing AtoM descriptions.

- Access review: born-digital materials with access or copyright restrictions are reviewed and cleared for online dissemination.

**Command**

**Notes**


## DIP metadata upload

## Links
The scripts were created by Alex Garnett. Source code and documentation are available on his GitHub site at: [https://github.com/axfelix/dip-mungers].

###### Last updated: Oct 30, 2020
