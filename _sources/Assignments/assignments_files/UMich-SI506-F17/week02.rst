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

Activities: Week 2
==================

You have the following graded activities:

* **Before class Monday:**

  * Read :ref:`Building a Program <build_program_chap>`
  * Read :ref:`Iteration<iteration_chap>`.
  
  * And try all of the exercises in the sections!

* **Before class Wednesday:**

  * Read :ref:`Conditionals <conditionals_chap>`
  * Read :ref:`File Input/Output <files_chap>`


* By **Sunday at 11:59PM**, save answers to the exercises in **Problem Set 2**:

  * Complete each of the problem set problems.
  * Submit your Demonstrate Your Understanding assignment.

.. _problem_set_2:

Problem Set
-----------

**Instructions:** Write the code you want to save in the provided boxes, and click **save & run** for each one. The last code you have saved for each one by the deadline is what will be graded.

.. datafile::  about_programming.txt
   :hide:

   Computer programming (often shortened to programming) is a process that leads from an
   original formulation of a computing problem to executable programs. It involves
   activities such as analysis, understanding, and generically solving such problems
   resulting in an algorithm, verification of requirements of the algorithm including its
   correctness and its resource consumption, implementation (or coding) of the algorithm in
   a target programming language, testing, debugging, and maintaining the source code,
   implementation of the build system and management of derived artefacts such as machine
   code of computer programs. The algorithm is often only represented in human-parseable
   form and reasoned about using logic. Source code is written in one or more programming
   languages (such as C++, C#, Java, Python, Smalltalk, JavaScript, etc.). The purpose of
   programming is to find a sequence of instructions that will automate performing a
   specific task or solve a given problem. The process of programming thus often requires
   expertise in many different subjects, including knowledge of the application domain,
   specialized algorithms and formal logic.
   Within software engineering, programming (the implementation) is regarded as one phase in a software development process. There is an on-going debate on the extent to which
   the writing of programs is an art form, a craft, or an engineering discipline. In
   general, good programming is considered to be the measured application of all three,
   with the goal of producing an efficient and evolvable software solution (the criteria
   for "efficient" and "evolvable" vary considerably). The discipline differs from many
   other technical professions in that programmers, in general, do not need to be licensed
   or pass any standardized (or governmentally regulated) certification tests in order to
   call themselves "programmers" or even "software engineers." Because the discipline
   covers many areas, which may or may not include critical applications, it is debatable
   whether licensing is required for the profession as a whole. In most cases, the
   discipline is self-governed by the entities which require the programming, and sometimes
   very strict environments are defined (e.g. United States Air Force use of AdaCore and
   security clearance). However, representing oneself as a "professional software engineer"
   without a license from an accredited institution is illegal in many parts of the world.

.. activecode:: ps_1_04
    :language: python
    :autograde: unittest

    **1.** Write code that uses iteration to print out each element of the list ``several_things``. Then, write code to print out the TYPE of each element of the list called ``several_things``.
    ~~~~
    several_things = ["hello", 2, 4, 6.0, 7.5, 234352354, "the end", "", 99]

    =====

    from unittest.gui import TestCaseGui

    class myTests(TestCaseGui):

      def test_output(self):
          self.assertIn('for', self.getEditorText(), "Testing your code (Don't worry about actual and expected values).")
          self.assertIn("<class 'str'>\n<class 'int'>\n<class 'int'>\n<class 'float'>\n<class 'float'>\n<class 'int'>\n<class 'str'>\n<class 'str'>\n<class 'int'>", self.getOutput(), "Testing output (Don't worry about actual and expected values).")

    myTests().main()

.. activecode:: ps_1_06
       :language: python
       :autograde: unittest

       **2.** Write code that uses iteration to print out each element of the list stored in ``excited_words``, BUT print out each element **without** its ending punctuation. You should see:

       ::

           hello
           goodbye
           wonderful
           I love Python

       (Hint: remember string slicing?)
       ~~~~
       excited_words = ["hello!", "goodbye!", "wonderful!", "I love Python?"]

       # Write your code here.
       =====
       from unittest.gui import TestCaseGui

       class myTests(TestCaseGui):

           def test_output(self):
               self.assertIn('for', self.getEditorText(), "Testing your code (Don't worry about actual and expected values).")
               self.assertIn("hello\ngoodbye\nwonderful\nI love Python", self.getOutput(), "Testing output (Don't worry about actual and expected values).")

       myTests().main()


.. activecode:: ps_2_01
    :language: python
    :autograde: unittest
  
    **3.** Write code to count the number of characters in ``original_str`` using the accumulation pattern and assign the answer to a variable ``num_chars_sent``. Do NOT use the ``len`` function to solve the problem (if you use it while you are working on this problem, comment it out afterward!)
    ~~~~
    original_str = "The quick brown rhino jumped over the extremely lazy fox."
     
     
    =====

    from unittest.gui import TestCaseGui

    class myTests(TestCaseGui):

        def testOne(self):
           self.assertEqual(num_chars_sent, len(original_str), "Testing whether num_chars_sent has the correct value")
           self.assertNotIn('len', self.getEditorText(), "Testing that you are not including the len function in your code. (Don't worry about Actual and Expected Values.)")

    myTests().main()

.. activecode:: ps_2_02
   :language: python
   :available_files: about_programming.txt
   :autograde: unittest

   **4.** Write code to open the file ``about_programming.txt`` which has been provided for you in this problem set, and assign the **number of lines** in the file to the variable ``file_lines_num``.
   ~~~~
   # Write your code here.

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

    def testOne(self):
       self.assertIn('open', self.getEditorText(), "Testing your code (Don't worry about actual and expected values).")
       self.assertEqual(file_lines_num,len(open("about_programming.txt","r").readlines()), "Testing to see that file_lines_num has been set to the number of lines in the file.")

   myTests().main()

.. activecode:: ps_2_03
   :language: python
   :autograde: unittest

   **5.** The program below doesn't always work as intended. Try uncommenting different lines setting the initial value of x. Tests will run at the end of your code, and you will get diagnostic error messages. 

   Fix the code so that it passes the test for each different value of x. So when the first line is uncommented, and when the second line, third line, and fourth line are each uncommented, you should always pass the test.

   (HINT: you don't have to make a big change.)
   ~~~~ 
   #x = 25
   #x = 15
   #x = 5
   #x = -10

   if x > 20:
     y = "yes"
   if x > 10:
     y = "no"
   if x < 0:
     y = "maybe"
   else:
     y = "unknown"

   print("y is " + str(y))

   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

     def testOne(self):
         print("No tests for the comment, of course -- we can only test stored values!\n")
         if x == 25:
             self.assertEqual(y, "yes", "test when x is 25: y should be 'yes'")
         elif x == 15:
             self.assertEqual(y, 'no', "test when x is 15: y should be 'no'")
         elif x == 5:
             self.assertEqual(y, 'unknown', "test when x is 5: y should be 'unknown'")
         elif x == -10:
             self.assertEqual(y, 'maybe', "test when x is -10: y should be 'maybe'")
         else:
             print("No tests when value of x is %s" % (x))

   myTests().main()

.. activecode:: ps_2_04
   :language: python
   :autograde: unittest

   **6.** How many characters are in each element of list ``lp``? Write code to print the length (number of characters) of each element of the list, on a separate line. (Do not write 8+ lines of code to do this. Use a for loop.)

   The output you get should be:

   :: 

     5
     13
     11
     12
     3
     12
     11
     6 

   Then, write code to print out each element of list ``lp`` *only if* the length of the element is an even number. Use iteration (a for loop).
   ~~~~
   lp = ["hello","arachnophobia","lamplighter","inspirations","ice","amalgamation","programming","Python"]
   ====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

     def test_output(self):
         self.assertIn('for', self.getEditorText(), "Testing your code (Don't worry about actual and expected values).")
     def test_outputA(self):
         self.assertIn("5\n13\n11\n12\n3\n12\n11\n6", self.getOutput(), "Testing output (Don't worry about actual and expected values).")
     def test_outputB(self):
         self.assertIn("inspirations\namalgamation\nPython", self.getOutput(), "Testing output (Don't worry about actual and expected values).")

   myTests().main()

.. activecode:: ps_2_05
   :language: python
   :autograde: unittest

   **7.** Write code to count the number of strings in list ``items`` that have the character ``w`` in it. Assign that number to the variable ``acc_num``. 

   HINT 1: Use the accumulation pattern! 

   HINT 2: the ``in`` operator checks whether a substring is present in a string.
   ~~~~
   items = ["whirring", "calendar", "wry", "glass", "", "llama","tumultuous","owing"]
   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

     def testOne(self):
         self.assertIn(' in ', self.getEditorText(), "Testing your code (Don't worry about actual and expected values).")
         self.assertEqual(acc_num, 3, "Testing that acc_num has been set to the number of strings that have 'w' in them.")

   myTests().main()

.. activecode:: ps_2_06
   :language: python
   :autograde: unittest

   **8.** Below is a dictionary ``diction`` with two key-value pairs inside it. The string ``"python"`` is one of its keys. Using dictionary mechanics, print out the value of the key ``"python"``.
   ~~~~
   diction = {"python":"you are awesome","autumn":100}

   # Write your code here.

   ====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

     def testOne(self):
         self.assertIn('you are awesome', self.getOutput(), "Testing your code (Don't worry about actual and expected values).")

   myTests().main()

.. activecode:: ps_2_07
   :language: python
   :autograde: unittest

   **9.** Here's another dictionary, ``nd``. 
   **PART 1**
   Write code to print out each key-value pair in it, one key and its value on each line. Your output should look somewhat like this (remember, the order may be different!):

   ::

     autumn spring
     4 seasons
     23 345
     well spring

   **PART 2**
   Then, write code to increase the value of key ``"23"`` by 5. 

   **PART 3**
   Finally, write code to print the value of the key ``"well"``. Your code should work no matter what the value of the key "well" is.

   **HINTS:** 
   - Printing things with a comma, e.g. ``print("hello", "everyone")`` will print out those things on the same line with  a space in between them: ``hello everyone``.
   - Your code should work no matter what the values corresponding to the keys are!
   ~~~~
   nd = {"autumn":"spring", "well":"spring", "4":"seasons","23":345}
   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

    def testOne(self):
       self.assertEqual(nd["23"], 350, "Testing that the value associated with the key '23' is 350")
       self.assertIn("autumn spring", self.getOutput(), "Testing output (Don't worry about actual and expected values).") 
       self.assertIn("well spring", self.getOutput(), "Testing output (Don't worry about actual and expected values).")
       self.assertIn("4 seasons", self.getOutput(), "Testing output (Don't worry about actual and expected values).")
       self.assertIn("23 345", self.getOutput(), "Testing output (Don't worry about actual and expected values).")

   myTests().main()

