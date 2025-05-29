## Kod źródłowy: 

```asm
    .global _start

_start:
    MOV R0, #5           @ Przykładowa wartość A
    MOV R1, #5           @ Przykładowa wartość B

    CMP R0, R1           @ Porównanie R0 i R1
    BEQ rowne            @ Jeśli równe -> skok do etykiety 'rowne'
    BNE rozne            @ Jeśli różne -> skok do etykiety 'rozne'

rowne:
    MOV R2, #1           @ Liczby są równe – R2 = 1
    B koniec

rozne:
    MOV R2, #0           @ Liczby są różne – R2 = 0

koniec:
    MOV R7, #1           @ sys_exit
    MOV R0, #0           @ Kod wyjścia
    SVC 0
