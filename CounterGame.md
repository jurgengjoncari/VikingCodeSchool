# 1. Understand the Problem
    1. Clarify the problem
        Find which player will say 100 by following the rules of the game.
        Practically we have two sets: __Numbers__, and __Players__, and its elements relate to each other. 
        This means that we have a function. 
        Since the __Numbers__ don't get repeated, the domain of this function is the __Numbers__ set.
        In this case the relation will be __IsAssigned__. For ex: NUMBER 1 __IsAssigned__ to PLAYER 1, etc.
        This is a complex function which requires other functions. So, a composite function. 
    2. ## Model the system and break the problem into pieces
        - We have __Numbers__ from 1 to 100.
            - Assign each of these __Numbers__ to a PLAYER
            - Find out which PLAYER will the NUMBER 100 be Assigned to.
        - We have a set of __Players__ oredered 1 to 10 in a circle. 
            - How to represent ordered items?
                - Usually by assigning each a letter or a number.
            - How to represent a circle? Repeat items?
                - Through some condition that repeats steps
            - Sometimes the order can be reversed. How to represent reversal?
                - For this a new function has to be implemented.
    3. Research similar solutions
2. Come up with a Plan
    1. Prioritize your work
    2. Map out your strategy
3. Implement the Plan
4. Verify your Results


Start with the first player,
assign him number 1
go down the line of __Players__ and assign each 

PROGRAM CounterGame:
    10 friends
    start counting from 1 to 100
    IF the number is divisible by 7
        THEN switch direction
    END
    IF the number is divisible by 11
        THEN skip to the next one
    END
END.

PLAYER 1 says 1
PLAYER 2 says 2
PLAYER 3 says 3
....
PLAYER 6 says 6
PLAYER 7 says 7
PLAYER 6 says 8
PLAYER 5 says 9
PLAYER 4 says 10
PLAYER 2 says 11
PLAYER 1 says 12
PLAYER 10 says 13
PLAYER 11 says 14
PLAYER 10 says 15
....
