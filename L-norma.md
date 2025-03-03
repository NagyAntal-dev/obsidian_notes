---
title:
  "{ title }": 
created:
  "{ date }": 
tags:
  - note
  - unsupervisedlearning
  - Egyetem
area:
---
# L-norma
## Tartalom
**L-norma skálázás** egy olyan módszer, melynek célja, hogy az adatpontokat (általában vektorokként ábrázolt adatokat) egységnyi hosszúságúvá alakítsuk. Ezzel az adataink összehasonlíthatóbbá válnak, különösen olyan esetekben, ahol az irány (azaz az arányok) fontosabb, mint az abszolút értékek.

---
#### Alapfogalmak

- **Norma:**  
    A vektor „normája” a vektor hosszát jelenti. Két gyakran használt norma:
    
    - **L1 norma:** Az összes komponens abszolút értékeinek összege.
    - **L2 norma:** Az euklideszi távolság, azaz a komponensek négyzetösszegének négyzetgyöke.
- **Skálázás célja:**  
    Az adatpontokat úgy transzformáljuk, hogy:
    
    - Minden adatpont értékei egy adott intervallumon belül legyenek (általában egységnyi hosszúságúak).
    - Egységes megjelenést biztosítunk, ami segíti a modell tanulását és a minták felismerését.
---
#### Módszer

1. **Kiszámolás:**  
    Adott egy vektor $\mathbf{x} = [x_1, x_2, \dots, x_n]$.
    
    - Az **L1 norma**: $$||\mathbf{x}||_1 = |x_1| + |x_2| + \dots + |x_n|$$
    - Az **L2 norma**: $$||\mathbf{x}||_2 = \sqrt{x_1^2 + x_2^2 + \dots + x_n^2}$$
 2. **Skálázás:**  
	Az eredeti vektor minden egyes komponensét elosztjuk a választott norma értékével:
	$$\mathbf{x}_{\text{scaled}} = \frac{\mathbf{x}}{||\mathbf{x}||}$$​
	Így az új vektor normája 1 lesz.

---
#### Előnyök

- **Egységnyi hosszúság:**  
    Az így kapott vektorok egységesek, így az összehasonlítások (például koszinusz hasonlóság) egyszerűbbé válnak, mert az értékek relatív arányai lesznek a lényegesek.
    
- **Iránynak megfelelő összehasonlítás:**  
    Mivel a skálázás után az abszolút értékek kiesnek, az adatpontok közötti hasonlóságot főként a vektorok iránya határozza meg.
    
- **Alkalmazási területek:**  
    Gyakran használják szöveges adatok reprezentációjában (pl. TF-IDF vektorok), képfeldolgozásban és bármilyen olyan esetben, ahol a vektor irányának mérése fontos.
---
#### L1 vs. L2 Norma

- **L1 skálázás:**  
    Az adatok abszolút értékeinek összege alapján skáláz, ami bizonyos esetekben ritkás (sparse) vektoroknál előnyösebb lehet.
    
- **L2 skálázás:**  
    Az euklideszi távolságot használja, és gyakran jobban tükrözi a vektorok "térbeli" hosszát. Általánosabb esetben alkalmazzák, amikor az adatok normális eloszlásúak.
## Összegzés
Az L-norma skálázás lehetővé teszi, hogy az adataink – leggyakrabban vektorok formájában – egységes, normára skálázott formát öltsenek. Ez elősegíti a gépi tanulási modellek hatékonyabb tanulását és a hasonlóságok pontosabb mérését, hiszen a hangsúly az adatok relatív irányán van, nem pedig az abszolút értékeken.  

A választott norma (L1 vagy L2) függ a konkrét alkalmazástól és az adatok jellegétől.

## Hivatkozások
- 
