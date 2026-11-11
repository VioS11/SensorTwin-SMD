# Data Card – Server Machine Dataset (SMD)

SMD este un dataset pentru detecția anomaliilor în **serii temporale multivariate**, format din date de monitorizare provenite de la **28 de servere**, fiecare având **38 de features**.

**Sursă:**  
Server Machine Dataset (SMD), publicat în repository-ul **OmniAnomaly – NetManAIOps**:  
https://github.com/NetManAIOps/OmniAnomaly/tree/master/ServerMachineDataset  
Lucrare asociată: Su et al. (2019), *Robust Anomaly Detection for Multivariate Time Series through Stochastic Recurrent Neural Network*.

**Perioadă:**  
Datasetul conține **708.405 observații train** și **708.420 observații test**, în total **1.416.825 observații** pentru cele 28 de servere. Durata monitorizării poate fi estimată presupunând o observație pe minut, dar nu poate fi verificată exact în lipsa timestamp-urilor.

**Rezoluție temporală:**  
Aproximativ **1 observație/minut**. Timestamp-urile explicite nu sunt incluse; ordinea rândurilor reprezintă succesiunea temporală.

**Unități:**  
Fiecare server are **38 de dimensiuni/features**. Denumirile și unitățile individuale ale acestor variabile nu sunt specificate explicit în documentația originală.

**Goluri / valori lipsă:**  
Valorile lipsă și coloanele constante sunt verificate separat pentru fiecare server, pe seturile train și test. Numărul acestora este raportat în tabelul de analiză de mai jos. Golurile temporale nu pot fi verificate direct, deoarece datasetul nu conține timestamp-uri explicite.

**Împărțire train/test:**  
Datasetul conține **28 de subseturi**, câte unul pentru fiecare server. Fiecare subset este împărțit cronologic în două părți aproximativ egale: **train** și **test**.

Setul de test este însoțit de:
- `test_label` – indică dacă fiecare timestep este normal (0) sau anomal (1);
- `interpretation_label` – indică dimensiunile asociate anomaliilor.

Cele 28 de servere sunt antrenate și evaluate independent.

**Distribuția anomaliilor:**  
Numărul și procentul observațiilor anormale sunt calculate separat pentru fiecare server, folosind etichetele din `test_label`.

Distribuția diferă între servere, iar anomaliile reprezintă o clasă minoritară. Rezultatele sunt prezentate în tabelul următor.

**Tabel – Statistici calculate pentru cele 28 de servere SMD**


| Machine      |  Train points |  Test points |  Anomalies |  Anomalies (%) |  Train missing |   Test missing |  Constant train |  Constant test |
|:-------------|--------------:|-------------:|-----------:|---------------:|---------------:|---------------:|----------------:|---------------:|
| machine-1-1  |         28479 |        28479 |       2694 |           9.46 |              0 |              0 |               8 |              6 |
| machine-1-2  |         23694 |        23694 |        542 |           2.29 |              0 |              0 |               5 |              5 |
| machine-1-3  |         23702 |        23703 |        817 |           3.45 |              0 |              0 |               4 |              4 |
| machine-1-4  |         23706 |        23707 |        720 |           3.04 |              0 |              0 |               4 |              4 |
| machine-1-5  |         23705 |        23706 |        100 |           0.42 |              0 |              0 |               8 |              8 |
| machine-1-6  |         23688 |        23689 |       3708 |          15.65 |              0 |              0 |               5 |              4 |
| machine-1-7  |         23697 |        23697 |       2398 |          10.12 |              0 |              0 |               4 |              4 |
| machine-1-8  |         23698 |        23699 |        763 |           3.22 |              0 |              0 |               8 |              8 |
| machine-2-1  |         23693 |        23694 |       1170 |           4.94 |              0 |              0 |               5 |              5 |
| machine-2-2  |         23699 |        23700 |       2833 |          11.95 |              0 |              0 |               7 |              7 |
| machine-2-3  |         23688 |        23689 |        269 |           1.14 |              0 |              0 |               7 |              6 |
| machine-2-4  |         23689 |        23689 |       1694 |           7.15 |              0 |              0 |               8 |              8 |
| machine-2-5  |         23688 |        23689 |        980 |           4.14 |              0 |              0 |               7 |              7 |
| machine-2-6  |         28743 |        28743 |        424 |           1.48 |              0 |              0 |               8 |              8 |
| machine-2-7  |         23696 |        23696 |        417 |           1.76 |              0 |              0 |               8 |              7 |
| machine-2-8  |         23702 |        23703 |        161 |           0.68 |              0 |              0 |               7 |              4 |
| machine-2-9  |         28722 |        28722 |       1755 |           6.11 |              0 |              0 |               8 |              8 |
| machine-3-1  |         28700 |        28700 |        308 |           1.07 |              0 |              0 |               8 |              7 |
| machine-3-10 |         23692 |        23693 |       1047 |           4.42 |              0 |              0 |               9 |              9 |
| machine-3-11 |         28695 |        28696 |        198 |           0.69 |              0 |              0 |               9 |              8 |
| machine-3-2  |         23702 |        23703 |       1109 |           4.68 |              0 |              0 |               6 |              6 |
| machine-3-3  |         23703 |        23703 |        632 |           2.67 |              0 |              0 |               2 |              3 |
| machine-3-4  |         23687 |        23687 |        977 |           4.12 |              0 |              0 |               8 |              8 |
| machine-3-5  |         23690 |        23691 |        426 |           1.8  |              0 |              0 |              10 |              8 |
| machine-3-6  |         28726 |        28726 |       1194 |           4.16 |              0 |              0 |               8 |              7 |
| machine-3-7  |         28705 |        28705 |        434 |           1.51 |              0 |              0 |               5 |              5 |
| machine-3-8  |         28703 |        28704 |       1371 |           4.78 |              0 |              0 |               8 |              7 |
| machine-3-9  |         28713 |        28713 |        303 |           1.06 |              0 |              0 |               8 |              7 |


**Licență:**  
Repository-ul OmniAnomaly este distribuit sub **MIT License**. Nu este specificată separat o licență distinctă pentru fișierele SMD.