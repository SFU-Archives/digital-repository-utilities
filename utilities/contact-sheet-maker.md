# ContactSheetMaker

ContactSheetMaker is a command-line Python script developed by Kelsey Poloney ca. 2020. It takes a folder of images (typically digital photographs) and creates a set of thumbnail images (one for each file) as a multi-page pdf document. It then structures the parent folder so that it is ready for ingest to [Archivematica](archivematica.md).

The resulting pdf mimics the traditional analog photographic contact sheet – a positive print of all negatives from a roll of film that facilitates scanning and selection of images. SFU Archives uses ContactSheetMaker when it receives transfers of folders that contain large numbers of photographs. Rather than uploading each photograph to [SFU AtoM](atom.md) as individual items, the processing archivist uses the script to create a digital contact sheet, then uploads that to AtoM as a representation of an **archival file**. Researchers can easily browse the pdf sheet and identify any images for which they would like copies. An archivist can then deliver the copies of the originals offline.

The script can be used in many circumstances, but was originally designed with a particular use case in mind: transfers of photos from campus units that employed staff photographers (e.g. University Communications). Photographers typically organized their files into folders representing photo shoots or projects. The folders often contain a very large number of very similar shots, only one or two of which may have been selected for publication / use. Typically the creators did not exercise any further appraisal (i.e. they did not destroy the non-selected images). They did not normally document which files were selected, and it is not usually possible to determine this years later. The Archives generally does not consider it feasible or desirable to do item-level appraisal and selection, but neither do we wish to flood SFU AtoM with a plethora of similar files. By uploading the contact sheet only, we provide simple access to all images, while allowing researchers to identify those for which they wish to get full copies.

### Links
- [Developer's GitHub site](https://github.com/kpoloney/contact_sheet)
- [SFU Archives usage guide (pdf)](/sfua-usage-guides/contact-sheet-maker-sfua.pdf)


###### Last updated: June 3, 2025
