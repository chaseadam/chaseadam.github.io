---
layout: post
title:  "Broken LED TV to Art"
date:   2015-10-24 20:00:00
categories: electronics salvage art 827
---
My budd Tom purchased a top of the line Samsung LED TV 5 or so years ago. Just after the warranty expired, it failed. I offered to take it off his hands and see if I could get it to work. Turned out that the panel had a fault.

I took the panel apart and removed the LCD portion of the panel leaving only the backlighting consisting of LEDs, light piping and high quality deffusers. A 100W+ light table might be useful for art of an architect friend of mine.

This project started close to 2 years ago, but I finally got sick of moving this panel between the loft, Shed, screened in porch. Amazingly, after all that movement, there is no significant damage to the panel.

The video/control board controlled the backlight and interfaced with the IR remote and capacitive touch signals without the Tconn board connected, so I sold the Tconn board on eBay.

I needed to understand the signalling between the motherboard and the power supply for three reasons:
* the backlight is at 100% intensity without the motherboard attached
* control backlight intensity with the goal of making it adaptive to ambient light
* put the panel in power saving mode (<1W)

After probing all of the pins with the televisionon and found the following pin statuses:

The television preserves the last on state, so I just switched a power strip to meaure the suspected signal pin go through the startup sequence. The startup sequence starts with the backlight intesity very low and then sets the backlight intensity to the previously stored value set by default or by the user. This allowed me to see the following differences on the signal line.

The television didn't come with a remote, so I used my Samsung S4 which has the Peel Smart Remote (aka WatchON) manufacturer bloatware app. Turns out the Samsung S4 has several conveient sensors [LINK] as well as this IR blaster. This allowed me to turn the television on and off without having to mess with the capacitive panel.

After turning off the television, the pins were mostly at 0V potential:

Power saving off mode:
grounded 5v signal turns off backlight, but still consumes 15W

http://www.sammobile.com/2013/04/10/hidden-innovation-in-the-galaxy-s4/



def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
