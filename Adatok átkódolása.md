---
tags:
  - Egyetem
  - note
  - unsupervisedlearning
status: Clean
---
**Dummy változó:** Csak bináris értéket vehet fel. Kvalitatív változót kvantitatívvá alakítjuk.
(igen/nem -> 1/0)
## Eszközök
### One-Hot Encoding
- Tetszőleges kategorikus változót dummy változókká alakít.
- Pl.: 'szak' -> 'szak_GI', 'szak_PI', 'szak_MI'

#### Hány dummy változóra van szükség?
- **Triviális kódolás:** Minden lehetséges értéknek egy dummy változó

| ID  |     Név     | Szak_GI | Szak_PI | Szak_MI |
| :-: | :---------: | :-----: | :-----: | :-----: |
|  1  | Kiss Aranka |  **1**  |    0    |    0    |
|  2  | Tóth János  |    0    |  **1**  |    0    |
|  3  | Nagy Péter  |    0    |    0    |  **1**  |
|  4  |  Nagy Ábel  |    0    |  **1**  |    0    |
- **Referencia kódolás:** Minden dummy változó 0 értéket vesz fel, mint egy referencia csoport.

| ID  |     Név     | Szak_GI | Szak_PI |
| :-: | :---------: | :-----: | :-----: |
|  1  | Kiss Aranka |  **1**  |    0    |
|  2  | Tóth János  |    0    |  **1**  |
|  3  | Nagy Péter  |    0    |    0    |
|  4  |  Nagy Ábel  |    0    |  **1**  |
#### Dummy változó csapda
Függetlennek tekintett változók között multikollinearitás áll fenn. Triviális kódolás esetén az egy változó értéke meghatározható a többi változó értékéből, mert egyik változó értéke megjósolható a többi változó lineáris kombinációjaként.

### Label Encoding
Kategorikus változókat (abc sorrend alapján) egyedi egész értékekkel helyettesíti
- a megfeleltetés egy-az-egyhez típusú és illesztéssel (fit, fit_transform) jön létre
- mivel egy-az-egyhez megfeleltetés jön létre, ezért létezik hozzá dekóder is, ami az ellentétel konverziót valósítja meg

| ID (Eredeti) |     Név     |       Szak (Eredeti)        |     | ID (Kódolt) |     Név     | Szak (Kódolt) |
| :----------: | :---------: | :-------------------------: | :-: | :---------: | :---------: | :-----------: |
|      1       | Kiss Aranka |    gazdaságinformatikus     |  →  |      1      | Kiss Aranka |       0       |
|      2       | Tóth János  | programtervező informatikus |  →  |      2      | Tóth János  |       2       |
|      3       | Nagy Péter  |     mérnökinformatikus      |  →  |      3      | Nagy Péter  |       1       |
|      4       |  Nagy Ábel  | programtervező informatikus |  →  |      4      |  Nagy Ábel  |       2       |
#### Kihívások
- Kategorikus értékekből gyakorlatilag ordinális értékekre cseréltük
- Fenn áll a veszély, hogy a modell elkezdi figyelni a sorrendi kapcsolatot

### Melyiket válasszam?
- **One-Hot Encoding**
	- Kategorikus értékek nem ordinálisak
	- Kategorikus értékek száma viszonylag alacsony
- **Label Encoding**
	- Kategorikus értékek ABC sorrend szerint ordinálisak (pl.: ált. iskola, gimi, Bsc, ...)
	- Kategorikus értékek száma meglehetősen magas, ezért One-Hot Encoding nagy memóriát enne

> **Fontos:** Vegyük figyelembe, hogy milyen modellel akarunk dolgozni!

### Ordinal Encoding
Az ordinális sztring értékű változókat megadott sorrend alapján egyedi egész értékekkel helyettesíti
- A megfeleltetés egy-az-egy típusú és illesztéssel (*fit*, *fit_transform*) jön létre.
- Mivel egy-az-egy megfeleltetés jön létre, ezért létezik hozzá dekóder is, ami az ellentétes konverziót valósítja meg.

**Előtte**

| ID  | Név         | Iskolai végzettség |
| --- | ----------- | ------------------ |
| 1   | Bármi Áron  | Egyetem BSc        |
| 2   | Pál Kata    | Egyetem MSc        |
| 3   | Tóth Aranka | Középiskola        |
| 4   | Kakukk Tom  | ?                  |

**Utána**

| ID | Név         | Szak |
|----|------------|------|
| 1  | Bármi Áron  | 1    |
| 2  | Pál Kata    | 3    |
| 3  | Tóth Aranka | 0    |
| 4  | Kakukk Tom  | 2    |
