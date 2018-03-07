# HW

ExitProcess proto
.data

source BYTE "This is the source string" ,0
target BYTE SIZEOF source DUP('#')


.code
main proc
	mov esi, SIZEOF source
	mov ecx, SIZEOF source
	mov edx, 0



MYLOOP:
	mov al, [source +esi-1]         ; get a character from source
	mov [target + edx],al        ; store it in the target
	inc edx                ; move to next character
	dec esi
   
	
	loop MYLOOP

   call ExitProcess
main endp
end
