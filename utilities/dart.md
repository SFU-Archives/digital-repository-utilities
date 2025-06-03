The **Digital Archivist's Resource Tool (DART)** is a desktop application developed and maintained by the Academic Preservation Trust ([AP Trust](https://aptrust.org/)) to support transfers of digital materials to repositories using the [BagIt File Packaging Format (RFC 8493)](https://datatracker.ietf.org/doc/html/rfc8493). Source code, documentation and download links are all available on AP Trust's [GitHub site](https://github.com/APTrust/dart).

In Fall 2023, SFU Archives retired its custom-built BagIt packaging app, [[SFU MoveIt]], and began investigating DART as a possible replacement. DART provides an interface for users to:
- Select files for packaging.
- Enter their contact information and some descriptive data about the material.
- Create a BagIt-compliant package ("bag") ready for transfer to Archives.

The app supports the creation of multiple BagIt Profiles that can accommodate different transfer scenarios and user groups (e.g. require different metadata fields). It can be configured to support transfers over a network to any sftp server or S3-compliant API. Finally, DART can also be used to validate bags received.

In SFU Archives' use, SFU staff and private donors:
- Install DART on their local machines.
- Import SFU-specific transfer profiles.
- Create transfer packages to their desktop.
- Transfer packages to the Archives via [SFU Vault](sfu-vault.md) or external drives physically delivered to the Archives.

No data is transferred over the network through DART (in the longer term this is something the Archives may investigate). On receipt of a transfer, the Archives uses DART to validate transfers.

As of June 2024, DART would is included in SFU's Managed Software Center, allowing university staff working on SFU-managed machines to easily download and install the program.

See the [Archives' DART usage guide](../sfua-usage-guides/dart-sfua.pdf) for details on configuration, settings and BagIt profiles.

### Links
- [DART GitHub site](https://github.com/APTrust/dart)
- [AP Trust (developer)](https://aptrust.org/)
- [BagIt specification](https://datatracker.ietf.org/doc/html/rfc8493)
- [SFU Archives usage guide (pdf)](../sfua-usage-guides/dart-sfua.pdf)


###### Last updated: June 3, 2025
###### [Back to Home](../README.md)
