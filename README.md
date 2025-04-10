# REDCap API Extractor

## Overview

Welcome, if you're reading this that means you're in the Youth Villages Research Department, welcome. The purpose of this software is when you have a need of accessing REDCap in some capacity to export data between REDCap projects for quicker data manipulation. The purpose of this application is to quickly combine fields that are the same between projects and export them into a combined csv formatted dataset.

## Setup

No setup is required as far as the installation of this program as the application runs entirely from the executable file. However some setup is needed on the REDcap side in order to grab information from REDCap projects.
 
## Getting Started

-  **Enabling API Access**: 
	- The first thing that you need to do is enable an API token for the project(s) that you'd like to pull data from. You do this by first getting your REDCap administrator to enable API Export permissions for you and generating an API Token. 
	- Permissions can be modified from the **User Rights** page under the Applications tab on your project. What you're looking for on the User Rights panel is **API Export** under Basic Privileges. Make sure that's checked, no need to worry about API Import/Update. 
	- Once you have API Export permissions, each project that you need data from, you need a unique API token for each project. There is no API tokens that can be created to store data for multiple projects, every API token is unique for each individual user for each individual project and is your ticket so to speak for data from that project.
-  **A Note About API Tokens**
	- These API tokens give folks access to you API projects as you without needing your REDCap log in details, so keep these API Tokens in a safe place and **DO NOT SHARE THEM** or store them where anybody can easily access them. If you feel that an API token has been compromised it is best to delete the API token and regenerate a new one. 
  

## Interface Summary

This is the Application interface. From top to bottom these are the parts of the application: 

 - **Environment Selector**: This is to select which REDCap environment you're querying from like Production vs Test.
 - **API Token Input Section**: This is where you'll input Tokens, one at a time or in bulk separated by commas. 
 - **API Token Window** : This is where all added API Tokens live, and can be deleted from.
 - **Save/Load Token Buttons** : This saves and loads your API Token list for easy recall.
 - **Fetch Data Button** : Button makes the API call and saves the data as CSV.
 - **Comapact Checkbox** : Reduces Files from WG2 to Selective fields (This will break on every other dataset.)

![Overview Image of Application](/.images/overview2.PNG) 

## Usage

1.  **Select Environment** 
First use the Environment Selector at the top of the application to select which instance of REDCap you'd like to pull API data from. Below is a list of the REDCap API Instances with the links they connect with:

| Instance Name  | Instance URL |
|--|--|
| Production | https://redcap.youthvillages.org/api/  |
| Test | https://redcaptest.youthvillages.org/api/ |
| Memphis Allies | https://redcap.memphisallies.org/api/ |
| Partners | https://redcapsp.youthvillages.org/api/ |
| New Allies | https://redcap.newallies.org/api/ |
|||

2. **Enter API Token(s)**
Begin typing in API tokens at the top in the textbox. You can enter one at a time or you can enter multiple API tokens separated by a comma and press the [ **Add Token(s)** ] button.

-  **Optional: Save / Load Token List**:
	-	If you have data pulls that you do regularly, it's best to save the token list so that you can quickly grab data projects without having to re-type all the API tokens. These files do contain your API token so be careful with these files.

3. **Export Data**
	Press the [ **Fetch Data & Export to CSV** ] button and choose where you'd like to save the data.

> ### Extra Information
> - Make sure that you don't repeat API tokens because that data will be duplicated, also note that any Record IDs will copy the Record IDs as well, for example if two survey's both have record ids that start with `["1","2","3"]` then in the results csv will have duplicate result ids `["1","2","3"]`.
> - A note about saving and loading API token lists: Only one list can be deleted at a time, there's no clear all tokens button (Maybe a later version), but loading an API token list removes all tokens that are currently in the token window and replaces it with the list; just a note to keep in mind. 


## Conclusion
Hopefully this tool gives the Research Department an upper edge in exporting data and pushing Youth Villages R.D. further. Enjoy!

> Author & Creator: Wongani F. Jere

  ## Release Notes

- v1.0 : Application created to Add API tokens, Save & Load API token lists and export data to CSV
- v1.2 : Environment Dropdown created to switch between PROD & Test. [ Add. Memphis Allies, Partners and New Allies are ready to be added ]
- v1.3 : Added in Partners, Memphis Allies, and New Allies into Environment window, and added exportCheckboxLabel, exportSurverFields, and exportDataAccessGroups to false.
- v1.3.1: Adding Logging
- v1.3.2: Adding Multithreading; Expanding logging and adding Progress Bar and Progress Bar Text.
- v1.3.3: Formatting Progress Bar & Text; adding Debug Logging and handling empty API pulls with validating API Requests
- v1.4: Added Multithreading for faster data pulls and to handle API calls and GUI on different threads; Added Logging Functionality to help with problem debugging as well as logging API Requests / with Validating them ; Added a progress bar with progress bar text to update on token API pulls so user can see information in real time. Adding handling of empty API calls and empty API token input into the token window.
- v1.5: Adding in compact checkbox to Consolidate fields to Walters shortlist for WG2. (Specific Use Case)
- v1.5.1: Attempting to fix App Icon and Execution Error with DASH Security Restriction & Removing file logging.