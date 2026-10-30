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

```
ORG 0000H
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
<img width="831" height="563" alt="image" src="https://github.com/user-attachments/assets/33aaf849-00ec-4f6e-9309-d673130ea155" />


## memory window
<img width="673" height="205" alt="image" src="https://github.com/user-attachments/assets/5d58d345-78e2-4f29-98ad-f715dfbaa7bf" />


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

```
ORG 0000H
       MOV R7,30H     ; Load number of elements
       DEC R7         ; Outer loop = n-1
	   
LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT

NEXT:  JNC DOWN       ; If A > B ? correct order ? skip
       ; Swap when A < B
       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R7,LOOP1

HERE:  SJMP HERE

END
 



```
## OUTPUT(Descending order)

<img width="940" height="558" alt="image" src="https://github.com/user-attachments/assets/3c5d130a-c414-43ba-b926-859740791e22" />




## Memory Window
<img width="676" height="161" alt="image" src="https://github.com/user-attachments/assets/49874d17-5744-4def-beba-135fb4f18ff0" />



---
## RESULT:

Thus the sorting of given data was done using 8051 keil software.

