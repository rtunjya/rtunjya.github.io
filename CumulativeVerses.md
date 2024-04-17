## Cumulative Verses

**Project description:** An in-class group assignment to use the programming skills mastered over the semester to develop a solution that uses at least one loop and at least one conditional statement and build a song cumulatively. We chose the song Partridge in a Pear Tree.

<img src="images/CumulativeVerses.png?raw=true"/>

### Code Structure

I divided different aspects of the song and stored them in separate string arrays. 

```C#
static string[] NumOfDays = new string[] // array to store number of days
        {

            "first day ",
            "second day ",
            "third day ",

            "fourth day ",
            "fifth day ",
            "sixth day ",
            "seventh day ",
            "eighth day ",
            "ninth day ",
            "tenth day ",
            "eleventh day ",
            "twelfth day ",
        };
```

Next, a nested loop to construct the song:

```C#
        static void Main()
        {
            // instantiating variables for nested loop
            int CurrentSection = 0; 
            int repetition = 0;

            // rafael helped me with the nested loop
            // loop logic: as long as var CurrentSection is less than var NumberVerses, add 1 to to var CurrentSection
            for (CurrentSection = 0; CurrentSection < NumberVerses; CurrentSection++) 
            {
                Write($"On the {NumOfDays[CurrentSection]} of Christmas, my true love gave to me "); // first line that repeats every verse

                // nested loop to construct every verse
                // the previous line(s) repeat as new lines are added
                // loop logic: as long as var repetition is greater than or equal to 0, subtract 1 from var repetition
                for (repetition = CurrentSection; repetition >= 0; repetition--) 
                {
                    Write(RepeatingLyrics[repetition]);

                }
                // double line spacing
                WriteLine("");
                WriteLine("");
            }
```

### Credits

Code written for class by Jay Gujral, Rafael Sabe, Gimar Bey.

For more details see [GitHub Repository](https://github.com/rtunjya/Week4_BreakoutGrp_JG.git).
