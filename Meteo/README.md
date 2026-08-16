Meteorologinių duomenų apdorojimo sistemos kūrimas

1. Duomenų nuskaitymo klasės realizacija
Sukurta Python klasė, užtikrinanti sistemingą duomenų gavimą iš api.meteo.lt šaltinio.
Objekto parametrai: Klasė inicializuojama nurodant vietovės kodą ir API bazinį adresą.
a) Metodas get_history: Nuskaito istorinius duomenis nurodytam intervalui (nuo–iki).
Rezultatas grąžinamas kaip pandas.DataFrame su pd.DatetimeIndex.
b) Metodas get_forecast: Nuskaito naujausius prognozės duomenis pasirinktai
vietovei.
Struktūra: Abiem atvejais užtikrinama, kad duomenys būtų pateikiami tvarkingu lentelės
formatu, tinkamu tiesioginei analizei.

2. Istorinių duomenų analizė (Praėję metai)
Atliktas duomenų apdorojimas už 12 mėnesių laikotarpį. Skaičiavimų rezultatai:
a) Vidurkiai: Apskaičiuota vidutinė metų temperatūra ir vidutinė oro drėgmė.
b) Paros ciklas ir laiko zonos: Šiame etape duomenys konvertuoti į Lietuvos laiko zoną
(Europe/Vilnius). Tai leido tiksliai identifikuoti dienos (08:00–20:00) ir nakties valandas
bei apskaičiuoti atitinkamus temperatūros vidurkius.
c) Kritulių prognozė savaitgaliais: Analizuota, kiek savaitgalių (šeštadienis/sekmadienis)
per metus turėjo lietaus prognozę, remiantis nurodytais kriterijais.

3. Duomenų apjungimas ir vizualizacija
Sukurta temperatūros kitimo diagrama, sujungianti praeitį ir ateitį:
Atvaizduojama paskutinės savaitės (7 dienų) faktinė išmatuota temperatūra.
Grafikas papildytas prognozės duomenimis, leidžiančiais vizualiai palyginti praėjusio
laikotarpio tendencijas su numatomais pokyčiais.

4. Aukšto dažnio duomenų interpoliacija
Sukurta funkcija duomenų detalumui padidinti:
Funkcionalumas: Priima temperatūros pandas.Series (valandinį dažnį).
Interpoliacija: Naudojant linijinį metodą, duomenys tankinami iki 5 minučių dažnio.
Panaudojimas: Tai leidžia gauti tolygų temperatūros kreivės modelį, užpildant tarpus
tarp valandinių matavimų.

Išvados
Sukurta programa sėkmingai realizuoja REST API duomenų surinkimą, jų transformaciją ir
specifinę analizę. Sprendimas pasižymi modularumu (atskira klasė duomenims), tikslumu (laiko
zonų įvertinimas skaičiuojant paros ciklus) ir duomenų praturtinimu (interpoliacija).
