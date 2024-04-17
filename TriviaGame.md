## Trivia Game

**Project description:** A simple trivia application that awards the user points for every correct answer. 

<img src="images/TriviaGame.png?raw=true"/>

### Code Structure

The first step is to instantiate global variables for questions, answers and the score tally. The questions and their correct answers are stored in a 2D array under a AskQuestions() method:

```C#
        public void askQuestions()
        {
            
            // question 1
            // 2D array with questions and answers
            string[,] QA = new string[3, 2] {
            {"1) 0.9 is an integer. True or False?", "False"},
            {"2) Is 'WON'T' a Boolean term?", "No" },
            {"3) Is it possible to add new items to arrays?", "No" }};

            //question 1
            string quesOne = QA[0, 0];
            WriteLine($"\n{quesOne}");
            string playerInput = ReadLine();
            string playerAnsOne = playerInput;
        
```
I use a number of conditional statements to catch different variations of the correct answers:

```C#
            //conditional statements to catch different versions of the correct answer
            //adds 1 to score for every correct answer
            if (playerAnsOne == QA[0, 1])
            {
                WriteLine("Correct! The answer is: False.");
                Score += 1;
                WriteLine($"Your score is: {Score}");

            }
            else if (playerAnsOne == "false")
            {
                WriteLine("Correct! The answer is: False.");
                Score +=1 ;
                WriteLine($"Your score is: {Score}");
            }
            else if (playerAnsOne == "F")
            {
                WriteLine("Correct! The answer is: False.");
                Score +=1 ;
                WriteLine($"Your score is: {Score}");
            }
            else if (playerAnsOne == "True")
            {
                WriteLine("Wrong! The correct answer is: False");
                WriteLine($"Your score is: {Score}");
            }
            else if (playerAnsOne == "true")
            {
                WriteLine("Wrong! The correct answer is: False");
                WriteLine($"Your score is: {Score}");
            }
            else
            {
                WriteLine("Wrong! The correct answer is: False");
                WriteLine($"Your score is: {Score}");
            }
```

For more details see [GitHub Repository](https://github.com/rtunjya/Wk3_HW_TriviaGame.git).
