---
title: Posts | REST API
---

# Object: Posts

* TOC
{:toc}


## What is a post ?


## Post Definition

Below is the JSON definition of a post.

Field Name | Type | Description
------------|------------|------------
`id` | **string** | The unique identifier of a post
`title` | **string** | The title of a post
`poster` | (Poster) **object** | The poster of a post
`post_time` | **date** | The post time of the post
`board` | **string** | The board to which the post belongs
`board_id` | **string** | The board id to which the post belongs
`sticky` | **boolean** | whether the post should reside at the bottom of the board 
`mark_sign` | **string** | mark sign of a post
`repliable` | **boolean** | whether the post can be replied
`body` | **string** | post body, which in html format
`qoute` | **string** | post qoute, in html format
`reply_count` | **integer** | reply number of the post
`reply_list` | ([post](/overview/posts)) **array** | post reply list

### Poster

Field Name | Type | Description
------------|------------|------------
`name` | **string** | The name of the poster
`nick` | **string** | The nick of the poster
`sign` | **string** | sign of the poster, in html format

### Post Body && Qoute


### Example

    {
      "id": "xxx",
      "title": "xxx",
      "poster":{
        "name": "xxx",
        "nick": "xxx",
        "sign": "xxx"
      },
      "post_time": "2014-09-26:00:00:00",
      "board": "xxx",
      "board_id": "xxx",
      "sticky": false,
      "mark_sign": "M",
      "repliable": true,
      "body": "xxx",
      "qoute": "xxx",
      "reply_count": 1234,
      "reply_list": [
      	{
      		...
      	},
      	...
      	{
      		...
      	}
      ]
    }