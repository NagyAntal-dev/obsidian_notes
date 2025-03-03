---
title:
  "{ title }": 
created:
  "{ date }": 
tags:
  - note
  - Egyetem
  - unsupervisedlearning
area:
---
# Z-Score
## Tartalom
A Z-score standardizáció segítségével minden attribútumot úgy transzformálunk, hogy azok középértéke 0, szórása pedig 1 legyen. Így minden változó egy összehasonlítható skálára kerül, és a modell nem torzul el a különböző mértékegységek miatt.
### Hogyan számítjuk ki a Z-score-t?

A Z-score számítása a következő képlettel történik:

$$Z = \frac{(X - \bar{x}_{A})}{S_{A}}$$
ahol:
- **$X$**: az eredeti adatpont
- **$\bar{x}_{A}$**: az adott attribútum átlaga
- **$S_{A}$**: az adott attribútum szórása

Ez a transzformáció azt jelenti, hogy minden adatpont relatív távolságát az átlagtól fejezzük ki, a szórás mértékegységének segítségével.

---
### Miért előnyös a Z-score alapú skálázás?

1. **Összehasonlíthatóság:**  
    Az összes attribútum azonos skálára kerül, így a különböző jellemzők hatását a modell kiegyensúlyozottan tudja kezelni.
    
2. **Modellek teljesítménye:**  
    Sok gépi tanulási algoritmus, például a K-nn, a SVM vagy a neurális hálózatok érzékenyek az adatok skálájára. A standardizáció javíthatja a konvergencia sebességét és a modell általános teljesítményét.
    
3. **Normalizált eloszlás:**  
    Bár a Z-score önmagában nem alakítja át az eloszlás alakját normál eloszlássá, a standardizált változók segítségével könnyebb azonosítani azokat az adatpontokat, amelyek jelentősen eltérnek a többitől (például anomáliák esetén).
---
### Mikor nem ajánlott a Z-score alapú skálázás?

- **Nem normális eloszlás:**  
    Ha az attribútumok eloszlása erősen ferde (skewed), előfordulhat, hogy a Z-score nem ad megfelelő eredményt. Ilyenkor más skálázási technikák, mint például a [[Min-Max Skálázás]], jobban működhetnek.
    
- **Robusztusság:**  
    A Z-score érzékeny az extrém értékekre (outlier-ekre). Ha az adathalmazban sok kiugró adat van, az átlag és szórás torzulhat, ezért érdemes lehet robusztusabb módszereket alkalmazni, például a medián és a kvartilis alapú skálázást.
## Összegzés
- A **Z-score skálázás** (standardizálás) egy olyan módszer, amely során az adatokat úgy transzformáljuk, hogy azok eloszlása nullához közeli átlagot és egységnyi szórást kapjon. A módszer lényege, hogy minden adatpontot az attribútum átlagához viszonyítunk, majd az eredményt elosztjuk a szórással.
- A Z-score skálázás különösen hasznos azoknál a gépi tanulási algoritmusoknál, amelyek feltételezik az adatok normális eloszlását, illetve amikor az attribútumok eltérő mértékegységekkel rendelkeznek.

## Hivatkozások
- 
