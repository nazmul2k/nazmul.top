---
title: "Add Screenshot Facility in I3wm"
date: 2025-02-08T11:43:48+06:00
draft: false
tags: ['i3wm','linux','linux tutorial']
---

**Dependencies:** maim, xclip, xdotool

**Optional Dependencies:** flameshot, shutter

```bash
######### Screenshots ########

bindsym $mod+Shift+s exec --no-startup-id flameshot gui


##  Screenshots in files
bindsym Print exec --no-startup-id maim --format=png "/home/$USER/Pictures/screenshot-$(date -u +'%Y%m%d-%H%M%SZ')-all.png"
bindsym $mod+Print exec --no-startup-id maim --format=png --window $(xdotool getactivewindow) "/home/$USER/Pictures/screenshot-$(date -u +'%Y%m%d-%H%M%SZ')-current.png"
bindsym Shift+Print exec --no-startup-id maim --format=png --select "/home/$USER/Pictures/screenshot-$(date -u +'%Y%m%d-%H%M%SZ')-selected.png"

## Screenshots in clipboards
bindsym Ctrl+Print exec --no-startup-id maim --format=png | xclip -selection clipboard -t image/png
bindsym Ctrl+$mod+Print exec --no-startup-id maim --format=png --window $(xdotool getactivewindow) | xclip -selection clipboard -t image/png
bindsym Ctrl+Shift+Print exec --no-startup-id maim --format=png --select | xclip -selection clipboard -t image/png
# bindsym mod1+Print exec --no-startup-id shutter
```
