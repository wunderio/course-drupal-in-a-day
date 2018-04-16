# Valmistautumisohjeet

Seuraavasti valmistautumalla saat päivästä eniten irti, mutta ei hätää, ilmankin pärjää. Kaverin kimppaan voi liittyä, jos kone hyytyy, ja asennuksiin saa apua ennen kurssin alkua. Pääasia, että saavut paikalle!

## Kannettava tietokone

Harjoituksiin sopii parhaiten kannettava tietokone, jossa on Linux, MacOS tai Windows 10 Pro käyttöjärjestelmä. Mutta tähän homma ei kaadu; minimivaatimus on, että olet itse paikalla, ja pitkälle pääsee jo sillä, että on tietokone, jossa on USB-portti.

## USB-portti?

Mikäli yhteensopivaa tietokonetta ei löydy, tai kehitysympäristön asentaminen ei onnistu/nappaa, on käytössä myös USB-tikkuja, joilta tietokoneen voi käynnistää suoraan kehitysympäristöön. Tällöin koneesi käynnistetään Linux-käyttöjärjestelmään, jossa on tarvittavat ohjelmistot esiasennettuina. Tämä USB-tikulta käynnistäminen ei tee muutoksia tietokoneesi omaan järjestelmään, mutta koneen oman käyttöjärjestelmän käyttö ei onnistu yhtäaikaa kehitysympäristön ollessa käynnissä. Huomaathan napata kyytiin myös mahdollisen lisälaitteen, jos koneestasi ei löydy omaa USB-porttia.

## Kehitysympäristön asentaminen

Omalle koneelle asennettava kehitysympäristö on Drupal-kehityksen tärkeimpiä työkaluja ja suosittelemmekin ainakin kokeilemaan sen asennusta. **Meiltä saat myös asennusapua paikan päällä tunnin ajan ennen kurssin aloitusta**, joten tulethan tällöin hyvissä ajoin.

### 1) Asenna Docker
Käyttöjärjestelmäkohtaiset asennusohjeet löydät alta. Asenna **stable**-versio.

Windows 10 Pro

* https://docs.docker.com/docker-for-windows/install/

MacOS

* https://docs.docker.com/docker-for-mac/install/

Linux

* Mene sivulle https://docs.docker.com/install/#server
* Etsi DOCKER CE-taulukosta oma Linux-jakelusi ja seuraa linkkiä asennusohjeisiin.

Windows / MacOS: Käynnistä Docker ikonista

### 2) Avaa komentorivi / komentokehote / pääte / terminaali
Windows 10 Pro

* Power Shell

MacOS & Linux

* Pääte / Terminal

### 3) Lataa Drupalin levykuva

Aja komentorivillä seuraava komento:
```
docker pull drupal
```

### 4) Käynnistä Drupal

Aja komentorivillä seuraava komento:

```
docker run -d -p 80:80 drupal
```

Kyseinen komento käynnistää Drupalin taustalle. Saat komennon vastaukseksi kontin instanssin tunnisteen, joka näyttä esimerkiksi tältä: `bd98dade2cac33b20dfe7516dc0a3f0991a502e7a3aa8e27485bbc64dccdcaa3`

### 5) Testaa

* Avaa selain
* Mene osoitteeseen http://localhost

Voilà! Olet valmis.

![Kuvakaappaus Drupalin asennusruudusta](/img/screenshot-install-drupal.png)

### 6) Drupalin pysäyttäminen ja uudelleenkäynnistäminen
Mikäli olet sammuttanut tai uudelleenkäynnistänyt koneen. Sinun tulee käyninstää Drupal uudelleen.

Käynnistä kontti uudelleen seuraavalla komennolla:

```
docker start bd98dade2cac33b20dfe7516dc0a3f0991a502e7a3aa8e27485bbc64dccdcaa3
```

Vois myös pysäyttää kontin milloin vain käyttämällä seuraavaa komentoa:

```
docker stop bd98dade2cac33b20dfe7516dc0a3f0991a502e7a3aa8e27485bbc64dccdcaa3
```

*Vinkki: Voit käyttää koko tunnisteen sijasta ensimäiset kolme kirjainta. Docker päättelee sen perusteella, mitä varsinaista konttia haluat komentaa. Mikäi kaksi samanlaista kolmen kirjaimen alkuista konttia löytyy, joudut tarkentamaan käyttämällä neljä tai useampaa merkkiä merkkijonon alusta.*

### Apua!
Ei hätää, meiltä saat asennusapua tuntia ennen kurssipäivän alkua, eli tervetuloa paikalle jo hyvissä ajoin.
