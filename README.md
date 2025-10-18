
# SQUARE WAVE GENERATOR WITH FREQUENCY 50KHZ

## AIM
To write and execute an square wave with frequency 50khz in assembly and c program.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) USING ASSEMBLY LANGUAGE

```
ORG 0000H         
MOV TMOD, #01H    
AGAIN: MOV P1, #0FFH  
CALL DELAY
MOV P1, #00H    
CALL DELAY      
SJMP AGAIN      
DELAY: MOV TH0, #0FFH
MOV TL0, #0FAH
SETB TR0       
WAIT: JNB TF0, WAIT  
CLR TR0      
CLR TF0      
RET           
END

```
### (ii)USING C LANGUAGE
```
ORG 00H
MOV DPTR,#4500H
MOV TMOD,#20H
MOV TH1,#0FDH
MOV SCON,#40H
SETB TR1
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
SJMP AGAIN
END

```

### OUTPUT:

<img width="1672" height="730" alt="Screenshot 2025-10-18 153539" src="https://github.com/user-attachments/assets/6ed6ae94-d394-47dd-a4be-a21d326a9bac" />

<img width="1668" height="720" alt="Screenshot 2025-10-18 151534" src="https://github.com/user-attachments/assets/010cc10c-13f2-4ebf-b96c-61a71724e33f" />

### RESULT:

Thus the square wave is generated using both assembly and C program  an the output is shown.

