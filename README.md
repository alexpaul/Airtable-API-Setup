# Airtable-API-Setup

## 1. 
You will only be interacting with the "Project Tracker" workspace which you have by default once you sign up and login to your Airtable account

![workspaces](Assets/workspaces.png)

## 2. 
Step to get your project key. Click on the help menu at the top right and select "API documentation"
![help menu](Assets/help-menu.png)

## 3 
Once in the API documentation, click on the Project tracker
![api documentation](Assets/api-documentation.png)

## 4
After clicking on the Project tracker your project id key will be in the curl request line to the top right, starts with /app_________
![create records documentation](Assets/create-records-documentation.png)

>After getting your (Project tracker key) and you (API key) this GET request endpoint will work in Postman to get back the data from your Project tracker `https://api.airtable.com/v0/(Project tracker id goes here)/Design%20projects?typecast=true&&api_key=(API key goes here)`
