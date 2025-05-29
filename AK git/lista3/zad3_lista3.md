## Kod źródłowy:

```asm
    .global _start

_start:
    LDR R0, =liczba      @ Załaduj adres liczby do R0
    LDR R0, [R0]         @ Załaduj wartość liczby do R0

    CMP R0, #0           @ Porównaj z zerem
    BGE koniec           @ Jeśli R0 >= 0, przejdź do końca

    RSB R0, R0, #0       @ R0 = 0 - R0 (oblicz wartość bezwzględną)

koniec:
    MOV R7, #1           @ sys_exit
    MOV R1, R0           @ Zapisz wartość R0 do R1 (opcjonalnie: wynik)
    MOV R0, #0
    SVC 0

.data
liczba: .word -5         @ Można zmieniać na 10, 0, -5 itd.