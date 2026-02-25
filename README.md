# code-project
restaurent management system
-------------------------
.MODEL SMALL
.STACK 100H

.DATA
MAXTABLES   DB 5              ; Maximum tables in restaurant
BOOKED     DB 0              ; Currently booked tables

MSG_FULL   DB "All Tables Are Booked!$"
MSG_BOOKED DB "Table Booked Successfully!$"

.CODE
MAIN PROC
    MOV AX, @DATA
    MOV DS, AX

    ; Check booked tables
    MOV AL, BOOKED
    CMP AL, MAXTABLES
    JE TABLE_FULL

    ; Book a table
    INC BOOKED
    LEA DX, MSG_BOOKED
    MOV AH, 09H
    INT 21H
    JMP EXIT

TABLE_FULL:
    LEA DX, MSG_FULL
    MOV AH, 09H
    INT 21H

EXIT:
    MOV AH, 4CH
    INT 21H

MAIN ENDP
END MAIN
