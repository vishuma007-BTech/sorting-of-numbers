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

```asm
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
<img width="669" height="218" alt="image" src="https://github.com/user-attachments/assets/32d540b7-53de-49e4-9876-a3150501b524" />
Entering the elements in 40H
<img width="689" height="246" alt="image" src="https://github.com/user-attachments/assets/3dc409a8-82df-40a5-9c9f-6aae0e996432" />
<img width="889" height="552" alt="image" src="https://github.com/user-attachments/assets/eafb47c5-c71b-4dba-be6d-a8db5ba59e4d" />
<img width="629" height="226" alt="image" src="https://github.com/user-attachments/assets/da20e8de-136a-4ef1-8780-3aec95a6d7e2" />



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

```asm
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
<img width="1035" height="185" alt="image" src="https://github.com/user-attachments/assets/32b4582a-58e7-4b99-a1f8-e7b7863420f0" />


---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.

