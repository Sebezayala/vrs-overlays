## US Weather and Satellite Overlays and controls for Virtual Radar Server using Leaflet maps

This JavaScript code is a plugin for the ADSB aircraft tracking [Virtual Radar Server](http://www.virtualradarserver.co.uk) software using the default Open Street Maps maps. This application must be used with the Virtual Radar Server [Custom Content plugin](http://www.virtualradarserver.co.uk/Documentation/CustomContent/Default.aspx) version 2.x. It has not been tested with the beta 3.x system. 

This plugin is derived from the work of 'nitro999'. You can see his overlay system at (https://github.com/nitro999/vrs-overlays).

I have removed all of the  UK specific overlays and code and have switched the radar overlays to the US Nexrad overlays available at (https://mesonet.agron.iastate.edu/ogc/). Specifically, this version uses the nexrad-n0r-900913 tile set which is the "current" composite base reflectivity. See the above site for other tilesets offered by Iowa State. 

Obviously, the radar overlay won't produce any radar returns outside the US - sorry.  I don't know of a leaflet tile radar source that is worldwide. 

The cloud cover image is worldwide, updated once per day. The image tiles are from NASA using the leaflet interface to the EPSG:4326 imagry. You can see NASA's demo of this at (https://nasa-gibs.github.io/gibs-web-examples/examples/leaflet/geographic-epsg4326.html).

Radar and Cloud overlay opacity is set to 30%. you can override this by editing the gnOpacity variable at the top of the "JSendOfBody.html" file. I haven't added it to the options. 

The radar and cloud overlays are not on by default, simply hover over the icon in the upper right of the map and click the one you want.  I do not reccomend both radar and clouds. 

Screenshot of working example:

![Screenshot](https://github.com/BoatrightTBC/vrs-overlays/blob/master/screenshot.PNG?raw=true)

##Installation Instructions##

* Download the files from Github (https://github.com/BoatrightTBC/vrs-overlays) using the green "Clone or Download" button. If you are used to Git, simply clone the repository, otherwise download the zip and extract the files somewhere.
* *DO NOT* put the files in the "program files (x86)" folder where the VRS program files live. If you do, they will not survive an update. 
...Let's assume you put the unzipped files in C:\VRS\weather. 
* If you haven't done it already, download and install the VRS Custom Content plugin. (http://www.virtualradarserver.co.uk/Download.aspx)
* In VRS go to Tools/Plugins. You should see Custom Content at the top of the window. 
* Click the Options button. 
...Recall that we are assuming your files are in c:\VRS\weather. If they're somewhere else replace that with your location in the following instructions. 
* Hit new. 
** Set "Inject file" to c:\VRS\weather\JSendOfBody.html
** Set At to  END of BODY
** Set Address to * 
** Ensure "Enabled" is clicked.
* Hit new again. 
** Set "Inject file" to c:\VRS\weather\JSendOfHead.html
** Set At to  END of HEAD
** Set Address to * 
** Ensure "Enabled" is clicked.
* Now, one of two choices: 
** If you have already used the custom content plugin to overwrite default files, and have your site root folder set to some location, copy the contents of the c:\vrs\weather\web folder into that location. 
** In the much more likely case that you've never done that, set the Site Root Folder at the bottom of the Options window to c:\VRS\weather\web 
* Hit ok 

You should be completely done.  If it doesn't work, post an install problem report either on the above mentioned github page, or in the Virtual Radar Server installation problems forum. 


