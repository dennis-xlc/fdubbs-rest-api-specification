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
`name` | **string** | User name.
`nick` | **string** | The nick name of the user.
`gender` | **string** | gender.
`horoscope` | **string** | Horoscope.
`birth_date` | **birth_date** | Birth date of the user.
`register_date` | **date** | Register date.
`total_online` | **long** | Total online time of the user.
`total_posts` | **long** | Total post number of the user.
`login_count` | **string** | Total login number of the user.
`last_login_ip` | **string** | Last login ip.
`last_login_time` | **date** | Last login time.
`status` | **status** | User status.
`signature` | **string** | User signature.
`ident` | **string** | User ident.
`introduction` | **string** | User introduction.


### Birth Date

Below is the JSON definition of the birth date.

Field Name | Type | Description
------------|------------|------------
`year` | **integer** | Year of  birth.
`month` | **integer** | Month of  birth.
`day` | **integer** | Day of birth.


### User Status

Below is the JSON definition of the user status.

Field Name | Type | Description
------------|------------|------------
`idle_time` | **long** | User idle time (in minutes).
`visible` | **boolean** | 'true' if the user is visible to other user.
`login_by_web` | **boolean** | 'true' if the user is login through web.
`description` | **integer** | User description.




### User Performance

Below is the JSON definition of the user performance.

Field Name | Type | Description
------------|------------|------------
`performance` | **string** | User performance.
`hp` | **integer** | User hp.
`level` | **integer** | User level.
`repeat` | **integer** | User repeat.
`contrib` | **integer** | User contrib.
`rank` | **string** | User rank.

