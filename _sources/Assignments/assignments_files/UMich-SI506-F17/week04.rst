:orphan:

..  Copyright (C) Jackie Cohen, Paul Resnick.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".


.. highlight:: python
    :linenothreshold: 500


Activities: Week 4
==================

You have the following graded activities:

* **Before Tuesday's class:**

  * Read :ref:`Dictionaries<dictionaries_chap>`
  * Review reading about :ref:`Understanding Code <understand_code_chap>`
  * Try the exercises included within each chapter section.
  * Read :ref:`Indefinite Iteration<while_chap>` and try the exercises in the sections.


* **Before Thursday's class:**
  
  * Read :ref:`Dictionary Accumulation<dictionary_accum_chap>` and try the exercises 
  * Read :ref:`Defining Functions<functions_chap>`, and try the exercises in that chapter


* **Before Sunday at 11:59 PM:**

  * Save answers to each of the exercises in :ref:`Problem Set 3 <problem_set_3>` and submit your **Demonstrate Your Understanding** assignment to Canvas.


Problem Set
-----------

.. _problem_set_3:

.. datafile:: timely_file.txt
   :hide:

   Autumn is interchangeably known as fall in the US and Canada, and is one of the four temperate seasons. Autumn marks the transition from summer into winter.
   Some cultures regard the autumn equinox as mid autumn while others, with a longer temperature lag, treat it as the start of autumn then. 
   In North America, autumn starts with the September equinox, while it ends with the winter solstice. 
   (Wikipedia)


.. activecode:: ps_2_08
   :language: python
   :autograde: unittest

   **1.** Below is an empty dictionary saved in the variable ``nums``, and a list saved in the variable ``num_words``. Use iteration and dictionary mechanics to add each element of ``num_words`` as a key in the dictionary ``nums``. Each key should have the value ``0``. The dictionary should end up looking something like this when you print it out (remember, you can't be sure of the order): ``{"two":0,"three":0,"four":0,"eight":0,"seventeen":0,"not_a_number":0}``
   ~~~~
   nums = {}
   num_words = ["two","three","four","seventeen","eight","not_a_number"]
   # Write your code here.

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

    def testOne(self):
       self.assertEqual(nums["two"], 0, "Testing that the key 'two' has been assigned the value of 0.")
       self.assertEqual(type(nums["seventeen"]), type(3), "Testing that the key 'seventeen' has been assigned a value whose type is an integer.")
       self.assertEqual(sorted(nums), sorted({"two": 0, "three": 0, "four": 0, "eight": 0, "seventeen": 0, "not_a_number": 0}), "Testing that the contents of nums is accurate.")

    def testOneA(self):
       self.assertIn('for', self.getEditorText(), "Testing that there is a for inside your code (Don't worry about actual and expected values).")

   myTests().main()


.. activecode:: ps_3_01
   :language: python

   **2.** Write code **that will keep printing what the user inputs over and over until the user enters the string "quit".**

   ~~~~
   # Write code here

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

      def testCode(self):
         self.assertIn("print", self.getEditorText(), "Testing code. (Don't worry about actual and expected values)")
         self.assertIn("while", self.getEditorText(), "Testing code. (Don't worry about actual and expected values)")
         self.assertIn("raw_input", self.getEditorText(), "Testing code. (Don't worry about actual and expected values)")

   myTests().main()


.. activecode:: ps_3_03
   :language: python
   :autograde: unittest

   **4.** Given the string ``s`` in the code below, write code to figure out what the most common word in the string is and assign that to the variable ``abc``. (Do not hard-code the right answer.) Hint: dictionary mechanics and dictionary accumulation will be useful here.
   ~~~~
   s = "Number of slams in an old screen door depends upon how loud you shut it, the count of slices in a bread depends how thin you cut it, and amount 'o good inside a day depends on how well you live 'em. All depends, all depends, all depends on what's around ya."

   # Write your code here.

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

    def testOne(self):
       self.assertEqual(abc, 'depends', "testing whether abc is set correctly")

    def testOneA(self):
       self.assertIn('for', self.getEditorText(), "Testing your code (Don't worry about actual and expected values).")

   myTests().main()


.. activecode:: ps_3_04
   :language: python

   **5.** Take a look at the code below. The function ``subtract_five`` is supposed to take one integer as input and return that integer minus 5. You'll get an error if you run it as is. Change the function so it works and passes the test!
   ~~~~
   def subtract_five(inp):
       print(inp - 5)
       return None

   y = subtract_five(9) - 6

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

      def testOne(self):
         self.assertEqual(y, -2, "Testing if y is -2")

   myTests().main()


.. activecode:: ps_3_05
   :language: python
   :autograde: unittest

   **6.** Define a function called ``change_amounts`` that takes one integer as input. If the input is larger than 10, it should return the input + 5. If the input is smaller than or equal to 10, it should return the input + 2.
   ~~~~ 
   # We've started you off with the first line...
   def change_amounts(num_here):
       pass # delete this line and put in your own code for the body of the function.

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

      def testOne(self):
         self.assertEqual(change_amounts(9), 11, "Testing if change_amounts(9) equals 11")
         self.assertEqual(change_amounts(12), 17, "Testing if change_amounts(12) equals 17")

   myTests().main()


