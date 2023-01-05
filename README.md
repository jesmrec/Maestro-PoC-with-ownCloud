# Maestro with ownCloud Android app

Maestro is a mobile UI testing framework, that improves coordination between actions and responses from devices. 

## Setup

Follow [the installation instructions](https://maestro.mobile.dev/getting-started/installing-maestro) from the official website to install Maestro in your computer. 

## Pre-requisites

You'll need an ownCloud server. If you don't have one, the `demo.owncloud.com` server is always available. You'll find credentials in web login view. 

The requirement to execute is having two folders in root called `Documents` and `Photos`, that will be used during test execution. 

Additionaly, a real Android device or emulator must be running. Ckeck the `adb devices` command to assure it is ready. That command should return one line for every attached device.

Then, fetch the code from the current repo. Browse into `samples` folder to start.

## Execution

First, install the apk in the attached device/emulator:

`adb install owncloud.apk`

Tests could be executed individually or all together.

#### To execute just one flow

`maestro test -e USERNAME=<username> -e PASSWORD=<pwd> -e URL=<server_url>  <flow_to_execute>`

Example: 

`maestro test -e USERNAME=john -e PASSWORD=smith -e URL="https://myserver.com" flowRename.yaml`

Successful execution will return something like:

[](OneFlow.jpg)

#### To execute all together

`maestro test -e USERNAME=<username> -e PASSWORD=<pwd> -e URL=<server_url> --format junit .`

The `--format junit` directive tells the system to create a `report.xml` file with the outcome. An example of `report.xml` is placed inside the `samples` folder.

Successful execution:

[](AllFlows.jpg)

## Documentation

Everything about maestro in the official site: [https://maestro.mobile.dev/](https://maestro.mobile.dev/)


## Next

iOS PoC
