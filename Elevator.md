## PROGRAM _Elevator_
The _Elevator_ is in the _current elevator floor_  
The _Person_ is in the _Current Person Floor_

__Press__ _Button_

IF __Has A Direction__ _Elevator_ = FALSE  
    THEN __Decide__ _Direction_  
ELSE,  
    IF the direction of the Elevator is different from the direction of the _Requested Floor_:  
        __Book__ _Later_  
    ELSE,  
        IF the _Requested Floor_ is between _current elevator floor_ and _First Requested Floor_:  
            __Book__ _Now_  
            Order Now from closest to furthest with the _current elevator floor_
        ELSE,
            __Book__ _Later_


## PROGRAM __Press__ _Button_
IF _Button_ = ARROW:  
    _Requested Floor_ <- _Current Person Floor_  
    _Requested Direction_ <- ARROW  
ELSE,  
    _Requested Floor_ <- _Button_  
    _Requested Direction_ <- _Current Person Floor_ - _current elevator floor_  


## PROGRAM _Something_ __Has A Direction__ 
IF _Something_ is MOVING OR BOOKED:   
    RETURN FALSE  
ELSE,  
    RETURN TRUE  


PROGRAM __Decide__ _Direction_  :

    IF _current elevator floor_ = First_Requested Floor_
        Do nothing, keep waiting for the next command, or maybe open the door
    ELSE:
        Go(First_Requested Floor_)


PROGRAM Go(SomeFloor):

    IF _current elevator floor_ < SomeFloor:
        direction of the Elevator is UP
        While _current elevator floor_ != SomeFloor:
            IF |_current elevator floor_ - SomeFloor| = 1:
                SLOW
            DECREASE _current elevator floor_ number by 1
    ELSE,
        direction of the Elevator is DOWN
        While _current elevator floor_ != SomeFloor:
            IF |_current elevator floor_ - SomeFloor| = 1:
                SLOW
            INCREASE _current elevator floor_ number by 1


__Book__ (DestinationFloor, When):

    IF When = Now:
        APPEND floor to Now list
    ELSE, IF When = Later:
        APPEND floor to Later list