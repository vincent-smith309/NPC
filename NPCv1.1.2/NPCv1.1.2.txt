#welcome to the Non Player Creator or NPC. Good luck on your adventures!

import random
import sys
from tkinter import *
from tkinter import Entry
from tkinter import filedialog

root = Tk()
root.title("NPC")
root.geometry("750x350")

def nameclick():
    global character_name
    continue_button = Button(root, text="Generate", command=match_function, padx=50)
    continue_button.grid(row=16, column=2, columnspan=2)
    character_name.get()
    return character_name


def match_function():
    character_gen = Label(root, text='''Your NPC is generated''')
    character_gen.grid(row=17, column=2, columnspan=2 )
    match int(Strength.get()):
        case 8 | 9:
            STR_bonus = -abs(1)
        case 10 | 11:
            STR_bonus = 0
        case 12 | 13:
                STR_bonus = 1
        case 14 | 15:
                STR_bonus = 2
        case 16 | 17:
                STR_bonus = 3
        case 18 | 19:
                STR_bonus = 4
        case _:
                STR_bonus = 5
    match int(Dexterity.get()):
        case 8 | 9:
                DEX_bonus = -abs(1)
        case 10 | 11:
                DEX_bonus = 0
        case 12 | 13:
                DEX_bonus = 1
        case 14 | 15:
                DEX_bonus = 2
        case 16 | 17:
                DEX_bonus = 3
        case 18 | 19:
                DEX_bonus = 4
        case _:
                DEX_bonus = 5
    match int(Constitution.get()):
        case 8 | 9:
            CON_bonus = -abs(1)
        case 10 | 11:
            CON_bonus = 0
        case 12 | 13:
            CON_bonus = 1
        case 14 | 15:
            CON_bonus = 2
        case 16 | 17:
            CON_bonus = 3
        case 18 | 19:
            CON_bonus = 4
        case _:
            CON_bonus = 5
    match int(Intelligence.get()):
        case 8 | 9:
                INT_bonus = -abs(1)
        case 10 | 11:
                INT_bonus = 0
        case 12 | 13:
                INT_bonus = 1
        case 14 | 15:
                INT_bonus = 2
        case 16 | 17:
                INT_bonus = 3
        case 18 | 19:
                INT_bonus = 4
        case _:
                INT_bonus = 5
    match int(Wisdom.get()):
        case 8 | 9:
                WIS_bonus = -abs(1)
        case 10 | 11:
                WIS_bonus = 0
        case 12 | 13:
                WIS_bonus = 1
        case 14 | 15:
                WIS_bonus = 2
        case 16 | 17:
                WIS_bonus = 3
        case 18 | 19:
                WIS_bonus = 4
        case _:
                WIS_bonus = 5
    match int(Charisma.get()):
        case 8 | 9:
                CHA_bonus = -abs(1)
        case 10 | 11:
                CHA_bonus = 0
        case 12 | 13:
                CHA_bonus = 1
        case 14 | 15:
                CHA_bonus = 2
        case 16 | 17:
                CHA_bonus = 3
        case 18 | 19:
                CHA_bonus = 4
        case _:
                CHA_bonus = 5
#hope this spellcasting ability match is idiot proof fixing it hopefully
    match sc_click.get():
        case "Intelligence" | "intelligence" | "INT" | "int":
            spell_attack = INT_bonus + int(proficiency_bonus.get())
            spell_save_DC = 8 + INT_bonus + int(proficiency_bonus.get())
        case "Wisdom" | "wisdom" | "WIS" | "wis":
            spell_attack = WIS_bonus + int(proficiency_bonus.get())
            spell_save_DC = 8 + WIS_bonus + int(proficiency_bonus.get())
        case "Charisma" | "charisma" | "CHA" | "cha":
            spell_attack = CHA_bonus + int(proficiency_bonus.get())
            spell_save_DC = 8 + CHA_bonus + int(proficiency_bonus.get())
        case _:
            spell_attack = INT_bonus + int(proficiency_bonus.get())
            spell_save_DC = 8 + INT_bonus + int(proficiency_bonus.get())
    hp_list = []
    for i in range(0, int(hit_die_total.get())):
        x = random.randint(1, int(hit_die.get())) + CON_bonus
        hp_list.append(x)
    hp = sum(hp_list)
    ac = 10 + DEX_bonus + int(ac_bonus.get())
    Strength_attack = STR_bonus + int(proficiency_bonus.get())
    Dexterity_attack = DEX_bonus + int(proficiency_bonus.get())
    file = filedialog.asksaveasfile(initialfile="my_character.txt", defaultextension='.txt', filetypes=[("Text file", ".txt"),
                                                                        ("All files", ".*")])

    filetext = ('''

    Your NPC is Complete!

    ''' + """
    """ + character_name.get() + '''
    ''' +
    "HP: " + str(hp) + '''
    ''' +

    "AC: " + str(ac) + '''
    ''' +

    "STR: " + (Strength.get()) + " STR Bonus: " + str(STR_bonus) + """
    """ +

    "DEX: " + (Dexterity.get()) + " DEX Bonus: " + str(DEX_bonus) + '''
    ''' +

    "CON: " + (Constitution.get()) + " CON Bonus: " + str(CON_bonus) + '''
    ''' +

    "INT: " + (Intelligence.get()) + " INT Bonus: " + str(INT_bonus) + '''
    ''' +

    "WIS: " + (Wisdom.get()) + " WIS Bonus: " + str(WIS_bonus) + '''
    ''' +

    "CHA: " + (Charisma.get()) + " CHA Bonus: " + str(CHA_bonus) + '''
    ''' +

    "Strength Attack Bonus: " + str(Strength_attack) + '''
    ''' +

    "Dexterity Attack Bonus: " + str(Dexterity_attack) + '''
    ''' +

    'Spell Save DC: ' + str(spell_save_DC) + '''
    ''' +

    'Spell Attack Bonus: ' + str(spell_attack))
    file.writelines(filetext)
    file.close()
#someone put me out of my misery XD

#placing buttons and entries in no particular order cause I'm a fucking mess
hit_die = StringVar(root)
hit_die.set("6")
hit_die_option_menu = OptionMenu(root, hit_die, "6", "8", "10", "12")
hit_die_option_menu.grid(row=8, column=2, columnspan=2)
hit_die_option_menu_label = Label(root, text="Hit Die Type: ")
hit_die_option_menu_label.grid(row=8, column=1, columnspan=2)

hit_die_total = StringVar(root)
hit_die_total.set("1")
hit_die_total_option_menu = OptionMenu(root, hit_die_total, "1", "2", "3", '4', '5', '6', '7', '8',
                                       '9','10', "11", '12', '13', '14', '15', '16', '17',"18",
                                       '19', '20'  )
hit_die_total_option_menu.grid(row=9, column=2, columnspan=2)
hit_die_total_option_menu_label = Label(root, text="Total Hit Dice(LVL): ")
hit_die_total_option_menu_label.grid(row=9, column=1, columnspan=2)

ac_bonus = Entry(root, width=10)
ac_bonus.grid(row=10, column=2, columnspan=2)
ac_bonus_label = Label(root, text="Bonus to AC OTHER than Dex bonus")
ac_bonus_label.grid(row=10, column=1, columnspan=2)

sc_click = StringVar(root)
sc_click.set("Intelligence")
spellcasting_ability_input = OptionMenu(root, sc_click, "Intelligence", "Wisdom", "Charisma")
spellcasting_ability_input.grid(row=11, column=2, columnspan=2)
spellcasting_ability_label = Label(root, text='''Spellcasting Ability: ''')
spellcasting_ability_label.grid(row=11, column=1, columnspan=2)

proficiency_bonus = Entry(root, width=10)
proficiency_bonus.grid(row=12, column=2, columnspan=2)
proficiency_bonus_label = Label(root, text="Prof. Bonus: ")
proficiency_bonus_label.grid(row=12, column=1, columnspan=2)

character_name = Entry(root, width=50)
character_name.grid(row=3, column=1)
character_name.insert(0, "NPC Name")

AS_1 = random.randint(8, 18)
AS_2 = random.randint(8, 18)
AS_3 = random.randint(8, 18)
AS_4 = random.randint(8, 18)
AS_5 = random.randint(8, 18)
AS_6 = random.randint(8, 18)
assign_scores_label = Label(root, text='''please choose where to assign these ability scores''')
assign_scores_label.grid(row=1, column=3, columnspan=3)
AS_1_label = Label(root, text=AS_1)
AS_1_label.grid(row=2, column=2)
AS_2_label = Label(root, text=AS_2)
AS_2_label.grid(row=2, column=3)
AS_3_label = Label(root, text=AS_3)
AS_3_label.grid(row=2, column=4)
AS_4_label = Label(root, text=AS_4)
AS_4_label.grid(row=3, column=2)
AS_5_label = Label(root, text=AS_5)
AS_5_label.grid(row=3, column=3)
AS_6_label = Label(root, text=AS_6)
AS_6_label.grid(row=3, column=4)

Strength = Entry(root)
Strength.grid(row=4, column=2)
Strength.insert(0, "STR")
Dexterity = Entry(root)
Dexterity.grid(row=4, column=3)
Dexterity.insert(0, "DEX")
Constitution = Entry(root)
Constitution.grid(row=4, column=4)
Constitution.insert(0, "CON")
Intelligence = Entry(root)
Intelligence.grid(row=5, column=2)
Intelligence.insert(0, "INT")
Wisdom = Entry(root)
Wisdom.grid(row=5, column=3)
Wisdom.insert(0, "WIS")
Charisma = Entry(root)
Charisma.grid(row=5, column=4)
Charisma.insert(0, "CHA")

start_screen_label = Label(root, text='''Hi! I'm The Non Player Creator
Welcome! I'm gonna help you create an NPC for your game! ''')
start_screen_label.grid(row=1, column=1)

name_button = Button(root, text="Give Them a Name", command=nameclick, padx=50)
name_button.grid(row=5, column=1)

root.mainloop()

 #yeet this shit is wild v1.1.2 on the waaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaay
 #huzzah!