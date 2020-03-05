# Ionic Live Update Demo

[![macOS](https://img.shields.io/badge/macOS-Catalina-black)](https://developer.apple.com/macos/)

> Ionic Appflow's Deploy feature makes it easy to deploy app updates in real time without going through a traditional app store submission process for the vast majority of business logic, UI, and style changes.
>
> Note: The Deploy feature only works on binary compatible changes (HTML, CSS, JS), meaning if you rely on native code updates you must resubmit to the app store first before using Deploy.
>
> [Deploy a Live Update](https://ionicframework.com/docs/appflow/quickstart/deploy)

## Get Started 
1. [Create a free Ionic account](https://ionicframework.com/getting-started#account)
2. [Connect Your Repo](https://ionicframework.com/docs/appflow/quickstart/connect)
3. [Install the Appflow SDK](https://ionicframework.com/docs/appflow/quickstart/installation)
4. [Push a Commit](https://ionicframework.com/docs/appflow/quickstart/push)
5. [Deploy a Live Update](https://ionicframework.com/docs/appflow/quickstart/deploy)

## Supported
**All cases**
* Simulator
* Debug running
* TestFlight
* App Store

## Examples

### Create Ionic Project

```
$ ionic start ionic-live-update-demo tabs --type=react --capacitor
$ ionic serve
```

### Set up for iOS

```
$ ionic build --prod
$ npx cap add ios
$ npx cap open ios
```

We should set our Bundle Identifier and Signing Team.

### Link Ionic Hub

```
$ ionic link 68de2b8d
$ git push ionic master
```

### Installing the Appflow SDK

```
$ ionic deploy add --app-id="68de2b8d" --channel-name="Production" --update-method="auto"
$ git push ionic master
```

Then, deploy a Live Update the following flow.

* Change & Commit on local
* Push to Ionic Hub from local
* Build & Deployment on Ionic Hub

No update the app on iOS, any changes the app from Ionic :tada:
