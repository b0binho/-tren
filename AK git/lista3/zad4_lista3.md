## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #12          @ Liczba A
    MOV R1, #25          @ Liczba B
    MOV R2, #18          @ Liczba C

    CMP R0, R1
    BGT r0_wieksze
    MOV R3, R1           @ Jeśli R1 >= R0, R3 = R1
    B porownaj_z_r2

r0_wieksze:
    MOV R3, R0           @ Jeśli R0 > R1, R3 = R0

porownaj_z_r2:
    CMP R3, R2
    BGT koniec           @ Jeśli R3 > R2, zostaje w R3
    MOV R3, R2           @ Jeśli R2 >= R3, R3 = R2

koniec:
    MOV R7, #1           @ sys_exit
    MOV R0, #0
    SVC 0