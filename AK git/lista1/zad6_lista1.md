##  Pytanie 6 
###  Dlaczego w przedstawionych programach na końcu wywoływana jest instrukcja SVC 0 z odpowiednimi wartościami w R7 i R0? Co by się stało, gdyby jej zabrakło?

Instrukcja `SVC 0` (Supervisor Call) służy do wywołania przerwania systemowego w celu wykonania operacji systemowej (np. zakończenia programu, wypisania tekstu na ekran itp.).

Rejestr **R7** zawiera numer wywołania systemowego, natomiast **R0** przekazuje argument (np. kod wyjścia programu).

Brak tej instrukcji spowodowałby, że program:
- nie zakończyłby się poprawnie,
- lub nie wykonałby operacji systemowej (np. nie wypisałby danych),
- potencjalnie zawiesiłby się lub uruchomił nieokreślone instrukcje.

**Przykład:**
```asm
MOV R7, #1     @ Kod systemowy 1 – zakończenie programu
MOV R0, #0     @ Kod wyjścia 0 – brak błędów
SVC 0          @ Wywołanie systemowe
```