---
title: "How to Fix Bangla Font Problem in Linux"
date: 2025-02-08T10:11:50+06:00
draft: false
---

Download Siyamrupali font and move it to `~/.local/share/fonts/bangla-fonts`

paste the code to `~/.config/fontconfig/conf.d/50-custom-bangla.conf`

```xml
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
<!-- Bangla (bn) -->
    <match target="font">
            <test name="lang" compare="contains">
                    <string>bn</string>
            </test>
            <alias>
                    <family>sans-serif</family>
                    <prefer>
                            <family>Siyamrupali</family>
                    </prefer>
            </alias>
    </match>

    <match target="font">
            <test name="lang" compare="contains">
                    <string>bn</string>
            </test>
            <alias>
                    <family>serif</family>
                    <prefer>
                            <family>Siyamrupali</family>
                    </prefer>
            </alias>
    </match>
<!-- Bangla (bn) ends -->
</fontconfig>
```
