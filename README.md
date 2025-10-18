SQUARE WAVE GENERATOR USING ASSEMBLY CODE AND C PROGRAM:

AIM:
To write and execute an square wave geneartor with frequency of 50khz using assembly code.

APPARATUS REQUIRED:

Personal Computer

Keil µVision Software

PROGRAM:

i)Using Assembly code:

ORG 0000H         
MOV TMOD, #01H    
AGAIN:  MOV P1, #0FFH  
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

ii)Using C Program:

#include <reg51.h>  
void delay(void);  
void main(void)
{
    TMOD = 0x01;  
    while(1)
    {
        P1 = 0xFF;  
        delay();   
        P1 = 0x00;  
        delay();
    }
}
void delay(void)
{
    TH0 = 0xFF;    
    TL0 = 0xF6;     
    TR0 = 1;       
    while (TF0 == 0);  
    TR0 = 0;        
    TF0 = 0;        
}

OUTPUT:

<img width="1672" height="730" alt="Screenshot 2025-10-18 153539" src="https://github.com/user-attachments/assets/b8b34ab8-1077-4c32-8935-66de47800476" />


<img width="1668" height="720" alt="Screenshot 2025-10-18 151534" src="https://github.com/user-attachments/assets/42881ade-5cc7-4ab1-b937-e924a436cb7e" />

RESULT:
Thus the Square Wave Generator using keil software was done and shown the output.
