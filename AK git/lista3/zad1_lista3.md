## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #5           @ Ustaw R0 = 5
    B dalej              @ Skocz bezwarunkowo do etykiety 'dalej'

    MOV R0, #10          @ (ta instrukcja zostanie pominięta)

dalej:
    MOV R1, #1           @ Potwierdzenie działania skoku – ustaw R1 = 1

    MOV R7, #1           @ sys_exit
    MOV R0, #0           @ Kod wyjścia 0 (sukces)
    SVC 0
