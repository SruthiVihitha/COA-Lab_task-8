Q 1. Write a program in assembly language to display a two-digit number on the screen. The two-digits number is required to be taken in the program itself.
CODE:
    org 100h

    mov al, 58d

    mov bl, 10
    div bl

    mov bh, al
    mov bl, ah
  
    mov ah, 09h       
    mov dx, OFFSET msg 
    int 21h  

    add bh, ‘0’             
    mov dl, bh
    mov ah, 02h
    int 21h   
    
    add bh, ‘0’             
    mov dl, bl
    mov ah, 02h
    int 21h    
    
    mov ah, 4ch 
    int 21h    
    
    msg DB 'The two digit number is: $'  

    END   
          
Output:
For 58d
![image](https://github.com/user-attachments/assets/fda9dea2-16ac-447a-addb-6377fe174fa0)

For 5Fh
![image](https://github.com/user-attachments/assets/65c398ea-b349-4914-83a7-c0d561b6e2c9)

 
Q 2. Write an assembly language program to take two single-digit integers from the user and print the result of addition on the screen.
CODE:
    org 100h

    mov dx, OFFSET msg_input1      
    mov ah, 09h       
    int 21h 

    mov ah, 01h       
    int 21h    
    sub al, ‘0’                   
    mov bl, al 

    mov dx, OFFSET msg_input2    
    mov ah, 09h            
    int 21h  

    mov ah, 01h       
    int 21h    
    sub al, ‘0’                   
    mov cl, al 

    add bl, cl
    add bl, ‘0’

    mov dx, OFFSET msg_output    
    mov ah, 09h       
    int 21h  

    mov dl, 0dh        
    mov ah, 02h 
    int 21h
    mov dl, 0Ah        
    int 21h

    mov ah, 4ch       
    mov 21h

msg_input  DB 'Enter the first single digit: $'  
msg_output DB 0Dh, 0Ah, 'Enter the second single digit: $'  
msg_error  DB 0Dh, 0Ah, 'The result of addition is: $ ‘

END   
          

Output:
![image](https://github.com/user-attachments/assets/e2947bd1-e21a-45ca-82f2-b20b6fcce9e3)
 




