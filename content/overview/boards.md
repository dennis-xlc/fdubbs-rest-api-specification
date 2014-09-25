---
title: Boards | REST API
---

# Object: Boards

* TOC
{:toc}


## What is a board ?

A board is ...

A board can be a directory, which contains a set of board(sub-board).


## Board definition

Below is the JSON definition of a board.

Field Name | Type | Description
------------|------------|------------
`id` | **string** | The unique identifier of a board
`name` | **string** | The name of a board
`description` | **string** | The description of a board
`category` | **string** | The category of a board
`total_posts` | **long** | Total number of posts in the board
`is_directory` | **boolean** | 'true' if the board is a directory. A directory can contain one or more boards.
`has_unread` | **boolean** | 'true' if the board contains anu unread post for the user, 'false' otherwise.
`managers` | (string) **array** | A list of the board manager's name. A board manager must be a user of the system.


### Example

    {
      "id": "...",
      "name": "...",
      "description": "...",
      "category": "...",
      "total_posts": 1234,
      "is_directory": false,
      "has_unread": true,
      "managers": [
        "abc",...,"xyz"
      ]
    }