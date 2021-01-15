# AP5 Pentest software : Reverse engineering

Hey u all,  
You will find in this repository some documentation along with exercices.   
You don't need to do it in order.  

Do not hesitate to ask me your questions.  



## Report guidelines

- Your report must contains the required content and has to be written in **Latex**  
- You start with 20 points. Each missing/wrong answer decrease your score by 1.5 point
- The report must be sent **before** the next classe. After that, you’ll lose 1 points per hour.


## Exercice 1: ASM master

You have an ASM code.
The goal is to explain its working line by line.

Can you translate it to C code ? (don’t include headers and main function)  

### Report content
- Copy the ASM code and comment each line. And write a global comment for each block of instruction.
```asm
; Put a string at the top of the stack
add     esp, 16 ; add 16 to the stack pointer
sub     esp, 12 ; substract 12 to the stack pointer
push    OFFSET FLAT:.LC2 ; push the address LC2 at the top of the stack
```
- Translate the code in C (use the appropriate latex listing (+0.5pts for proper syntax highlighting))



## Exercice 2: Dynamite Reverse

Today the 15th of january 1866. You’re a texas adventurer. (okay, imagine plz)
Your worst ennemy has created a C-software (again, imagine) which is controlling the burning of a dynamite stick.  
Figure out how to disarm this. 

Use the same methodology as seen during the classe.  

```bash
gcc -m32 -o dynamite.exe source.c  
strip dynamite.exe
```

### Report content 
- What is the secret PIN-Code ?
- Screenshot the Ghidra decompiled (and analysed) functions.
- Using static analysis, what are the steps for secret pin code hashing ? Write the secret pin code after each step. 
```
 Example:
 PIN CODE 6666
 Each pin code digit is divised by 2
 PIN CODE 3333
```
- Using dynamic analysis can you find a quicker way to obtain the code ?



## Exercice 3: Malware

Patrick from compta has discovered virus on his computer. You did an Incident response on his computer, and found out a strange file.
You decided to do some RE to analyse its behaviour. For that purpose you have created a secure environment in order to execute the file.  

**Do not worry for your computer, the file is harmless**    


```bash
gcc -m32 -o malware.exe source.c  
strip malware.exe
```

### Report content 
- Trace the software with strace. Explain the system calls you have found. 
- Which one is potentially dangereous ? Why ?
- Is there any way to prevent the virus damages ? Describe how.
