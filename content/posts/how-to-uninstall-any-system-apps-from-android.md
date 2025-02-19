---
title: "How to Uninstall Any System Apps From Android"
date: 2025-02-08T21:24:51+06:00
draft: false
tags: ['android system apps', 'uninstall software', 'remove app', 'uninstall system apps', 'android app uninstall']
---

# Method 1: With a PC

1. Turn on developer options of you android phone and turn on USB Debugging.
2. Connect your phone with PC and always allow debugging from this device.
3. Install `adb drivers` for your phone in your PC and type `adb devices`
4. If your device show in your PC then finally run the command.

```shell
adb shell pm uninstall --user 0 "app_name_here"
```
> use the `-k` option if you need to keep the user data

# Method 2: Without a PC

1. Download and install `local adb` app. also known as `ladb`
2. Turn on developer options of you android phone and turn on Wireless Debugging.
3. Tap on Pair With Code and open the window in split mode.
4. Open the `ladb` app and put the port and pairing code in the correct field of the `ladb` app.
5. Wait till your phone accept the connection and finally type the following command.

```shell
pm uninstall --user 0 "app_name_here"
```
> use the `-k` option if you need to keep the user data

Useful Links: [miui bloat remove](https://selivan.github.io/2020/02/25/removing-bloatware-from-xiaomi-miui-android.html) - [install removed apps](https://xdaforums.com/t/how-to-install-get-back-uninstalled-apps-apks-with-adb.3894235/) - [Method 2](https://xdaforums.com/t/how-to-install-get-back-uninstalled-apps-apks-with-adb.3894235/page-4#post-84291287)
