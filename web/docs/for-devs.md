# For Developers

FoxLauncher is a platform that has a good deal of benefits that typical websites don't have. This page is dedicated to informing developers on the differences from typical web development.

## Info

### What are all these funny file names?

`.flr` : FoxLauncher Resource, a js file
`.flz` : [FoxLauncher Zip](#creating-a-flc), a zip file containing a folder of the same name
`.flc` : [FoxLauncher Config](#creating-a-flc), an xml file with config data.

### Creating a .flz

An `.flz` will load provided it contains mostly arbitrary zip data, but for usability its advised it contains a folder named the same thing as the folder.

Heres an example example `.flz` file tree
```bash
tab-game.zip # zip file
└── tab-game # index folder
    ├── index.html # arbitrary contents
    ├── index.js
    └── config.flc
```

### Creating a .flc

A `config.flc` is searched for when installing an extension, this can be technically stored anywhere, but I advise you to put it in the [index folder](#creating-a-flz).

A basic config looks like this:

```xml
<?xml version="1.0" encoding="utf-8"?>
<SETTINGS>
    <NAME>Tab Game</NAME>
    <AUTHOR>FoxMoss</AUTHOR>
    <PERMISSIONS>
        <PERM>tabs</PERM>
    </PERMISSIONS>
</SETTINGS>
<!-- GETTING GOOD USE OUT OF THE CAPS LOCK KEY, AREN'T YOU? -->
```

## Limits

### Links, Reloading, and History

Basically any page load request that was not initiated by the browser or the user for a page using a `filesystem:` url will be blocked by chrome. 

Please see [Tab Control](#tab-control)

## Extended Privileges

Most extended privileges FoxLaunched sites have can be summed up fairly easily. If FoxLauncher is installed on an extension page, you can then access the same chrome APIs that it has access to.

Check [here](https://developer.chrome.com/docs/extensions/reference/) for the list of all chrome APIs.

### Tab Control

Controlling tabs can instead be accessed by the chrome.tabs API. This API is accessible to most extensions and due to the possessive powers of FoxLauncher, if the filesystem is a child of an extension you can access the same control of an extension.

You can read the documentation for this API here [developer.chrome.com/docs/extensions/reference/tabs/](https://developer.chrome.com/docs/extensions/reference/tabs/).

### BoyKisser API

The name says it all, you can probably guess the code for this one.