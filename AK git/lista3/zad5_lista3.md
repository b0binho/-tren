## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #8          @ Pierwsza liczba
    MOV R1, #12         @ Druga liczba

    BL max2             @ Wywołanie podprogramu

    @ R0 zawiera teraz większą z dwóch liczb

    MOV R7, #1          @ sys_exit
    MOV R0, #0
    SVC 0

@ ===== Podprogram max2 =====
@ Wejście: R0, R1
@ Wyjście: R0 = max(R0, R1)

max2:
    CMP R0, R1          @ Porównanie R0 z R1
    BGE ret             @ Jeśli R0 >= R1, pozostaje w R0
    MOV R0, R1          @ Jeśli R1 > R0, przepisz R1 do R0

ret:
    BX LR               @ Powrót z podprogramu