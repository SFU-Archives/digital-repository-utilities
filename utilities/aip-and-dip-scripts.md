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
These are command-line scripts to support ad-hoc retrieval of packages from Archivematica and upload to AtoM, by-passing the interfaces provided by those applications. In some cases, they provide a faster alternative to the application interface; in others, there is no interface for the required action and the command-line provides the only method.

## Installation
[AIP retrieve](#aip-retrieve) is an `scp` (secure copy) command that can be run from Terminal and does not need to be installed.

The DIP scripts are compiled Python scripts that should be installed on your computer so that they can be easily run as line commands in Terminal. Download copies from the shared drive at `ITM002-40 > DRUtilities > AIP_DIP_Scripts`. Unzip the files and move to your `/usr/local/bin/` directory.

```
$ mv <file_path_of_downloaded_copy> /usr/local/bin/
```

**Notes**
- You will need administrator access to your computer to move the files to your `/usr/local/bin/` folder.

- Your SFU user name must be added to the `vm-admin` maillist in order to access the VMs on which AIPs and DIPs are stored.

- You must have passwordless key-based authentication, i.e. your computer's RSA key must be added to the VMs as an authorized key.

## Usage
Example line commands (exposing VM names and file paths) are documented on the Archives' wiki for internal use only.

### AIP retrieve
You can download AIPs through your web browser from the Archivematica or Storage Service interface, but this can be slow when the AIP is large. The `AIP retrieve` command provides a quicker alternative, using `scp` (security copy).

**Command**
```
$ scp -r <<user_name>>@<<server_name:'<<aip_location>>*' .
```

**Notes**
- Target file path is different depending on whether the package is a fully processed AIP or still in backlog; see the Archives' internal documentation for details.

- You cannot use `scp` to download AIPs stored in the encrypted directory; it will only work with standard, unencrypted AIPs.

- Packages will download to your `home` directory on your computer.

**Use cases**
- General: you need to download a large AIP and transfer via the web browser is slow.

There are various scenarios in which an archivist needs to download an AIP:
- Reference: researcher requests access to files in their original or preservation formats.
- Processing: you need to manually redact an access copy (AIP must be restructured and re-ingested).
- Processing: you want to manually re-normalize files outside Archivematica.

### DIP retrieve
This script downloads a stored DIP along with an accompanying `csv` file.
- Stored DIPs can also be downloaded from the Storage Service interface, but not all Archives' staff have access to Storage Service; and Storage Service will not create / download the `csv` file.

**Command**
```
$ dip-retrieve <pipeline> <user_name> <aip_name>

```

**Notes**
- You may need to do some work to find the AIP name: e.g. get the AIP UUID from AtoM, search the Archivematica `Archival storage` tab, then copy the AIP name to your clipboard.

- There is a field in the AIS database AIP record for `AIP name`, but we have only recently begun capturing this (in the past we just recorded the UUID with a descriptive note); always update this field when possible to facilitate future retrievals.

- The DIP will download to your `Desktop` folder.

- The DIP will include all the DIP digital objects plus a csv file listing all file names; the `csv` file is used in the [DIP upload](#dip-upload) and [DIP metadata upload](#dip-metadata-upload) scripts.

**Use cases**
- Reference: researcher requests access to materials described but not available in AtoM (e.g. high-risk copyright protected works; restricted materials only available under a Research Agreement).

- Processing: you want to quality control Archivematica processing, i.e. verify that the DIP copy is functional (e.g. video plays properly).

- Accessioning: you want to get the size of the DIP to record in the AIS database AIP record.

### DIP upload
This script uploads DIP objects to existing description records in SFU AtoM, using a csv file to map objects to descriptions.

**Edit the csv file**

You must first run the [DIP retrieve script](#dip-retrieve) and edit the `csv` file included in the DIP package.
- The `csv` file will be included in the `objects` folder and it will have the same name as the parent DIP folder, e.g. `ACN2018-025_Fellman_EmailAttachments.csv`.

The csv file has two columns: `filename` and `slug`.
- The `filename` column (A) lists the names of the digital objects in the DIP; the names include the UUID that Archivematica assigned to each object.
- The `slug` column (B) will be blank; this is where you enter the AtoM slugs.

The AtoM slug is the last part of the AtoM url that follows `server_name.archives.sfu.ca/`
- E.g. in `cottonwood.archives.sfu.ca/f-10-4-0-0-0-1` the slug is `f-10-4-0-0-0-1`.
- In SFU AtoM, the slug is typically (but not always) identical to the unit's reference code, with the `f-` prefix in lowercase.

Find the AtoM slugs of the existing descriptions and enter them into column B of the csv file, matching the slug to the appropriate filename.

Save the `csv` file with changes and leave it in the same location.

**Command**
```
$ dip-upload <server_name> <dip_file_path>
```

**Notes**
- Check the AtoM records to verify that DIP upload was successful.

**Use cases**
- Digitization: you digitize previously described analog materials and want to upload the digital copies to the existing AtoM descriptions.

- Access review: you review born-digital materials with access or copyright restrictions and the records are now cleared for online dissemination.

## DIP metadata upload
This script is similar to the [DIP upload](#dip-upload) script, except it sends only the minimal file metadata about the DIP objects rather than the full object itself.
- This is the equivalent of doing a bulk **metadata only DIP upload**.

- For instructions and notes on editing the DIP csv file, see [DIP upload](#dip-upload) above.

**Command**
```
$ dip-upload <server_name> <dip_file_path>
```

**Use cases**
- Digitization: you digitize previously described analog materials, have not yet cleared the records for access or copyright restrictions but you would like to send the digital object metadata to the existing Atom records to indicate to users that digital copies exist.

## Links
The scripts were created by Alex Garnett. Source code and documentation are available on his GitHub site at: https://github.com/axfelix/dip-mungers.

###### Last updated: May 6, 2021
