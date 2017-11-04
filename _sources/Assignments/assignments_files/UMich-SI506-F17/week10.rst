:orphan:

..  Copyright (C) Jackie Cohen.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Activities: Week 10
===================

* **Before class Tuesday:**

  * Read or carefully review the chapter about :ref:`Flickr / complex APIs and caching data<flickr_api_chap>`.
  * Check out the `Flickr Photos Search API documentation <https://www.flickr.com/services/api/flickr.photos.search.html>`_ and the `Flickr Photo API documentation <https://www.flickr.com/services/api/flickr.photos.getInfo.html>`_. Consider:
    * How would you compose an API request that searches for photos tagged "rivers"?
    * How would you compose an API request to get a bunch of information about one particular photo? What information do you need to have about that photo to do so?
  * Both of these links can be found here, `at the description of ALL of the Flickr API endpoints, or services <https://www.flickr.com/services/api/>`_. Glance over this link, click around... what questions do you have? What is most confusing about this? What makes sense? What does the documentation at each of these links mean to you? (Each represents one *endpoint* -- like what you need to know to use one base url to get a certain set of data from Flickr.)


* **Before class Wednesday:**

  *



* **Before Sunday at 11:59 PM:**

  * Complete all of Problem Set 7 and submit it to Canvas.
  * Submit the Demonstrate Your Understanding assignment for this week on Canvas.

.. _problem_set_7:

Problem Set
-----------

.. note::

	Reminder: we do not debug code when grading, and we do not grade code that does not run! Make sure your code runs completely before submitting it, so you see all the test output! You should comment out any code that does not run.

**There are 4 files to download for this problem set:**

In this problem set, you'll build on the skills you practiced in Problem Set 6. **You will:**

* Open JSON-formatted files and load the data in them into Python objects
* Deal with nested dictionaries to extract information
* Set up a caching pattern for your file
* Write a function that gets data from Flickr which depends upon the function's input, and caches new data
* Extracts information from data you get from the Flickr API

Follow the instructions in the file -- make sure to read them carefully, as they provide hints and help for what to do for each problem.

There is also a challenge provided at the end of the problem set file!

To complete the challenge, if you wish to, you'll need to do a little bit more data processing and write one more function that caches data/gets data from a cache.

Check out the `Flickr Photo Info API documentation <https://www.flickr.com/services/api/flickr.photos.getInfo.html>`_ -- you'll need to make requests to this Flickr API endpoint to complete it!

(Hint: if you want each of the tags from each photo,  you'll have to make a request to THIS API endpoint with, say, the id of the photo you want data about...)

We will discuss the challenge in more detail later on in class.
