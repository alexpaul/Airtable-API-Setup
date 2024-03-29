# Airtable-API-Setup

This document walks you through the resources needed to get setup with an Airtable API key and a Project tracker workspace key. First sign up to an Airtable account [here](https://airtable.com/). Once sign up follow step 1 below to get your API key. You will also need the Project tracker key to continue on to step 6 to make a GET request to get the Project tracker data.

## Objective 

* Attain an Airtable API Key 
* Project tracker key 
* GET request for your Project tracker data 
* POST to your Project tracker

## 1. Account 
![account](Assets/account.jpg)

## 2. Access API Key 
![api key](Assets/access-api-key.jpg)

## 3. Workspaces include Project Tracker workspace
You will only be interacting with the "Project Tracker" workspace which you have by default once you sign up and login to your Airtable account

![workspaces](Assets/workspaces.png)

## 4. Help menu 
Step to get your project key. Click on the help menu at the top right and select "API documentation"
![help menu](Assets/help-menu.png)

## 5. API documentation
Once in the API documentation, click on the Project tracker
![api documentation](Assets/api-documentation.png)

## 6. Project tracker - create records API documentation
After clicking on the Project tracker your project id key will be in the curl request line to the top right, starts with /app_________
![create records documentation](Assets/create-records-documentation.png)

## 7. GET request endpoint and info 
>After getting your (Project tracker key) and you (API key) this GET request endpoint will work in Postman to get back the data from your Project tracker `https://api.airtable.com/v0/(Project tracker id goes here)/Design%20projects?typecast=true&&api_key=(API key goes here)`

#### Postman GET response to get back Project tracker data (see endpoint above)
![project tracker data](Assets/postman-request.png)

## 8. Set the Content-Type header in Postman to make a POST request

POST endpoint `https://api.airtable.com/v0/(Project tracker key goes here)/Design%20projects?typecast=true&api_key=(API key goes here)`   
Headers: "application/json" "Content-Type"

The Content-Type needs to be `application/json` 

![postman headers](Assets/postman-headers.png)

This is a sample JSON HTTP body (This would be your Swift model that you convert to Data using JSONEncoder to Post to the Project tracker)   
```json 
{
	"records" : [
		{
			"fields": {
				"Name": "Saint Lucia",
				"About": "Tropical Island Paradise with a drive-in volcano. Known as Helen of the West.", 
				"Project images": [
					{
						"url": "http://www.premiumcaribbean.nl/wp-content/uploads/2017/08/Piton-Soufriere-1024x659.jpg"
					}
				]
			}
		}
	]
}
```

## 9. Making a POST request in Postman. 

When making a POST request in Postman add the data to be sent in the HTTP body section of Postman

#### In the following POST it fails as the field name `About` does not exist as a column in the Project tracker 
![failed post](Assets/post-failed-unknown-field.png)


## 10. Select the `+` button in the Project tracker on Airtable to create a new field 

![select add to create a new field](Assets/select-add-button-for-new-field.png)

## 11. Create new field in the Project tracker 

![create new field](Assets/create-new-field.png)

## 12. POST requests now succeeds as all fields exist on the Project tracker workspace on Airtable

![post successful](Assets/post-success-field-exist.png)


