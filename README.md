# code-project
restaurent management system
-------------------------
.MODEL SMALL
.STACK 100H
.DATA
.CODE
MAIN PROC
    MOV AX, 5
    ADD AX, 3
    MOV AH, 4CH
    INT 21H
MAIN ENDP
END MAIN
