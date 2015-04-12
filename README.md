Connect4 game master and players ...
ideas:

(1) we should be able to run the game master as something like:
$ c4GM -inp infile.inp -out outfile.out

where inpfile.inp has the following:

# beginning of inpfile.inp
# this is a comment
token1 /path/to/player1.exe
token2 /maybe/a/different/path/to/player2.exe

# end of inpfile.inp

where player1.exe and player2.exe are standalone executables. This way, anyone can write
their players in any language they want. 

(2) The game board should be a standardized format which can be input to the player.exe executable. 
Something like :

$ player1.exe -inp gamefile.txt -token 1

where the gameboard is filled with tokens of 0, 1, or, 2. This way, the player.exe can look at the
board and know if it should play or not under the assumption that token 1 ALWAYS goes first. for example

$ player1.exe -inp gamefile.txt -token 1

0000000
0000000
0000000
0000000
0000000
0000000

would change the state of the game board but

$ player1.exe -inp gamefile.txt -token 1

0000000
0000000
0000000
0000000
0000000
0100000

would not.

(3) the GM should worry about win/loss/scratch state of the game and not the executables
(4) We should allow an option for the GM to run multiple instances of the game. For example maybe

# beginning of inpfile.inp
# this is a comment
token1 /path/to/player1.exe
token2 /maybe/a/different/path/to/player2.exe
ngames 20

# end of inpfile.inp

would run 20 different matches between the player1.exe and player2.exe algorithms, alternating who 
goes first each time?





