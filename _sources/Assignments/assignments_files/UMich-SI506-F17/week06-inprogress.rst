:orphan:

..  Copyright (C) Jackie Cohen.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Activities: Week 5
==================

* **Before class Monday:**

  * Read the :ref:`Unix<unix_chapter>` chapter and try the exercises in that chapter on your computer
  * Also read `this tutorial on Unix pipes <http://www.ee.surrey.ac.uk/Teaching/Unix/unix3.html>`_ (you can ignore the ``who`` command in the tutorial) and `this tutorial on the Unix command grep <http://www.ee.surrey.ac.uk/Teaching/Unix/unix2.html>`_ (you can scroll down to it on that page).
  * Read :ref:`Installing a text editor<text_editor_installation>` section for background, and make sure you have a text editor installed. (You can leave the rest of the installation chapter aside; it may contain some outdated information!) We recommend `Atom <https://atom.io/>`_, which is only available for Mac, or `Sublime Text <https://www.sublimetext.com/>`_, which is available for Windows OR Mac. **Microsoft Word or NotePad will not work for programs! You must install a Text Editor program that works for writing Python code.**
  * Read the `Python installation instructions <https://umich.instructure.com/courses/172984/assignments/329369>`_ on Canvas.  


EDIT: This is the one that really probably has to change. It needs to be half in the textbook and have sorting happen in activecodes.

 
* **Before class Wednesday:**

  * Read just the :ref:`introduction to Unit Testing<test_cases_chap>`. (We will discuss this on Monday in lecture! You do *not* have to read the rest of this chapter beyond the introductory section; it addreses material we have not learned yet in this course. We will focus in more depth on that material later in the semester. But this week is the first time you will see the code for Unit Tests, so we will teach you how to understand the output you get from them when you run problem sets on your own computer.)
  * Read :ref:`Sorting and anonymous functions<sort_chap>`
  * Review the :ref:`Unix<unix_chapter>` chapter, and *make sure* you have addressed any problems you have with native Python installation with an instructor.


* **Before Sunday at 11:59 PM**, compete :ref:`Problem Set 5<problem_set_5>` and submit it to Canvas. You'll also see instructions for the problems in the file you download from Canvas, but since this the transitional problem set, we've put the instructions here as well.

.. note::

  Starting this week, with **problem set 5**, your problem sets will be completed in ``.py`` files that you will download from Canvas and edit to add your answers. You will test them and work on them by running them via the command prompt. 

  Note that the test output will look different now -- you won't have the nice box with colors that you have in the textbook. However, you will still have the same information and more power to see what is being tested.

  **You will submit your final files in Canvas assignments.** However, the instructions for each problem on the assignment will be found in the textbook, as usual. You will need to reference the textbook for the instructions for each problem, and in the files we provide you, we will provide whatever code (if any) that we intend you to start with, beneath comments e.g. ``## [PROBLEM 1]``.

  Your problem set grades, once they are complete, will appear in the textbook progress page, just like your other problem sets.

  **Please make sure that you include the "ps#", e.g. ``ps5`` in your problem set file name when you submit it.** (Even better, don't change the file name at all!) We need that to grade it! Don't make the instructional team sad.



Problem Set 5
-------------

To find the file for your problem set, and to submit your assignment on Canvas, go `HERE <updatelink.com>`_.

.. external:: ps_5_1

    1. Write code to sort the list ``fall_list`` in reverse alphabetical order. Assign the result of the sorted list to the variable ``sorted_fall_list``.

.. external:: ps_5_2

    2. First, write code to sort the list ``food_amounts`` by the key ``sugar_grams``, from lowest to highest. Assign that sorted list to the variable ``sorted_sugar``. 

    Next, write code to sort the list ``food_amounts`` by the value of the key ``carbohydrate`` minus the value of the key ``fiber`` in each one, from lowest difference to highest. Assign this sorted list to a variable ``raw_carb_sort``.

.. external:: ps_5_3

    3. Use the ``curl`` Unix command to download the file ``words.txt``, like so: ``curl http://www.puzzlers.org/pub/wordlists/ospd.txt > words.txt``. Make sure to do so in the same directory where you have saved this ``ps5.py`` file.

    There are 19 3-letter words in the Scrabble dictionary provided in the ``words.txt`` file which contain the letter 'z'. Write code to generate a list of them. That list should be sorted in *reverse* alphabetical order (i.e. ``'zoo'`` should be first and ``'adz'`` should be last). Save that list in a variable ``short_z_words``.

    **NOTE:** to get rid of the blank line character at the end of each line in the file, use the ``.strip()`` string method.

.. external:: ps_5_4

    4. Write code to generate a list of the 10 highest-scoring words from the Scrabble dictionary that contain the letter 'z'. Save it in the variable ``best_z_words``. You may assume there are no bonuses that double or triple letter values or entire words. The dictionary saved in ``letter_values`` contains the Scrabble score information: its keys are letters, and its values are the scores associated with those letters.

    If you have never played Scrabble before, `here is an explanation <https://en.wikipedia.org/wiki/Scrabble>`_ of what it is. (You do not need that information to solve this problem. All you need to know is that each letter is associated with a number of points, and you want to find the ten words that are associated with the largest point totals.)

    **HINT:** In the textbook section on Accumulating Results from a Dictionary, there is code that computes the scrabble score for the entire text of "A Study in Scarlet". You may want to adapt that.

.. external:: ps_5_5

    5. We have provided a nested list in the variable ``nl``. Write code to accumulate a list containing the second (as humans count) element of each sub-list and save it in a variable ``second_elems``.

.. external:: ps_5_6

    6. Define a function ``convert_nums``. The function should accept an integer as input, representing a number of hours. It should return a tuple of that number converted to minutes (* 60), and then that number converted to seconds (* 3600). For example, if ``1`` were input into the function, the return value of that invocation should be the tuple ``60, 3600``.

.. external:: ps_5_7

    7.  We've provided a complex nested dictionary saved in the variable ``fb_data``. This is a lot like real data you'll get from Facebook (but a little bit simpler, and fake data). 

    Here we've also provided some questions to help you. We will not grade, or expect you to write, answers to these questions, but we suggest you think about them and write them in comments to practice understanding this big nested data structure. Test your predictions using print statements in the code file! Questions:

    - What type is the structure saved in the variable ``fb_data``?
    - What about ``fb_data["data"][1]``?
    - What about ``fb_data["data"][0]["from"]``?
    - What about ``fb_data["data"][0]["id"]``?

    Now, write a line of code to assign the value of the first message ("This problem might...") from the big ``fb_data`` data structure to a variable called ``first_message``. (Do not hard-code your answer! That means, write it in terms of fb_data, so that it would work with any content stored in the variable ``fb_data`` that has the same structure as that of the one we gave you.)

    Then write a second line of code to assign the value of the name of the second person who posted ("John Smythe") to a variable called ``second_name``. Do not hard code your answer!






