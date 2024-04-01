## Midterm Project: Grocery Store Simulator

**Project description:** Grocery Store Simulator is a fun, relaxing game where the user plays as a grocery store clerk and interacts with customers with different personalities.


### 1. Game Premise

The goal of the game is to suggest the best items to the customer to earn as much money as possible over the course of 3 levels. Clearing a level unlocks a new item you can add to your grocery store inventory. The winner suggestion earns the user a 20% tip, the highest tip. The second-best option earns the user a 10% tip, and suggesting the wrong item ends the level with the customer leaving, prompting the user to try again.



### 2. Characters

Store Clerk: playable character
John: level one customer
Linda: level two customer
Ashleighygh: level three customer


```C#
    class Clerk
    {
        public string name;

        public void SetClerkName()
        { // user sets player name
            Write("What is your name? ");
            name = ReadLine();
            
        }
        public void TalkToCustomer()
        { // opening greeting for each customer
            WriteLine($"You: Welcome to our store! My name is: {name}");
            WriteLine("You: How can I help you today?");
        }
    }
```

### 3. Items

Default inventory:
-	Apples
-	Cupcakes (sold in a box of 6)
-	Charcuterie board
Clearing level one unlocks Soda.
Clearing level two unlocks pumpkins.


<img src="images/Picture1.jpg?raw=true"/>

### 4. Customer Personalities Become More Challenging as The Game Progresses

As the user starts new levels, they face customers with more challenging personalities. 

Level one: the customer is polite
Level two: the customer is slightly more rude, a “Karen.”
Level three: the customer is a very rude health-obsessed person.

```C#
        public string[] rightResponses; // array for customer responses when suggested the correct item
        public string[] wrongResponses; // array for customer responses when suggested the wrong item
        public string Introduction; // string for customer introductions

        public enum Personalities
        {
            // the game has 3 customers, each is more annoying than the last. instantiation of personality types
            NICE,
            KAREN,
            HEALTHMONSTER
        }

        public Personalities personality; //constructor

        public Customer(Personalities personality)
        {
            this.personality = personality;
```

 ### 5. Credits

 This game was made with help and tutoring from Dominic Frugoli and Rafael Margarido Sabe. Dominic Frugoli helped reinforce key programming concepts during the making of this game. Rafael Margarido Sabe helped me majorly refactor my code with enum Types, lists and arrays.


For more details see [GitHub Repository]([https://guides.github.com/features/mastering-markdown/](https://github.com/rtunjya/StoreApp_Midterm.git)).
