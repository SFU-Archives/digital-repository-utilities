# SFU Archives BagIt Profiles

A [BagIt Profile](https://bagit-profiles.github.io/bagit-profiles-specification/) sets out a particular implementation of the BagIt File Packaging Format specification [(RFC 8493)](https://datatracker.ietf.org/doc/html/rfc8493), indicating which of the many optional BagIt elements are included and how. Bags can be created and validated against particular profiles.

SFU Archives has created three profiles for different transfer scenarios. Version numbers are included in the profile names. Current versions are all version `1.0`.

The Archives uses DART as its preferred packaging tool. Producers who wish to transfer digital records to SFU Archives should download and install DART and import the appropriate profile(s) into the app.

## Import a profile into DART

## Current profiles
### SFU University Records Transfer
Use for transfers of university records from SFU departments or units by SFU staff.

[SFU University Records Transfer v1.0](university-records-transfer-v1-0.json)

```
https://raw.githubusercontent.com/SFU-Archives/digital-repository-utilities/master/bagit-profiles/university-records-transfer-v1-0.json
```

### Private Organization Transfer
Use for transfers of corporate records from organizations that are not formally part of SFU.

[Private Organization Transfer v1.0](private-organization-transfer-v1-0.json)

```
https://raw.githubusercontent.com/SFU-Archives/digital-repository-utilities/master/bagit-profiles/private-organization-transfer-v1-0.json
```

### Personal Archives Transfer
Use for transfers of personal archival records from individual donors.

[Personal Archives Transfer v1.0](personal-archives-transfer-v1-0.json)

```
https://raw.githubusercontent.com/SFU-Archives/digital-repository-utilities/master/bagit-profiles/personal-archives-transfer-v1-0.json
```
## Non-current profiles
The Archives maintains previous iterations of the profiles in case users send transfers with non-current versions.
- [Personal Archives Transfer v0.1](personal-archives-transfer-v0-1.json) (Nov 2023 - May 2024)
- [Private Organization Transfer v0.1](private-organization-transfer-v1-0.json) (Nov 2023 - May 2024)
- [SFU University Records Transfer v0.1](university-records-transfer-v0-1.json) (Nov 2023 - May 2024)
