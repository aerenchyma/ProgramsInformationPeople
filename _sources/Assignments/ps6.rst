:orphan:

..  Copyright (C) Jackie Cohen, Paul Resnick.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Activities through 3/5 (through Spring Break)
=============================================

* **Before class Monday 2/20:**

  * Read :ref:`Python modules <modules_chap>`
  * Make sure to read :ref:`pip module installer <pip_chap>` (and install the ``pip`` module)
  * Read :ref:`Fetching data <requests_chap>`
  * Read :ref:`REST APIs<rest_apis_chap>`
  * Check out `this iTunes Search API documentation<https://affiliate.itunes.apple.com/resources/documentation/itunes-store-web-service-search-api/>`_ and consider how to use it to make an API request. You don't have to understand it, but you *should* have taken a good look at it.

.. usageassignment::
  :subchapters: PythonModules/intro-ModulesandGettingHelp, PythonModules/Therandommodule, Installation/pip, Requests/intro, Requests/fetching_a_page, Requests/how_the_Internet_works, Requests/urls, Requests/http, Requests/requests_details, RESTAPIs/intro, RESTAPIs/RequestURLs, RESTAPIs/DebugURLs, RESTAPIs/jsonlib, RESTAPIs/unicode, RESTAPIs/requestsCookbook
  :assignment_name: Lecture Prep 11
  :deadline: 2017-02-20 17:30
  :pct_required: 75
  :points: 50

* **Before Wednesday's class, 2/22:**

  * Read :ref:`Try/Except <exceptions_chap>`
  * Read :ref:`String Formatting<formatting_chap>`
  * You may find it helpful to read this `External Tutorial on Reading CSV Files <https://thenewcircle.com/s/post/1572/python_for_beginners_reading_and_manipulating_csv_files>`_
  * Read :ref:`Writing files<write_text_file_chap>` (also note :ref:`Writing CSV files<csv_chap>`)
  * Read :ref:`Using REST APIs<using_RESTAPIs_chap>`
  * Read :ref:`How to Fix Common Problems using your native machine's Python<gotchas_chap>`, which may also be helpful as we move forward.

.. usageassignment::
  :subchapters: Exceptions/intro-exceptions, Exceptions/using-exceptions, StringFormatting/intro-PrintinginPython2.7, StringFormatting/Interpolation, StringFormatting/CSV, Files/WritingTextFiles, UsingRESTAPIs/cachingResponses, UsingRESTAPIs/flickr,
    NativeInterpreterGotchas/FixCommonProblems
  :assignment_name: Prep 13
  :deadline: 2017-02-26 17:30
  :pct_required: 75
  :points: 50

* **Before Sunday 3/5 at 11:59 PM:**

  * Complete all of :ref:`Problem Set 6 <problem_set_6>` and the Demonstrate Your Understanding assignment for this week.

.. note::

  Your Problem Set 6 is due after spring break. However, we *strongly* suggest you try to finish it beforehand, by this Sunday 2/26! We will not be holding office hours over spring break.

  You may also want to take a look at Problem Set 7 over spring break, since you'll need to read to prepare for the Monday afterward.

.. _problem_set_6:

Problem Set
-----------

Go `HERE to see the Problem Set 6 assignment <https://umich.instructure.com/courses/150918/assignments/231794>`_, where you can find where to edit and submit files for this assignment.

You'll see very abbreviated instructions for each step in the file you download. Here on this page, you'll see extended instructions for each step to complete the problem set.

Note especially for this problem set, since you're getting real live data, we cannot test everything. You'll have to both look at our tests and instructions AND examine your output to ensure that you have reasonable results. (We will look at your results and output when we grade the problem set. As always, we do not grade problem sets that do not run. Make sure you have no syntax errors!)

----

The FAA (Federal Aviation Administration) has put out a REST API for accessing current information about US airports. You'll be using it in the following exercises.

.. note::

    Almost all of the following exercises build on one another. You can use code you wrote in earlier exercises in later ones. If you keep this in mind, this problem set may be even easier for you.

.. external:: ps_6_1

    1. Point your web browser to the following URL: ``http://services.faa.gov/airport/status/DTW?format=json``

    The text that is shown in your browser is a JSON-formatted dictionary. It can easily be converted into a python dictionary and processed in a manner similar to what we have done with the Facebook feed previously. The exercise below guides you through the process of writing python code that uses this RESTful API to extract information about some airports. Pointing your browser to this link is not graded. But you should do it, because it'll provide you with understanding for the remainder of the problem set.

.. external:: ps_6_2

    **PROBLEM 1: Encoding query parameters in a URL**

    Manually create the dictionary you will need to pass to the params argument when you make a request. The key in the dictionary should be ``'format'``, and its value should be ``'json'``, since this is the only parameter required by the FAA REST API. You could discover this via reading their documentation, but in this case, we're just telling you so. 

    Save the dictionary you create in a variable called url_parameters. You should do this in 3 or fewer lines of code (it can also be done in 1 line!).

.. external:: ps_6_3
    
    **PROBLEM 2: Making a request and saving a response object**

    Next, write the whole assignment statement to do the following:
    - make a request to the base url for the FAA api
    - concatenate the airport code string ``"DTW"`` to the base url, 
    - and pass that as well as the ``url_parameters`` dictionary you already created to the ``requests.get`` method. 

    We've provided a bit of code in the file for you to use as you do this:

    .. sourcecode:: python

        baseurl = 'http://services.faa.gov/airport/status/'
        airport = 'DTW'

    Save the response that will be returned when the ``request.get`` method is called properly to a variable called ``airport_response``. (We're doing this small step by small step.) So, after this code is executed, ``airport_response`` should contain a *response object* from the FAA API.

.. external:: ps_6_4

    **PROBLEM 3: Grabbing data off the web**

    Put the request you made above in a proper try/except clause. If it doesn't work, your code should print out ``That didn't work``. 

    If the request is successful, your code should use the ``.json()`` method on the response you get back to turn the data into one big Python dictionary. Save the Python dictionary in the variable ``airport_data``.

    If you're wondering what you got back, you can use the ``pretty`` function we provided for you in the code file like so: ``print pretty(airport_data)``. This will show you an easier-to-read version of the data you got. 

    Note that you can't do anything with the result of an invocation of the ``pretty`` function, it is just for you to look at data and read it easily. Print is for people, and so is ``pretty`` -- the result of that is mostly useless to your program.

.. external:: ps_6_5

    **PROBLEM 4: Extracting relevant information from a dictionary**

    Now you have a JSON-formatted Python dictionary with a bunch of data from the FAA about the airport with code **DTW**.  

    Remember how you had to concatenate the "DTW" string to the base url for the API, and then add the parameters, to make a request to this API!

    Now, going back to the skills you learned in the Nested Data chapter:

    From the airport data dictionary, extract the airport code (e.g. ``DTW``), the ``reason`` field from within the ``status``, the current temperature, and the last time the data was updated.

    Save these pieces of info in variables called, respectively: ``airport_code``, ``status_reason``, ``current_temp``, ``recent_update``.

    To see what you saved in these variables, you may want to run code like:

    .. sourcecode:: python

        print airport_code
        print status_reason
        print current_temp
        print recent_update


.. external:: ps_6_6

    **PROBLEM 5: Generalizing your code**

    At this point, you'll consider the code you've written so far in your file, and make it generalizable. Which means... FUNCTIONS.

    Define a function called ``get_airport()`` that accepts a three-letter airport code string as input, and returns a Python dictionary (like the one you saved in ``airport_data`` above) with data about that airport. 

    This function should work no matter where it is called, with just the input of an airport code like "DTW" or "PDX"! It should *not* depend upon global variables. (So, if you input ``"DTW"`` into your ``get_airport`` function, you should get a different result returned than if you invoke the function with the input ``"LAX"``, and so on.

    You can assume that the requests module is available in your file, though (you do not have to import it again in your function definition of ``get_airport``).

.. external:: ps_6_7

    **PROBLEM 6: More code generalization**

    Now, write another function called ``extract_airport_data()`` that accepts an airport code string as input, like ``"LAX"``, and returns a tuple: of the airport name, status reason, current temp, and recent update. This function should call the ``get_airport()`` function.

.. external:: ps_6_8

    **PROBLEM 7: Create examples of using your newly defined functions**

    Now, iterate over the ``fav_airports`` list we've provided in your code file and print out the abbreviated info for each one, by calling ``extract_airport_data()``.

    After that code is executed, you should see 4 different tuples of airport data, each on a separate line. 

.. external:: ps_6_9

    **PROBLEM 8: Error handling and exceptions**

    We have provided an invocation of ``extract_airport_data`` with a bogus airport code in the code file, like so:

    ``print extract_airport_data("XYZ")``

    If you run it as is, it should throw an exception.

    Wrap the call to ``extract_airport_data`` in a try/except block, so that you should see: ``Sorry, that didn't work.`` printed out when you run your code.

.. external:: ps_6_10

    **PROBLEM 9: Dealing with real live data**

    We've provided a list of airport codes in the variable ``possible_airports``, in the problem set code file. But not all of them are valid airports! Write code that iterates over this list and prints out a tuple of the airport data for each one. *But*, if it's not a valid airport code, your code should print ``Failed for airport <whatever the code is that didn't work>``, e.g. ``Failed for airport JAC``. Use a try/except block to do this.

.. external:: ps_6_11

    **Using real live data to write a CSV file**

    Finally, instead of printing out the results of code like you wrote above, you'll write the data to a CSV file. Iterate over the same list ``possible_airports`` again, but this time, write code to write to a CSV file called ``airport_temps.csv`` with 4 columns: ``airport_code``, ``status_reason``, ``current_temp``, ``recent_update``. 

    Your resulting CSV file should have at least 5 lines: 4 lines for real airport data, and 1 line for the column headers. The content of each cell should have well-formatted data: no extra parentheses, just the specific value that corresponds to that header!

    In a case where you encounter an invalid airport code, you should *not* write to the CSV file. Instead, you should print to the console: ``Failed for airport <whatever the bad airport code is>``. Use a try/except block to do this.

    **Make sure the CSV file you create is called airport_temps.csv. We will run tests on the CSV files post-submission, and we depend on the name of the file being correct.**

    Open the document in Excel or in Google Drive to make sure that it is properly formatted.

    **You should not upload the CSV file your code creates -- when we run your code, it'll appear!**


.. external:: ps6_dyu

    Complete this week's `Demonstrate Your Understanding <https://umich.instructure.com/courses/150918/assignments/231781>`_ assignment on Canvas.

