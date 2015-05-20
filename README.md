<p align="center">
<img align="center" src="api_giphy_header.gif" width="100%" alt="API Giphy logo"/>
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
            	type: "gif",
				id: "FiGiRei2ICzzG",
				url: "http://giphy.com/gifs/funny-cat-FiGiRei2ICzzG",
				bitly_gif_url: "http://gph.is/1fIdLOl",
				bitly_url: "http://gph.is/1fIdLOl",
				embed_url: "http://giphy.com/embed/FiGiRei2ICzzG",
				username: "",
				source: "http://tumblr.com",
				rating: "g",
				caption: "",
				content_url: "",
				import_datetime: "2014-01-18 09:14:20",
				trending_datetime: "1970-01-01 00:00:00",
				images: {
					fixed_height: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/200.gif",
						width: "568",
						height: "200",
						size: "460622",
						mp4: "http://media2.giphy.com/media/FiGiRei2ICzzG/200.mp4",
						mp4_size: "13866",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/200.webp",
						webp_size: "367786"
					},
					fixed_height_still: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/200_s.gif",
						width: "568",
						height: "200"
					},
					fixed_height_downsampled: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/200_d.gif",
						width: "568",
						height: "200",
						size: "476276",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/200_d.webp",
						webp_size: "100890"
					},
					fixed_width: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/200w.gif",
						width: "200",
						height: "70",
						size: "90483",
						mp4: "http://media2.giphy.com/media/FiGiRei2ICzzG/200w.mp4",
						mp4_size: "14238",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/200w.webp",
						webp_size: "47302"
					},
					fixed_width_still: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/200w_s.gif",
						width: "200",
						height: "70"
					},
					fixed_width_downsampled: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/200w_d.gif",
						width: "200",
						height: "70",
						size: "71069",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/200w_d.webp",
						webp_size: "13186"
					},
					fixed_height_small: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/100.gif",
						width: "284",
						height: "100",
						size: "460622",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/100.webp",
						webp_size: "72748"
					},
					fixed_height_small_still: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/100_s.gif",
						width: "284",
						height: "100"
					},
					fixed_width_small: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/100w.gif",
						width: "100",
						height: "35",
						size: "90483",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/100w.webp",
						webp_size: "18298"
					},
					fixed_width_small_still: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/100w_s.gif",
						width: "100",
						height: "35"
					},
					downsized: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy.gif",
						width: "500",
						height: "176",
						size: "426811"
					},
					downsized_still: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy_s.gif",
						width: "500",
						height: "176"
					},
					downsized_large: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy.gif",
						width: "500",
						height: "176",
						size: "426811"
					},
					original: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy.gif",
						width: "500",
						height: "176",
						size: "426811",
						frames: "22",
						mp4: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy.mp4",
						mp4_size: "51432",
						webp: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy.webp",
						webp_size: "291616"
					},
					original_still: {
						url: "http://media2.giphy.com/media/FiGiRei2ICzzG/giphy_s.gif",
						width: "500",
						height: "176"
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
            type: "gif",
			id: "feqkVgjJpYtjy",
			url: "http://giphy.com/gifs/eyes-shocked-bird-feqkVgjJpYtjy",
			bitly_gif_url: "http://gph.is/XJ200y",
			bitly_url: "http://gph.is/XJ200y",
			embed_url: "http://giphy.com/embed/feqkVgjJpYtjy",
			username: "",
			source: "http://littleanimalgifs.tumblr.com/post/17994517807",
			rating: "g",
			caption: "",
			content_url: "",
			import_datetime: "2013-03-21 04:03:08",
			trending_datetime: "2014-11-12 06:22:52",
			images: {
				fixed_height: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200.gif",
					width: "445",
					height: "200",
					size: "445432",
					mp4: "http://media0.giphy.com/media/feqkVgjJpYtjy/200.mp4",
					mp4_size: "27279",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200.webp",
					webp_size: "420734"
				},
				fixed_height_still: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_s.gif",
					width: "445",
					height: "200"
				},
				fixed_height_downsampled: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_d.gif",
					width: "445",
					height: "200",
					size: "183225",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_d.webp",
					webp_size: "89516"
				},
				fixed_width: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.gif",
					width: "200",
					height: "90",
					size: "115885",
					mp4: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.mp4",
					mp4_size: "31919",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.webp",
					webp_size: "122600"
				},
				fixed_width_still: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_s.gif",
					width: "200",
					height: "90"
				},
				fixed_width_downsampled: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.gif",
					width: "200",
					height: "90",
					size: "83007",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.webp",
					webp_size: "26460"
				},
				fixed_height_small: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100.gif",
					width: "223",
					height: "100",
					size: "445432",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/100.webp",
					webp_size: "129604"
				},
				fixed_height_small_still: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100_s.gif",
					width: "223",
					height: "100"
				},
				fixed_width_small: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100w.gif",
					width: "100",
					height: "45",
					size: "115885",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/100w.webp",
					webp_size: "41620"
				},
				fixed_width_small_still: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100w_s.gif",
					width: "100",
					height: "45"
				},
				downsized: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
					width: "334",
					height: "150",
					size: "511581"
				},
				downsized_still: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
					width: "334",
					height: "150"
				},
				downsized_large: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
					width: "334",
					height: "150",
					size: "511581"
				},
				original: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
					width: "334",
					height: "150",
					size: "511581",
					frames: "27",
					mp4: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.mp4",
					mp4_size: "97841",
					webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.webp",
					webp_size: "270108"
					},
					original_still: {
					url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
					width: "334",
					height: "150"
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
				url: "http://giphy.com/gifs/eyes-shocked-bird-feqkVgjJpYtjy",
				bitly_gif_url: "http://gph.is/XJ200y",
				bitly_url: "http://gph.is/XJ200y",
				embed_url: "http://giphy.com/embed/feqkVgjJpYtjy",
				username: "",
				source: "http://littleanimalgifs.tumblr.com/post/17994517807",
				rating: "g",
				caption: "",
				content_url: "",
				import_datetime: "2013-03-21 04:03:08",
				trending_datetime: "2014-11-12 06:22:52",
				images: {
					fixed_height: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200.gif",
						width: "445",
						height: "200",
						size: "445432",
						mp4: "http://media0.giphy.com/media/feqkVgjJpYtjy/200.mp4",
						mp4_size: "27279",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200.webp",
						webp_size: "420734"
					},
					fixed_height_still: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_s.gif",
						width: "445",
						height: "200"
					},
					fixed_height_downsampled: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_d.gif",
						width: "445",
						height: "200",
						size: "183225",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200_d.webp",
						webp_size: "89516"
					},
					fixed_width: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.gif",
						width: "200",
						height: "90",
						size: "115885",
						mp4: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.mp4",
						mp4_size: "31919",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w.webp",
						webp_size: "122600"
					},
					fixed_width_still: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_s.gif",
						width: "200",
						height: "90"
					},
					fixed_width_downsampled: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.gif",
						width: "200",
						height: "90",
						size: "83007",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/200w_d.webp",
						webp_size: "26460"
					},
					fixed_height_small: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100.gif",
						width: "223",
						height: "100",
						size: "445432",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/100.webp",
						webp_size: "129604"
					},
					fixed_height_small_still: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100_s.gif",
						width: "223",
						height: "100"
					},
					fixed_width_small: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100w.gif",
						width: "100",
						height: "45",
						size: "115885",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/100w.webp",
						webp_size: "41620"
					},
					fixed_width_small_still: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/100w_s.gif",
						width: "100",
						height: "45"
						},
					downsized: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
						width: "334",
						height: "150",
						size: "511581"
					},
					downsized_still: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
						width: "334",
						height: "150"
					},
					downsized_large: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
						width: "334",
						height: "150",
						size: "511581"
					},
					original: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.gif",
						width: "334",
						height: "150",
						size: "511581",
						frames: "27",
						mp4: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.mp4",
						mp4_size: "97841",
						webp: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy.webp",
						webp_size: "270108"
					},
					original_still: {
						url: "http://media0.giphy.com/media/feqkVgjJpYtjy/giphy_s.gif",
						width: "334",
						height: "150"
					}
				}
			},
			{
				type: "gif",
				id: "7rzbxdu0ZEXLy",
				url: "http://giphy.com/gifs/mrdiv-art-mrdiv-disco-ball-7rzbxdu0ZEXLy",
				bitly_gif_url: "http://gph.is/13YkU2y",
				bitly_url: "http://gph.is/13YkU2y",
				embed_url: "http://giphy.com/embed/7rzbxdu0ZEXLy",
				username: "mrdiv",
				source: "http://mrdiv.tumblr.com/post/48618427039/disco-sphere",
				rating: "g",
				caption: "",
				content_url: "",
				import_datetime: "2013-06-18 11:30:02",
				trending_datetime: "1970-01-01 00:00:00",
				images: {
					fixed_height: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200.gif",
						width: "200",
						height: "200",
						size: "95494",
						mp4: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200.mp4",
						mp4_size: "17167",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200.webp",
						webp_size: "71556"
					},
					fixed_height_still: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200_s.gif",
						width: "200",
						height: "200"
					},
					fixed_height_downsampled: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200_d.gif",
						width: "200",
						height: "200",
						size: "188423",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200_d.webp",
						webp_size: "48112"
					},
					fixed_width: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200w.gif",
						width: "200",
						height: "200",
						size: "95494",
						mp4: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200w.mp4",
						mp4_size: "17167",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200w.webp",
						webp_size: "71556"
					},
					fixed_width_still: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200w_s.gif",
						width: "200",
						height: "200"
					},
					fixed_width_downsampled: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200w_d.gif",
						width: "200",
						height: "200",
						size: "188423",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/200w_d.webp",
						webp_size: "48112"
					},
					fixed_height_small: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/100.gif",
						width: "100",
						height: "100",
						size: "95494",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/100.webp",
						webp_size: "25250"
					},
					fixed_height_small_still: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/100_s.gif",
						width: "100",
						height: "100"
					},
					fixed_width_small: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/100w.gif",
						width: "100",
						height: "100",
						size: "95494",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/100w.webp",
						webp_size: "25250"
					},
					fixed_width_small_still: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/100w_s.gif",
						width: "100",
						height: "100"
					},
					downsized: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy.gif",
						width: "500",
						height: "500",
						size: "1012692"
					},
					downsized_still: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy_s.gif",
						width: "500",
						height: "500"
					},
					downsized_large: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy.gif",
						width: "500",
						height: "500",
						size: "1012692"
					},
					original: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy.gif",
						width: "500",
						height: "500",
						size: "1012692",
						frames: "9",
						mp4: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy.mp4",
						mp4_size: "52678",
						webp: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy.webp",
						webp_size: "262666"
					},
					original_still: {
						url: "http://media1.giphy.com/media/7rzbxdu0ZEXLy/giphy_s.gif",
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
            type: "gif",
			id: "wWAIKcFASEFz2",
			url: "http://giphy.com/gifs/superman-santa-chandler-bing-wWAIKcFASEFz2",
			bitly_gif_url: "http://gph.is/XMD6gE",
			bitly_url: "http://gph.is/XMD6gE",
			embed_url: "http://giphy.com/embed/wWAIKcFASEFz2",
			username: "",
			source: "http://daytripperrevolution.tumblr.com/post/13729531842",
			rating: "g",
			caption: "",
			content_url: "",
			import_datetime: "2013-03-24 17:48:35",
			trending_datetime: "1970-01-01 00:00:00",
			images: {
				fixed_height: {
					url: "http://media3.giphy.com/media/wWAIKcFASEFz2/200.gif",
					width: "358",
					height: "200",
					size: "126220",
					mp4: "http://media2.giphy.com/media/wWAIKcFASEFz2/200.mp4",
					mp4_size: "10967",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/200.webp",
					webp_size: "186460"
				},
				fixed_height_still: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/200_s.gif",
					width: "358",
					height: "200"
				},
				fixed_height_downsampled: {
					url: "http://media3.giphy.com/media/wWAIKcFASEFz2/200_d.gif",
					width: "358",
					height: "200",
					size: "352636",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/200_d.webp",
					webp_size: "159946"
				},
				fixed_width: {
					url: "http://media3.giphy.com/media/wWAIKcFASEFz2/200w.gif",
					width: "200",
					height: "112",
					size: "51889",
					mp4: "http://media2.giphy.com/media/wWAIKcFASEFz2/200w.mp4",
					mp4_size: "16299",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/200w.webp",
					webp_size: "70302"
				},
				fixed_width_still: {
					url: "http://media1.giphy.com/media/wWAIKcFASEFz2/200w_s.gif",
					width: "200",
					height: "112"
				},
				fixed_width_downsampled: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/200w_d.gif",
					width: "200",
					height: "112",
					size: "131311",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/200w_d.webp",
					webp_size: "60336"
				},
				fixed_height_small: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/100.gif",
					width: "179",
					height: "100",
					size: "126220",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/100.webp",
					webp_size: "56790"
				},
				fixed_height_small_still: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/100_s.gif",
					width: "179",
					height: "100"
				},
				fixed_width_small: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/100w.gif",
					width: "100",
					height: "56",
					size: "51889",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/100w.webp",
					webp_size: "21266"
				},
				fixed_width_small_still: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/100w_s.gif",
					width: "100",
					height: "56"
				},
				downsized: {
					url: "http://media0.giphy.com/media/wWAIKcFASEFz2/giphy.gif",
					width: "500",
					height: "279",
					size: "508488"
				},
				downsized_still: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/giphy_s.gif",
					width: "500",
					height: "279"
				},
				downsized_large: {
					url: "http://media0.giphy.com/media/wWAIKcFASEFz2/giphy.gif",
					width: "500",
					height: "279",
					size: "508488"
				},
				original: {
					url: "http://media0.giphy.com/media/wWAIKcFASEFz2/giphy.gif",
					width: "500",
					height: "279",
					size: "508488",
					frames: "7",
					mp4: "http://media2.giphy.com/media/wWAIKcFASEFz2/giphy.mp4",
					mp4_size: "45225",
					webp: "http://media2.giphy.com/media/wWAIKcFASEFz2/giphy.webp",
					webp_size: "305416"
				},
				original_still: {
					url: "http://media2.giphy.com/media/wWAIKcFASEFz2/giphy_s.gif",
					width: "500",
					height: "279"
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
			type: "gif",
			id: "Ggjwvmqktuvf2",
			url: "http://giphy.com/gifs/american-psycho-christian-bale-Ggjwvmqktuvf2",
			image_original_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/giphy.gif",
			image_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/giphy.gif",
			image_mp4_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/giphy.mp4",
			image_frames: "11",
			image_width: "500",
			image_height: "256",
			fixed_height_downsampled_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/200_d.gif",
			fixed_height_downsampled_width: "391",
			fixed_height_downsampled_height: "200",
			fixed_width_downsampled_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/200w_d.gif",
			fixed_width_downsampled_width: "200",
			fixed_width_downsampled_height: "102",
			fixed_height_small_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/100.gif",
			fixed_height_small_still_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/100_s.gif",
			fixed_height_small_width: "195",
			fixed_height_small_height: "100",
			fixed_width_small_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/100w.gif",
			fixed_width_small_still_url: "http://s3.amazonaws.com/giphygifs/media/Ggjwvmqktuvf2/100w_s.gif",
			fixed_width_small_width: "100",
			fixed_width_small_height: "51"                 
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
			id: "op7uqYWBm3R04",
			url: "http://giphy.com/gifs/food-krush-groove-the-fat-boys-op7uqYWBm3R04",
			bitly_gif_url: "http://gph.is/1FupHza",
			bitly_url: "http://gph.is/1FupHza",
			embed_url: "http://giphy.com/embed/op7uqYWBm3R04",
			username: "",
			source: "http://televandalist.com/post/104471085874",
			rating: "y",
			caption: "",
			content_url: "",
			import_datetime: "2014-12-06 06:21:55",
			trending_datetime: "2015-04-01 16:05:01",
			images: {
					fixed_height: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/200.gif",
						width: "360",
						height: "200",
						size: "0",
						mp4: "http://media0.giphy.com/media/op7uqYWBm3R04/200.mp4",
						mp4_size: "367554",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/200.webp",
						webp_size: "875414"
					},
					fixed_height_still: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/200_s.gif",
						width: "360",
						height: "200"
					},
					fixed_height_downsampled: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/200_d.gif",
						width: "360",
						height: "200",
						size: "140417",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/200_d.webp",
						webp_size: "130658"
					},
					fixed_width: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/200w.gif",
						width: "200",
						height: "111",
						size: "0",
						mp4: "http://media0.giphy.com/media/op7uqYWBm3R04/200w.mp4",
						mp4_size: "342209",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/200w.webp",
						webp_size: "327936"
					},
					fixed_width_still: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/200w_s.gif",
						width: "200",
						height: "111"
					},
					fixed_width_downsampled: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/200w_d.gif",
						width: "200",
						height: "111",
						size: "368276",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/200w_d.webp",
						webp_size: "49460"
					},
					fixed_height_small: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/100.gif",
						width: "180",
						height: "100",
						size: "0",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/100.webp",
						webp_size: "281042"
					},
					fixed_height_small_still: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/100_s.gif",
						width: "180",
						height: "100"
					},
					fixed_width_small: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/100w.gif",
						width: "100",
						height: "56",
						size: "0",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/100w.webp",
						webp_size: "108110"
					},
					fixed_width_small_still: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/100w_s.gif",
						width: "100",
						height: "56"
					},
					downsized: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy.gif",
						width: "400",
						height: "222",
						size: "2071771"
					},
					downsized_still: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy_s.gif",
						width: "400",
						height: "222"
					},
					downsized_large: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy.gif",
						width: "400",
						height: "222",
						size: "2071771"
					},
					original: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy.gif",
						width: "400",
						height: "222",
						size: "2071771",
						frames: "41",
						mp4: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy.mp4",
						mp4_size: "928142",
						webp: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy.webp",
						webp_size: "1004522"
					},
					original_still: {
						url: "http://media0.giphy.com/media/op7uqYWBm3R04/giphy_s.gif",
						width: "400",
						height: "222"
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
           type: "gif",
			id: "XMfznXqrNvH2w",
			url: "http://giphy.com/gifs/animatedtext-transparent-lol-XMfznXqrNvH2w",
			image_original_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/giphy.gif",
			image_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/giphy.gif",
			image_mp4_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/giphy.mp4",
			image_frames: "30",
			image_width: "629",
			image_height: "154",
			fixed_height_downsampled_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/200_d.gif",
			fixed_height_downsampled_width: "817",
			fixed_height_downsampled_height: "200",
			fixed_width_downsampled_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/200w_d.gif",
			fixed_width_downsampled_width: "200",
			fixed_width_downsampled_height: "49",
			fixed_height_small_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/100.gif",
			fixed_height_small_still_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/100_s.gif",
			fixed_height_small_width: "408",
			fixed_height_small_height: "100",
			fixed_width_small_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/100w.gif",
			fixed_width_small_still_url: "http://s3.amazonaws.com/giphygifs/media/XMfznXqrNvH2w/100w_s.gif",
			fixed_width_small_width: "100",
			fixed_width_small_height: "24"
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
				id: "sj0sbNi9cv2dG",
				url: "http://giphy.com/gifs/cat-transparent-sj0sbNi9cv2dG",
				bitly_gif_url: "http://gph.is/Kq60z1",
				bitly_url: "http://gph.is/Kq60z1",
				embed_url: "http://giphy.com/embed/sj0sbNi9cv2dG",
				username: "",
				source: "http://ibehhvinny.tumblr.com/post/71539185754/so-coot",
				rating: "g",
				caption: "",
				content_url: "",
				import_datetime: "2014-01-04 15:39:18",
				trending_datetime: "1970-01-01 00:00:00",
				images: {
					fixed_height: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200.gif",
						width: "193",
						height: "200",
						size: "136213",
						mp4: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200.mp4",
						mp4_size: "156945",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200.webp",
						webp_size: "142110"
					},
					fixed_height_still: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200_s.gif",
						width: "193",
						height: "200"
					},
					fixed_height_downsampled: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200_d.gif",
						width: "193",
						height: "200",
						size: "45291",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200_d.webp",
						webp_size: "21510"
					},
					fixed_width: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200w.gif",
						width: "200",
						height: "207",
						size: "140056",
						mp4: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200w.mp4",
						mp4_size: "157163",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200w.webp",
						webp_size: "147254"
					},
					fixed_width_still: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200w_s.gif",
						width: "200",
						height: "207"
					},
					fixed_width_downsampled: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200w_d.gif",
						width: "200",
						height: "207",
						size: "46481",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/200w_d.webp",
						webp_size: "22310"
					},
					fixed_height_small: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/100.gif",
						width: "97",
						height: "100",
						size: "136213",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/100.webp",
						webp_size: "60522"
					},
					fixed_height_small_still: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/100_s.gif",
						width: "97",
						height: "100"
					},
					fixed_width_small: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/100w.gif",
						width: "100",
						height: "104",
						size: "140056",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/100w.webp",
						webp_size: "63260"
					},
					fixed_width_small_still: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/100w_s.gif",
						width: "100",
						height: "104"
					},
					downsized: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy.gif",
						width: "400",
						height: "414",
						size: "422870"
					},
					downsized_still: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy_s.gif",
						width: "400",
						height: "414"
					},
					downsized_large: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy.gif",
						width: "400",
						height: "414",
						size: "422870"
					},
					original: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy.gif",
						width: "400",
						height: "414",
						size: "422870",
						frames: "39",
						mp4: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy.mp4",
						mp4_size: "292473",
						webp: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy.webp",
						webp_size: "289928"
					},
					original_still: {
						url: "http://media0.giphy.com/media/sj0sbNi9cv2dG/giphy_s.gif",
						width: "400",
						height: "414"
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
            type: "gif",
			id: "11eZCNibwDFx6w",
			url: "http://giphy.com/gifs/11eZCNibwDFx6w",
			bitly_gif_url: "http://gph.is/1ptYDDI",
			bitly_url: "http://gph.is/1ptYDDI",
			embed_url: "http://giphy.com/embed/11eZCNibwDFx6w",
			username: "",
			source: "http://www.gifbay.com/gif/here_take_this-123255/",
			rating: "g",
			caption: "",
			content_url: "",
			import_datetime: "2014-03-25 00:52:20",
			trending_datetime: "2015-01-08 16:09:46",
			images: {
				fixed_height: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/200.gif",
					width: "295",
					height: "200",
					size: "118405",
					mp4: "http://media1.giphy.com/media/11eZCNibwDFx6w/200.mp4",
					mp4_size: "265838",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/200.webp",
					webp_size: "219116"
				},
				fixed_height_still: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/200_s.gif",
					width: "295",
					height: "200"
				},
				fixed_height_downsampled: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/200_d.gif",
					width: "295",
					height: "200",
					size: "63883",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/200_d.webp",
					webp_size: "33256"
				},
				fixed_width: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/200w.gif",
					width: "200",
					height: "135",
					size: "72894",
					mp4: "http://media1.giphy.com/media/11eZCNibwDFx6w/200w.mp4",
					mp4_size: "175118",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/200w.webp",
					webp_size: "115364"
				},
				fixed_width_still: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/200w_s.gif",
					width: "200",
					height: "135"
				},
				fixed_width_downsampled: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/200w_d.gif",
					width: "200",
					height: "135",
					size: "29898",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/200w_d.webp",
					webp_size: "17654"
				},
				fixed_height_small: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/100.gif",
					width: "148",
					height: "100",
					size: "118405",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/100.webp",
					webp_size: "67436"
				},
				fixed_height_small_still: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/100_s.gif",
					width: "148",
					height: "100"
				},
				fixed_width_small: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/100w.gif",
					width: "100",
					height: "68",
					size: "72894",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/100w.webp",
					webp_size: "40942"
				},
				fixed_width_small_still: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/100w_s.gif",
					width: "100",
					height: "68"
				},
				downsized: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy.gif",
					width: "294",
					height: "199",
					size: "375114"
				},
				downsized_still: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy_s.gif",
					width: "294",
					height: "199"
				},
				downsized_large: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy.gif",
					width: "294",
					height: "199",
					size: "375114"
				},
				original: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy.gif",
					width: "294",
					height: "199",
					size: "375114",
					frames: "39",
					mp4: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy.mp4",
					mp4_size: "321196",
					webp: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy.webp",
					webp_size: "203110"
				},
				original_still: {
					url: "http://media1.giphy.com/media/11eZCNibwDFx6w/giphy_s.gif",
					width: "294",
					height: "199"
				}
}        },
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

