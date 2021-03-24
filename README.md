# statfin2powerbi
Näillä PBI-malleilla on tarkoitus helpottaa Statfin-rajapinnan hyödyntämistä Power BI:ssä.

Tilastokeskuksella on useita avoimia tietokantoja (https://www.stat.fi/tup/tilastotietokannat/index.html), joista voi noutaa dataa REST API -rajapinnan kautta.
Power BI:ssa voi lähettää POST-kutsuja, johon saa vastauksena datasetin arvot sekä listan avaimista, joita arvot esittävät. Avaimien yhdistäminen on tehtävä itse oikealla tavalla. Nämä Power BI -mallit piilottavat sen kompleksisuuden. Käyttäjän täytyy vain valita sopiva malli perustuen siihen kuinka monta tietojoukkoa (dimensiota) datasetissä on, ja kopioida Tilastokeskuksen sivulta rajapintakutsun osoite ja sisältö.

Tässä ohjeet datan tuomiseen Power BI:hin.

1. Valitse verkkokäyttöliittymässä taulukko, jonka haluat tuoda, esim. väestön ennakkotiedot (https://pxnet2.stat.fi/PXWeb/pxweb/fi/StatFin/StatFin__vrm__vamuu/statfin_vamuu_pxt_11lj.px/).
2. Valitse valintalaatikoista tiedot, jotka haluat tuoda. Valitse 'näytä taulukko'.
3. Avaa uusi PowerBI-tiedosto, valitse Tiedostot-->Tuo-->Power BI -malli. Valitse tämän projektin pakatusta kansiosta, malli, jossa dimensioita, eli tietoja, joita valitsit (Ikä, sukupuoli, aika, jne.). Dimensioiden nimi on ilmoitettu mallin nimessä numerolla (esim. Tilastokeskus_4 on neljän dimension malli).
4. Avaa kyselyeditori. Seuraavaksi pitää korvata url -ja body -kyselyn sisältö vastaavilla arvoilla.
5. Tilastokeskuksen sivuilta, jossa valitsemasi taulukko on, skrollaa alas ja valitse 'Lisää taulukko sovellukseesi'. Kopioi URL-kentän arvo ja liitä se Power BI:ssä url-kyselyn arvoksi. Samoin tavoin kopioi JSON Query -kentän arvo ja liitä se Power BI:ssä body-kyselyn arvoksi.
6. Kyselyn data päivittyy nyt Data-nimiseen kyselyyn Query editorissa.

Vastaan voi tulla ongelmia, jos haet liikaa dataa kyselyssäsi. Tällöin voit kokeilla uudestaan valitsemalla pienemmän määrän muuttujia tietokentissä.

Mukana on myös malli ilman datasetin muodostamista sekä malli, jossa Turun tilastollinen aluejako valmiina.

