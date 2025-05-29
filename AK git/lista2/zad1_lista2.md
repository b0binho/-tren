## Kod źródłowy:

```asm
    .global _start

_start:
    MOV R0, #42       @ Załaduj wartość 42 do rejestru R0
    MOV R1, R0        @ Skopiuj wartość z R0 do R1

    MOV R7, #1        @ Kod systemowy 1 = sys_exit (Linux)
    MOV R0, #0        @ Kod wyjścia 0 (brak błędu)
    SVC 0             @ Wywołanie systemowe