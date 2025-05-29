## Kod źródłowy:

```asm
    .global _start

    .data
memory: .word 0      @ Zarezerwowane miejsce w pamięci na dane

    .text

_start:
    MOV R0, #100          @ Załaduj wartość 100 do R0
    LDR R2, =memory       @ Załaduj adres etykiety 'memory' do R2
    STR R0, [R2]          @ Zapisz wartość z R0 pod adres wskazany przez R2
    LDR R1, [R2]          @ Załaduj wartość z pamięci (adres w R2) do R1

    MOV R7, #1            @ Kod systemowy 1 = sys_exit
    MOV R0, #0            @ Kod wyjścia programu
    SVC 0                 @ Wywołanie systemowe