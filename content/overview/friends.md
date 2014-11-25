---
title: Friends | REST API
---

# Object: Friends

* TOC
{:toc}


## What is a friend ?

A friend is ...




## Friend Definition

Below is the JSON definition of a friend.

Field Name | Type | Description
------------|------------|------------
`id` | **string** | user id.
`nick` | **string** | User nick.
`last_login_ip` | **string** | last login ip.
`last_action` | **string** | last action.
`idle_time` | **long** | idle time in minutes.
`desc` | **string** | description.


### Example

    {
      "id": "xxx",
      "nick": "xxx",
      "last_login_ip": "xxx",
      "last_action": "xxx",
      "idle_time": 123456,
      "desc": "xxx"
    }