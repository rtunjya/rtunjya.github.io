## Reverb Simulator Documentation
### Jay Gujral | PROG 201: Programming II

**Overview**

This project is a simulation of how different materials in a room absorb or reflect sound. This simulation is comparatively basic – the player can move with arrow keys and change the materials of the obstacles and walls of the room; there are other factors (temperature, humidity) that impact the qualities of the sound as well. This simulation is best thought of as a demonstration of the reflectiveness or absorptiveness of the given materials, since I’ve chosen to go with more exaggerated changes to the sound so that the differences are apparent even to people who aren’t familiar with acoustics concepts.

### UML Diagram

 <img src="images/ReverbSimUML.png?raw=true"/>
 
**Experience**

Due to the complexity of the calculations required for this simulation, I chose to keep the actual interface fairly basic. The player is given instructions and a brief explanation of the interface, and can begin playing immediately. 
The player is represented with a blue square. The sound source is a point source represented by a red circle. There are two obstacles represented by gray squares. The player can move around the simulated room with arrow keys – the player can move around the obstacles and go behind them as well. The distance of the player from the sound source affects the current volume of the sound – which is written above the simulation and presented on a scale of 0 to 1. 
The player can choose to change the materials the walls and obstacles are made of by selecting between carpet, metal, foam and glass from a dropdown menu. Pressing a button applies the change, and along with the change of sound, the player is given a brief description of the reflective qualities of the chosen material. The player’s distance from the sound along with the chosen material of the room together affect what the user hears.
 
 <img src="images/ReverbSimScreenshot.png?raw=true"/>
 
### System

**Elements of Simulation**

The main elements that change the output of the system are the player’s distance from the sound source and the material of the walls and obstacles. The player moves around with arrow keys, and the further the player moves away from the source, the quieter the sound gets. 

Carpet and foam are highly absorptive materials, therefore they do not reflect sound. When either of these two materials are chosen, the player only hears a dry signal with no reflections, and the only audible difference is the boost or attenuation of volume based on distance. 
When standing behind the obstacles, the player may observe a sudden reduction in volume; this is to demonstrate the absorptive nature of the materials.
Metal and glass are highly reflective materials. When either of these two materials are chosen, the player hears different kinds of reflections along with the original sound. The sound is more washed out, and the player hears echoes of the original sound as well. 

The player will observe that the volume occasionally behaves in unexpected ways when the reflective materials are chosen. This is because the reflection of the sounds also affect how the loudness changes based on the player’s distance. The player may observe an increase of reflections when standing behind the obstacles; this is to demonstrate the reflective nature of the materials.


The inverse square law with respect to sound intensity states that the intensity of a sound in an open field decreases as the distance from its source increases; this is an exponential attenuation. Representing this (an open field, exponential sound attenuation) in a simulation would be incredibly challenging and not possible with the timeframe of the project or the knowledge I presently have. Therefore, I decided to calculate the volume attenuation linearly. 

The program calculates the reflection and absorption of the 4 materials by using the absorption coefficient assigned to each material. Acousticians have assigned a number to each material to denote how it absorbs sound, this is called the absorption coefficient. I have used a version of this principle to build my simulation. 

The absorption coefficients of the materials I have chosen do not necessarily reflect the actual numbers and rules with which acousticians make their calculations, but they follow the same principles (porous materials like foam and carpet absorb sound, metal and glass reflect sound), and the coefficients assigned to the materials behave in relation to one another in the program. I use a 0 to 1 scale for the absorption coefficients- metal is 0.2 because it doesn’t absorb a lot of sound. Foam is 0.9 because it absorbs a lot of sound. To give my reverb methods specific values for absorption and reflection, each material also has a reflection coefficient, which is also on a 0 to 1 scale. Metal is 0.6 because it reflects sound, foam is 0.25 because it doesn’t reflect a lot of sound. There is a transmission coefficient as well, and this is used to ensure that the volume changes take the room materials into account as well.

 
### C# Programming Skills

**Base and Derived Classes**

Base Class: GameComponent

Derived Classes: Player, Sound Source

Code excerpts from project:
 
  <img src="images/ReverbSimGameComp.png?raw=true"/>

   <img src="images/ReverbSimPlayer.png?raw=true"/>
 
Explain usage in project: The GameComponent class sets up the x and y axes. It also stores the direction enum that is used by the Player class to move around. While the SoundSource class doesn’t move, it still uses these elements for sound source placement and its relation to where the player is in the space. Most of that logic isn’t in these methods, but is in the MainWindow.xaml.cs class.


### Collection

 <img src="images/ReverbSimReverb.png?raw=true"/>

<img src="images/ReverbSimXAMLdotCS.png?raw=true"/>
  
Explain usage in project: I use lists in my project to keep track of the obstacles, walls and reverb reflections.


### Enum

Definition: An enumeration type (or enum type) is a value type defined by a set of named constants of the underlying integral numeric type. 

  <img src="images/ReverbSimEnum.png?raw=true"/>
    
   <img src="images/ReverbSimMove.png?raw=true"/>
     
Explain usage in project: I used enums to set up directions in my project. I use the values I instantiated to set up the arrow key movement for the player.

 
### Credits

I consulted my notes from my Psychoacoustics class at Columbia College Chicago for the volume and reverb calculations and absorption, reflection and transmission coefficients.
I used ChatGPT to refine and double check my math for the geometry, volume and reverb calculations and used it for help with debugging my code 


### Research

“Inverse Square Law.” Inverse Square Law - an Overview | ScienceDirect Topics, www.sciencedirect.com/topics/engineering/inverse-square-law. Accessed 9 Dec. 2024. 

Lamas, Luis. “How to Process Audio Files in .NET with Naudio.” Luis Llamas, 8 Dec. 2024, www.luisllamas.es/en/naudio/. 

Peek, Walker. “Common Absorption Coefficients for Acoustical Treatments.” Commercial Acoustics®, Publisher Name Commercial AcousticsPublisher Logo, 20 Nov. 2021, commercial-acoustics.com/common-absorption-coefficients-for-acoustical-treatments/. 

Bill Wagner. “C# Language Reference.” Microsoft Learn, learn.microsoft.com/en-us/dotnet/csharp/language-reference/. Accessed 9 Dec. 2024. 
