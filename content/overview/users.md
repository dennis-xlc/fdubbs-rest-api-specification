---
title: Users | REST API
---

# Object: Users

* TOC
{:toc}


## What is a user ?

A user is ...




## User Definition

Below is the JSON definition of a user.

Field Name | Type | Description
------------|------------|------------
`profile` | (User Profile) **object** | basic profile of the user.
`history` | (User History) **object** | history data of the user.
`performance` | (User Performance) **object** | performance of the user.


### User Profile

Below is the JSON definition of the User Profile.

Field Name | Type | Description
------------|------------|------------
`id` | **string** | user id.
`nick` | **string** | nick.
`gender` | **string** | gender.
`birth_date` | (Birth Date) **object** | user birthday.
`is_visible` | **boolean** | is visible.
`is_web` | **boolean** | is login on web.
`introdution` | **string** | user introdution.
`desc` | **string** | desc.
`signature` | **string** | user signature.

### User Status

Below is the JSON definition of the user status.

Field Name | Type | Description
------------|------------|------------
`idle_time` | **long** | User idle time (in minutes).
`visible` | **boolean** | 'true' if the user is visible to other user.
`login_by_web` | **boolean** | 'true' if the user is login through web.
`description` | **integer** | User description.


### Birth Date

Below is the JSON definition of the user birthday.

Field Name | Type | Description
------------|------------|------------
`year` | **integer** | year of birth.
`month` | **integer** | month of birth.
`day` | **integer** | day of birth.


### User History

Below is the JSON definition of the user history data.

Field Name | Type | Description
------------|------------|------------
`register_date` | **date** | register date of the user.
`idle_time` | **long** | idle time in minutes.
`online_time` | **long** | total online time in min.
`post_count` | **long** | total number of posts.
`login_count` | **long** | total times of posts.
`last_login_time` | **date** | last login time.
`last_login_ip` | **string** | last login ip.

### User Performance

Below is the JSON definition of the user performance.

Field Name | Type | Description
------------|------------|------------
`horoscope` | **string** | horoscope.
`ident` | **integer** | ident.
`performance` | **string** | User performance.
`hp` | **long** | User hp.
`level` | **long** | User level.
`repeat` | **long** | User repeat.
`contrib` | **long** | User contrib.
`rank` | **string** | User rank.


### Example

    {
      "profile": {
      	"id": "xxx",
      	"nick": "xxx",
      	"gender": "M",
      	"birth_date": {
      		"year": 1988,
      		"month": 10,
      		"day": 28
      	},
      	"is_visible": true,
      	"is_web": false,
      	"introdution": "xxx",
      	"desc": "xxx",
      	"signature": "xxx"
      },
      "history": {
      	"register_date": "2014-09-26:00:00:00",
      	"idle_time": 123456,
      	"online_time": 123456,
      	"post_count": 12345,
      	"login_count": 1234,
      	"last_login_time": "2014-09-26:00:00:00",
      	"last_login_ip": "xxx"
      },
      "performance": {
      	"horoscope": "xxx",
      	"ident": 123,
      	"performance": "xxx",
      	"hp": 123456789,
      	"level": 123,
      	"repeat": 1234,
      	"contrib": 12345,
      	"rank": "xxx"
      }
    }
