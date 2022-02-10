# OpenAPI Tooling

This project is provided by the OpenAPI Initiative as a means to centralize ecosystem information on OpenAPI-related tooling. It leverages open source projects that have gone before to provide a consolidated list of tooling.

This project Kanban board for Tooling can be found here: https://github.com/OAI/Projects/projects/4

## Roll Call

The following projects are being leveraged to provide the majority of the source information.

| Name | Source | Description |
| ---- | ------ | ----------- |
| OpenAPI Specification | https://github.com/OAI/OpenAPI-Specification | IMPLEMENTATIONS.md file containing tooling list. |
| OpenAPI.Tools | https://github.com/apisyouwonthate/openapi.tools | APIs Your Won't Hate efforts to create uber list of tooling. |
| API.guru | https://github.com/apis-guru/awesome-openapi3 | Repository/site based on tagged repositories in Github.<br>This repository reuses the build approach rather than pulling the list from the source. |

## Design

The design approach is split into two features:

* A unified list of tooling merged from sources across the interwebs that users can grab and slice-and-dice as they see fit.
* A website that allows users to search and inspect the tooling data first hand.

Each is expanded upon in the sections below.

### Unified Tooling List

The tooling list is built in largely the same format as the majority of projects that have blazed a trail in tooling before (which of course this project takes full advantage of).

In order to bring this together in a sensible way a Gulp-based process has been implemented. Gulp was chosen given the relative ease with which functions can be implemented to massage the data stream and to ensure the build is not closely-coupled to a CI tool.

Currently only the initial build is implemented. The steps are as follows:

* Retrieve each tooling source.
* Combine source data based on repository name.
* Normalise property names across sources using simple statistics (Sørensen–Dice, Damerau–Levenshtein distance).
* Get repository metadata from GitHub.
* Write to [docs/tools.yaml](docs/tools.yaml)

This process will be amended to include a merge process to capture updates to sources and merge into the existing dataset.

### Website

This is a work-in-progress and as yet undocumented.
