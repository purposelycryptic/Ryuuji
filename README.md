<p align="center">
 <img src="https://i.imgur.com/jNiKbgl.png">
</p>
<h1 align="center">Ryuuji</h1>

<p align="center">
First attempt at a Taiga-Plex interface middleware</p>

_____

**Status:** Currently **NOT ACTUALLY WORKING** _(just shows Plex activity)_

**Last Activity:** March 2019
_____

[Taiga](https://github.com/erengy/taiga) is the best Windows-based Anime-watching Tracking app that I am aware of, but sadly, it is also incompatible with the (arguably) best Media Center Server Platform for Anime (outside of the web interface, which is mostly there for server management).

So, since Taiga can't understand what Plex is saying, I figured it needed a helpful friend to help with social interactions like this - that would be Ryuuji.


This initial attempt at interfacing the two is basically a simple script inside an HTML page that reads Plex's activity, and displays it in the browser tab's title bar and window. The script can't run if the page is lauched directly from Explorer, so it needs to be on a server of some sort (not necessarily or even preferably another physical server, though). While making it, I kept it on an XAMPP Apache instance on my media server, so the folder structure in the repo has that in mind - the content of the '_xampp_' folder can simply be pasted into yours. If you want to use something like Docker instead, you can just use the content of the '_htdocs_' folder.

Since this is a very simple first attempt, before accessing the page in your browser, you will need to add your Plex Server information to the HTML file you would like to use (the only difference is the logo shown when inactive), specifically replacing the placeholder items **[IP_ADDRESS]**, **[PLEX_PORT]** and **[X_PLEX_TOKEN]** with your Plex Server's IP Address, the Port number Plex is using, and the X-Plex-Token, respectively (as you probably picked up from their names. The IP and Port are needed in two separate locations.

Once you are done, you should be good to go! Just direct your browser to your XAMPP or Docker instance's IP and port, followed by either _'/plex.html'_ or _'/ryuuji.html'_, depending on your earlier decision. It should look something like **192.168.1.66:8972/plex.html**, except with your actual IP and port.


Following are some images to give you an idea of what to expect:


**Plex Inactive - Using ryuuji.html**

![Inactive - Taiga + Ryuuji Logo](https://i.imgur.com/22fLK9P.jpg)


**Plex Inactive - Using plex.html**

![Inactive - Plex Logo](https://i.imgur.com/hbO5kir.jpg)


**Plex Active - Playing Video**

![Active - Playing Video](https://i.imgur.com/CQkT3Sv.jpg)


**Plex Active - Paused**

![Active - Paused](https://i.imgur.com/T4yWsly.jpg)


### Note:
As mentioned in the 'Status' above, Ryuuji doesn't actually interact with Taiga at present, as it doesn't have its own entry in [Anisthesia](https://github.com/erengy/anisthesia), which Taiga uses to detect media being played; I tried to make the output mimic the Plex Web Interface Player and other browser-based solutions from Anisthesia, but witout success.

Due to shattering the middle-finger on my dominant hand last fall, my hand was in a cast for the rest of the year, leaving any projects or ideas I was working on on hiatus, including this one. While incapacitated, I started wondering if this was the best approach to the issue, or if a simple webhook python or C# app/widget would be a better choice. At least it could run without any secondary programs required. I figured I'd put this up on GH anyway, in case I either decide to at least get it functional, or someone else might do something with it.
