---
toc: true
comments: true
layout: post
title: Data Structures Writeup
courses: { compsci: {week: 31} }
type: hacks
---

# Data Structures Writeup

## Collections
- From VSCode using SQLite3 Editor, show your unique collection/table in database, display rows and columns in the table of the SQLite database.
![]({{ site.baseurl }}/images/ds1.png "Data Table")
This data table shows our data for the probability calculator of getting a 90%+. The data consists of the subject, whether the individual's attention was focused/divided, and how many solutions they found (0-4). When a user inputs specific values that align with the ones in the table, their probability of getting a 90%+ is calculated and returned.

- From VSCode model, show your unique code that was created to initialize table and create test data.
![]({{ site.baseurl }}/images/ds2.png "Data Code")
This Python script implements a machine learning model within a Flask environment to predict scores based on attention-related data. It begins by importing necessary libraries and sets up a Flask Blueprint for API organization, although the 'flask_restful' module imported remains unused. The core of the script revolves around the 'AttentionModel' class, which encapsulates model initialization, training, and prediction functionalities. The class employs a singleton pattern to ensure efficient memory usage and training by maintaining a single instance throughout the application's lifecycle. The model is trained using a linear regression model and a decision tree regressor to assess feature importance. Testing functions are provided to initialize the model and evaluate its performance on theoretical attention cases, showcasing both score prediction and feature weight extraction. This structured approach demonstrates key machine learning concepts, including data preprocessing, model training, prediction, and model evaluation.

## Lists and Dictionaries
- In VSCode using Debugger, show a list as extracted from database as Python objects.
![]({{ site.baseurl }}/images/ds3.png "List")

- In VSCode use Debugger and list, show two distinct example examples of dictionaries, show Keys/Values using debugger.
![]({{ site.baseurl }}/images/ds4.png "Dictionaries")

## APIs and JSON
- In VSCode, show Python API code definition for request and response using GET, POST, UPDATE methods. Discuss algorithmic condition used to direct request to appropriate Python method based on request method.
![]({{ site.baseurl }}/images/ds5.png "Python API Code")
This Flask API code defines a route for predicting scores based on attention-related data. It utilizes the Flask framework along with the Flask-RESTful extension to handle HTTP requests and responses. The 'AttentionAPI' class defines a method for handling POST requests, where attention data is sent to the server for prediction using the 'AttentionModel'. The response is then returned as JSON.

- In VSCode, show algorithmic conditions used to validate data on a POST condition.
![]({{ site.baseurl }}/images/ds6.png "POST")

- In Postman, show URL request and Body requirements for GET, POST, and UPDATE methods.
![]({{ site.baseurl }}/images/ds7.png "URL request, body requirements")

- In Postman, show the JSON response data for 200 success conditions on GET, POST, and UPDATE methods.
![]({{ site.baseurl }}/images/ds8.png "JSON response data")

- In Postman, show the JSON response for error for 400 when missing body on a POST request.
![]({{ site.baseurl }}/images/ds9.png "400 error")

- In Postman, show the JSON response for error for 404 when providing an unknown user ID to a UPDATE request.
![]({{ site.baseurl }}/images/ds10.png "404 error")

## Frontend
- In Chrome inspect, show response of JSON objects from fetch of GET, POST, and UPDATE methods.
![]({{ site.baseurl }}/images/ds11.png "JSON response")

- In the Chrome browser, show a demo (GET) of obtaining an Array of JSON objects that are formatted into the browsers screen.
![]({{ site.baseurl }}/images/ds12.png "Demo")

- In JavaScript code, describe fetch and method that obtained the Array of JSON objects.
![]({{ site.baseurl }}/images/ds13.png "JavaScript Code")
The fetch function is utilized to send a POST request to the URL /api/attention/predict, along with data in JSON format containing values retrieved from input fields on the webpage. This request is configured with the appropriate headers to indicate that the content is JSON. Upon receiving a response from the server, the code parses it as JSON and then displays a calculated probability in an alert dialog box. Error handling is implemented to catch any potential errors that may occur during the process, logging them to the console for debugging purposes. Overall, this code snippet demonstrates how to use the fetch function to interact with an API endpoint asynchronously and handle the response accordingly in a web application.

- In JavaScript code, show code that performs iteration and formatting of data into HTML.
![]({{ site.baseurl }}/images/ds14.png "Iteration, Formatting")

- In the Chrome browser, show a demo (POST or UPDATE) gathering and sending input and receiving a response that show update. Repeat this demo showing both success and failure.
![]({{ site.baseurl }}/images/ds15.png "Demo")

- In JavaScript code, show and describe code that handles success. Describe how code shows success to the user in the Chrome Browser screen.
![]({{ site.baseurl }}/images/ds16.png "Success")
The JavaScript code demonstrates how to handle a successful fetch operation and display fetched data on the Chrome Browser screen. Upon calling the 'fetchData' function, a request is sent to a designated server endpoint. The response is checked for success by examining the status code, and if successful, the response body is parsed as JSON. The parsed data is then logged to the console and presented to the user by dynamically generating a list element to encapsulate the data. Each item in the data array generates a list item element with details from the item, appended to the list element, and subsequently added to the HTML document. Error handling is also implemented, logging errors to the console and providing an error message to the user. Overall, when executed in the Chrome Browser, the fetched data is displayed as a list, offering users the requested information in an organized manner.

- In JavaScript code, show and describe code that handles failure. Describe how the code shows failure to the user in the Chrome Browser screen.
![]({{ site.baseurl }}/images/ds17.png "Failure")
The JavaScript code showcases how to handle fetch operation failures and communicate them to users on the Chrome Browser screen. When 'fetchData' is called, it requests data from a server endpoint. Inside the fetch promise chain, the response status is checked for success; if it's unsuccessful, an error is thrown. The subsequent .catch() block captures any fetch errors, logging them to the console for debugging. Additionally, it dynamically generates a new paragraph element to display the error message 'Failed to fetch data. Please try again later.', appending it to the HTML document's body. Thus, when a fetch operation fails, the error message appears on the Chrome Browser screen, informing users of the encountered issue and suggesting they try again later.