# BWSC Bot
A web scraping bot that scrapes the BWSC customer portal and uploads the data to a Google Sheet.

## Requirements

- Node 20.0.0 (Download [here](https://nodejs.org/en/download/))
  - Install after downloading the installer. Just hit next until the installation is finished. (Do not check the checkbox for installing Chocolatey)

## Installation

1. Download the zip file or clone the repository.
2. Extract the zip file after downloading.
3. Open the project
4. Open the terminal/command prompt and navigate to the project folder
    - `cd path/to/project`
5. Run the following command to install the required packages
    - `npm install`
6. Create a .env file in the root directory of the project and paste the following code
    ```
        PAGE = 'https://customerportal.bwsc.org'
        SPREADSHEET_ID = '1Yr8hNjoOlfuBHb1Pr5nKj6qdTJjgTv8JZBdfTT8yyUw'
        UPLOAD_DATA_SHEET_ID = '1CuhgeGqAh4HTTYZGsOwCvZVR3Z-WEi06908vb9CTE10' 
    ```
    wherein the `PAGE` is the URL of the page you want to scrape, `SPREADSHEET_ID` is the ID of the spreadsheet where the data will be stored, and `UPLOAD_DATA_SHEET_ID` is the ID of the spreadsheet where the data will be uploaded.

    #### How to get the spreadsheet ID
    1. Open the Google Sheet
    2. Copy the ID from the URL. Here is an example URL:
        - `https://docs.google.com/spreadsheets/d/1Yr8hNjoOlfuBHb1Pr5nKj6qdTJjgTv8JZBdfTT8yyUw/edit#gid=0`
        - The ID is `1Yr8hNjoOlfuBHb1Pr5nKj6qdTJjgTv8JZBdfTT8yyUw`
    #### How to get the upload data sheet ID
    1. Open the Google Sheet
    2. Copy the ID from the URL. Here is an example URL:
        - `https://docs.google.com/spreadsheets/d/1CuhgeGqAh4HTTYZGsOwCvZVR3Z-WEi06908vb9CTE10/edit#gid=0`
        - The ID is `1CuhgeGqAh4HTTYZGsOwCvZVR3Z-WEi06908vb9CTE10`
    #### What is the difference between SPREADSHEET_ID and UPLOAD_DATA_SHEET_ID
    - `SPREADSHEET_ID` is the spreadsheet where the data for account was stored
    - `UPLOAD_DATA_SHEET_ID` is the spreadsheet where the data will be uploaded.

## Important Notes
- Downloaded .csv files will be stored in the `downloads` folder.
- Make sure that the `downloads` folder is created in the root directory of the project.
- Delete the contents of the `downloads` (all .csv files only) folder before running the script to avoid confusion except for `.gitignore` file.

## Running the script
1. Open the terminal/command prompt and navigate to the project folder
    - `cd path/to/project`
2. Run the following command to start the script
    - `node .`

## For issues
- Slack me hihi :D

## Problems Olivia might encounter that's why I created a function for it:
- Problem 1: What if the files are downloaded but the bot failed to rename the files. What should I do next? The names are confusing?
    - Solution: I added a functionality that will rename the files in the `downloads` folder. Run the following command to rename the files: `node rename_files.js`

- Problem 2: What if I already renamed the files? How can I upload it to the google sheet? or what if I want to manually upload the data to the Google Sheet?
  - Solution: I added a functionality that will upload the data to the Google Sheet. Run the following command to upload the data: `node upload_data.js`



