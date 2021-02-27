PROGRAM COUNTER_GAME:
    NUMBER = 1
    PLAYER = 1
    DIRECTION = 1
    WHILE NUMBER <= 100 DO:
        NUMBER = NUMBER + 1
        WHILE PLAYER <= 10 AND 1 <= PLAYER DO:
            PLAYER = PLAYER + DIRECTION
            IF MODULO(NUMBER, 7) = 0:
                DIRECTION = -1
                IF PLAYER = 10
                    PLAYER = 1
                ELSE IF PLAYER = 1
                    PLAYER = 10
                ELSE
                    DIRECTION = -1
            END
            IF MODULO(NUMBER, 11) = 0:
                PLAYER = PLAYER + 2
            END
        END
    END
END.

f(x) = {
    n * 10 - x, 
    x - (n - 1) * 10, 
}