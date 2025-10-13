
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character
```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B'
WAIT:JNB TI, WAIT
CLR TI 
END
```
### (ii) Serial Port to Transfer a Message
```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ  B,AGAIN
END
```

### OUTPUT:
<img width="1920" height="1200" alt="Screenshot (179)" src="https://github.com/user-attachments/assets/e825b292-c75d-4ad0-a1e8-8dcbe8bf483d" />

<img width="1920" height="1200" alt="Screenshot (181)" src="https://github.com/user-attachments/assets/6d074d8a-56f0-4932-b455-57d4e1296938" />


### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
