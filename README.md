# Structure of readme:  
* Repository structure  
* General conventions  
* Cheat Engine tables and comments conventions  

# Repository structure  
* CE tables - saves of CE tables with explanations of assembly code / functions / stack state, and etc in comments  
* functionList - list of functions, with their adresses, arguments, and a brief description / details of work  
* structureList - list of structures , that are dynamically creating when game runs, like zombie offsets from mod doc. also contains offsets
* idList - selfexplanatory, it is various IDs, like zombie types from zombieStruct, and similar stuff
* variableList - list of Variables, used by functions, and their meaning. Often they are self explanatory, but let it be, just in case
* Scripts - well, my scripts (btw, would be grateful for credit)
* TODO - TODO
* Readme - very cool must read file  

# General Conventions
* prefixes before line means degree on confidence:  
(???) - absolutely don't know  
(??)  - vague theories with vague evidences  
(?)   - function/variable purpose is known, but with vague details  
(!)   - both function/variable purpose and mechanism of work is known, but missing some details
      - function/variable is almost fully known, very low doubts and uncertainty  
	  
* if variable / functions is named undecided than... well, i hasn't decided it yet ?\_(?)_/? (it was meant to be this smile: https://memepedia.ru/wp-content/uploads/2017/05/Shrug-Emoticon-dunno-lol.jpg)
* all hex values (and maybe all values), greater than 9 are presented i form hex(decimal) like: 1A(26)

# CE table comments conventions:  

ATTENTION!!! CE table ONLY work with files named "PlantsVsZombies.exe". If you want to change that, than you need to open ce table file in text redactor, and change all strings "PlantsVsZombies.exe" to what you need  
same stuff with prefixes  

* comment of any instruction that changes stack pointer (esp) contains values of esp in hex, that will be after instruction execution, relative to what esp was during call of corresponding function/variable  
example (imagined):  
call 00624500  
...  
00624500:  
push ebx			comment:	esp -4  

* comment of instruction at the start of a function contains data of what variables were in stack, and what were in registers (esp is relative to its value at function call)  
example on real function comment (1312D0 - damage to zombie with armor):  
Calculation of damage if zombie has armor  
Stack:  
+C    DMGModifier
+8    DMG  
+4    zombieStruct2  
-4    DMGModifier and 8  
-C    DMGModifier  
-10(16)   DMG  
-14(20)   zombieStruct2  
-18(24)   unk1  
esp -8  
registers:  
eax: ???  
ebx: projModifier  

* instructions, that modify registers contains value, that this register will have after execution  
example (1312D0):  
mov eax,[esp+14]		comment:	eax: projModifier  

* jmp/jne and other jump instructions will have a condition in which jump occurse, written in pseudocode, and optional human readable explanation next to it  
example:  
cpm eax,ecx
jne 00457000				comment:	if(projModifier != 4)	checks if damage type is not freezing  

* instruction, that call functions contain name of this function, from my documentation  
example(imagined):  
call 000623118			comment:	spawnZombie(type=eax, speed=ebx)  
