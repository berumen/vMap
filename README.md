vMap
====

A lightning jQuery plugin with HTML 5 that makes Google Maps v3 easy by sending a simple JSON Data Structure.

vMap not only displays the location markers in the map, but also displays a list with the locations, this list offers some extra features, for example: A location can be clicked and it will be highlighted in the map.

Copyright (c) 2012 Victor Hugo Garcia - iacido[at]gmail.com

How to use
----------

To get started, download the plugin, unzip it and copy files to your website/application directory.
Load files in the <head> section of your HTML document. Make sure you also add the jQuery library.

	<head>
		<script src="http://maps.googleapis.com/maps/api/js?key=abcdef&sensor=true" type="text/javascript"></script>
        <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js"></script>
        <link rel="stylesheet" href="/jquery.vmap.css" type="text/css"/>
        <script type="text/javascript" src="/jquery.vmap.js"></script>
    </head>

Note, you should change `key` parameter for the one given by Google.

Add the follow HTML to your page under body tag (`section` tag is optional):
	
	<section>
		<div id="map_canvas">
			
		</div>
		<div id="map_list">
			
		</div>
	</section>
	
Initialize the script like this:

    <script>
        $(document).ready(function() {
            $('#map_canvas').vmap({url:"/webservice/get_locations"});
        });
    </script>

It can aslo be passed optional options objects which will extend the default values. Example:

    <script>
        $(document).ready(function() {
            $('#map_canvas').vmap({
				url: "/webservice/get_locations",
				data: "{'address':'known'}",
				initLatitude: "31.74",
				initLongitude: "-95.42",
				initZoom: 4,
				classAddress: "street",
				classTitle: "title"
            });
        });
    </script>

Note, ajax requests are subject to the [same origin policy](http://en.wikipedia.org/wiki/Same_origin_policy).

Mandatory Parameters
----------
<strong>url</strong> A string containing the URL to which the request is sent.


Optional Parameters
----------
<strong>data</strong> Data to be sent to the server on the Url specified.

<strong>initLatitude</strong> is the Latitude where the map will be centered initially.

<strong>initLongitude</strong> is the Longitude where the map will be centered initially.

<strong>initZoom</strong> is the initial zoom of the map (integer).

<strong>classAddress</strong> assign a class to the tag that encloses the location.

<strong>classTitle</strong> assign a class to the tag where the location title is displayed.


Server Side
----------

The data must be returned in strict JSON format, below is a sample of the structure:

	{
    "items": [{
				"Title": "Location Name 01",
				"Link": "/to-some-where.aspx",
				"Latitude": "72.372055",
				"Longitude": "-19.7305979",
				"Address": "1900 Test Road, State, Country, ZipCode"
			}, {
				"Title": "Location Name 02",
				"Link": "/any-where.aspx",
				"Latitude": "72.372055",
				"Longitude": "-19.747201",
				"Address": "1900 Test Road, State, Country, ZipCode"
			}
			]
	}
	
License / Download
----------

vMap licensed under Creative Commons Attribution-NonCommercial 3.0 license.
You are free to use vMap for your personal or non-profit website projects.
You can get the author's permission to use vMap for commercial websites. 

Bug tracker
-----------

Have a bug? Please create an issue on GitHub at https://github.com/vhugogarcia/vMap/issues

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/b900f12a3465e3691a819495c7e15848 "githalytics.com")](http://githalytics.com/vhugogarcia/vMap)