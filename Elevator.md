### PROGRAM _Elevator_
The _Elevator_ is in the _Current Elevator Floor_  
The _Person_ is in the _Current Person Floor_  
1. __Press__ _Button_
1. The  _Elevator_ __Has A Direction__? 
    1. IF FALSE, THEN __Decide__ _Direction_  
    1. ELSE:  
        1. IF the direction of the Elevator != the direction of the _Requested Floor_, __Book__ __Later__  
        1. ELSE, IF the _Requested Floor_ is between _Current Elevator Floor_ and _First Requested Floor_:
            1. __Book__ _Now_  
            1. __Order__ _Now_ from closest to furthest with the _Current Elevator Floor_
        1. ELSE, __Book__ __Later__

### PROGRAM __Press__ _Button_
1. _Button_ = ARROW?
    1. IF TRUE:  
        1. _Requested Floor_ <- _Current Person Floor_  
        1. _Requested Direction_ <- ARROW  
    1. ELSE,  
        1. _Requested Floor_ <- _Button_  
        1. _Requested Direction_ <- _Current Person Floor_ - _Current Elevator Floor_  

### PROGRAM _Something_ __Has A Direction__ 
1. _Something_ is MOVING OR BOOKED?
    1. IF TRUE, RETURN FALSE  
    1. ELSE, RETURN TRUE  

### PROGRAM __Decide__ _Direction_ 
1. _Current Elevator Floor_ = _First Requested Floor_?
    1. IF TRUE, do nothing, keep waiting for the next command, or maybe open the door
    1. ELSE, __Go to__ _First Requested Floor_

### PROGRAM __Go to__ _SomeFloor_
1. IS _Current Elevator Floor_ < _SomeFloor_?
    1. IF TRUE, direction of the Elevator is UP
        1. While _Current Elevator Floor_ != _SomeFloor_:
            1. IF |_Current Elevator Floor_ - _SomeFloor_| = 1, SLOW DOWN
            1. _Current Elevator Floor_ <- _Current Elevator Floor_ - 1
    1. ELSE,
        1. direction of the Elevator is DOWN
        1. While _Current Elevator Floor_ != _SomeFloor_:
            1. IF |_Current Elevator Floor_ - _SomeFloor_| = 1, SLOW DOWN
            1. _Current Elevator Floor_ <- _Curent Elevator Floor_ + 1

### PROGRAM _When_ __Book__ _DestinationFloor_
1. IF _When_ = _Now_, APPEND floor to _Now_ list.
1. ELSE, IF _When_ = _Later_, APPEND floor to _Later_ list.