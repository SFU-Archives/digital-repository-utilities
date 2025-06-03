# Bagger

**Bagger** is open-source, java-based desktop application for creating, editing, and validating Bags – i.e. packages of data files that adhere to the [BagIt specification](https://tools.ietf.org/html/rfc8493). Bagger was developed by the Library of Congress. The latest version ([2.8.1](https://github.com/LibraryOfCongress/bagger/releases/tag/v2.8.1)) was released in April 2018 but is no longer actively maintained.

SFU Archives initially used Bagger in its digital transfer workflow to validate transfer packages received and add validation metadata. The Archives had its own preferred Bag-creating packager [SFU MoveIt](sfu-moveit.md) and used Bagger only for validation purposes.

Because Bagger has not been actively updated, the current version validates Bags against BagIt version 0.97 rather than 1.0 (finalized in Oct 2018). Bagger will fail packages that use "1.0" as the `BagIt-Version` in the `bagit.txt` file.

In the Fall of 2023, SFU Archives decided to retire [SFU MoveIt](sfu-moveit.md) and discontinue using Bagger for validation. In 2024 the Archives adopted [DART](dart.md) as a single utility for both packaging and validation.

### Links
- [Bagger GitHub page](https://github.com/LibraryOfCongress/bagger).
- [SFU Archives usage guide (pdf)](../sfua-usage-guides/bagger-sfua.pdf)


###### Last updated: June 3, 2025
###### [Back to Home](../README.md)
