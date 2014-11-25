---
title: Using cursors to navigate collections | REST API
---

# Using cursors to navigate collections

* TOC
{:toc}

### Cursoring

The Shinify REST API utilizes a technique called `cursoring` to paginate large result sets. Cursoring separates results into pages (the size of which are defined by the `count` request parameter) and provides a means to move backwards and forwards through these pages.

To retrieve cursored results, you initially pass a `cursor` with a value of `-1` to the endpoint. By default, an API endpoint that supports cursoring will assume `-1` was passed as cursor if you do not provide one. The response to a cursored request will contain `previous_cursor` and `next_cursor`.

The `next_cursor` is the cursor that you should send to the endpoint to receive the next batch of responses, and the `previous_cursor` is the cursor that you should send to receive the previous batch. You will know that you have requested the last available page of results when the API responds with a `next_cursor = 0`.

### Pseudocode

The pseudocode to iterate over all responses from a cursored endpoint is:

	cursor = -1
	api_path = "https://shinify.herokuapp.com/api/v1/someCollection"

	do {
		url_with_cursor = api_path + "&cursor=" + cursor
		response_dictionary = perform_http_get_request_for_url( url_with_cursor )
		cursor = response_dictionary[ 'next_cursor' ]
	}
	while ( cursor != 0 )

### Example

Let’s see a real-life example of cursors in action. Consider the common scenario where we want to obtain the list of post reply. Instead of returning all replies in one response set, the endpoint will instead return pages of results.

#### Request

	GET https://shinify.herokuapp.com/api/v1/post/12345/reply

#### Response (truncated)

	{
		"board_id": "xxx",
		"post_id": "xxx",
		"reply_list": [
			{
	      		...
	      	},
	      	...
	      	{
	      		...
	      	}
      	],
      	"next_cursor": "1374004777531007833",
      	"previous_cursor": "0"
    }


We now have a means to move forwards through our dataset, via the `next_cursor`. To get the next batch of at least 20 results, perform the same request, but set the cursor to the value of the `next_cursor`.

#### Request

	GET https://shinify.herokuapp.com/api/v1/post/12345/reply?cursor=1374004777531007833

#### Response (truncated)

	{
		"board_id": "xxx",
		"post_id": "xxx",
		"reply_list": [
			{
	      		...
	      	},
	      	...
	      	{
	      		...
	      	}
      	],
      	"next_cursor": "1323935095007282836",
      	"previous_cursor": "-1374003371900410561"
    }


Notice that we now have a `next_cursor` as well as a `previous_cursor`. This means that we can now move back and forth through our results. Let’s keep advancing through the data with the next cursor.

#### Request

	GET https://shinify.herokuapp.com/api/v1/post/12345/reply?cursor=1323935095007282836

#### Response (truncated)

	{
		"board_id": "xxx",
		"post_id": "xxx",
		"reply_list": [
			{
	      		...
	      	},
	      	...
	      	{
	      		...
	      	}
      	],
      	"next_cursor": "0",
      	"previous_cursor": "-1323886329961827926"
    }

Huzzah. The `next_cursor` is now 0, which indicates that there are no more remaing pages. We’ve now completed iterating over the post’ reply.
