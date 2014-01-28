### Change font size of file sidebar and tab labels

Select `Preferences / Browse Packages`, and go to `Theme - Default directory`. 

Open `Default.sublime-theme` file.

Locate `sidebar_label` and `tab_label` text in this file. Add `"font.size"` attribute like this:

```
{
    "class": "sidebar_label",
    "color": [0, 0, 0],
    "font.bold": false,
    "font.size": 14.0           <- only this line added
}

...

{
    "class": "tab_label",
    "fg": [0, 0, 0, 255],
    "shadow_color": [255, 255, 255, 80],
    "shadow_offset": [0, 1],
    "font.size": 14.0           <- only this line added
},
``` 
