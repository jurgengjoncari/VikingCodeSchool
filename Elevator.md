PROGRAM Elevator:

    The Elevator is in the CurrentElevatorFloor
    The Person is in the CurrentPersonFloor
    Press(Button)
    IF HasADirection(Elevator) = No:
        Decide(Direction)
    ELSE:
        IF DirectionIs(Elevator) != DirectionIs(RequestedFloor):
            Book(Later)
        ELSE:
            IF the RequestedFloor is between CurrentElevatorFloor and FirstRequestedFloor:
                Book(Now)
                Order Now from closest to furthest with the CurrentElevatorFloor
            ELSE:
                Book(Later)


PROGRAM Press(Button):
    IF Button = ARROW:
        RequestedFloor = CurrentPersonFloor
        RequestedDirection
    ELSE:
        RequestedFloor
        RequestedDirection = CurrentElevatorFloor

PROGRAM HasADirection(Something):

    IF Something is MOVING or BOOKED:
        RETURN No
    ELSE,
        RETURN Yes


PROGRAM Decide(Direction):

    IF CurrentElevatorFloor = FirstRequestedFloor
        Do nothing, keep waiting for the next command, or maybe open the door
    ELSE:
        Go(FirstRequestedFloor)


PROGRAM Go(SomeFloor):

    IF CurrentElevatorFloor < SomeFloor:
        DirectionIs(Elevator) = UP
        While CurrentElevatorFloor != SomeFloor:
            IF |CurrentElevatorFloor - SomeFloor| = 1:
                SLOW
            DECREASE CurrentElevatorFloor number by 1
    ELSE,
        DirectionIs(Elevator) = DOWN
        While CurrentElevatorFloor != SomeFloor:
            IF |CurrentElevatorFloor - SomeFloor| = 1:
                SLOW
            INCREASE CurrentElevatorFloor number by 1


Book(DestinationFloor, When):

    IF When = Now:
        APPEND floor to Now list
    ELSE, IF When = Later:
        APPEND floor to Later list