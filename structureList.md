Example of format:

structureName{
(levelOfConfidence)hexOffset(DecimalOffset) - NameInDocumentation - description | type		links:
(levelOfConfidence)hexOffset(DecimalOffset) - NameInDocumentation - description | type		links:
...
notes
}

zombieStruct:
008(8)		-		x						- The zombies x value																							| ???
00C(12)   -  	y 					- The zombies y value (not float) 														    | ???
020(32)   -    	layer 				- The layer that the zombie is on 														| ???
024(36)   -  	type 				- Zombie type 																			              | ???
028(40)   -  	state 				- Zombie State (refer to Zombie States) 												| ???
02C(44)   -		x_Float 			- The zombies x value																	          | ???
030(48)   -	  	y_Float  			- The zombies y value																	        | ???
034(52)   - 	speed    			- Zombie speed (aka how fast the zombie travels)								| ???
051(81)   -  	isEating 			- determines if the zombie is eating 1, is yes, 0 is no (byte)	| byte
0AC(172)  -  	Decelerate 			- Decelerate																			            | ???
0B0(176)  -  	Butter 				- Butter																				                | ???
0B4(180)  -  	Freeze 				- Freeze																				                | ???
0B8(184)  -  	Hypno 				- Hypno (byte)																			            | ???
0B9(185)  -  	Blow Away																									                    | ???
0BF(191)  -  	Garlic Effect																								                  | ???
0C0(192)  -  	nothing																										                    | ???
0C4(196)  -  	zombieArmor         - zombie armorm type (1 - cone, 2 - bucket, 3 - football armor)	| ???
0C8(200)  -  	zombieHP 			- current HP of zombie 																	        | ???
0CC(204)  -  	zombieMaxHP 		- max HP of zombie																		        | ???
0D0(208)  -  	zombieArmorHP 		- current HP of armor																	      | ???
0D4(212)  -		zombieArmorMaxHP 	- max HP of zombie armor																    | ???
0EC(236)  -  	Destroys zombie		- flag for game to destroy zombie														| ???
11C(284)  -  	Zombie size																									                  | ???


Projectile:
30(48)    - x 						- x position 																			                | float
(?)44(68) - y						- y position 																			                  | float
(!)58(88) - undecided				- trajectoryType or maybe just projectileType										| ???

plant:
04 (04)   -		undecided ??? strange pointer
1C (28)   - 	lane				- lane on which it is planted															        | ???
28 (30)   - 	plantOffset			- offset on this lane in tiles (from 1 to 8)									| ???
