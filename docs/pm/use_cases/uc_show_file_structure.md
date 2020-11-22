---
layout: default
title: UCS Show file structure
nav_order: 2
has_children: true
parent: Use cases
grand_parent: Project management
---

# Use Case Specification: Show file structure
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Show file structure
### Brief Description
The file structure is stored inside an encrypted reference table (JSON file) and stored on the server in order to be able to synchronize the files between multiple devices.
After the client downloaded the table and successfully decrypted the file, parsing of the file structure becomes possible.

### Mockup
![Mockup for file structure](../../../img/use_cases/mockups/show_file_structure.png)

## Flow of Evenets
### Basic Flow
![Activity Diagram for use case show file structure](../../../img/use_cases/activity_diagrams/ad_show_file_structure.svg)

## Gherkin file
You can find the feature file for this use case [here](https://github.com/Vaultionizer/vault-android-app/blob/master/app/src/test/java/com/vaultionizer/vaultapp/features/FileViewerUC.feature).

### Alternative Flow
n/a

## Special Requirements
n/a

## Preconditions
* User is logged in
* User has valid reference file stored encrypted on the server

## Postconditions
n/a

## Extension Points
n/a
