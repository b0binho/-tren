## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #30          @ Załaduj 30 do R0
    MOV R1, #10          @ Załaduj 10 do R1

    ADDS R2, R0, R1      @ Dodaj R0 + R1 => R2, ustaw flagi
    SUBS R3, R2, R1      @ Odejmij R1 od R2 => R3, ustaw flagi

    CMP R3, #30          @ Porównaj R3 z 30
    BEQ sukces           @ Jeśli równe, przejdź do sukces
    BNE blad             @ Jeśli nie, przejdź do blad

sukces:
    MOV R7, #1           @ sys_exit
    MOV R0, #0           @ Kod wyjścia 0 (OK)
    SVC 0

blad:
    MOV R7, #1           @ sys_exit
    MOV R0, #1           @ Kod wyjścia 1 (błąd)
    SVC 0
