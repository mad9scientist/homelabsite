+++
title = 'Easier Options for Music Server'
date = 2024-05-07T15:50:13-05:00
type = 'post'
+++
So... 

A day or two ago I wrote about setting up a [VM to stream music](/post/music-streaming-server/) to my Google Home Speakers. Since then, I realized a better option - just use Google Chrome/Chromium to stream directly - 🤦‍♂️.

I was so focus on the problem, I didn't realize this option:

* Original goal was to *not* have a desktop environment (CLI Only)
* When I did switch to having a DE I used my preferred browser - Firefox

Now I get the same functionality as described in the reference post above, but only using 'one' application - Chromium. 

----

I do have an quick update on the configuration I did in the previous [article](/post/music-streaming-server/). It works fine with only a few problems.

* Random Logout from while sitting on desktop <br> May be issue with Ubuntu 24.04
* After 20-24 hours of continuous playback would crash/stop <br> mkChromecast would have a communication error with the main Google Home for the Speaker Group. Requiring the restart of the mkChromecast Process. 

Other than having to 'restart' the mkChromecast process once every 20-24 hours it worked great.

----

Now I'm going to do an experiment to see if I can do this just from the CLI in a LXC container with headless Chrome &mdash; wish me luck.

If you have thoughts or a suggestion, tag me on [Twitter](https://twitter.com/mad9scientist) or [drop me a line here](https://mad9scientist.com/contact/).