:orphan:

..  Copyright (C) Jackie Cohen, Paul Resnick.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".


Activities through 10/7
=======================

* **Before Monday's class, 10/3:**

  * Read :ref:`Unix<unix_chapter>`, and try the exercises in that chapter on your computer
  * Read `this tutorial on Unix pipes <http://www.ee.surrey.ac.uk/Teaching/Unix/unix3.html>`_ (you can ignore the ``who`` command in the tutorial) and `this tutorial on the Unix command grep <http://www.ee.surrey.ac.uk/Teaching/Unix/unix2.html>`_ (you can scroll down to it on that page).
  * **If you use a Windows computer,** read and do the installation in the :ref:`instructions for installing git bash<install_git_bash>` section. 
  * **Everyone** should read :ref:`Installing a text editor<text_editor_installation>` and the subsequent sections on installing and running python (there is a section for mac users and a section for Windows users). Try to do the exercises and installations. You will address any installation problems you have (hopefully none! Fingers crossed) in section this week.

  * The installation chapter explains the software we will help you support in this course. We strongly recommend that you use this.
    
  * You are not being graded on *whether you have read* the installation chapter, but you are expected to have done so if you need to! We will proceed with the assumption after this week that you have a setup that is congruent with this course, so please make sure that is the case.
    
  * If you have already installed Python, check to **make sure you have Python 2.7 installed on your computer.** We will be using that version of Python in this course, and the files we provide you and expect you to use will not always be compatible with both. If you have installed Python 3, you can and should download Python 2.7.12 `here <https://www.python.org/downloads/>`_. (If you do not have access to a personal computer, you should already have contacted the instructional staff, but please do so ASAP!)

.. usageassignment::
  :subchapters: Unix/CommandPrompt, Unix/FoldersAndPaths, Unix/DirectoriesAndCopying, Unix/lessCommand
  :assignment_name: Prep 08
  :deadline: 2016-10-03 21:40
  :pct_required: 80
  :points: 50

* **Before Tuesday 10/4 at 11:59 PM:**

  * Complete :ref:`Reading Response 5<reading_response_5>`.

* **Before Wednesday's class, 10/5:**

  * Read :ref:`Optional and Keyword Parameters<optional_params_chap>`  and try the exercises in the sections listed below.

.. usageassignment::
  :subchapters: OptionalAndKeywordParameters/OptionalParameters, OptionalAndKeywordParameters/KeywordParameters
  :assignment_name: Prep 09
  :deadline: 2016-10-05 21:40
  :pct_required: 80
  :points: 50

* **Before Sunday 10/9 at 11:59 PM:**

  * Complete all of :ref:`Problem Set 4<problem_set_4>`, including the :ref:`Problem Set 4 Unix Exercises<problem_set_4_unix>` and the Demonstrate Your Understanding assignment for this week.

.. note::

  This week's problem set involves some saving code in Activecode windows below, and some work on your own computer + submission of screenshots to Canvas. All of the instructions are below!

.. datafile:: timely_file.txt
   :hide:

   Autumn is interchangeably known as fall in the US and Canada, and is one of the four temperate seasons. Autumn marks the transition from summer into winter.
   Some cultures regard the autumn equinox as mid autumn while others, with a longer temperature lag, treat it as the start of autumn then. 
   In North America, autumn starts with the September equinox, while it ends with the winter solstice. 
   (Wikipedia)


Problem Set
-----------
.. _problem_set_4:

.. activecode:: ps_4_01
   :available_files: timely_file.txt
   :language: python
   :autograde: unittest
   :hidecode:

   **1.** We've given you another data file in this problem. It's called ``timely_file.txt``. Write code to figure out which is the most common word in the file. Save the string that is most common word in the file in the variable ``abc``. 

   ~~~~
   # Write code here!
        
   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

      def testCode(self):
         self.assertNotIn("= 'the'", self.getEditorText(), "Testing code input (Don't worry about actual and expected values)")
         self.assertIn("open",self.getEditorText(),"Testing that you have probably opened the file (Don't worry about actual and expected values)")

      def testOne(self):
         self.assertEqual(abc, 'the', "testing whether abc is set correctly.")

   myTests().main()

In the next few questions, you’ll build components and then a complete program that lets people play Hangman.

Below is an image from the middle of a game...

.. image:: Figures/HangmanSample.JPG

Your first task is just to understand the logic of the program, by matching up elements of the flow chart above with elements of the code below. In later problems, you'll fill in a few details that aren't fully implemented here.  

You may find it helpful to run this program in order to understand it. It will tell you feedback about your last guess, but won't tell you where the correct letters were or how much health you have in the game, and it won't stop if you guess all the letters, so you can't *really* play with this version of the code here. (It can also go on for a very long time, until you exceed the time limit in the code window, unless you cancel it yourself.) Allowing the game to do those things (manage health, show you the word you've guessed so far) comes from code you will write in later problems!

.. activecode:: ps_4_hangman_code
  :hidecode:

  This is the base code for a Hangman game. (If you have never played Hangman, you can go to ``https://en.wikipedia.org/wiki/Hangman_(game)`` for an explanation of what it is.)
  ~~~~
  def blanked(word, guesses):
      return "blanked word"

  def health_prompt(x, y):
      return "health prompt"

  def game_state_prompt(txt ="Nothing", h = 6, m_h = 6, word = "HELLO", guesses = ""):
      res = "\n" + txt + "\n"
      res = res + health_prompt(h, m_h) + "\n"
      if guesses != "":
          res = res + "Guesses so far: " + guesses.upper() + "\n"
      else:
          res = res + "No guesses so far" + "\n"
          res = res + "Word: " + blanked(word, guesses) + "\n"

      return(res)

  def main():
      max_health = 3
      health = max_health
      secret_word = raw_input("What's the word to guess? (Don't let the player see it!)")
      secret_word = secret_word.upper() # everything in all capitals to avoid confusion
      guesses_so_far = ""
      game_over = False

      feedback = "let's get started"

      # Now interactively ask the user to guess
      while not game_over:
          prompt = game_state_prompt(feedback, health, max_health, secret_word, guesses_so_far)
          next_guess = raw_input(prompt)
          next_guess = next_guess.upper()
          feedback = ""
          if len(next_guess) != 1:
              feedback = "I only understand single letter guesses. Please try again."
          elif next_guess in guesses_so_far:
              feedback = "You already guessed that"
          else:
              guesses_so_far = guesses_so_far + next_guess
              if next_guess in secret_word:
                  if blanked(secret_word, guesses_so_far) == secret_word:
                     feedback = "Congratulations"
                     game_over = True
                  else:
                      feedback = "Yes, that letter is in the word"
              else: # next_guess is not in the word secret_word
                  feedback = "Sorry, " + next_guess + " is not in the word."
                  health = health - 1
                  if health <= 0:
                      feedback = " Waah, waah, waah. Game over."
                      game_over= True

      print(feedback)
      print("The word was..." + secret_word)

  import sys #don't worry about this line; you'll understand it next week
  sys.setExecutionLimit(60000)     # let the game take up to a minute, 60 * 1000 milliseconds
  main() # invoke the main() game function

See the flow chart below for a better understanding of what's happening in the code for the Hangman game overall. Your first task is just to understand the logic of the program, by matching up elements of the flow chart above with single numeric lines of the code below (which line of code corresponds to the box?). Answer in comments, below. *Each answer should be no more than 4 numbers that represent lines of code, but each question can be answered with 1 or 2 line numbers!*

In later problems, you'll fill in a few details that aren't fully implemented in the code above.
 
.. image:: Figures/HangmanFlowchart.jpg

.. activecode:: ps_4_02

   # What line(s) of code in the above code window do what's mentioned in the flowchart's Box 1? 

   # What line(s) of code do what's mentioned in Box 2?

   #What line(s) of code do what's mentioned in Box 3?
 
   # What line(s) of code do what's mentioned in Box 4?

   # What line(s) of code do what's mentioned in Box 5?

   # What line(s) of code do what's mentioned in Box 6?

   # What line(s) of code do what's mentioned in Box 7?

   # What line(s) of code do what's mentioned in Box 8?

   # What line(s) of code do what's mentioned in Box 9?

   # What line(s) of code do what's mentioned in Box 10?

   # What line(s) of code do what's mentioned in Box 11?


.. activecode:: ps_4_03
   :language: python
   :autograde: unittest
   :hidecode:

   **3.** The next task you have is to create a correct version of the ``blanked`` function. It should take 2 inputs: a word, and a string of the letters that have been guessed already. 

   It should return a string with the same number of characters as the word, but with the UNrevealed characters replaced by an underscore (a ``_``). 

   **HINT:** Iterate through the letters in the word, accumulating characters as you go. If you try to iterate through the guesses, it's harder.

   ~~~~   
   # Define your function here.


   # Sample calls to this function
   # (Remember, these won't work until you define the function blanked)
   print blanked("hello", "elj")
   #should output _ell_
   print blanked("almost","amsvr")
   # should output a_m_s_ 


   =====

   from unittest.gui import TestCaseGui

   class myTests(TestCaseGui):

      def testOne(self):
         self.assertEqual(blanked('hello', 'elj'), "_ell_", "testing blanking of hello when e,l, and j have been guessed.")
      def testTwo(self):
         self.assertEqual(blanked('hello', ''), '_____', "testing blanking of hello when nothing has been guessed.")
      def testThree(self):
         self.assertEqual(blanked('ground', 'rn'), '_r__n_', "testing blanking of ground when r and n have been guessed.")
      def testFour(self):
         self.assertEqual(blanked('almost', 'vrnalmqpost'), 'almost', "testing blanking of almost when all the letters have been guessed.")

   myTests().main()

.. activecode:: ps_4_04
    :autograde: unittest
    :hidecode:

    **4.** Now you have to create a good version of the ``health_prompt`` function: Define a function called ``health_prompt``. The first parameter should be the current health the player has (an integer), and the second parameter should be the maximum health a player can have (an integer). The function should return a string with ``+`` signs for the current health, and ``-`` signs for the health that has been lost so far.
    ~~~~
    # Define your function here.




    # Sample invocations of the function.

    print health_prompt(3, 7)
    #this statement should produce the output
    #health: +++----

    print health_prompt(0, 4)
    #this statement should produce the output
    #health: ----

    =====

    from unittest.gui import TestCaseGui

    class myTests(TestCaseGui):

      def testOne(self):
         self.assertEqual(health_prompt(3,7), "+++----", "Testing health_prompt(3,7)")
      def testTwo(self):
         self.assertEqual(health_prompt(0,4), "----", "Testing health_prompt(0,4)")
      def testThree(self):
         self.assertEqual(health_prompt(5,5), "+++++", "Testing health_prompt(5,5)")

    myTests().main()


.. external:: problem_set_4_05

   **5.** You have all the pieces of a fully functioning hangman program! Now you can put together a program on your own computer to play Hangman.

   In the below code window is all of the code for the hangman program, *except* for the two functions you just defined in problems 1 and 2. (It does not include the special lines allowing it to run in the textbook, and it does not have those function definitions, so this code will not run as expected! It's just provided here for you to copy.)

   Copy your two function definitions, from the last two problems, into a *Python file* on your computer, just like ``prog1.py`` from last week, except a much more complicated program. Save that file as ``hangman.py``.

   Then copy all the code in the box below into that file, too, underneath the function definitions you just copied in.

   (This will let you play the game with a friend -- after you enter in a word, a bunch of blank lines will print out, and then when they get the computer to play, they won't see the word you typed!)

   Save this Python program, and run it with the command line: ``cd`` to the correct directory where you saved the file, and then type ``python hangman.py``, as you learned last week.

   .. sourcecode:: python
     
      def game_state_prompt(txt ="Nothing", h = 6, m_h = 6, word = "HELLO", guesses = ""):
          res = "\n" + txt + "\n"
          res = res + health_prompt(h, m_h) + "\n"
          if guesses != "":
              res = res + "Guesses so far: " + guesses.upper() + "\n"
          else:
              res = res + "No guesses so far" + "\n"
          res = res + "Word: " + blanked(word, guesses) + "\n"
   
          return(res)

      def main():
          max_health = 3
          health = max_health
          secret_word = raw_input("What's the word to guess? (Don't let the player see it!)")
          secret_word = secret_word.upper() # everything in all capitals to avoid confusion
          guesses_so_far = ""
          game_over = False

          feedback = "let's get started"

          # Now interactively ask the user to guess
          while not game_over:
              prompt = game_state_prompt(feedback, health, max_health, secret_word, guesses_so_far)
              next_guess = raw_input(prompt)
              next_guess = next_guess.upper()
              feedback = ""
              if len(next_guess) != 1:
                  feedback = "I only understand single letter guesses. Please try again."
              elif next_guess in guesses_so_far:
                  feedback = "You already guessed that"
              else:
                  guesses_so_far = guesses_so_far + next_guess
                  if next_guess in secret_word:
                      if blanked(secret_word, guesses_so_far) == secret_word:
                          feedback = "Congratulations"
                          game_over = True
                      else:
                          feedback = "Yes, that letter is in the word"
                  else: # next_guess is not in the word secret_word
                      feedback = "Sorry, " + next_guess + " is not in the word."
                      health = health - 1
                      if health <= 0:
                          feedback = " Waah, waah, waah. Game over."
                          game_over= True

          print(feedback)
          print("The word was..." + secret_word)

      main()


.. external:: ps4_dyu

    Complete this week's `Demonstrate Your Understanding <>`_ assignment on Canvas.
