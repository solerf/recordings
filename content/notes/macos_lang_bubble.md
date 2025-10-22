+++
title = 'Stop macos language bubble'
date = '2025-10-22T16:25:44+02:00'
draft = false
tags = ['macos']
+++

I think it started to appear in Sonoma version, in any case to stop this annoying thing:

![image](/images/macos_lang_bubble.png)

```shell
# 1st
sudo mkdir -p /Library/Preferences/FeatureFlags/Domain

# then
sudo /usr/libexec/PlistBuddy \ 
  -c "Add 'redesigned_text_cursor:Enabled' bool false" \
    /Library/Preferences/FeatureFlags/Domain/UIKit.plist
```

and then reboot.

Source: https://stackoverflow.com/questions/77248249/disable-macos-sonoma-text-insertion-point-cursor-caps-lock-indicator
