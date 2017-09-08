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


Activities: Week 3
==================

You have the following graded activities:

* **Before Monday's class:**

  * Read :ref:`Dictionaries<dictionaries_chap>`
  * Read about :ref:`Understanding Code <understand_code_chap>`
  * Try the exercises included within each chapter section.

  
  * Read :ref:`Indefinite Iteration<while_chap>` and try the exercises in below listed sections
  * Review the :ref:`Files<files_chap>` chapter.


* **Before Wednesday's class:**
  
  * Read :ref:`Dictionary Accumulation<dictionary_accum_chap>` and try the exercises in below listed sections
  * Read :ref:`Defining Functions<functions_chap>`, and do the exercises in that chapter


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


.. activecode:: ps_3_02
   :language: python

   **3.** Below is a function definition. **DO NOT** change it! 

   We have also provided some invocations of that function. Run those and see what they do.

   Below the comment provided in the code window, write a few calls to this function yourself, with whatever appropriate input you want.

   Finally, write a few sentences in comments in the code window that explain what's happening in this function called list_end_with_string. You should explain what happens if a list like ``l`` gets input into this function AND what happens if a list like ``b`` gets input into it. 

   Don't forget to run it and save!

   ~~~~
   # Function definition
   def list_end_with_string(new_list):
       if type(new_list[-1]) == type("hello"):
           return new_list
       new_list.append("the last element is a string no matter what now!")
       return new_list

   # Some function calls and lines that print out the results
   l = [3,46,6]
   b = [4,"hi",10,"12",12,123,"whoa!"]
   print(list_end_with_string([1,2]))
   print(list_end_with_string(l))
   print(list_end_with_string(b))

   # Now write a couple invocations of this function yourself below this line.


   # Write your comments here.


.. activecode:: ps_3_03
   :language: python
   :autograde: unittest

   **4.** Given the string ``s`` in the code below, write code to figure out what the most common word in the string is and assign that to the variable ``abc``. (Do not hard-code the right answer.) Hint: dictionary mechanics will be useful here.
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


.. activecode:: ps_3_06
   :language: python
   :autograde: unittest

   **7.** Define a function ``is_prefix`` that takes two strings as inputs and returns the boolean value ``True`` if the first string is a prefix of the second string, but returns the boolean value ``False`` otherwise. You can assume the first string will always be shorter than, or the same length as, the second string.

   ~~~~   
   # Define your function here.


   # Here's a couple example function calls, printing the return value
   # to show you what it is.
   print(is_prefix("He","Hello")) # should print True
   print(is_prefix("Hello","He")) # should print False
   print(is_prefix("Hi","Hello")) # should print False
   print(is_prefix("lo","Hello")) # should print False
   print(is_prefix("Hel","Hello")) # should print True
   print(is_prefix("Hello","Hello")) # should print True
   # Remember, these won't work at all until you have defined a function called is_prefix

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

      def testOne(self):
         self.assertEqual(is_prefix("Big", "Bigger"), True, "Testing whether 'Big' is a prefix of 'Bigger'")
      def testTwo(self):
         self.assertEqual(is_prefix("Bigger", "Big"), False, "Testing whether 'Bigger' is a prefix of 'Big'")
      def testThree(self):
         self.assertEqual(is_prefix('ge', 'Bigger'), False, "Testing whether 'ge' is a prefix of 'Bigger'")
      def testFour(self):
         self.assertEqual(is_prefix('Bigge', "Bigger"), True, "Testing whether 'Bigge' is a prefix of 'Bigger'")
      def testFive(self):
         self.assertEqual(is_prefix("Bigger","Bigger"),True,"Testing whether 'Bigger' counts as a prefix of 'Bigger'")
      def testSix(self):
         self.assertEqual(is_prefix("big","Bigger"),False,"Testing whether 'big' is a prefix of 'Bigger'")
      def testSeven(self):
         self.assertEqual(is_prefix("Biggerxyz","Bigger"),False,"Testing whether 'Biggerxyz' is a prefix of 'Bigger'")

   myTests().main()

