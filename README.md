# Litgrid analizė — V. Jasevičius

Trumpas aprašymas
-----------------
Šis projektas (Jupyter Notebook: `Litgrid_V_Jasevicius.ipynb`) atlieka faktinių elektros gamybos ir vartojimo duomenų analizę per paskutinius ~6 mėnesius. Tikslas — sujungti gamybos (hidro, saulė, vėjas, šiluminės, kaupimo ir kt.) ir vartojimo duomenis, apskaičiuoti suminę generaciją, disbalansą (generacija − vartojimas) ir pateikti vizualizacijas bei mėnesines suvestines (pvz., procentinę gamybos dalį pagal šaltinį).

Duomenų šaltiniai
-----------------
- Litgrid atviroji API (`https://openapi.litgrid.eu/v1`) — gamybos ir vartojimo kategorijos.

Trumpas veikimo aprašas
-----------------------
1. Užklausa į Litgrid API pagal reikalingas gamybos ir vartojimo kategorijas.
2. Gavusių įrašų konvertavimas į pandas DataFrame ir filtravimas paskutiniams ~180 dienų.
3. Duomenų pivot’inimas (kiekviena gamybos kategorija — atskiras stulpelis).
4. Gamybos ir vartojimo sujungimas pagal laiką.
5. Apskaičiavimai:
   - Suminė generacija (MW)
   - Disbalansas = Suminė generacija − Vartojimas
   - Kiekvieno šaltinio procentinė dalis (mėnesinės suvestinės)
6. Vizualizacijos: laiko eilutės (generacija vs vartojimas), disbalanso grafikas, mėnesinės apskritiminės diagramos.


