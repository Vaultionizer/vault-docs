---
layout: default
title: UCS Create space
nav_order: 2
has_children: true
parent: Use cases
grand_parent: Project management
---

# Use Case Specification: Create Space
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Create Space
### Brief Description
In order to create a space the user has to specify certain properties (e.g. local space name and encryption algorithm for the keys).
The properties are then tranfered to the server via a HTTP Rest-call. 

### Mockup
![Activity Diagram for use case create space](../../../img/use_cases/mockups/AddNewSpace.png)

## Flow of Evenets
### Basic Flow
![Activity Diagram for use case create space](../../../img/use_cases/activity_diagrams/ad_create_space.svg)

### Alternative Flow
n/a

## Special Requirements

## Preconditions
* User is logged in

## Postconditions
n/a

## Extension Points
n/a