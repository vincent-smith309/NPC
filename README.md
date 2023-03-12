# NPC
NPC: The Non Player Create
NPCv1 readme.txt
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Welcome to NPCv1, a piece of software designed in python 3.11.2 to provide quick stats for 5th Edition Dungeons And Dragons NPCs. 
Hoping this automation saves me and my fellow DMs time, so this program is open source and free to all, including all past versions and updates.

DO NOT PAY FOR THIS PROGRAM.

It is a truly Free Software, not Donation Ware, so you should never recieve any adds or popups asking you for money.

Please only download from official links provided by The Fool. If you feel obliged to give me a donation I won't turn it down, but it is not required and the software itself will never prompt you to give a donation.

Got some decent quality of life things coming in v1.2

f you want to donate please contact me on Discord

Contact info: Discord: thefool309#9194
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
THINGS YOU SHOULD KNOW
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.)You WILL need python v3.11.2. This program utilizes the match function, which only came around in python v3.10, and I have only tested it using v3.11.2.


2.)The "Spellcasting Ability" box will only utilize these inputs 
	("Intelligence" | "intelligence" | "INT" | "int" any of these four will set your spellcasting ability as Intelligence)           
        ("Wisdom" | "wisdom" | "WIS" | "wis" | any of these four will set your spellcasting ability as Wisdom)
        ("Charisma" | "charisma" | "CHA" | "cha" | any of these four will set your spellcasting ability as Charisma)


2.1)The Spellcasting Ability must be defined for the program to run, so if you're making a noncasting character just put any command down and disregard the spellcasting stats.


3.)The rest of the boxes only accept numbers, aside from the name box which will accept any string. The program will fail and not export the text file if you fill these blanks in with anything but numbers.


3.1)You can however put any number you'd like in any of these spaces that take numbers. Ability score bonuses are capped at 5 however, and will never return a value higher.


4.)You MUST rename the text file that the stats export to, or it will be saved over the next time you run the program. (you can also alternatively change the default file name in the code before you run the program each time)


4.1)I will be looking into a way to integrate a file explorer so you can choose your own paths to save your NPCs to in future updates, so message me on Discord if you'd like info on my progress.


5.)The Box that asks "Whats your hit die type in #?" accepts a numerical value that is the maximum number on your hit die. (Ex. A d8 hit die would simply be entered in this box as "8") 

6.)all errors are reported via the python console.

7.)Have fun on your adventures!!! ^~^


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
KNOWN ERRORS 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
PermissionError: [errno 13] permission denied:
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
windows.) Navigate to the default text file that it exports to. (my_character.txt) 
	right click, and select properties
	navigate to the security tab
	allow full control. 

Linux.) chmod 755 /path/to/my_character.txt
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
