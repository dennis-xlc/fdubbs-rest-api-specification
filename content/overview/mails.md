---
title: Mails | REST API
---

# Object: Mails

* TOC
{:toc}


## What is a mail ?

A mail is ...




## Mail Definition

Below is the JSON definition of a mail.

Field Name | Type | Description
------------|------------|------------
`id` | **string** | The mail id.
`link` | **string** | The link of the mail.
`title` | **string** | The title of this mail.
`unread` | **boolean** | 'true' if the mail has not read.
`mark_sign` | **string** | The mark sign of the mail.
`source` | **string** | The source of the mail.
`ip_address` | **string** | The ip address of this mail.
`sent_time` | **date** | The sent time of this mail.
`sender_name` | **string** | The name of the sender.
`sender_nick` | **string** | The nick of the sender.
`content` | **string** | The content of this mail.

### Example

    {
      "id": "xxx",
      "link": "xxx",
      "title": "xxx",
      "unread": true,
      "mark_sign": "+",
      "source": "xxx",
      "ip_address": "xxx",
      "sent_time": "2014-09-26:00:00:00",
      "sender_name": "xxx",
      "sender_nick": "xxx",
      "content": "xxx"
    }

