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
This data table shows our data for the probability calculator of getting over a 90%. The data consists of the subject, whether the individual's attention was focused/divided, and how many solutions they found (0-4). When a user inputs specific values that align with the ones in the table, their probability of getting a 90%+ is calculated and returned.

- From VSCode model, show your unique code that was created to initialize table and create test data.
![]({{ site.baseurl }}/images/ds2.png "Data Code")
This Python script implements a machine learning model within a Flask environment to predict scores based on attention-related data. It begins by importing necessary libraries and sets up a Flask Blueprint for API organization, although the 'flask_restful' module imported remains unused. The core of the script revolves around the 'AttentionModel' class, which encapsulates model initialization, training, and prediction functionalities. The class employs a singleton pattern to ensure efficient memory usage and training by maintaining a single instance throughout the application's lifecycle. The model is trained using a linear regression model and a decision tree regressor to assess feature importance. Testing functions are provided to initialize the model and evaluate its performance on theoretical attention cases, showcasing both score prediction and feature weight extraction. This structured approach demonstrates key machine learning concepts, including data preprocessing, model training, prediction, and model evaluation.

## Lists and Dictionaries
- In VSCode using Debugger, show a list as extracted from database as Python objects.
![]({{ site.baseurl }}/images/ds3.png "List")
This list comprises data representing various subjects, each accompanied by details such as their attention type, categorized as either "focused" or "divided," the count of solutions they have found, and their overall score. Each object encapsulates this information, providing insights into the performance and focus level of each subject, along with their respective achievements. This structured dataset offers a comprehensive overview of the subjects' engagement, problem-solving capabilities, and overall performance, facilitating deeper analysis and informed decision-making.

- In VSCode use Debugger and list, show two distinct example examples of dictionaries, show Keys/Values using debugger.
![]({{ site.baseurl }}/images/ds4.png "Dictionaries")
Each dictionary encapsulates key-value pairs representing subject attributes such as subject number, attention type, and the number of solutions. By inspecting these dictionaries using the Debugger, one gains insights into individual subject profiles within the dataset. These dictionaries serve as structured representations of subject information, enabling efficient retrieval and analysis of pertinent data points. With clear delineation of keys and corresponding values, these dictionaries facilitate easy navigation and understanding of subject characteristics, aiding in tasks such as performance evaluation and trend identification.

## APIs and JSON
- In VSCode, show Python API code definition for request and response using GET, POST, UPDATE methods. Discuss algorithmic condition used to direct request to appropriate Python method based on request method.
![]({{ site.baseurl }}/images/ds5.png "Python API Code")
This Flask API code defines a route for predicting scores based on attention-related data. It utilizes the Flask framework along with the Flask-RESTful extension to handle HTTP requests and responses. The 'AttentionAPI' class defines a method for handling POST requests, where attention data is sent to the server for prediction using the 'AttentionModel'. The response is then returned as JSON.

- In VSCode, show algorithmic conditions used to validate data on a POST condition.
![]({{ site.baseurl }}/images/ds6.png "POST")
In this code snippet from VSCode, a Flask API endpoint is defined to handle POST requests related to attention data. The algorithmic conditions for data validation are not explicitly implemented here, but the framework allows for the reception and processing of JSON data sent via POST requests. Upon receiving the data, the code retrieves it using Flask's request.get_json() method, and then utilizes a singleton instance of the AttentionModel to predict certain outcomes based on the received data. While the code doesn't include specific data validation logic within the post() method, it effectively demonstrates the handling of POST requests within a Flask application, ensuring secure transmission of data and providing a structured response in JSON format. This setup aligns with the standard semantics of using POST requests to send data to a server for processing, offering flexibility and security benefits for handling various types of data payloads.

- In Postman, show URL request and Body requirements for GET, POST, and UPDATE methods.
![]({{ site.baseurl }}/images/ds7.png "URL request, body requirements")
In Postman, the URL http://127.0.0.1.8086/api/attentions/predict serves as the endpoint for predicting attention-related data. For GET requests, no body is required, while POST requests entail sending JSON data for processing, with potential updates handled by PUT or PATCH requests.

- In Postman, show the JSON response data for 200 success conditions on GET, POST, and UPDATE methods.
![]({{ site.baseurl }}/images/ds18.png "JSON response data")
In Postman, the JSON response data for successful GET, POST, and UPDATE requests typically includes the requested resource's details or a confirmation message, along with a status code of 200 indicating success. These responses facilitate verification of successful data retrieval, addition, or modification, ensuring smooth interaction with the API.

- In Postman, show the JSON response for error for 400 when missing body on a POST request.
![]({{ site.baseurl }}/images/ds9.png "400 error")
The JSON response for error 400 typically includes an error message indicating the missing or invalid request body, along with a status code of 400 indicating a client-side error. This response prompts users to provide the necessary data payload to fulfill the request properly, ensuring adherence to the API's requirements.

- In Postman, show the JSON response for error for 404 when providing an unknown user ID to a UPDATE request.
![]({{ site.baseurl }}/images/ds8.png "404 error")
The JSON response for error 404 usually includes an error message indicating that the requested resource (user ID) was not found, along with a status code of 404 indicating a client-side error. This response prompts users to verify the correctness of the provided user ID and ensures clear communication of the resource's absence in the server's database.

## Frontend
- In Chrome inspect, show response of JSON objects from fetch of GET, POST, and UPDATE methods.
![]({{ site.baseurl }}/images/ds11.png "JSON response")
When I'm inspecting data for my attention and subjects project, it's essential for ensuring everything is accurate and functional. Using Chrome inspect, I can closely examine the responses from API requests, making sure the right data is being retrieved, updated, or processed as needed. This hands-on approach helps me identify any issues or inconsistencies, allowing me to troubleshoot effectively and refine the functionality of my project.

- In the Chrome browser, show a demo (GET) of obtaining an Array of JSON objects that are formatted into the browsers screen.
![]({{ site.baseurl }}/images/ds12.png "Demo")
In the Chrome browser, I can showcase fetching an array of JSON objects by utilizing the Fetch API or AJAX requests to retrieve data directly from my project's server. This allows me to visualize subject-related data directly on the browser's screen, enhancing my understanding and analysis within the project.

- In JavaScript code, describe fetch and method that obtained the Array of JSON objects.
![]({{ site.baseurl }}/images/ds13.png "JavaScript Code")
The fetch function is utilized to send a POST request to the URL /api/attention/predict, along with data in JSON format containing values retrieved from input fields on the webpage. This request is configured with the appropriate headers to indicate that the content is JSON. Upon receiving a response from the server, the code parses it as JSON and then displays a calculated probability in an alert dialog box. Error handling is implemented to catch any potential errors that may occur during the process, logging them to the console for debugging purposes. Overall, this code snippet demonstrates how to use the fetch function to interact with an API endpoint asynchronously and handle the response accordingly in a web application.

- In JavaScript code, show code that performs iteration and formatting of data into HTML.
![]({{ site.baseurl }}/images/ds14.png "Iteration, Formatting")
In my JavaScript code, I utilize a constant named "data" containing a list of variables representing my project's dataset. Additionally, I employ a dedicated function responsible for iterating through this data and formatting it into HTML, enabling seamless integration of dynamic content into my project's web interface.

- In the Chrome browser, show a demo (POST or UPDATE) gathering and sending input and receiving a response that show update. Repeat this demo showing both success and failure.
![]({{ site.baseurl }}/images/ds15.png "Demo")
In the Chrome browser, I can demonstrate a POST or UPDATE operation by gathering user input and sending it to the server, receiving a response indicating a successful update within my project's attention and subject management system. Repeating this demo showcases both successful updates, ensuring data integrity, and failure scenarios, enabling robust error handling and user feedback mechanisms within the project.

- In JavaScript code, show and describe code that handles success. Describe how code shows success to the user in the Chrome Browser screen.
![]({{ site.baseurl }}/images/ds16.png "Success")
The JavaScript code demonstrates how to handle a successful fetch operation and display fetched data on the Chrome Browser screen. Upon calling the 'fetchData' function, a request is sent to a designated server endpoint. The response is checked for success by examining the status code, and if successful, the response body is parsed as JSON. The parsed data is then logged to the console and presented to the user by dynamically generating a list element to encapsulate the data. Each item in the data array generates a list item element with details from the item, appended to the list element, and subsequently added to the HTML document. Error handling is also implemented, logging errors to the console and providing an error message to the user. Overall, when executed in the Chrome Browser, the fetched data is displayed as a list, offering users the requested information in an organized manner.

- In JavaScript code, show and describe code that handles failure. Describe how the code shows failure to the user in the Chrome Browser screen.
![]({{ site.baseurl }}/images/ds17.png "Failure")
The JavaScript code showcases how to handle fetch operation failures and communicate them to users on the Chrome Browser screen. When 'fetchData' is called, it requests data from a server endpoint. Inside the fetch promise chain, the response status is checked for success; if it's unsuccessful, an error is thrown. The subsequent .catch() block captures any fetch errors, logging them to the console for debugging. Additionally, it dynamically generates a new paragraph element to display the error message 'Failed to fetch data. Please try again later.', appending it to the HTML document's body. Thus, when a fetch operation fails, the error message appears on the Chrome Browser screen, informing users of the encountered issue and suggesting they try again later.