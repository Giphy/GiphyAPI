<p align="center">
<img align="center" src="transparent_logo_horizontal_large.png" width="500" alt="API Giphy logo"/>
</p>


# Giphy API Documentation

Giphy is an animated [GIF](http://en.wikipedia.org/wiki/Graphics_Interchange_Format) search engine.

## Access and API Keys

The Giphy API is open to the public. We have instituted a simple, single public beta key system to let anyone try it out. The API key is required for all endpoints. <b>The public beta key is "dc6zaTOxFJmzC"</b>.  Please use this key while you develop your application and experiment with your integrations.

Once you are ready to use the Giphy API in production, please contact [api@giphy.com](mailto:api@giphy.com) to request a unique API key. <b>Please make the subject of your email "API Key Request".</b> This is important as it will help us keep track of your request. In the body of your email please provide the following:

- Your app name with brief description, web / app store links, etc.  

- What is the 'live date' of the app or feature that integrates with the API?  Briefly describe how the Giphy API integrates with your app, include any screenshots if it helps.

- As per our section 5 A of our [terms of service](http://giphy.com/terms), we require all apps that use the Giphy API to conspicuously display "Powered By Giphy" attribution marks. You can find approved [official logo marks here](http://giphymedia.s3.amazonaws.com/giphy-attribution-marks.zip). In your email, please attach screenshot of your app that shows the attribution marks.  If you do not include them you will be requested for them so please include them in your initial request to expediate the process. 

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
+ rating - limit results to those rated (y,g, pg, pg-13 or r). 

### Sample Response, Search

    {
        "data": [
            {
                "type": "gif",
                "id": "DFiwMapItOTh6",
                "url": "http://giphy.com/gifs/funny-cat-DFiwMapItOTh6",
                "bitly_gif_url": "http://gph.is/1aakRc4",
                "bitly_url": "http://gph.is/1aakRc4",
                "embed_url": "http://giphy.com/embed/DFiwMapItOTh6",
                "username": "",
                "source": "http://tumblr.com",
                "rating": "g",
                "caption": "",
                "content_url": "",
                "import_datetime": "2014-02-01 10:26:38",
                "trending_datetime": "1970-01-01 00:00:00",
                "images": {
                    "fixed_height": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/200.gif",
                        "width": "302",
                        "height": "200",
                        "mp4": "http://media.giphy.com/media/DFiwMapItOTh6/200.mp4"
                    },
                    "fixed_height_still": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/200_s.gif",
                        "width": "302",
                        "height": "200"
                    },
                    "fixed_height_downsampled": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/200_d.gif",
                        "width": "302",
                        "height": "200"
                    },
                    "fixed_width": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/200w.gif",
                        "width": "200",
                        "height": "132",
                        "mp4": "http://media.giphy.com/media/DFiwMapItOTh6/200w.mp4"
                    },
                    "fixed_width_still": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/200w_s.gif",
                        "width": "200",
                        "height": "132"
                    },
                    "fixed_width_downsampled": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/200w_d.gif",
                        "width": "200",
                        "height": "132"
                    },
                    "downsized": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/giphy.gif",
                        "width": "245",
                        "height": "162",
                        "size": "653626"
                    },
                    "downsized_still": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/giphy_s.gif",
                        "width": "245",
                        "height": "162"
                    },
                    "original": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/giphy.gif",
                        "width": "245",
                        "height": "162",
                        "size": "653626",
                        "frames": "54",
                        "mp4": "http://media.giphy.com/media/DFiwMapItOTh6/giphy.mp4"
                    },
                    "original_still": {
                        "url": "http://media4.giphy.com/media/DFiwMapItOTh6/giphy_s.gif",
                        "width": "245",
                        "height": "162"
                    }
                }
            },
            ... 24 more items
        ],
        "meta": {
            "status": 200,
            "msg": "OK"
        },
        "pagination": {
            "total_count": 1947,
            "count": 25,
            "offset": 0
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
            "type": "gif",
            "id": "feqkVgjJpYtjy",
            "url": "http://giphy.com/gifs/feqkVgjJpYtjy",
            "bitly_gif_url": "http://gph.is/XJ200y",
            "bitly_url": "http://gph.is/XJ200y",
            "embed_url": "http://giphy.com/embed/feqkVgjJpYtjy",
            "username": "",
            "source": "http://littleanimalgifs.tumblr.com/post/17994517807",
            "rating": "g",
            "caption": "",
            "content_url": "",
            "import_datetime": "2013-03-21 04:03:08",
            "trending_datetime": "2014-09-23 22:49:53",
            "images": {
                "fixed_height": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200.gif",
                    "width": "445",
                    "height": "200",
                    "mp4": "http://media.giphy.com/media/feqkVgjJpYtjy/200.mp4"
                },
                "fixed_height_still": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200_s.gif",
                    "width": "445",
                    "height": "200"
                },
                "fixed_height_downsampled": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200_d.gif",
                    "width": "445",
                    "height": "200"
                },
                "fixed_width": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.gif",
                    "width": "200",
                    "height": "90",
                    "mp4": "http://media.giphy.com/media/feqkVgjJpYtjy/200w.mp4"
                },
                "fixed_width_still": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_s.gif",
                    "width": "200",
                    "height": "90"
                },
                "fixed_width_downsampled": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.gif",
                    "width": "200",
                    "height": "90"
                },
                "downsized": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
                    "width": "334",
                    "height": "150",
                    "size": "511581"
                },
                "downsized_still": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
                    "width": "334",
                    "height": "150"
                },
                "original": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
                    "width": "334",
                    "height": "150",
                    "size": "511581",
                    "frames": "27",
                    "mp4": "http://media.giphy.com/media/feqkVgjJpYtjy/giphy.mp4"
                },
                "original_still": {
                    "url": "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
                    "width": "334",
                    "height": "150"
                }
            }
        },
        "meta": {
            "status": 200,
            "msg": "OK"
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
        data: [
        {
            type: "gif",
            id: "feqkVgjJpYtjy",
            url: "http://giphy.com/gifs/feqkVgjJpYtjy",
            bitly_gif_url: "http://gph.is/XJ200y",
            bitly_url: "http://gph.is/XJ200y",
            embed_url: "http://giphy.com/embed/feqkVgjJpYtjy",
            username: "",
            source: "http://littleanimalgifs.tumblr.com/post/17994517807",
            rating: "g",
            trending_datetime: "1970-01-01 00:00:00",
            images: {
                fixed_height: {
                    url: "http://media3.giphy.com/media/feqkVgjJpYtjy/200.gif",
                    width: "445",
                    height: "200",
                    mp4: "http://media.giphy.com/media/feqkVgjJpYtjy/200.mp4"
                },
                fixed_height_still: {
                    url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_s.gif",
                    width: "445",
                    height: "200"
                },
                fixed_height_downsampled: {
                    url: "http://media2.giphy.com/media/feqkVgjJpYtjy/200_d.gif",
                    width: "445",
                    height: "200"
                },
                fixed_width: {
                    url: "http://media1.giphy.com/media/feqkVgjJpYtjy/200w.gif",
                    width: "200",
                    height: "90",
                    mp4: ""
                },
                fixed_width_still: {
                    url: "http://media2.giphy.com/media/feqkVgjJpYtjy/200w_s.gif",
                    width: "200",
                    height: "90"
                },
                fixed_width_downsampled: {
                    url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.gif",
                    width: "200",
                    height: "90"
                },
                original: {
                    url: "http://media3.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
                    width: "334",
                    height: "150",
                    size: "511581",
                    frames: "27",
                    mp4: "http://media.giphy.com/media/feqkVgjJpYtjy/giphy.mp4"
                },
                original_still: {
                    url: "http://media3.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
                    width: "334",
                    height: "150"
                }
            }
        },
        {
            type: "gif",
            id: "7rzbxdu0ZEXLy",
            url: "http://giphy.com/gifs/7rzbxdu0ZEXLy",
            bitly_gif_url: "http://gph.is/13YkU2y",
            bitly_url: "http://gph.is/13YkU2y",
            embed_url: "http://giphy.com/embed/7rzbxdu0ZEXLy",
            username: "mrdiv",
            source: "http://mrdiv.tumblr.com/post/48618427039/disco-sphere",
            rating: "g",
            trending_datetime: "1970-01-01 00:00:00",
            images: {
                fixed_height: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/200.gif",
                    width: "200",
                    height: "200",
                    mp4: "http://media.giphy.com/media/7rzbxdu0ZEXLy/200.mp4"
                },
                fixed_height_still: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/200_s.gif",
                    width: "200",
                    height: "200"
                },
                fixed_height_downsampled: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/200_d.gif",
                    width: "200",
                    height: "200"
                },
                fixed_width: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/200w.gif",
                    width: "200",
                    height: "200",
                    mp4: "http://media.giphy.com/media/7rzbxdu0ZEXLy/200w.mp4"
                },
                fixed_width_still: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/200w_s.gif",
                    width: "200",
                    height: "200"
                },
                fixed_width_downsampled: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/200w_d.gif",
                    width: "200",
                    height: "200"
                },
                original: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/giphy.gif",
                    width: "500",
                    height: "500",
                    size: "1012692",
                    frames: "9",
                    mp4: "http://media.giphy.com/media/7rzbxdu0ZEXLy/giphy.mp4"
                },
                original_still: {
                    url: "http://media3.giphy.com/media/7rzbxdu0ZEXLy/giphy_s.gif",
                    width: "500",
                    height: "500"
                }
            }
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

    http://api.giphy.com/v1/gifs/translate?s=superman&api_key=dc6zaTOxFJmzC

[Example](http://api.giphy.com/v1/gifs/translate?s=superman&api_key=dc6zaTOxFJmzC) translate query.


###### Path

    /v1/gifs/translate

###### Parameters

+ s - term or phrase to translate into a GIF
+ rating - limit results to those rated (y,g, pg, pg-13 or r). 

### Sample Response, Translate

    {
        "data": {
            "type": "gif",
            "id": "FiBzv5FRE85PO",
            "url": "http://giphy.com/gifs/superman-man-of-steel-FiBzv5FRE85PO",
            "bitly_gif_url": "http://gph.is/19bNnce",
            "bitly_url": "http://gph.is/19bNnce",
            "embed_url": "http://giphy.com/embed/FiBzv5FRE85PO",
            "username": "",
            "source": "http://perezhilton.tumblr.com/post/52728801979/man-of-steel-sequel-already-greenlit-henry-cavill",
            "rating": "g",
            "caption": "",
            "content_url": "",
            "import_datetime": "2013-06-21 17:58:38",
            "trending_datetime": "1970-01-01 00:00:00",
            "images": {
                "fixed_height": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/200.gif",
                    "width": "347",
                    "height": "200",
                    "mp4": "http://media.giphy.com/media/FiBzv5FRE85PO/200.mp4"
                },
                "fixed_height_still": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/200_s.gif",
                    "width": "347",
                    "height": "200"
                },
                "fixed_height_downsampled": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/200_d.gif",
                    "width": "347",
                    "height": "200"
                },
                "fixed_width": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/200w.gif",
                    "width": "200",
                    "height": "115",
                    "mp4": "http://media.giphy.com/media/FiBzv5FRE85PO/200w.mp4"
                },
                "fixed_width_still": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/200w_s.gif",
                    "width": "200",
                    "height": "115"
                },
                "fixed_width_downsampled": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/200w_d.gif",
                    "width": "200",
                    "height": "115"
                },
                "downsized": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/giphy.gif",
                    "width": "500",
                    "height": "288",
                    "size": "976762"
                },
                "downsized_still": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/giphy_s.gif",
                    "width": "500",
                    "height": "288"
                },
                "original": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/giphy.gif",
                    "width": "500",
                    "height": "288",
                    "size": "976762",
                    "frames": "16",
                    "mp4": "http://media.giphy.com/media/FiBzv5FRE85PO/giphy.mp4"
                },
                "original_still": {
                    "url": "http://media3.giphy.com/media/FiBzv5FRE85PO/giphy_s.gif",
                    "width": "500",
                    "height": "288"
                }
            }
        },
        "meta": {
            "status": 200,
            "msg": "OK"
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
+ rating - limit results to those rated (y,g, pg, pg-13 or r). 

### Sample Response, Random

    {
        "data": {
            "type": "gif",
            "id": "Ggjwvmqktuvf2",
            "url": "http://giphy.com/gifs/american-psycho-christian-bale-Ggjwvmqktuvf2",
            "image_original_url": "http://s3.amazonaws.com/giphymedia/media/Ggjwvmqktuvf2/giphy.gif",
            "image_url": "http://s3.amazonaws.com/giphymedia/media/Ggjwvmqktuvf2/giphy.gif",
            "image_mp4_url": "http://s3.amazonaws.com/giphymedia/media/Ggjwvmqktuvf2/giphy.mp4",
            "image_frames": "11",
            "image_width": "500",
            "image_height": "256",
            "fixed_height_downsampled_url": "http://s3.amazonaws.com/giphymedia/media/Ggjwvmqktuvf2/200_d.gif",
            "fixed_height_downsampled_width": "391",
            "fixed_height_downsampled_height": "200",
            "fixed_width_downsampled_url": "http://s3.amazonaws.com/giphymedia/media/Ggjwvmqktuvf2/200w_d.gif",
            "fixed_width_downsampled_width": "200",
            "fixed_width_downsampled_height": "102",
            "rating": "g",
            "username": "",
            "caption": "",
            "tags": [
                "christian bale",
                "american psycho"
            ]
        },
        "meta": {
            "status": 200,
            "msg": "OK"
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

+ limit (optional) limits the number of results returned. By default returns 25 results.
+ rating - limit results to those rated (y,g, pg, pg-13 or r). 

### Sample Response, Trending

    {
        data: [
            {
                type: "gif",
                id: "kBgD5qopuOZk4",
                url: "http://giphy.com/gifs/kBgD5qopuOZk4",
                bitly_gif_url: "http://gph.is/1vWnMi9",
                bitly_url: "http://gph.is/1vWnMi9",
                embed_url: "http://giphy.com/embed/kBgD5qopuOZk4",
                username: "",
                source: "http://ruinedchildhood.com/post/100283411891/icoulduseinsouciantmaybe-notean-magneto-and",
                rating: "g",
                caption: "",
                content_url: "http://fhlostonsparadise.tumblr.com/post/20782429698",
                import_datetime: "2014-10-18 01:25:16",
                trending_datetime: "2014-10-28 18:52:00",
                images: {
                    fixed_height: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/200.gif",
                        width: "200",
                        height: "200",
                        mp4: "http://media.giphy.com/media/kBgD5qopuOZk4/200.mp4"
                    },
                    fixed_height_still: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/200_s.gif",
                        width: "200",
                        height: "200"
                    },
                    fixed_height_downsampled: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/200_d.gif",
                        width: "200",
                        height: "200"
                    },
                    fixed_width: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/200w.gif",
                        width: "200",
                        height: "200",
                        mp4: "http://media.giphy.com/media/kBgD5qopuOZk4/200w.mp4"
                    },
                    fixed_width_still: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/200w_s.gif",
                        width: "200",
                        height: "200"
                    },
                    fixed_width_downsampled: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/200w_d.gif",
                        width: "200",
                        height: "200"
                    },
                    downsized: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/giphy.gif",
                        width: "245",
                        height: "245",
                        size: "1023297"
                    },
                    downsized_still: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/giphy_s.gif",
                        width: "245",
                        height: "245"
                    },
                    original: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/giphy.gif",
                        width: "245",
                        height: "245",
                        size: "1023297",
                        frames: "22",
                        mp4: "http://media.giphy.com/media/kBgD5qopuOZk4/giphy.mp4"
                    },
                    original_still: {
                        url: "http://media1.giphy.com/media/kBgD5qopuOZk4/giphy_s.gif",
                        width: "245",
                        height: "245"
                    }
                }
            },
            ... 24 more items here 
        ],
        pagination: {
            count: 25,
            offset: 0
        },
        meta: {
            status: 200,
            msg: "OK"
        }
    }
    
    
## GIPHY STICKER API 
The Giphy API that provide only animated stickers (aka animated GIFs with transparent backgrounds) in the responses. The available endpoints are as follows:

    - Sticker Search
    - Sticker Roulette (Random) 
    - Sticker Trending
    - Sticker Translate 

### STICKER API PUBLIC KEY : dc6zaTOxFJmzC 

Note: the public key is subject to rate limit constraints. We do not encourage live production deployments to use the public key.

### STICKER Search Endpoint 

Replicates the functionality and requirements of the classic Giphy search, but returns animated stickers rather than gifs. Example [cat](http://api.giphy.com/v1/stickers/search?q=cat&api_key=dc6zaTOxFJmzC)

    http://api.giphy.com/v1/stickers/search?q=cat&api_key=dc6zaTOxFJmzC 
###### Path

    /v1/stickers/search

###### Parameters

+ q - search query term or phrase
+ limit - (optional) number of results to return, maximum 100. Default 25
+ offset - (optional) results offset, defaults to 0
+ rating - limit results to those rated (y,g, pg, pg-13 or r). 

###### Sample Response: Search
    
    {
        "data": [
            {
                "type": "gif",
                "id": "sj0sbNi9cv2dG",
                "url": "http://giphy.com/gifs/cat-transparent-sj0sbNi9cv2dG",
                "bitly_gif_url": "http://gph.is/Kq60z1",
                "bitly_url": "http://gph.is/Kq60z1",
                "embed_url": "http://giphy.com/embed/sj0sbNi9cv2dG",
                "username": "",
                "source": "http://ibehhvinny.tumblr.com/post/71539185754/so-coot",
                "rating": "g",
                "caption": "",
                "content_url": "",
                "import_datetime": "2014-01-04 15:39:18",
                "trending_datetime": "1970-01-01 00:00:00",
                "images": {
                    "fixed_height": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/200.gif",
                        "width": "193",
                        "height": "200",
                        "mp4": "http://media.giphy.com/media/sj0sbNi9cv2dG/200.mp4"
                    },
                    "fixed_height_still": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/200_s.gif",
                        "width": "193",
                        "height": "200"
                    },
                    "fixed_height_downsampled": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/200_d.gif",
                        "width": "193",
                        "height": "200"
                    },
                    "fixed_width": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/200w.gif",
                        "width": "200",
                        "height": "207",
                        "mp4": "http://media.giphy.com/media/sj0sbNi9cv2dG/200w.mp4"
                    },
                    "fixed_width_still": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/200w_s.gif",
                        "width": "200",
                        "height": "207"
                    },
                    "fixed_width_downsampled": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/200w_d.gif",
                        "width": "200",
                        "height": "207"
                    },
                    "downsized": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/giphy.gif",
                        "width": "400",
                        "height": "414",
                        "size": "422870"
                    },
                    "downsized_still": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/giphy_s.gif",
                        "width": "400",
                        "height": "414"
                    },
                    "original": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/giphy.gif",
                        "width": "400",
                        "height": "414",
                        "size": "422870",
                        "frames": "39",
                        "mp4": "http://media.giphy.com/media/sj0sbNi9cv2dG/giphy.mp4"
                    },
                    "original_still": {
                        "url": "http://media2.giphy.com/media/sj0sbNi9cv2dG/giphy_s.gif",
                        "width": "400",
                        "height": "414"
                    }
                }
            },
            ... 24 more items
        ],
        "meta": {
            "status": 200,
            "msg": "OK"
        },
        "pagination": {
            "total_count": 573,
            "count": 25,
            "offset": 0
        }
    }
    

### STICKER Roulette (Random) Endpoint

Returns a spotaneously selected sticker from Giphy's sticker collection. Optionally limit scope of result to a specific tag. Like the GIF random endpoint, Punctuation will be stripped and ignored. Use a hyphen for phrases. Example [oops](http://api.giphy.com/v1/stickers/random?api_key=dc6zaTOxFJmzC&tag=oops), [birthday](http://api.giphy.com/v1/stickers/random?api_key=dc6zaTOxFJmzC&tag=birthday) or [thank-you](http://api.giphy.com/v1/stickers/random?api_key=dc6zaTOxFJmzC&tag=whatever). Search terms should be URL encoded.
    
    http://api.giphy.com/v1/stickers/random?api_key=dc6zaTOxFJmzC&tag=oops

[Example](http://api.giphy.com/v1/stickers/random?api_key=dc6zaTOxFJmzC) random query.

###### Path

    /v1/sticker/random

###### Parameters

+ q - search query term or phrase

###### Sample Reponse: Random

    {
        "data": {
            "type": "gif",
            "id": "8yAVe11H5MzCg",
            "url": "http://giphy.com/gifs/animatedtext-transparent-green-8yAVe11H5MzCg",
            "image_original_url": "http://s3.amazonaws.com/giphymedia/media/8yAVe11H5MzCg/giphy.gif",
            "image_url": "http://s3.amazonaws.com/giphymedia/media/8yAVe11H5MzCg/giphy.gif",
            "image_mp4_url": "http://s3.amazonaws.com/giphymedia/media/8yAVe11H5MzCg/giphy.mp4",
            "image_frames": "30",
            "image_width": "503",
            "image_height": "191",
            "fixed_height_downsampled_url": "http://s3.amazonaws.com/giphymedia/media/8yAVe11H5MzCg/200_d.gif",
            "fixed_height_downsampled_width": "527",
            "fixed_height_downsampled_height": "200",
            "fixed_width_downsampled_url": "http://s3.amazonaws.com/giphymedia/media/8yAVe11H5MzCg/200w_d.gif",
            "fixed_width_downsampled_width": "200",
            "fixed_width_downsampled_height": "76",
            "rating": "pg-13",
            "username": "animatedtext",
            "caption": "requested by slightly-invisible",
            "tags": [
                "transparent",
                "green",
                "mom",
                "yolo",
                "oops"
            ]
        },
        "meta": {
            "status": 200,
            "msg": "OK"
        }
    }

### STICKER Trending Endpoint

Get the latest stickers trending on Giphy with this endpoint.  

    http://api.giphy.com/v1/stickers/trending?api_key=dc6zaTOxFJmzC

[Example](http://api.giphy.com/v1/stickers/trending?api_key=dc6zaTOxFJmzC&limit=4&fmt=html) trending query with html formatted response.

[Example](http://api.giphy.com/v1/stickers/trending?api_key=dc6zaTOxFJmzC&limit=4) trending query with default json response.

###### Path

    /v1/stickers/trending

###### Parameters

+ s - term or phrase to translate into a GIF
+ limit - (optional) number of results to return, maximum 100. Default: 25
+ offset - (optional) results offset, defaults to 0);
+ fmt - (optional) return results in html or json format.
+ rating - limit results to those rated (y,g, pg, pg-13 or r). 

###### Sample Response: Trending Stickers

    {
        data: [
            {
                type: "gif",
                id: "c6MjvgBu55ahi",
                url: "http://giphy.com/gifs/transparent-c6MjvgBu55ahi",
                bitly_gif_url: "http://gph.is/1s5KDEN",
                bitly_url: "http://gph.is/1s5KDEN",
                embed_url: "http://giphy.com/embed/c6MjvgBu55ahi",
                username: "",
                source: "http://myspaceglitter.tumblr.com/post/53041962471",
                rating: "pg",
                caption: "",
                content_url: "http://perhosia-vatsassa.tumblr.com/post/53038261647",
                trending_datetime: "2014-09-12 19:06:52",
                images: {
                    fixed_height: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/200.gif",
                        width: "174",
                        height: "200",
                        mp4: "http://media.giphy.com/media/c6MjvgBu55ahi/200.mp4"
                    },
                    fixed_height_still: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/200_s.gif",
                        width: "174",
                        height: "200"
                    },
                    fixed_height_downsampled: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/200_d.gif",
                        width: "174",
                        height: "200"
                    },
                    fixed_width: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/200w.gif",
                        width: "200",
                        height: "230",
                        mp4: "http://media.giphy.com/media/c6MjvgBu55ahi/200w.mp4"
                    },
                    fixed_width_still: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/200w_s.gif",
                        width: "200",
                        height: "230"
                    },
                    fixed_width_downsampled: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/200w_d.gif",
                        width: "200",
                        height: "230"
                    },
                    downsized: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/giphy.gif",
                        width: "473",
                        height: "544",
                        size: "489315"
                    },
                    downsized_still: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/giphy_s.gif",
                        width: "473",
                        height: "544"
                    },
                    original: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/giphy.gif",
                        width: "473",
                        height: "544",
                        size: "489315",
                        frames: "4",
                        mp4: "http://media.giphy.com/media/c6MjvgBu55ahi/giphy.mp4"
                    },
                    original_still: {
                        url: "http://media2.giphy.com/media/c6MjvgBu55ahi/giphy_s.gif",
                        width: "473",
                        height: "544"
                    }
                }
            },      
            ... 24 more items
        ],
        pagination: {
            count: 25,
            offset: 0
        },
        meta: {
            status: 200,
            msg: "OK"
        }
    }

### STICKER Translate Endpoint

Using the same alogirithm as the GIF translate endpoint, the sticker translate endpoint turns words into stickers.

    http://api.giphy.com/v1/stickers/translate?s=hungry&api_key=dc6zaTOxFJmzC

[Example](http://api.giphy.com/v1/stickers/translate?s=hungry&api_key=dc6zaTOxFJmzC) translate query.


###### Path

    /v1/stickers/translate

###### Parameters

+ s - term or phrase to translate into a gif

###### Sample Response, Translate

    {
        "data": {
            "type": "gif",
            "id": "VgJ7V2O0voODm",
            "url": "http://giphy.com/gifs/animated-gif-pixel-art-killscreen-VgJ7V2O0voODm",
            "bitly_gif_url": "http://gph.is/1pDqEst",
            "bitly_url": "http://gph.is/1pDqEst",
            "embed_url": "http://giphy.com/embed/VgJ7V2O0voODm",
            "username": "",
            "source": "http://killscreen.tumblr.com/post/67476623758/via",
            "rating": "g",
            "caption": "",
            "content_url": "",
            "import_datetime": "2013-11-19 17:27:00",
            "trending_datetime": "2014-09-16 18:13:33",
            "images": {
                "fixed_height": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/200.gif",
                    "width": "200",
                    "height": "200",
                    "mp4": "http://media.giphy.com/media/VgJ7V2O0voODm/200.mp4"
                },
                "fixed_height_still": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/200_s.gif",
                    "width": "200",
                    "height": "200"
                },
                "fixed_height_downsampled": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/200_d.gif",
                    "width": "200",
                    "height": "200"
                },
                "fixed_width": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/200w.gif",
                    "width": "200",
                    "height": "200",
                    "mp4": "http://media.giphy.com/media/VgJ7V2O0voODm/200w.mp4"
                },
                "fixed_width_still": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/200w_s.gif",
                    "width": "200",
                    "height": "200"
                },
                "fixed_width_downsampled": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/200w_d.gif",
                    "width": "200",
                    "height": "200"
                },
                "downsized": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/giphy.gif",
                    "width": "100",
                    "height": "100",
                    "size": "4518"
                },
                "downsized_still": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/giphy_s.gif",
                    "width": "100",
                    "height": "100"
                },
                "original": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/giphy.gif",
                    "width": "100",
                    "height": "100",
                    "size": "4518",
                    "frames": "6",
                    "mp4": "http://media.giphy.com/media/VgJ7V2O0voODm/giphy.mp4"
                },
                "original_still": {
                    "url": "http://media2.giphy.com/media/VgJ7V2O0voODm/giphy_s.gif",
                    "width": "100",
                    "height": "100"
                }
            }
        },
        "meta": {
            "status": 200,
            "msg": "OK"
        }
    }

**Once you are ready to use the Giphy STICKER API in production**, please contact [api@giphy.com](mailto:api@giphy.com) to request a unique API key. Please make the subject of your email "Sticker API Key Request". This is important as it will help us keep track of your request. 

## Code Examples

Below are code samples in Python, JavaScript, Ruby, PHP and the command line on connecting to the API to make a search query for "ryan gosling".


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

