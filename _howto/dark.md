---
title: Use the Dark theme
layout: howto
feedback: https://www.7cups.com/@RarelyCharlie
---
*Dark* is a customizable theme modifer for 7 Cups that provides an inverted (white on black), high contrast or low contrast theme.

### Who can use Dark?
You can probably use Dark if you use 7 Cups in a web browser on a computer.

You might be able to use Dark if you use 7 Cups in a web browser on an Android device.

You cannot use Dark on an Apple iOS device.

You cannot use Dark if you use the 7 Cups App on any kind of device.

### What you need
To use Dark, you need to install two things in this order:

1. First install [Tampermonkey](http://tampermonkey.net/) in your web browser.

   If your web browser is not compatible with Tampermonkey, then you probably cannot proceed with the next step. However, at [Greasy Fork](https://greasyfork.org/en) you can find some information about alternatives to Tampermonkey.

2. Next, install the [Dark](https://greasyfork.org/en/scripts/370980-7-cups-dark-theme) script.

To install each of these in turn, click the relevant link and follow the instructions.

### Turning the theme on and off
To turn the theme on and off, use the button at the top left of the screen (beside the teacup logo):

![Button](/assets/dark/button.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

The theme remembers the setting when you reload the page or go to another page.

### Settings
To customize the theme, go to your My Settings page (by logging in to 7 Cups, clicking on your own profile image at the top right, and choosing My Settings from the menu).

Dark adds a **Dark Theme** section to the page:

![Settings](/assets/dark/settings.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

(This shows a member account's settings. For listeners it looks a little different but it operates the same way.)

When you change the settings, they are applied after a short delay. The theme remembers your settings and you do not have to save your profile (unless you have changed something else there).

Use the **Dark theme** checkbox to choose a dark (white on black) theme as shown above. Clear the checkbox to choose a normal (black on white) theme.

Use the **Brightness** slider to adjust the brightness, if necessary. Its normal position is in the middle (0%).

Use the **Contrast** slider to adjust the contrast, if necessary. Its normal position is near the right-hand end (100%).

The default when you install Dark is: dark theme, brightness -20%, contrast 50%:

![Default](/assets/dark/default.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

The 7 Cups default (without Dark) is: normal theme, brightness 0% (in the middle), contrast 100%. There is no point in using these settings, except as a starting point for making changes:

![Normal](/assets/dark/normal.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

For a high contrast dark theme, try: dark theme, brightness 15%, contrast 120%:

![Very dark](/assets/dark/inverted-hi.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

For a low contrast normal (black on gray) theme, try: normal theme, brightness 10%, contrast 50%:

![Low contrast](/assets/dark/normal-lo.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

It is easy to choose settings that make the page unreadable! If you can't even see the sliders, use the button at the top left to remove the custom theme temporarily.

Use the **Apply contrast to images** checkbox to apply your contrast setting to images. This may be useful if you find images too bright.

Use the **Use custom styles** checkbox to add custom styles to the theme. This is an advanced setting and you need some specialized knowledge to use it effectively. However, playing with it cannot do harm. When you check the box, an area appears where you can type custom style rules using the CSS language. For example:

![Settings](/assets/dark/settings-css.png){:style="box-shadow: 2px 2px 8px 0px rgba(0,0,0,0.75);"}

### Known issues
The colors of some elements in the page do not change in the same way. This problem mostly affects images. For example, an image of black text on a white background will not change to white on black. You can only reduce the contrast of images.

Dark takes a relatively long time to work every time you load a page. This means that on every page you see normal colors for a moment before Dark kicks in.

### Removing Dark
If you want to remove Dark, you can temporarily disable the script or you can delete it. You can also disable or delete Tampermonkey.

### Feedback
Please provide feedback in the forum: [Dark theme with contrast settings](https://www.7cups.com/forum/LaurasOffice_133/SuggestionsandProblemSolving_383/Darkthemewithcontrastsettings_167439/)

Alternatively, to contact the author go to [@RarelyCharlie](https://www.7cups.com/@RarelyCharlie) and send a message.

Please do not send feedback about this unofficial feature to 7 Cups, because they will be unable to act on it.

