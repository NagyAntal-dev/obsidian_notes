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
# Attribútum értékének skálázása
## Tartalom
Az attribútum értékének skálázása a Data Science egyik alapvető lépése, melynek célja, hogy a különböző jellemzők (feature-ök) értéktartományát összehangoljuk. Ez nemcsak a modellek konvergenciáját segíti elő, hanem javítja a gépi tanulási algoritmusok teljesítményét is.

---
#### 1. Tulajdonság Skálázása vs. Normalizálás

- **Tulajdonság skálázása (Feature Scaling):**  
    Ebben az esetben az adatok tartománya változik úgy, hogy az értékek relatív sorrendje megmarad, de az abszolút értékek átskálázódnak egy előre meghatározott intervallumba (például \[0, 1\] vagy \[-1, 1\]).  
    _Példa:_ Min-max skálázás, ahol az új értékeket az alábbi képlettel számoljuk:  
    $xscaled= \frac{x - \min(x)}{\max(x) - \min(x)}​$
    
- **Normalizálás (Normalization):**  
    Itt az adatok eloszlása megváltozik. A cél az, hogy az adatokat egy adott eloszlás (például normális eloszlás) felé transzformáljuk. Ez különösen hasznos, ha az adatok nem normál eloszlásúak, mivel egyes algoritmusok (pl. lineáris regresszió) jobban működnek normális eloszlású bemenetekkel.
---
#### 2. Gyakorlati Megfontolások

- **Miért fontos a skálázás?**
    
    - Sok gépi tanulási algoritmus (például k-NN, SVM vagy neurális hálózatok) érzékenyek a különböző skálájú attribútumokra, ezért az egységesítés javítja a modell teljesítményét.
    - Az optimalizációs algoritmusok gyorsabban konvergálnak, ha az inputok közel azonos nagyságrendűek.
- **Mikor melyiket érdemes alkalmazni?**
    
    - **Skálázás** akkor előnyös, ha az adatok relatív eloszlása fontos, de nem feltétlenül kell átalakítani az eloszlást.
    - **Normalizálás** különösen akkor hasznos, ha az adatok nem normális eloszlásúak, és egy adott algoritmus érzékeny az eloszlás formájára.
---
### Módszerek
- [[Min-Max Skálázás]]
- [[Z-Score]]
- [[L-norma]]
- [[Normalizáció Decimális Skálázással]]
- [[Log Transzformáció]]
## Összegzés
- 

## Hivatkozások
- 
