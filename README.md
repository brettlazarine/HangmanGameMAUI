# **HangmanGameMAUI**

A quick, fun game led by Hector Perez on his Udemy course: *.NET MAUI course with Visual Studio 2022 creating PROJECTS*

The XAML is contained in a single Grid with 2 rows. The first row is a Vertical Stack Layout where the controls for display are kept. The second row is a Flex Layout with Wrap and SpaceEvenly attributes, which allows the Bindable Layout to create a code-generated on-screen keyboard.

The codebehind is powered by a number of Methods that perform the functionality of the application:
- *PickWord()* selects a random word from the *words* List
- *CalculateWord()* applies the guessed letter to *Spotlight*, and enters the letter if it was correct or _ if the guess was wrong
- *Button_Clicked()* passes the letter of the Button that was clicked to the *HandleGuess()* method, and disables the Button
- *HandleGuess()* checks whether the guess was correct or not
  - If correct, it calls *CalculateWord()* and *CheckIfGameWon()*
  - If wrong, *mistakes* is incremented, *UpdateStatus()* is called, calls *CheckIfGameLost()*, and updates *CurrentImage* to reflect the amount of incorrect guesses so far
- *CheckIfGameLost()* checks if *mistakes* equals *maxWrong* and, if so: updates *Message*, applies *answer* to *Spotlight*, and calls *DisableLetters()*
- *DisableLetters()* and *EnableLetters()* disable/enable the letter Buttons
- *CheckIfGameWon()* verifies that *Spotlight* equals *answer* and, if so: updates *Message* and calls *DisableLetters()*
- *UpdateStatus()* injects *mistakes* and *maxWrong* into a string that displays the user's progress towards failure
- *Reset_Clicked()* resets all values to their base, selects a new word, and then calls *EnableLetters()*
  
