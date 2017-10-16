:orphan:

..  Copyright (C) Jackie Cohen.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Activities: Week 7 (this is the week that includes the Mon-Tues of Fall Break)
==============================================================================

* **No class Monday because of Fall Break**

* **Remember that your Unix Problems are due immediately after fall break, on 10/18 at 11:59 PM, on Canvas**. You can see the assignment: :ref:`Unix Problems<unix_problems>`

* **Before class Thursday:**
  
  * Read :ref:`Sorting and anonymous functions<sort_chap>`
  * Try all the exercises you can and try to formulate questions about concepts you find confusing/articulate ways of solving exercises in English.
  * Make sure your Python installation is working properly.
  * Read just the :ref:`introduction to Unit Testing<test_cases_chap>`. (We will discuss this in lecture! You do *not* have to read the rest of this chapter beyond the introductory section; it addresses material you have NOT learned yet in this course. We will focus in more depth on that material later in the semester. But this week is the first time you will see the code for Unit Tests, so we will teach you how to understand the output you get from them when you run problem sets on your own computer.)
  * If you have time, read :ref:`Nested Data and Nested Iteration<nested_chap>` and try exercises in the section. We'll be doing a bit of introduction to this topic today, before exploring it more next week.


* **Before Sunday 11:59 PM:**

  * Save answers to Problem Set 5, below.

Your next DYU, **Demonstrate Understanding 6**, is due **October 29** to give you time to get readjusted from the midterm, but you may get started on it at any time! You've already done all of the readings necessary to complete it.

Problem Set
-----------

.. _problem_set_5:

.. activecode:: ps_5_01
  :language: python

  **1.** Write code to sort ``fall_list`` alphabetically and save the result in the variable ``sorted_fall_list``.

  ~~~~
  fall_list = ["leaves","apples","autumn","bicycles","pumpkin","squash","excellent"]

  =====

  from unittest.gui import TestCaseGui

  class myTests(TestCaseGui):

    def testCode(self):
       self.assertEqual(sorted_fall_list,sorted(fall_list), "Testing the value of sorted_fall_list")

  myTests().main()

.. activecode:: ps_5_02
  :language: python

  **2.** Write code to do two things: **(a)** sort the list ``food_amounts`` by the value of each dictionary's key ``"sugar_grams"``, and save the result in a variable ``sorted_by_sugar``. 

  **(b)** Net carbohydrates for each dictionary data structure can be found by subtracting the value associated with the key ``"fiber"`` *from* the value associated with the key ``"carbohydrate"``. Sort this list of dictionaries by the value of each's *net carbohydrates*, **in order from the most to the least**, largest -> smallest, and save the result, the properly sorted list, in a variable called ``sorted_net_carbs``. 

  **HINT:** You'll at least need to pass a function to the ``key`` parameter of the ``sorted`` function to solve **(a)** AND to solve **(b)** -- but for each part, you *could* solve it in a single line of code.

  ~~~~
  food_amounts = [{"sugar_grams":245,"carbohydrate":83,"fiber":67},{"carbohydrate":74,"sugar_grams":52,"fiber":26},{"fiber":47,"carbohydrate":93,"sugar_grams":6}]

  =====

  from unittest.gui import TestCaseGui

  class myTests(TestCaseGui):

    def test_sorted_sugar(self):
       self.assertEqual(sorted_sugar, sorted(food_amounts, key=lambda x: x["sugar_grams"]), "Testing the value of sorted_sugar")

    def test_sorted_net(self):
       self.assertEqual(sorted_net_carbs, sorted(food_amounts, key=lambda x: x["carbohydrate"]-x["fiber"],reverse=True),"Testing the value of sorted_net_carbs")

  myTests().main()


.. activecode:: ps_5_03
  :language: python

  **3.** Use a for loop to print the second element of each tuple in the list ``new_tuple_list``.

  ~~~~
  new_tuple_list = [(1,2),(4, "umbrella"),("chair","hello"),("soda",56.2)]

  =====

  from unittest.gui import TestCaseGui

  class myTests(TestCaseGui):

    def testCode(self):
       self.assertIn("2\numbrella\nhello\n56.2", self.getOutput(), "Testing output of your code. (Don't worry about Differences shown)")

  myTests().main()


.. activecode:: ps_5_04
  :language: python

  **4.** We have provided a nested list in the variable ``nl``. Write code to accumulate a list containing the second (as humans count) element of each sub-list and save it in a variable ``second_elems``.

  ~~~~
  nl = [["nested","data","is"],["really","fun"],[11,["hooray","hooray"],"yay"]]


  =====

  from unittest.gui import TestCaseGui

  class myTests(TestCaseGui):

    def testCode(self):
       self.assertEqual(second_elems,[x[1] for x in nl], "Testing value of second_elems")

  myTests().main()


.. activecode:: ps_5_05
  :language: python

  **5.** Define a function ``convert_nums``. The function should accept an integer as input, representing a number of hours. It should return a tuple of that number converted to minutes (* 60), and then that number converted to seconds (* 3600). For example, if 1 were input into the function, the return value of that invocation should be the tuple ``60, 3600``.

  **Then,** write an invocation to ``convert_nums`` so that, **in one line of code**, you assign the value ``120`` to the variable ``two_hours_mins``, and the value ``7200`` to the variable ``two_hours_seconds``. (**HINT:** 7200 is equal to 3600 * 2)

  ~~~~
  # Write your code here.


  =====

  from unittest.gui import TestCaseGui

  class myTests(TestCaseGui):

    def testFunc1(self):
       self.assertEqual(convert_nums(1),(60,3600), "Testing that convert_nums(1) results in 60,3600")
    def testFunc2(self):
       self.assertEqual(convert_nums(15),(900,54000), "Testing that convert_nums(15) reqults in 900,54000")

  myTests().main()
