---
title: Sections | REST API
---

# Object: Sections

* TOC
{:toc}


## What is a section ?

A section contains a set of [`boards`](/overview/boards).



## Section definition

Below is the JSON definition of a section.

Field Name | Type | Description
------------|------------|------------
`id` | **string** | The unique identifier of a section
`name` | **string** | The name of a section
`category` | **string** | The category of a section
`boards` | ([board](/overview/boards)) **array** | all [`boards`](/overview/boards) belong to the section

### Example

    {
      "id": "xxx",
      "name": "xxx",
      "category": "xxx",
      "boards": [
        {
          ...
        },
        ...
        {
          ...
        }
      ]
    }