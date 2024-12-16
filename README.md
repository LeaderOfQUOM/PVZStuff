# PVZStuff  
PVZStuff... what you expecting, huh?  
Also, the formatting is a bit broken, so it is better to read in raw (button in up right corner),  
even though i edited it in notepad++ with plain text with CRLF  
idk the reason, will try to fix in next few days  

prefixes before line means degree on confidence:  
(???) - absolutely don't know  
(??)  - vague theories with vague evidences  
(?)   - function/variable purpose is known, but with vague details  
(!)	  - both function/variable purpose and mechanism of work is known, but missing some details  
	  - function/variable is almost fully known, very low doubts and uncertainty  
	  
if variable / functions is named undecided than... well, i hasn't decided it yet ?\_(?)_/? (it was meant to be this smile: https://memepedia.ru/wp-content/uploads/2017/05/Shrug-Emoticon-dunno-lol.jpg)  

--------------------------------------------------------------------------------------------------
CE table comments conventions:  

ATTENTION!!! CE table ONLY work with files named "PlantsVsZombies.exe". If you want to change that, than you need to open ce table file in text redactor, and change all strings "PlantsVsZombies.exe" to what you need  
same stuff with prefixes  

comment of any instruction that changes stack pointer (esp) contains values of esp in hex, that will be after instruction execution, relative to what esp was during call of corresponding function/variable  
example (imagined):  
call 00624500  
...  
00624500:  
push ebx			comment:	esp -4  

comment of instruction at the start of a function contains data of what variables were in stack, and what were in registers (esp is relative to its value at function call)  
example on real function (1312D0 - damage to zombie with armor):  
Calculation of damage if zombie has armor  
Stack:  
+C   projModifier  
+4    zombieStruct2  
-4     projModifier and 8  
-C    projModifier  
-10   projID  
-14   zombieStruct2  
-18   unk1  
esp -8  
registers:  
eax: ???  
ebx: projModifier  

instructions, that modify registers contains value, that this register will have after execution  
example (1312D0):  
mov eax,[esp+14]		comment:	eax: projModifier  

jmp/jne and other jump instructions will have a condition in which jump occurse, written in pseudocode, and optional human readable explanation next to it  
example:  
cpm eax,ecx
jne 00457000				comment:	if(projModifier != 4)	checks if damage type is not freezing  

instruction, that call functions contain name of this function, from my documentation  
example(imagined):  
call 000623118			comment:	spawnZombie()  
