# ClamAV

**ClamAV** is an open-source antivirus engine that scans files for viruses and malware.

The Archives uses ClamAV in the digital transfer workflow to check transfer packages and remove infected files before ingest to the repository. If you find infected files in a given transfer, you should contact the producer to advise them of the situation.

See [SFU Archives usage guide](../sfu-archives-guides/clamav.pdf) for details on intallation and configuration. The two basic commands SFU Archives uses are `freshclam` (update virus definitions) and `clamscan` (run check on a folder)

```
freshclam
```

```
clamscan -ri --log=/path/to/log.txt /path/to/transfer/folder
```

Flags:
- `-r` = recursive: scan all sub-folders and items.

- `-i` = infected: print only names of infected files.

- `--log` = output the scan results to a separate log file; give the full path + file name and extension (e.g. `--log=/Users/richarddancy/Desktop/Clamscan/log.txt`)

- `transfer folder` = the folder's file path; you can get this by simply dragging the folder into your Terminal window.

### Links
- [ClamAV website](https://www.clamav.net)
- [SFU Archives usage guide (pdf)](../sfua-usage-guides/clamav-sfua.pdf)


###### Last updated: June 3, 2025
###### [Back to Home](../README.md)
