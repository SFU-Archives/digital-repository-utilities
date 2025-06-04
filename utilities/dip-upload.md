# DIP Upload

SFU Archives uses [Archivematica](archivematica.md) as its digital preservation platform. Archivematica creates **Archival Information Packages (AIPs)** for long-term preservation and can send **Dissemination Information Packages (DIPs)** to [SFU AtoM](atom.md) as access copies.

When sending DIPs to AtoM, Archivematica always creates a new AtoM description record, linked to an existing **parent** description. This standard Archivematica workflow, however, cannot be used when the DIP object maps to an already existing AtoM description (e.g. an existing item). There are two main use cases:

1. **Digitization:** previously described analog materials that have existing AtoM descriptions are digitized and ready for upload to AtoM.

2. **Access / copyright review:** digital materials previously ingested to Archivematica and described in AtoM are reviewed for access or copyright restrictions, cleared (no restrictions apply), and can now be uploaded to AtoM.

In 2018, SFU's Alex Garnett created a set of **DIP munger scripts** to handle these scenarios. The archivist:
- Installed the scripts on their local machine and edits the config file with server and user credential information (one-time).
- Downloaded Archivematica's **stored DIP** using the `dip-retrieve` script.
- Edited a csv file created by `dip-retrieve` to map DIP objects to AtoM url stubs.
- Uploaded the DIP + csv file to AtoM (using `dip-upload` to send the digital objects to AtoM, `dip-metadata` for metadata only).
-

In 2021, Tessa Walsh (Artefactual Systems) revised the scripts to work with new security requirements in the Archives' server environment (SFU Cloud), including the need to run the scripts with Multi-Factor Authentication (MFA).

In 2024 the Archives migrated its servers to RHEL9, and there were difficulties installing and making the scripts work in the new environment. In May 2025 the Archives decided to retire the DIP munger scripts and instead rely on DIP upload methods Artefactual have built using a Symfony `digitalobject:load` command. Now the archivist:
- Downloads the Archivematica **stored DIP** using Storage Service.
- Creates a csv file with `slug` and `filename` columns to map DIP objects to AtoM description records.
- Uploads the DIP + csv file to the AtoM server.
- Logs on to the AtoM server to run the Symfony upload command.

### Links
- [Alex Garnett's original DIP munger scripts (GitHub)]
- [Tessa Walsh / Artefactual's revised DIP munger scripts (GitHub)]
- [Artefactual documentation]

###### Last updated: June 3, 2025
###### [Back to Home](../README.md)
