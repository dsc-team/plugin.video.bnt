# Based on: Simple example plugin for Kodi mediacenter

## Why I did it
I was trying to create a really simple plugin, as I didn't found one that allows watching the Bulgarian National TV archives.
The plugin is based on the default video example. It is a really really simple one, and it scrapes the webpage content. 
I was unable to find any documentation or any API that BNT might have to obtain the archives lists.

## How it works
It uses BeautifulSoup python module to read the html page (bnt.bg/predavaniya) and to extract some info.
It loops inside the `div` component I identified to contain the most active archives.
Then, it follows the links to the particular `predavane` subpage, and then it follows the next link where it finds the `href` with the `mp4` url.
Because of these loops and loops and loops it works slow.

Unfortinately, from the location on the planet where I leave, it is tooooo slow to grab all the sub-content videos.

Hence I've hardcoded a limit, to give up after the 4th subcategory. Otherwise, the kodi simply times out and terminates the search.

## Disclaimer
I'm not a python guy, in fact this plugin is result of my very first 3 hours in python. It does the work for me.
Please, fork the code and improve, if you can do it better, just don't criticize.
IT works really slow here (the opposite end of the globe), but it does the job for me, so I don't intend to improve it further.

## How to generate deployable plugin:
If you are in the module dolder, assuming the folder is named `plugin.video.bnt`, run the following (Linux / Mac)

```
cd ..
zip -r plugin.video.bnt.zip plugin.video.bnt -x *.git*

```
For windows, just zip the folder and provide to kodi.

License: [GPL v.3](http://www.gnu.org/copyleft/gpl.html)
