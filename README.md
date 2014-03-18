<p align="center">
<img align="center" src="api_giphy_logo_sparkle_clear.gif" width="330" alt="API Giphy logo"/>
</p>


# Giphy API Documentation

Giphy is an animated [GIF](http://en.wikipedia.org/wiki/Graphics_Interchange_Format) search engine.

## Access and API Keys

The Giphy API is open to the public. We have instituted a simple, single public beta key system to let anyone try it out. The API key is required for all endpoints. <b>The public beta key is "dc6zaTOxFJmzC"</b>.  Please use this key while you develop your application and experiment with your integrations.

Once you are ready to use the Giphy API in production, please contact [api@giphy.com](mailto:api@giphy.com) to request a unique API key. In your email please provide the following information:

- The app name with brief description, web / app store links, etc.

- What is the 'live date' of the app or feature that integrates with the API?

- As per our section 5 A of our [terms](http://giphy.com/terms), we require all apps that use the Giphy API to conspicuously display "Powered By Giphy" attribution marks. You can find approved [official logo marks here](http://giphymedia.s3.amazonaws.com/giphy_api_icons.zip). Please be sure to include a screen shot of your app that includes the attribution.

<b>Note: the public key is subject to rate limit constraints. We do not encourage live production deployments to use the public key.</b>


## Overview

The [Giphy API](http://api.giphy.com) provides the following JSON endpoints:

+ search
+ GIF by id
+ GIFs by id
+ translate
+ random 
+ trending

The search endpoint replicates the search found on [Giphy](http://giphy.com). Translate is an experimental endpoint designed to be used for GIF dialects and random returns a single random GIF, optionally limited to a specified tag. Learn more about the rest in the documentation below.

The Giphy API implements a REST-like interface. Connections can be made with any HTTP enabled programming language. The Giphy API also implements [CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing), allowing you to connect to Giphy from JavaScript / Web browsers on your own domain.

###### Host

    api.giphy.com

###### Parameters

+ api_key - The public beta key is <b>"dc6zaTOxFJmzC"</b>


## Search Endpoint

Search all Giphy GIFs for a word or phrase. Punctuation will be stripped and ignored. Use a plus or url encode for phrases. Example [paul+rudd](http://api.giphy.com/v1/gifs/search?q=paul+rudd&api_key=dc6zaTOxFJmzC), [ryan+gosling](http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=dc6zaTOxFJmzC) or [american+psycho](http://api.giphy.com/v1/gifs/search?q=american+psycho&api_key=dc6zaTOxFJmzC). 

	http://api.giphy.com/v1/gifs/search?q=funny+cat&api_key=dc6zaTOxFJmzC	

[Example](http://api.giphy.com/v1/gifs/search?q=funny+cat&api_key=dc6zaTOxFJmzC&limit=1&offset=0) search query.

###### Path

    /v1/gifs/search

###### Parameters

+ q - search query term or phrase
+ limit - (optional) number of results to return, maximum 100. Default 25.
+ offset - (optional) results offset, defaults to 0.

### Sample Response, Search

    {
        "data": [
            {
                "bitly_fullscreen_url": "http://gph.is/XJIocS",
                "bitly_gif_url": "http://gph.is/XJIp0f",
                "bitly_tiled_url": "http://gph.is/XJIr8i",
                "id": "iU1NUdMq3sx3O",
                "images": {
                    "fixed_height": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/200.gif",
                        "width": "267"
                    },
                    "fixed_height_downsampled": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/200_d.gif",
                        "width": "267"
                    },
                    "fixed_height_still": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/200_s.gif",
                        "width": "267"
                    },
                    "fixed_width": {
                        "height": "150",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/200w.gif",
                        "width": "200"
                    },
                    "fixed_width_downsampled": {
                        "height": "150",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/200w_d.gif",
                        "width": "200"
                    },
                    "fixed_width_still": {
                        "height": "150",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/200w_s.gif",
                        "width": "200"
                    },
                    "original": {
                        "frames": "3",
                        "height": "375",
                        "size": "189975",
                        "url": "http://media0.giphy.com/media/iU1NUdMq3sx3O/giphy.gif",
                        "width": "500"
                    }
                },
                "type": "gif",
                "url": "http://giphy.com/gifs/iU1NUdMq3sx3O"
            }
        ],
        "meta": {
            "msg": "OK",
            "status": 200
        },
        "pagination": {
            "count": 1,
            "offset": "0",
            "total_count": 249
        }
    }


## Get GIF by ID Endpoint

Returns meta data about a GIF, by GIF id. In the below example, the GIF ID is "feqkVgjJpYtjy"

	http://api.giphy.com/v1/gifs/feqkVgjJpYtjy?api_key=dc6zaTOxFJmzC

[Example](http://api.giphy.com/v1/gifs/feqkVgjJpYtjy?api_key=dc6zaTOxFJmzC) get GIF by id query

###### Path

	/v1/gifs/<gif_id>


### Sample Response, Get GIF by ID

	{
	    "data": {
	        "bitly_fullscreen_url": "http://gph.is/XJ1Y8Q",
	        "bitly_gif_url": "http://gph.is/XJ200y",
	        "bitly_tiled_url": "http://gph.is/XJ1Y8T",
	        "id": "feqkVgjJpYtjy",
	        "images": {
	            "fixed_height": {
	                "height": "200",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/200.gif",
	                "width": "445"
	            },
	            "fixed_height_downsampled": {
	                "height": "200",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/200_d.gif",
	                "width": "445"
	            },
	            "fixed_height_still": {
	                "height": "200",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/200_s.gif",
	                "width": "445"
	            },
	            "fixed_width": {
	                "height": "90",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/200w.gif",
	                "width": "200"
	            },
	            "fixed_width_downsampled": {
	                "height": "90",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/200w_d.gif",
	                "width": "200"
	            },
	            "fixed_width_still": {
	                "height": "90",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/200w_s.gif",
	                "width": "200"
	            },
	            "original": {
	                "height": "150",
	                "url": "http://media.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
	                "width": "334"
	            }
	        },
	        "type": "gif",
	        "url": "http://giphy.com/gifs/feqkVgjJpYtjy"
	    },
	    "meta": {
	        "msg": "OK",
	        "status": 200
	    }
	}


## Get GIFs by ID Endpoint

A multiget version of the get GIF by ID endpoint. In this case the IDs are feqkVgjJpYtjy and 7rzbxdu0ZEXLy

    http://api.giphy.com/v1/gifs?api_key=dc6zaTOxFJmzC&ids=feqkVgjJpYtjy,7rzbxdu0ZEXLy

[Example](http://api.giphy.com/v1/gifs?api_key=dc6zaTOxFJmzC&ids=feqkVgjJpYtjy,7rzbxdu0ZEXLy) get GIFs by Id

##### Path

    /v1/gifs

##### Parameters

+ ids - a comma separated list of IDs to fetch GIF size data.

## Sample Response, Get GIFs by ID

    {
        "data": [
            {
                "bitly_fullscreen_url": "http://gph.is/13YkU2A",
                "bitly_gif_url": "http://gph.is/13YkU2y",
                "bitly_tiled_url": "http://gph.is/13YkTf4",
                "embed_url": "http://giphy.com/embed/7rzbxdu0ZEXLy",
                "id": "7rzbxdu0ZEXLy",
                "images": {
                    "fixed_height": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/200.gif",
                        "width": "200"
                    },
                    "fixed_height_downsampled": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/200_d.gif",
                        "width": "200"
                    },
                    "fixed_height_still": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/200_s.gif",
                        "width": "200"
                    },
                    "fixed_width": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/200w.gif",
                        "width": "200"
                    },
                    "fixed_width_downsampled": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/200w_d.gif",
                        "width": "200"
                    },
                    "fixed_width_still": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/200w_s.gif",
                        "width": "200"
                    },
                    "original": {
                        "frames": "9",
                        "height": "500",
                        "size": "1012692",
                        "url": "http://media0.giphy.com/media/7rzbxdu0ZEXLy/giphy.gif",
                        "width": "500"
                    }
                },
                "type": "gif",
                "url": "http://giphy.com/gifs/7rzbxdu0ZEXLy"
            },
            {
                "bitly_fullscreen_url": "http://gph.is/XJ1Y8Q",
                "bitly_gif_url": "http://gph.is/XJ200y",
                "bitly_tiled_url": "http://gph.is/XJ1Y8T",
                "embed_url": "http://giphy.com/embed/feqkVgjJpYtjy",
                "id": "feqkVgjJpYtjy",
                "images": {
                    "fixed_height": {
                        "height": "200",
                        "url": "http://media3.giphy.com/media/feqkVgjJpYtjy/200.gif",
                        "width": "445"
                    },
                    "fixed_height_downsampled": {
                        "height": "200",
                        "url": "http://media2.giphy.com/media/feqkVgjJpYtjy/200_d.gif",
                        "width": "445"
                    },
                    "fixed_height_still": {
                        "height": "200",
                        "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200_s.gif",
                        "width": "445"
                    },
                    "fixed_width": {
                        "height": "90",
                        "url": "http://media1.giphy.com/media/feqkVgjJpYtjy/200w.gif",
                        "width": "200"
                    },
                    "fixed_width_downsampled": {
                        "height": "90",
                        "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.gif",
                        "width": "200"
                    },
                    "fixed_width_still": {
                        "height": "90",
                        "url": "http://media2.giphy.com/media/feqkVgjJpYtjy/200w_s.gif",
                        "width": "200"
                    },
                    "original": {
                        "frames": "27",
                        "height": "150",
                        "size": "511581",
                        "url": "http://media3.giphy.com/media/feqkVgjJpYtjy/original.gif",
                        "width": "334"
                    }
                },
                "type": "gif",
                "url": "http://giphy.com/gifs/feqkVgjJpYtjy"
            }
        ],
        "meta": {
            "msg": "OK",
            "status": 200
        },
        "pagination": {
            "count": 2,
            "offset": 0,
            "total_count": 2
        }
    }


## Translate Endpoint

This is prototype endpoint for using Giphy as a translation engine for a GIF dialect.  The translate API draws on search, but uses the Giphy "special sauce" to handle translating from one vocabulary to another. In this case, words and phrases to GIFs.  Use a plus or url encode for phrases.

    http://api.giphy.com/v1/gifs/translate?s=superman&api_key=dc6zaTOxFJmzC&limit=1

[Example](http://api.giphy.com/v1/gifs/translate?s=superman&api_key=dc6zaTOxFJmzC&limit=1) translate query.


###### Path

    /v1/gifs/translate

###### Parameters

+ s - term or phrase to translate into a GIF

### Sample Response, Translate

    {
        "data": {
            "bitly_fullscreen_url": "http://gph.is/XH7Sri",
            "bitly_gif_url": "http://gph.is/XH7V6j",
            "bitly_tiled_url": "http://gph.is/XH7Srk",
            "id": "3avUsGhmckIYE",
            "images": {
                "fixed_height": {
                    "height": "200",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/200.gif",
                    "width": "289"
                },
                "fixed_height_downsampled": {
                    "height": "200",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/200_d.gif",
                    "width": "289"
                },
                "fixed_height_still": {
                    "height": "200",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/200_s.gif",
                    "width": "289"
                },
                "fixed_width": {
                    "height": "138",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/200w.gif",
                    "width": "200"
                },
                "fixed_width_downsampled": {
                    "height": "138",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/200w_d.gif",
                    "width": "200"
                },
                "fixed_width_still": {
                    "height": "138",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/200w_s.gif",
                    "width": "200"
                },
                "original": {
                    "height": "346",
                    "url": "http://media.giphy.com/media/3avUsGhmckIYE/giphy.gif",
                    "width": "500"
                }
            },
            "type": "gif",
            "url": "http://giphy.com/gifs/3avUsGhmckIYE"
        },
        "meta": {
            "msg": "OK",
            "status": 200
        }
    }


## Random Endpoint

Returns a random GIF, limited by tag. Excluding the tag parameter will return a random GIF from the Giphy catalog.

    http://api.giphy.com/v1/gifs/random?api_key=dc6zaTOxFJmzC&tag=american+psycho

[Example](http://api.giphy.com/v1/gifs/random?api_key=dc6zaTOxFJmzC&tag=american+psycho) random query

###### Path

    /v1/gifs/random


###### Parameters

+ tag - the GIF tag to limit randomness by

### Sample Response, Random

	{
	    "data": {
	        "id": "12jp1Z7ITCrPxe",
	        "image_original_url": "http://media.giphy.com/media/12jp1Z7ITCrPxe/giphy.gif"
	    },
	    "meta": {
	        "msg": "OK",
	        "status": 200
	    }
	}


## Trending GIFs Endpoint

Fetch GIFs currently trending online. The data returned mirrors that used to create [The Hot 100](http://giphy.com/hot100) list of GIFs on [Giphy](http://giphy.com). Returns 25 results by default.

    http://api.giphy.com/v1/gifs/trending?api_key=dc6zaTOxFJmzC

[Example](http://api.giphy.com/v1/gifs/trending?api_key=dc6zaTOxFJmzC) trending GIFs query.
[Example](http://api.giphy.com/v1/gifs/trending?api_key=dc6zaTOxFJmzC&limit=5) trending GIFs limited to 5 results.

###### Path

    /v1/gifs/trending

##### Parameters

+ limit (optional) limits the number of results returned. 


### Sample Response, Trending

    
    {
        data: [
            {
                type: "gif",
                id: "jI6YyYxUHHEw8",
                url: "http://giphy.com/gifs/jI6YyYxUHHEw8",
                bitly_gif_url: "",
                bitly_fullscreen_url: "",
                bitly_tiled_url: "",
                embed_url: "http://giphy.com/embed/jI6YyYxUHHEw8",
                images: {
                    fixed_height: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/200.gif",
                        width: "333",
                        height: "200"
                    },
                    fixed_height_still: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/200_s.gif",
                        width: "333",
                        height: "200"
                    },
                    fixed_height_downsampled: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/200_d.gif",
                        width: "333",
                        height: "200"
                    },
                    fixed_width: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/200w.gif",
                        width: "200",
                        height: "120"
                    },
                    fixed_width_still: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/200w_s.gif",
                        width: "200",
                        height: "120"
                    },
                    fixed_width_downsampled: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/200w_d.gif",
                        width: "200",
                        height: "120"
                    },
                    original: {
                        url: "http://media0.giphy.com/media/jI6YyYxUHHEw8/giphy.gif",
                        width: "500",
                        height: "300",
                        size: "618230",
                        frames: "68"
                    }
                }
            }
        ],
        pagination: {
            total_count: 1447,
            count: 1,
            offset: 0
        },
        meta: {
            status: 200,
            msg: "OK"
        }
    }


## Code Examples

Below are code samples in Python, JavaScript, Ruby, PHP and the command line on connecting to the API to make a search query for ryan gosling.


#### Python scripting language

    # python
    import urllib,json
    data = json.loads(urllib.urlopen("http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=dc6zaTOxFJmzC&limit=5").read())
    print json.dumps(data, sort_keys=True, indent=4)


#### JavaScript scripting language

    #javascript, jQuery
    var xhr = $.get("http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=dc6zaTOxFJmzC&limit=5");
    xhr.done(function(data) { console.log("success got data", data); });


#### Ruby scripting language

    #ruby
    require 'net/http'
    require 'json'
    url = "http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=dc6zaTOxFJmzC&limit=5"
    resp = Net::HTTP.get_response(URI.parse(url))
    buffer = resp.body
    result = JSON.parse(buffer) 
    print result 


#### PHP scripting language

    // php
    $url = "http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=dc6zaTOxFJmzC&limit=5";
    print_r(json_decode(file_get_contents($url)));


#### Command line, cURL

    # curl, command line
    curl "http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=dc6zaTOxFJmzC&limit=5"


## Sharing and Promoting your Giphy API Project

Projects that leverage the Giphy API can be submitted to [Giphy labs](http://giphy.com/labs). Learn more about [Giphy labs](http://giphy.com/labs).


## Additional Information

Please submit corrections via [github issues](https://github.com/giphy/GiphyAPI/issues). Please see the [terms](http://giphy.com/terms) for any restrictions on using 
the service. 

Note: the public beta key will be decommissioned at a point in the future. Usage in production is prohibited and not recommended. Developers seeking to leverage the Giphy API should contact [api@giphy.com](mailto:api@giphy.com) for a unique API key.

We recommend the JSONview plugin for [Firefox](https://addons.mozilla.org/en-us/firefox/addon/jsonview/) or [Chrome](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en).

