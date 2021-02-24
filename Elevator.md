PROGRAM Elevator:  

    You're outside of the elevator at TheDestinationFloor 
    The elevator is on TheCurrentFloor
    Press the UP or DOWN button to request the elevator to GoTo(TheDestinationFloor):
    Get inside of the elevator
    Press the TheDestinationFloor button
    CloseTheDoor()
    GoTo(TheDestinationFloor)
END

PROGRAM GoTo(TheDestinationFloor):

    IF the TheCurrentFloor != TheDestinationFloor:  
        IF TheDestinationFloor > TheCurrentFloor:
            WHILE TheCurrentFloor != TheDestinationFloor:
                TheCurrentFloor = TheCurrentFloor + 1
            END
        ELSE,
            WHILE TheCurrentFloor != TheDestinationFloor:
                TheCurrentFloor = TheCurrentFloor - 1
            END
        END
        Stop
        Open the door
    ELSE, 
        Open the door
    END
END

PROGRAM CloseTheDoor:

    IF there are no people in the door path:
        Close the door
    ELSE,
        Don't close the door
    END
END

PROGRAM Requested(Floor):

    IF somebody requests the elevator on the Floor while on its way
        IF it has the same direction,  
            the elevator goes to the closest TheDestinationFloor
        ELSE, 
            the elevator goes on normally to the destination and opens.  
            After it's closed, goes to the person that requested in earlier. 
            IF somebody enters the elevator and presses a different number
                IF the TheDestinationFloor number is on its way, 
                    the elevator stops
                    opens there
                    closes
                    Goes on to the destination
                    opens there
                    closes
                    continues to the previews destination
                ELSE,
                    continues the normal flow
                    then continues on to the last TheDestinationFloor number typed
                END
            ELSE,
                it goes on with the normal flow
            END
        END
    ELSE,
        continue normally to the destination
    END
END

## Clarify
Design a proper working elevator. 
The goal of an elevator is to transport people from one TheDestinationFloor to another. Practically, three steps:

## High-level
- It accepts user input
- It has sensors
## Low-level
is capable of interpreting and executing the commands:
- "open elevator door"
- "close elevator door"
- "go up full speed"
- "go down full speed"
- "slow down"
- "stop"

...and it accepts user input in the form of:

- TheDestinationFloor buttons inside the elevator
- door open and close buttons inside the elevator
- up and down call buttons on each TheDestinationFloor

...and it has sensors for:

- IF a human is in the door closing path
- IF it is currently at a TheDestinationFloor (instead of in-between TheDestinationFloors)

...and it has a few quirky requirements:

- it must "slow down" at least 1 TheDestinationFloor before it stops.
- there is a small chance that it actually stops between TheDestinationFloors by accident (it's an old elevator)