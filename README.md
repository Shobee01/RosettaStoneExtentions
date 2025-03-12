# Rosetta Extentios
IF YOU NEED TO COMPLETE YOUR 30 HOURS CONTACT US VIA WHATSAPP NUM .
        +212 693094897
            
<font color="green">For personal speacial reasons we have closed The extention. if you have special requests , or you need it for work please contact us in the following number .
Or contact us via :
    shobee.market@gmail.com</font>

- [Introduction](#introduction)
- [Install](#install)
    - [Chrome](#chrome-based-browsers)
    - [Firefox](#firefox-based-browsers)
- [How to use](#how-to-use)
    - [Adding time](#adding-time)
        - [Foundations](#adding-time-in-foundations)
        - [Fluency builder](#adding-time-in-fluency-builder)
    - [Validating lesson](#validating-lesson)
        - [Foundations](#validating-lesson-in-foundations)
        - [Fluency builder](#validating-lesson-in-fluency-builder)

## Introduction

rosettaextention is a browser extension that allows one to add time and validate
lessons on rosetta stone learning language platform.

> rosettaextention, and your rosetta stone goes stonks.

## Install

### Chrome based browsers

1. Using github release

To use the extension in a chrome-based browser, you need to:
- download the file `rosettaextention-chrome.tar.gz` from the latest release on
  your machine.
- create a folder named `rosettaextention` somewhere on your machine to store the
  extension
- run the following command in the `rosettaextention` folder.
```bash
$ tar xvzf /path/to/rosettaextention-chrome.tar.gz
```

2. Using nix package manager

Instead of the previous commands, if you are on a nix system **supporting
flakes**, you can run the following commands, which will give your the path to
the `rosettaextention` folder (named `rosettaextention-chrome`)

```bash
$ nix build --out-link "" --print-out-paths github:m1dugh/rosettaextention#chrome
```

**This part if for all users indepently of whether you are using github method
or nix method.**

In your browser:
- go to `chrome://extensions`
- check the `Developer mode` toggle
- click `Load unpacked`
- Select your `rosettaextention` folder

### Firefox based browsers

- download the file `rosettaextention.xpi` from the latest release.
- alternatively, if using nix package manager with flake support, your can run
  the following command.
```bash
$ nix build --out-link "" --print-out-paths github:m1dugh/rosettaextention#mozilla
```
- go to `about:addons` in your browser
- click the settings button and go to `Debug addons`.
- click `Load Temporary Add-On`
- select the `rosettaextention.xpi` file in the file picker, or the path the nix
  command gave you.

*Warning: This method only installs the extension temporarily, meaning that if
you close your browser, the addon will be uninstalled. This is due to firefox
policies not allowing unverified extensions to be used.*

## How to use

### Adding time

#### Adding time in Foundations

To add time on `foundations` product, you need to go to your exercises, and
click ignore or resolve one question at least. Once this is done, a time field
should appear on the extension page on which you can add your time.

#### Adding time in Fluency builder

To add time on `fluency builder` product, you need to go to your exercises, and
answer at least one exercise. If the add time field does not appear, it means
that no time request was caught, you need to refresh the question and answer it
once again. To have the time added, you need to finish the lesson you used to
add time.

*Note: If you don't see the add time field, it means that the actions you took
on Rosetta stone website did not lead to adding legitimate time, and therefore,
you need to answer other questions.*

### Validating lesson

#### Validating lesson in Foundations

To validate a lesson, one needs to start a lesson, and go through all of the
questions through the `ignore` button on the bottom right. Once all the
questions have been seen, clicking the `validate lesson` button should validate
the lesson. If not, go back to your home page, click on the same lesson, it
should ask you `Do you want to continue or reset ?`, you can choose both, and
validate lesson again until it works. It should work after 3/4 times maximum.


#### Validating lesson in Fluency builder

Right now, the validate lesson feature is not available on rosetta stonks.


## Building the application

### Building the worker

The worker can be packaged using the following command
```
$ deno task build:worker
```

Which creates the packaged file `/dist/worker.esm.js` which is the packaged
file for the worker.

### Building the frontend

The worker can be packaged using the following command
```
$ deno task build:front
```

Which creates the packaged file `/dist/frontend.esm.js` which is the packaged
file for the frontend.

## Packaging the extension

### Chrome

To package the extension for chrome, the following command can be ran:

```
$ make chrome
```

### Firefox

To package the extension for firefox, the following command can be ran:

```
$ make firefox
```

Which will produce `rosettaextention.xpi`, the file for the extension that can be
loaded in firefox.
