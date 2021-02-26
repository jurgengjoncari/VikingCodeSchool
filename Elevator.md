PROGRAM Elevator:

    The Elevator is in the CurrentFloor
    Press(Button)
    IF HasADirection(Elevator) = No:
        Decide(Direction)
    ELSE:
        IF it is not the same direction:
            Book(Later)
        ELSE:
            IF the RequestedFloor is between CurrentFloor and DestinationFloor:
                Book(Now)
                Order Now from closest to furthest with the CurrentFloor
            ELSE:
                Book(Later)


PROGRAM Press(Button):

    IF IsArrow(Button):
        IF ArrowIs(Buton) = UP:
            DirectionIs = UP
        ELSE:
            DirectionIs = DOWN
    ELSE:
        IF 


PROGRAM HasADirection(Something):

    IF Something is MOVING or BOOKED:
        RETURN No
    ELSE,
        RETURN Yes


PROGRAM Decide(Direction):

    IF CurrentFloor = RequestedFloor
        Do nothing, keep waiting for the next command, or maybe open the door
    ELSE:
        Go(RequestedFloor)


PROGRAM Go(SomeFloor):

    While CurrentFloor != SomeFloor:
        IF |CurrentFloor - SomeFloor| = 1:
            SLOW
            IF CurrentFloor < SomeFloor:
                DECREASE CurrentFloor number by 1
            ELSE,
                INCREASE CurrentFloor number by 1


Book(DestinationFloor, When):

    IF When = Now:
        APPEND floor to Now list
    ELSE, IF When = Later:
        APPEND floor to Later list