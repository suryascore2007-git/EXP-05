# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)

```ORG 0000H
       MOV R7,30H     
       DEC R7         

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT

NEXT:  JC DOWN

       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R7,LOOP1

HERE:  SJMP HERE

END

```
## OUTPUT(Ascending order)
Entering the number of elements to be stored in 30H

<img width="669" height="218" alt="image" src="https://github.com/user-attachments/assets/4fc64c11-cf4a-4c96-a459-aaab889c51d2" />

Entering the elements in 40H

<img width="689" height="246" alt="image" src="https://github.com/user-attachments/assets/97e11ce7-3473-4c8e-b4d7-5272abbb7d99" />

<img width="889" height="552" alt="image" src="https://github.com/user-attachments/assets/9c0aa8f6-9ce2-412a-9dfa-b148411e0f41" />

<img width="629" height="226" alt="image" src="https://github.com/user-attachments/assets/716218e0-01a0-40a1-9db1-2b336df1563e" />



---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)

```ORG 0000H
LOOP1:MOV R0,#40H
MOV R6,#04h
DEC R6
LOOP:MOV A,@R0
INC R0
MOV B,@R0
CJNE A,B,NEXT
NEXT:JNC DOWN
MOV@R0,A
DEC R0
MOV@R0,B
INC R0
DOWN:DJNZ R6,LOOP
MOV R1,#04h
DJNZ R1,LOOP1
END











```
## OUTPUT(Descending order)

<img width="1035" height="185" alt="image" src="https://github.com/user-attachments/assets/3334a34f-9968-4518-b496-488f1f1f1d81" />



---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.
