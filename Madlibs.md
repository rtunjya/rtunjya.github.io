## Madlibs

**Project description:** I built a Madlibs Generator by following a tutorial on programmingisfun.com. Here is a definition of Madlibs according to the website:

"The application will ask a player to enter in words, it will store those words, and then replace words in a quote, story, or other short piece of text that will be written to the console window. The random words are often humorous when incorporated, so it can be fun to play after it is built."

<img src="images/Madlibs.png?raw=true"/>

### Code Structure

The first step in building the Madlibs App is to instantiate string variables for all the words being substituted. For this application, I used the same Madlibs words and sentences used in the Programming Is Fun tutorial.
Next, I created a method to collect Madlibs words from the user, and store them in the string variables I instantiated. 

The next step is to simply write out the story with the user's inputs in place of the original words:

```C#
        static void WriteStory()
        {
            // write out story
            Story = $"They all agreed that it was a huge {Creature}, {Luminous}, {Ghastly}, and {Spectral}. I have {Cross} these men, one of them a hard-headed {Countryman}, one a {Farrier}, and one a moorland {Farmer}, who all tell the same story of this {Dreadful} {Apparition}, exactly corresponding to the {Hound} of the legend. ";
            Console.WriteLine(Story);
        }
```

### Credits

Tutorial link: [Programming is Fun](https://programmingisfun.com/simple-csharp-madlib-part-one/)

For more details see [GitHub Repository](https://github.com/rtunjya/Madlibs.git).
