###### [Digital Repository Utilities](../README.md)

# maildir2mbox
`maildir2mbox` is an command line Python script adapted by SFU Archives ca. 2013 from an [existing project](http://yergler.net/blog/2010/06/06/batteries-included-or-maildir-to-mbox-again/) originally created by Nathan Yergler in June 2010 and ported to Python 3 by Philippe Fremy. SFU's Alex Garnett made additional modifications in 2019.

The Archives has used the script to convert `maildir` exported from SFU Mail by OfflineImap to `mbox` format for ingest into Archivematica and ePADD.

Note that as of June 2022, SFU Archives also uses the proprietary software Emailchemy to perform conversions. Emailchemy's user interface makes it somewhat easier to use, and it also supports conversions to and from other email formats.

## Contents
- [Download](#download)
- [Configuration](#configuration)
- [Usage](#usage)
- [Code](#code)

## Download
The script is stored on the Archives' shared drive at `ITM002-40 > DRUtilities > maildir2mbox > maildir2mbox.py`.

Once downloaded, it can be run from any location on your computer.

## Configuration
None required.

## Usage
To run, open a Terminal window:
- `$ python3 <<path/to/script>> <<path/to/maildir/input/folder/>> <<path/to/mbox/output/folder/>>`

## Code
The full code of the script is given below, save as a Python file (`.py`).

```
#!/usr/bin/env python3
import os
import sys
import mailbox
import email
USAGE = u"""
$ python maildir2mbox.py [maildir_path] [mbox_path]
"""
def maildir_to_mailbox(maildir_path, mbox_path):
    """
    slightly adapted from maildir2mbox.py,
    Nathan R. Yergler, 6 June 2010
    http://yergler.net/blog/2010/06/06/batteries-included-or-maildir-to-mbox-again/
    Port to Python 3 by Philippe Fremy
    """
    # open the existing maildir and the target mbox file
    maildir = mailbox.Maildir(maildir_path, email.message_from_binary_file)
    n = len(maildir)
    if n == 0:
        return
    mbox = mailbox.mbox(mbox_path)
    # lock the mbox
    # mbox.lock()
    # iterate over messages in the maildir and add to the mbox
    n = len(maildir)
    for i, v in enumerate(maildir.iteritems()):
        key, msg = v
        if (i % 10) == 9:
            print( 'Progress: msg %d of %d' % (i+1,n))
        try:
            mbox.add(msg)
        except Exception:
            print( 'Exception while processing msg with key: %s' % key )
            traceback.print_exc()
    # close and unlock
    mbox.close()
    maildir.close()
if __name__ == '__main__':
    if len(sys.argv) < 3:
        print(USAGE)
        sys.exit(0)
    maildir_path = sys.argv[-2]
    mbox_path = sys.argv[-1]
    # Canonize paths
    maildir_path = os.path.realpath(maildir_path)
    mbox_path = os.path.realpath(mbox_path)
    print("{} -> {}".format(maildir_path, mbox_path))
    if not os.path.exists(mbox_path):
        os.makedirs(mbox_path)
    maildir_dirs = ['cur', 'new', 'tmp']
    for root, dirs, files in os.walk(maildir_path):
        if root == maildir_path:
            continue
        relpath = os.path.relpath(root, maildir_path)
        mbox_subpath = os.path.join(mbox_path, relpath)
        os.makedirs(mbox_subpath)
        # We don't have to traverse empty directories, only if they are Maildir
        if not set(maildir_dirs).issubset(dirs):
            continue
        # Prune from dirs subsequent cur, new, tmp directories
        dirs[:] = [d for d in dirs if d not in maildir_dirs]
        # Create directory in the target
        # This isn't needed with Outlook, uncomment on other IMAPs
        # if not os.path.exists(mbox_subpath):
        #    print("Creating {}".format(mbox_subpath))
        #    os.makedirs(mbox_subpath)
        maildir_to_mailbox(root, mbox_subpath + '.mbox')
```

###### Last updated: Jul 26, 2022
