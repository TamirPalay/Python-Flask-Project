# coding-project-template
This repo is for the practice project which is to be based on Embedded AI libraries. 

Overview
In this project, we make use of the embedded Watson AI libraries, to create an application that would perform sentiment analysis on a provided text. We then deploy the said application over the web using Flask framework.

NLP sentiment analysis is the practice of using computers to recognize sentiment or emotion expressed in a text. Through NLP, sentiment analysis categorizes words as positive, negative or neutral.

Sentiment analysis is often performed on textual data to help businesses monitor brand and product sentiment in customer feedback, and understanding customer needs. It helps attain the attitude and mood of the wider public which can then help gather insightful information about the context.

For creating the sentiment analysis application, we'll be making use of the Watson Embedded AI Libraries. Since the functions of these libraries are already deployed on the Cloud IDE server, there is no need of importing these libraries to our code. Instead, we need to send a POST request to the relevant model with the required text and the model will send the appropriate response.

A sample code for such an application could be:
import requests
def <function_name>(<input_args>):
    url = '<relevant_url>'
    headers = {<header_dictionary>}
    myobj = {<input_dictionary_to_the_function>}
    response = requests.post(url, json = myobj, headers=header)
    return response.text

This application can now be called using Python shell. To test the application, open a Python shell using python3.11 to open the python shell on the current directory i.e practice_project. Make sure that the current directory is practice_project.
python3.11
In the python shell, import the function sentiment_analyzer.
from sentiment_analysis import sentiment_analyzer



Task 5: Run Unit tests on your application
Since now we have a functional aplication, it is required that we run unit tests on some test cases to check the validity of its outputs.
For running unit tests, we need to create a new file that calls the required application function from the package and tests its for a known text and output pair.
For this, complete the following steps.
Create a new file in practice_project folder, called test_sentiment_analysis.py.
In this file, import the sentiment_analyzer function from the SentimentAnalysis package. Also import the unittest library.
from SentimentAnalysis.sentiment_analysis import sentiment_analyzer
import unittest
Create the unit test class. Let's call it TestSentimentAnalyzer. Define test_sentiment_analyzer as the function to run the unit tests.
Define 3 unit tests in the said function and check for the validity of the following statement - label pairs.
“I love working with Python”: “SENT_POSITIVE”
“I hate working with Pyhton”: “SENT_NEGATIVE”
“I am neutral on Python”: “SENT_NEUTRAL”
class TestSentimentAnalyzer(unittest.TestCase):
def test_sentiment_analyzer(self):
    # Test case for positive sentiment
    result_1 = sentiment_analyzer('I love working with Python')
    self.assertEqual(result_1['label'], 'SENT_POSITIVE')
    
    # Test case for negative sentiment
    result_2 = sentiment_analyzer('I hate working with Python')
    self.assertEqual(result_2['label'], 'SENT_NEGATIVE')
    
    # Test case for neutral sentiment
    result_3 = sentiment_analyzer('I am neutral on Python')
    self.assertEqual(result_3['label'], 'SENT_NEUTRAL')
Copied!
Call the unit tests.
Click here for solution
Add the following line at the end of the file.
1
unittest.main()


Task 6: Deploy as web application using Flask
To deploy the application, exectue the file server.py from the terminal.
python3.11 server.py
The app is now running on localhost:5000. To access the application, go to the Skills Network Toolbox tab and click on Launch Application. Enter the Appplication port as 5000, and click on Your Application.
