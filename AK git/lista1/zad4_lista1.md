##  Pytanie 4
###  W jaki sposób dodajemy dwie liczby w asemblerze ARM? Jaka będzie składnia dodawania wartości z R1 i R2 i umieszczenia wyniku w R0?

Używamy instrukcji `ADD` w formacie:

**Przykład:**
```asm
ADD R0, R1, R2   @ R0 = R1 + R2
```

