:orphan:

..  Copyright (C) Jackie Cohen.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. highlight:: python
    :linenothreshold: 500

Extra HW Problems
=================

.. activecode:: ps_extra_01
    :language: python
    :autograde: unittest

    Add one line of code to assign a list containing only the third through fifth elements of ``whoa_list`` (as humans count, so ``[4, 6.0, 7.5]``) to the variable ``some_of_list``. You must use **slicing** and refer to ``whoa_list`` in your code. **HINT:** Remember the rules of slicing and indices of sequences in Python! Also remember that the type of ``some_of_list`` should be a **list** when you are done running your code!
    ~~~~
    whoa_list = ["hello", 2, 4, 6.0, 7.5, 234352354, "the end", "", 99]

    =====

    from unittest.gui import TestCaseGui

    class myTests(TestCaseGui):

      def test_output(self):
          self.assertEqual(some_of_list,[4,6.0,7.5],"Testing that some_of_list has the correct value")
          self.assertEqual(whoa_list,["hello", 2, 4, 6.0, 7.5, 234352354, "the end", "", 99],"Testing that whoa_list has not changed (this test should pass right away!)")

    myTests().main()


.. activecode:: ps_extra_02
    :language: python
    :autograde: unittest

    Write code, using the accumulation pattern, to iterate over ``new_string`` and accumulate a new string in the variable ``exclam_string`` with an exclamation point (``!``) after each of the characters. It should look like this: ``h!i! !e!v!e!r!y!o!n!e!``. You must use the accumulation pattern -- do not hard-code.
    ~~~~
    new_string = "hi everyone"


    =====

    from unittest.gui import TestCaseGui

    class myTests(TestCaseGui):

      def test_output(self):
          self.assertEqual(exclam_string,"h!i! !e!v!e!r!y!o!n!e!","Testing that exclam_string has the correct value")
      def test_output2(self):
          self.assertTrue("!" in exclam_string,"Testing that there is at least one ! in exclam_string")
      def test_output3(self):
          self.assertIn("for",self.getEditorText(),"Testing that there is the word 'for' in your code")

    myTests().main()



.. activecode:: ps_extra_03
    :language: python
    :autograde: unittest

    Define a function called ``build_acronym`` that accepts a string and returns an all-uppercase acronym from the string. For example, if the input were ``probably your term has One newcomer``, the return value should be the string ``PYTHON``. It should not matter how many spaces are between the words -- no spaces should occur in the acronym return value.
    ~~~~
    # Define your function here...

    =====

    from unittest.gui import TestCaseGui
    class myTests(TestCaseGui):

      def test_output(self):
          self.assertEqual(build_acronym("probably your term has one newcomer"),"PYTHON")
      def test_two(self):
          self.assertEqual(build_acronym("probably Your Term Has One newcomer"),"PYTHON")
      def test_three(self):
          self.assertEqual(build_acronym("thank God it's Friday"),"TGIF")
      def test_four(self):
          self.assertEqual(build_acronym("wow"),"W")
      def test_five(self):
          self.assertEqual(build_acronym(""),"")
      def test_six(self):
          self.assertEqual(build_acronym("ANYMORE      ATHENS ARE AHH"),"AAAA")
      def test_seven(self):
          self.assertEqual(build_acronym("probably     your term     has    one    Newcomer"),"PYTHON")


    myTests().main()


.. activecode:: ps_extra_04
    :language: python
    :autograde: unittest

    Define a function ``until_three`` that accepts a list. The function should return a list that is exactly the same as the input list *except* that **if there is an integer 3 in the list**, the returned list should *not* include that *or* anything that occurs in the input list after it.

    For example, if the input list is ``["hello", 3.5, 6.7, "python is great"]``, then the return value should also be ``["hello", 3.5, 6.7, "python is great"]``. However, if the list is ``["hello", 3, 6.7, "python is great"]`` the return value should simply be ``["hello"]``. If the input list is ``[3]``, the return value should be the empty list: ``[]``.

    You may choose any way of achieving this goal as long as the function ``until_three`` you define does what is described and passes all the tests.
    ~~~~
    # Define your function here...


    =====

    from unittest.gui import TestCaseGui
    class myTests(TestCaseGui):

      def test_output(self):
          self.assertEqual(until_three(["hello", 3.5, 6.7, "python is great"]),["hello", 3.5, 6.7, "python is great"])
      def test_two(self):
          self.assertEqual(until_three(["hello", 3, 6.7, "python is great"]),["hello"])
      def test_three(self):
          self.assertEqual(until_three([3]),[])
      def test_four(self):
          self.assertEqual(until_three([4,5,6,7,3]),[4,5,6,7])
      def test_five(self):
          self.assertEqual(until_three([4,56,7,8,3,3,3,6]),[4,56,7,8])

    myTests().main()
