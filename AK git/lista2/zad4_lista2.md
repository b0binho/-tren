## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #15         @ A = 15
    MOV R1, #25         @ B = 25
    MOV R2, #10         @ C = 10
    MOV R3, #5          @ D = 5

    ADD R4, R0, R1      @ R4 = A + B = 15 + 25 = 40
    SUB R5, R2, R3      @ R5 = C - D = 10 - 5 = 5
    SUB R6, R4, R5      @ R6 = R4 - R5 = 40 - 5 = 35

    CMP R6, #35         @ Porównaj wynik z oczekiwaną wartością
    BEQ sukces
    BNE blad

sukces:
    MOV R7, #1          @ sys_exit
    MOV R0, #0          @ Kod wyjścia 0 = OK
    SVC 0

blad:
    MOV R7, #1          @ sys_exit
    MOV R0, #1          @ Kod wyjścia 1 = błąd
    SVC 0
