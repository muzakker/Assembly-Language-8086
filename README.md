# Assembly-Language-8086
This repository represents the codes that was done a while ago, Spring-19. 
I was then a 3rd semester student. 
I took Computer Organization & Architecture (COA) course, that was the first where I truly understood the handiness of high-level programming languages.
I mean in my two semesters I did C and CPP both are high-level programming languages and things can be done so easily.
For instance, adding two numbers in a typical C++ programming language will be like this:
 
 #include<iostream.h>
 using namespace std;
 int main()
 {
    int a, b;
    cin >> a >> b;
    cout << a + b;
    return 0;
}

It gets even more easier for programming languages like python. But in assembly language which is a low-level language things get pretty messier than this.

.model small
.stack 100h
.data
msg1 db "Enter First Decimal Number : $"
msg2 db ,0dh,0ah,"Enter Second Decimal : $"
msg3 db ,0dh,0ah,"SUM of Entered Numbers = $"
num1 db ?;
num2 db ?,;
ans db ?,"$"
.code  
main proc 
    
mov ax,@data            ;initiaize ds
mov ds,ax  
mov dx,offset msg1      ;load and display msg1
mov ah,09
int 21h
mov ah,1h               ;read first initial
int 21h
sub al,30h
mov num1,al 
mov dx,offset msg2      ;load and display msg2
mov ah,9
int 21h
                        ;read second initial
mov ah,1h
int 21h
sub al,30h
mov num2,al
mov dx,offset msg3
mov ah,9                ;load and display msg3
int 21h
mov al,num1             ;add num1 and num2
add al,num2 
add al,30h              ;moves value into ans
mov ans,al
mov dx,offset ans       ;load and display msg3
mov ah,9
int 21h 
                        ;returns control to dos
mov ah, 4ch
int 21h 
main endp
end main                

This code is only for adding two single digits. (ref: http://code4beginner.com/8086/8086-Assembly-Language-Program-To-Add-Two-Single-Digit-Numbers.html)
It seems challenging at first, but I can assure you it is a lot more fun. 
For the first time I felt like I was talking to the machine itself, I can see the changes bit by bits.
It's surreal. 
