org 7C00h
mov     ax, 07C0h
mov     ss, ax
mov     sp, 03FEh
xor     ax, ax
mov     ds,ax
mov     ah00h
mo      al,03h
int     10h
mov     ah, 02h
mov     al, 1
mov     ch, 0                   
mov     cl, 2
mov     dh, 0
mov     dl, 0
mov     bx, 0800h
mov     es, bx
mov     bx, 0
int     13h
jmp     0800h:0000h

or      0000h
push    cs
pop     ds
call crearscreen
lea si, mensagem 
mov ah,0eh
repetição 
mov al,[si]
cmp al,0h
jz terminou 
int 10h
inc si
jmp repetição 
terminou:
mov ah,0h
int 16h
mov ax,0040h
mov ds,ax
mov w.[0072h], 1234h
jmp 0FFFFh:0000h
mov     ah, 06h
mov     al, 0
mov     bh, 0000_1111b
clearscreen proc
mov     ch, 0         
    mov     cl, 0              
    mov     dh, 19h      
    mov     dl, 50h 
    int     10h
    popa
    ret
    clearscreen endp
    Mensagem db ‘Meu primeiro SO’,0
    
