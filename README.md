# Jira2Plane
Notebook to transfer projects from Jira to Plane
This notebook has been convert to jupyter notebook, but was prepared and tested only as Google Colab notebook
Adaptation will be needed to run it as jupyter notebook locally, in particular for file reading.

## What does it do ?

This notebook allows to copy jira projects into plane self hosted Community Edition version

It allows copying one project at a time, with a few manual operations

It will map priorities and states according to a customizable mapping plan

It will map users according to a mapping table you need to complete first

It will create issues from all jira stories, issues, tasks, sub-tasks
It will create modules from jira epic
It will generate comments as they are in jira, except for attachment links which will be copied, but non functional

It will extract jira attachments, push them in a GDrive folder, and add them as additional comments in Plane

It will not conserve the same sequence of issue ids as in Jira, but it will add an additional comment per each issue in Plane with the correspondance issue id in Jira


## Prerequisites

Extract your projects from the Jira issue view using the Export > Export excel csv (all fields)

Export your atlassian website cookie using a browser extension like Cookie Editor and copy them in a file (default name atlassian_cookie.json)

Create an API key in your plane workspace

Retrieve plane user ids using a dummy project with dummy tasks, each assigned to an individual plane user
Retrieve all the jira user names and ids you need to map from the project exports

either copy this notebook into a Google Colab or : 
- Install pandas in your python environment
- Install google.colab and googleapiclient in your python environment

## How to run

The notebook is organized in 5 sections

- Imports and Plane variables
	- a few cells needs to be updated with your values before running
- Imports and variables to manage attachments with GDrive
	- a few cells needs to be updated with your values before running
- Import / create in Plane : functions
	- Only function definition : can be run as a block, as is
- Export one project from Jira :
	- needs to be udpated / followed one cell at a time
- Import / create in Plane : execution
	- first cell need to be updated with Plane project_id, second for check, the rest can be run as is
