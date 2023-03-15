# NPC
NPC: The Non Player Create
NPCv1 readme
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Welcome to NPCv1, a piece of software designed in python 3.11.2 to provide quick stats for 5th Edition Dungeons And Dragons NPCs. 
Hoping this automation saves me and my fellow DMs time, so this program is open source and free to all, including all past versions and updates.

DO NOT PAY FOR THIS PROGRAM.

It is a truly Free Software, not Donation Ware, so you should never recieve any adds or popups asking you for money.

Please only download from official links provided by The Fool. If you feel obliged to give me a donation I won't turn it down, but it is not required and the software itself will never prompt you to give a donation.

Got some decent quality of life things coming in v1.2

I have plans to add a "random backstory and appearance generator" that will drop a paragraph about the npcs looks and backstory.

If you want to donate please contact me on Discord

Contact info: Discord: thefool309#9194
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
THINGS YOU SHOULD KNOW
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.)You WILL need python v3.11.2. This program utilizes the match function, which only came around in python v3.10, and I have only tested it using v3.11.2.

2.)The Spellcasting Ability must be defined for the program to run, so if you're making a noncasting character just put any command down and disregard the spellcasting stats.

3.)The Ability score boxes only accept numbers. the name box which will accept any string. The program will fail and not export the text file if you fill these blanks in with anything but numbers.

3.1)You can however put any number you'd like in any of these spaces that take numbers. Ability score bonuses are capped at 5 however, and will never return a value higher.

4.)You MUST rename the text file that the stats export to, or it will be saved over the next time you run the program. (you can also alternatively change the default file name in the code before you run the program each time)

5)I have integrated a file dialog box so you can save your text file as whatever you'd like, and wherever you'd like

6.)Have fun on your adventures!!! ^~^



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
KNOWN ERRORS 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
PermissionError: [errno 13] permission denied:(FIXED IN VERSION 1.1.2)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
windows.) Navigate to the default text file that it exports to. (my_character.txt) 
	right click, and select properties
	navigate to the security tab
	allow full control. 

Linux.) chmod 755 /path/to/my_character.txt



-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
