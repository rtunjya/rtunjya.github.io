## Jay’s House of Cards Documentation 
### Jay Gujral | October 24, 2024 | PROG 201: Programming II
### Framework Overview 


**Overview:**
 My personal objective for this game was to try to minimize redundant code as much as possible, use the best practices I have learned so far, and think in an object-oriented way. 
In order to do this, I tried to plan my code ahead of time and break it down into more specific methods than I have ever done. All of my games are divided into the following blocks:
A main Play() method where the deck is made and all other methods are called.
A PlayerRound() or Compare() method that structures the game rounds: the main game mechanism
Within this method, the game mechanism is assembled primarily with methods used to shuffle, draw and show cards. All of the methods that involve handling the card deck are written in the Deck class, which is arguably the most important class besides the game classes themselves.
The Game class holds common methods that will be needed across games such as adding cards to a hand and drawing & comparing. More on this in the polymorphism section.
However this approach would not have worked with Highest Match. This game involves several moving parts, and in order to manage them I broke it down into smaller methods. There is a main PlayerRound() method, separate methods to evaluate player and dealer hands, compare both hands, swap cards, show final results and return to the main menu. 


### UML Diagram

 <img src="images/CardgameUML.png?raw=true"/>


### Object-Oriented Programming
**Polymorphism**

Definition: Polymorphism occurs when one has different classes related to one another, which allows objects to be treated as though they are part of a common base class even though they are of different classes.

<img src="images/CompareandDrawCards.png?raw=true"/>

Explain usage in project: my main Game class includes a CompareCardValues() method which will be overridden in derived class and a DrawAndCompare() method which handles the first part of the two games that compare values and suits each. Since this section is the same for both games, it made sense to refactor my code and place this method in the base class. 
Here is an example of how this is being implemented:
 
<img src="images/CompareCardValues.png?raw=true"/>

**Inheritance (“is a”)** 

Definition: inheritance is a hierarchy of classes that allows efficient coding by minimizing repetitive code and encouraging writing flexible code that can be reused.
The examples above are examples of inheritance as well, but another example of inheritance in my code is the AddCardsToHand() method in my Game class:

<img src="images/AddCardstoHand.png?raw=true"/>

Explain usage in project: I use this method in the Highest Match derived class to add cards to the dealer’s hand and the player’s hand. My player and dealer classes also inherit from the Person class, however I’m not using that as an example because the only piece of code they have is a Score variable.

**Encapsulation** 

Definition: encapsulation is the principle of grouping attributes and methods under a single unit, such as a class, in order to restrict access from external code and all actions in a program are controlled by the class’s methods.

In the Highest Match class, most methods are private and cannot be accessed by any other code in the program. This prevents any unintended actions on the player’s hand and enables me to, for example, set consistently implemented rules about how the cards are swapped.

<img src="images/SwapCards.png?raw=true"/>

### Experimentation and Questions
Writing and refactoring my code to minimize redundancy was my biggest goal for this project. Learning to think in an object-oriented way takes practice, and it’s tempting to write code in a linear way in one large, convoluted method. I tried organizing my code in methods as I was planning my games- I drew a UML for the Highest Match game to help me visualize how to make all the moving parts work. As I was refactoring my code, I tried to find code I could move to the base Game class to reduce repetitive code, broke down the game mechanism into smaller methods and tried to condense my code into fewer lines, if they were accomplishing the same objective. 
I’m now curious to learn how else I can optimize this project further with everything we’ve learned since we were assigned the project, as I’m certain there’s more I can do to improve my code.


**How will you use what you learned in this playtest session to improve your application?**

First and most importantly, I will fix the bugs in the game- start at the most significant bugs and work down to improving more minute details. There’s two strange lines of text (picture below) that keep coming up at the top of the console, and occasionally the higher or lower game gives an invalid answer message even though the user has typed in the word correctly. I need to work on the app’s exception catching and add specific messages for different kinds of exceptions. I will change how the user interacts in the game (specifically in Higher or Lower and Apples or Oranges) to make the playing experience less tedious. 
I will likely seek help from IAM’s student tutors to work through these bugs.

**How will you use what you learned to improve your application for the next version?**

I would like to add a few features to the game that I couldn’t add in this version, such as players being able to exit the game whenever they’d like, not just when the game is over. I think the game could be more visual as well. I will also try to refactor the code further to explore different, possibly more efficient ways I can achieve the same objectives.

### Credits
Janell Baxter: provided help in the early stages of the project, especially with the Card Deck class
Sally Juetner (IAM Tutoring): extensive help in working out game logic for Highest Match and debugging
