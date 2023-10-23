# Kevin Chen CSE 15L Lab Report 2
## Screenshot 1: 

**Request:** /add-message?s=Hello

<img width="755" alt="Screenshot 2023-10-22 at 9 49 18 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/c3c1d70a-bb9a-4f5d-8c74-45b9c35872f6">

**Description:** In this screenshot, the `public String handleRequest(URI url)` method is being used and that is the method in the Handler class. The relevant argument to this method is the url request as a string, as this determines the action that is done by the web server. The values of relevant fields that are changed include the return message, which gets the string that is entered on the url as input. Also the variable "num", which represents a counter of the number of strings added, initializes to 1 when the first message is entered through the url.

## Screenshot 2: 
**Request:** /add-message?s=How are you

<img width="848" alt="Screenshot 2023-10-22 at 9 50 39 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/4ab89095-5887-43cb-82b3-fb5451d9ed04">

**Description:** In this screenshot, the `public String handleRequest(URI url)` method is also being used and that is the method in the Handler class. The relevant argument is the url request as a string, as this determines the action that is done by the web server. The values of relevant fields that are changed are the return message, which adds the newly entered string("How are you") on the url and has an incremeted number count from the message before. The "num" variable, which represents a counter of the number of messages added, increments by 1, when "How are you" is entered.



Here is my code for StringServer:

<img width="781" alt="Screenshot 2023-10-22 at 10 15 10 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/1f9d5c37-db56-4f30-a6f6-13e9eb926125">


<img width="871" alt="Screenshot 2023-10-22 at 10 15 25 PM" src="https://github.com/kevinkchen1/cse15l-lab-reports/assets/108315438/2d9dab63-bc56-4473-99fd-3cc2cb0627c1">

