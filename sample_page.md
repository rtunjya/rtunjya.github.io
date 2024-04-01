## Midterm Project: Grocery Store Simulator

**Project description:** Grocery Store Simulator is a fun, relaxing game where the user plays as a grocery store clerk and interacts with customers with different personalities.![image](https://github.com/rtunjya/rtunjya.github.io/assets/157548278/21cd9a3d-3567-4fe6-bef8-5b87c24a0a37)


### 1. Game Premise

The goal of the game is to suggest the best items to the customer to earn as much money as possible over the course of 3 levels. Clearing a level unlocks a new item you can add to your grocery store inventory. The winner suggestion earns the user a 20% tip, the highest tip. The second-best option earns the user a 10% tip, and suggesting the wrong item ends the level with the customer leaving, prompting the user to try again. ![image](https://github.com/rtunjya/rtunjya.github.io/assets/157548278/5d5378d1-fb0d-44ae-aaca-7c93996cd4d9)



### 2. Characters

Store Clerk: playable character
John: level one customer
Linda: level two customer
Ashleighygh: level three customer
![image](https://github.com/rtunjya/rtunjya.github.io/assets/157548278/ddab9a62-0931-4627-9a84-84d1318321ad)

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
![image](https://github.com/rtunjya/rtunjya.github.io/assets/157548278/a188b795-3136-45cc-961d-06b2e0df6207)


<img src="images/dummy_thumbnail.jpg?raw=true"/>

### 4. Customer Personalities Become More Challenging as The Game Progresses

As the user starts new levels, they face customers with more challenging personalities. 

Level one: the customer is polite
Level two: the customer is slightly more rude, a “Karen.”
Level three: the customer is a very rude health-obsessed person.
![image](https://github.com/rtunjya/rtunjya.github.io/assets/157548278/55a58658-35e8-41bc-9472-ec48e94dffa9)

 ### 5. Credits

 This game was made with help and tutoring from Dominic Frugoli and Rafael Margarido Sabe. Dominic Frugoli helped reinforce key programming concepts during the making of this game. Rafael Margarido Sabe helped me majorly refactor my code with enum Types, lists and arrays. ![image](https://github.com/rtunjya/rtunjya.github.io/assets/157548278/08f7c1ad-5200-48a2-9b9c-23fd58f656fa)


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
