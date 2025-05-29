## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #7           @ Mnożna: 7
    MOV R1, R0           @ Początkowy wynik = 7

    ADDS R1, R1, R0      @ R1 = R1 + 7 => 14
    ADDS R1, R1, R0      @ R1 = R1 + 7 => 21

    CMP R1, #21          @ Czy wynik to 21?
    BEQ sukces
    BNE blad

sukces:
    MOV R7, #1           @ sys_exit
    MOV R0, #0           @ Kod wyjścia 0 (OK)
    SVC 0

blad:
    MOV R7, #1           @ sys_exit
    MOV R0, #1           @ Kod wyjścia 1 (błąd)
    SVC 0
