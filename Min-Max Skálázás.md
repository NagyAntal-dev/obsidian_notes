---
title:
  "{ title }": 
created:
  "{ date }": 
tags:
  - note
  - Egyetem
  - unsupervisedlearning
  - alapok
area:
---
# Min-Max Skálázás
## Tartalom
A **Min-Max skálázás** egy egyszerű és gyakran használt módszer az adatok előfeldolgozásában, melynek célja, hogy az egyes attribútumok értéktartományát egy előre meghatározott intervallumba (általában \[0, 1\] vagy \[-1, 1\]) transzformálja. Ezáltal az eltérő skálájú jellemzők összehasonlíthatóvá és egységesítettevé válnak, ami különösen fontos olyan gépi tanulási algoritmusoknál, amelyek érzékenyek a bemenetek relatív nagyságára.

#### Alapgondolat és Képlet

- **Cél:**  
    Az eredeti adatokat úgy transzformáljuk, hogy a legkisebb érték 0, a legnagyobb pedig 1 legyen (vagy tetszőleges megadott alsó és felső határ).
    
- **Képlet:**  
    Ha egy $x$ értékhez tartozik az eredeti skálán, az új érték $x_{\text{scaled}}$​ a következőképpen számolható:
    
    $$x_{\text{scaled}} = \frac{x - \min(x)}{\max(x) - \min(x)}​$$
    
    Itt:
    
    - $\min(x$) az adott attribútum legkisebb értéke,
    - $\max(x)$ az adott attribútum legnagyobb értéke.
- **Általánosítás:**  
    Ha egy adott intervallumra, például $[a, b]$ szeretnénk skálázni, akkor a képlet módosul:
    
    $$x_{\text{scaled}} = a + \frac{(x - \min(x))  (b - a)}{\max(x) - \min(x)}$$
#### Előnyök

- **Egyszerűség:**  
    A képlet könnyen érthető és implementálható.
    
- **Normalizált tartomány:**  
    Az értékek egy standardizált intervallumban lesznek, ami javítja a gépi tanulási modellek konvergenciáját és teljesítményét.
    
- **Összehasonlíthatóság:**  
    Az eltérő mértékegysékkel rendelkező attribútumok összevonhatóak, így a modell nem fog "túldominálódó" jellemzők miatt torzulni.
    
#### Hátrányok

- **Outlier-ek érzékenysége:**  
    Ha az adatok között szélsőséges értékek (outlier-ek) vannak, ezek jelentősen torzíthatják a skálázást, mivel a $\min(x)$ és $\max(x)$ értékek meghatározása ilyen esetben nem reprezentatív.
    
- **Dinamikus adatok esetén:**  
    Amennyiben az adatok folyamatosan változnak, az újonnan érkező értékek miatt a skálázás újraszámolása szükséges lehet.
---
## Példa
Tegyük fel, hogy egy adatsorban az értékek 50 és 200 között mozognak. Egy $x = 125$ érték átskálázása a $[0, 1]$ intervallumra így történik:

$$x_{\text{scaled}} = \frac{125 - 50}{200 - 50} = \frac{75}{150} = 0.5$$

Ez azt jelenti, hogy az $x=125$ az adatsor közepét képviseli.
