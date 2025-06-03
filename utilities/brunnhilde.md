**Brunnhilde** is an open-source utility for analysis and file characterization of disk images and file directories. The app was developed and is maintained by [Tessa Walsh](https://github.com/tw4l). The app can be run in a GUI or via command line.

Instructions below are given for both the [GUI](#usage-gui) and [command line](#usage-command-line) versions, but the Archives' preference is to use the command line.
- The command line version is simpler to run than the GUI, which use a deprecated element (`basename`) and requires the user to edit settings on different tabs.

SFU Archives uses Brunnhilde in both its digital transfer and archival processing workflows. It is used to analyze transfer packages prior to ingest and support validation and accessioning; and in archival arrangement and description the archivist can use Brunnhilde to better understand the contents of an accrual, identify duplicates, support appraisal, and document file formats.

## Installation
See the installation instructions on Walsh's GitHub repo for both [brunnhilde](https://github.com/tw4l/brunnhilde) and the [brunnhilde-gui](https://github.com/tw4l/brunnhilde-gui). Note that various dependencies may also need to be installed.

## Configuration
There are no special configuration requirements.

## Usage: command line
Open a Terminal window and run the following command:

```
brunnhilde.py -nz /target/directory /output/directory/
```

Flags:
- `-n`: skips virus scan with [[ClamAV]] (assuming you have already run virus scan as part of the transfer process).
- `-z`: scans contents of zip, tar, gzip, warc, and arc archive files

To get the `target directory`, drag the target folder into your Termainal window after typing `-nz `.

The `output directory` will be created by the script.

## Usage: GUI
Brunnhilde provides a user interface, but it must be launched from the command line in Terminal.
- Open a Terminal window.
- Navigate to the installation folder and run `$ python3 main.py`.
- You can also just drag the `main.py` file into the Terminal window after entering `$ python3 `.

The Archives' digital transfer procedures typically work with file directories rather than disk images.

On the Brunnhilde interface `Options` tab, initialize the following settings **before** processing the transfer.
- **Uncheck** the boxes under `Virus scanning`; the archivist should run [[ClamAV]] independently as part of the transfer workflow.
- Select "sha256" under `Checksum algorithm`.
- Leave **unchecked** the boxes under `Disk image options` (unless working with disk images).
- Under `General options`:
  - **Check** the boxes `Scan archive files...` and `Include Siegfried warnings in HTML report`.
  - Leave **unchecked** the boxes `Run bulk_extractor` and `Throttle Siegfried`.

To process a transfer, use the `Directory` tab.
- `Source`: navigate to the transfer folder; it should be unzipped.
- `Destination`: navigate to the output location; this can be anywhere on your computer.
- `Accession number/identifier`: use the following convention: `ACNYYYY-NNN` (e.g. `ACN2020-041`).
- Click the `Start scan` button.
- The `Status` field will show "In progress".

You will receive a desktop notification when Brunnhilde completes processing.
- For large transfers, completion may take some time (e.g. several hours).

## Links
- Brunnhilde GitHub site: https://github.com/tw4l/brunnhilde.
- Brunnhilde GUI GitHub site: https://github.com/tw4l/brunnhilde-gui.
- SFU Archives digital transfer procedures for archivists: [step 3.4: Analyze files](https://github.com/SFU-Archives/digital-transfer/blob/master/procedures/standard-archives/03-validation.md#34-analyze-files).

## Screenshot
![](https://github.com/SFU-Archives/digital-repository-utilities/blob/master/screenshots/brunnhilde.png)

`Last updated: Nov 27, 2023`
