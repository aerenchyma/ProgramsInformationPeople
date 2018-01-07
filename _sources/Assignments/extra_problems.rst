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
