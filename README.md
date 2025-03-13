# Jira2Plane

Jira_to_Plane notebook : <a href="https://colab.research.google.com/github/preste-ai/Jira2Plane/blob/main/Jira_to_Plane_(public).ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" height=22.5></a>

Notebook to transfer projects from Jira to Plane.

This notebook has been converted to jupyter notebook, but it was prepared and tested only as a Google Colab notebook.

Adaptation will be needed to run it as a jupyter notebook locally, in particular for file reading.

## What does it do ?

This notebook allows to copy jira projects into plane self hosted Community Edition version

- It allows copying one project at a time, with a few manual operations
- It maps priorities and states according to a customizable mapping plan
- It maps users according to a mapping that needs to be prepared beforehand.
- It creates issues from all jira stories, issues, tasks, sub-tasks
- It creates modules from jira epic
- It generates comments as they exist in jira, except for attachment links which are copied, but not directly functional
- It extracts jira attachments, push them into a GDrive folder, and add them as additional comments in Plane
- It does not keep the same sequence of issue ids as in Jira, but it adds an additional comment per each issue in Plane with the corresponding issue id in Jira


## Prerequisites

Extract your projects from the Jira issue view using the Export > *Export excel csv (all fields)*

Export your atlassian website cookie using a browser extension like Cookie Editor and copy them in a file (default name atlassian_cookie.json)

Create an API key in your plane workspace

Retrieve plane user ids using a dummy project with dummy tasks, each assigned to an individual plane user.

Retrieve all the jira user names and ids you need to map from the project exports (they are easily findable in the project exports)

Either copy this notebook into a Google Colab or : 
- Install pandas in your python environment
- Install google.colab and googleapiclient in your python environment
- Update file reading / writing instructions

## How to run

The notebook is organized in 5 sections

- Imports and Plane variables
	- a few cells need to be updated with your values before running => once for all
- Imports and variables to manage attachments with GDrive
	- a few cells need to be updated with your values before running => once for all, except maybe for the attachments project folder if you prefer to have a separate folder for each project
- Import / create in Plane : functions
	- Only function definition : can be run as a block, as is
- Export one project from Jira :
	- needs to be udpated / followed one cell at a time, for each project
- Import / create in Plane : execution
	- first cell need to be updated with Plane project_id, second for check, the rest can be run as is
