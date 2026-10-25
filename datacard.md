# Data Card – Server Machine Dataset (SMD)

SMD este un dataset pentru detecția anomaliilor în **serii temporale multivariate**, format din date de monitorizare provenite de la **28 de servere**, fiecare având **38 de features**.

**Sursă:**  
Server Machine Dataset (SMD), publicat în repository-ul **OmniAnomaly – NetManAIOps**:  
https://github.com/NetManAIOps/OmniAnomaly/tree/master/ServerMachineDataset  
Lucrare asociată: Su et al. (2019), *Robust Anomaly Detection for Multivariate Time Series through Stochastic Recurrent Neural Network*.

**Perioadă:**  
Aproximativ **5 săptămâni** de monitorizare.

**Rezoluție temporală:**  
Aproximativ **1 observație/minut**. Timestamp-urile explicite nu sunt incluse; ordinea rândurilor reprezintă succesiunea temporală.

**Unități:**  
Fiecare server are **38 de dimensiuni/features**. Denumirile și unitățile individuale ale acestor variabile nu sunt specificate explicit în documentația originală.

**Goluri / valori lipsă:**  
Documentația originală nu raportează explicit valori lipsă. Acestea sunt verificate programatic pentru fiecare subset înainte de preprocesare.

**Împărțire train/test:**  
Datasetul conține **28 de subseturi**, câte unul pentru fiecare server. Pentru fiecare server, seria temporală este împărțită cronologic în două părți aproximativ egale: **train** și **test**. Cele 28 de subseturi sunt antrenate și evaluate separat.

Setul de test este însoțit de:
- `test_label` – indică dacă fiecare timestep este normal sau anomal;
- `interpretation_label` – indică dimensiunile care contribuie la anomalie.

**Licență:**  
Repository-ul OmniAnomaly este distribuit sub **MIT License**. Nu este specificată separat o licență distinctă pentru fișierele SMD.