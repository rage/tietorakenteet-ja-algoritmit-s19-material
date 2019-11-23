---
path: '/viikko-13-dev'
title: 'Viikko 13: Komponentit ja virittävät puut'
overview: true
---

Viikon 13 tehtävien deadline: su 15.12. klo 23:59

## Tehtävät

<programming-exercise name='1. Komponentit' tmcname='viikko13-Viikko13Tehtava1'>

Tietoverkossa on `n` konetta (numeroitu 1, 2, ..., `n`),
joiden välillä ei ole alussa yhteyksiä
vaan jokainen kone on oma komponenttinsa.
Tehtäväsi on pitää kirjaa komponenttien määrästä,
kun verkkoon tulee yhteyksiä.

Tee luokka `Komponentit`, jossa on seuraavat metodit:

* `Komponentit(int n)`: koneiden määrä annetaan konstruktorissa
* `void yhdista(int a, int b)`:
  lisää yhteyden koneiden `a` ja `b` välille
* `int laske()`:
  ilmoittaa, montako komponenttia verkossa on

Rajat:

- 1 &le; `n` &le; 10<sup>5</sup>
- metodia `yhdista` kutsutaan enintään 10<sup>5</sup> kertaa
- metodia `laske` kutsutaan enintään 10<sup>5</sup> kertaa

Seuraava koodi esittelee luokan käyttämistä:

```java
Komponentit k = new Komponentit(5);
System.out.println(k.laske()); // 5
k.yhdista(1,2);
k.yhdista(2,3);
System.out.println(k.laske()); // 3
k.yhdista(1,3);
System.out.println(k.laske()); // 3
k.yhdista(4,5);
System.out.println(k.laske()); // 2
```

</programming-exercise>

<programming-exercise name='2. Kunnostus' tmcname='viikko13-Viikko13Tehtava2'>

Bittimaassa on `n` kaupunkia (numeroitu 1, 2, ..., `n`),
joiden välillä on teitä.
Tiet ovat kuitenkin huonossa kunnossa,
ja niitä aletaan kunnostaa.

Tavoitteena on, että kunnostuksen jälkeen minkä tahansa
kahden kaupungin välillä pystyy liikkumaan kunnostettuja teitä.
Mikä on pienin mahdollinen kustannus,
kun tiedät jokaisesta tiestä, paljonko sen kunnostus maksaa?


Tee luokka `Kunnostus`, jossa on seuraavat metodit:

* `Kunnostus(int n)`: kaupunkien määrä annetaan konstruktorissa
* `void lisaaTie(int a, int b, int x)`:
  lisää kaupunkien `a` ja `b` välille tien,
  jonka kunnostaminen maksaa `x`
* `int laske()`:
  ilmoittaa pienimmän kustannuksen teiden kunnostukseen
  (tai –1, jos tavoite ei ole mahdollinen)

Rajat:

- 1 &le; `n` &le; 10<sup>5</sup>
- 1 &le; `x` &le; 1000
- ensin metodia `lisaaTie` kutsutaan enintään 10<sup>5</sup> kertaa
- sitten metodia `laske` kutsutaan tasan kerran

Seuraava koodi esittelee luokan käyttämistä:

```java
Kunnostus k = new Kunnostus(4);
k.lisaaTie(1,2,1);
k.lisaaTie(1,3,4);
k.lisaaTie(2,3,6);
k.lisaaTie(2,4,5);
k.lisaaTie(3,4,3);
System.out.println(k.laske()); // 8
```

Selitys: paras ratkaisu on kunnostaa tiet
(1,2), (1,3) ja (3,4),
jolloin kaikkien kaupunkien välillä on yhteys ja
kunnostuksen hinta on 1 + 4 + 3 = 8.

</programming-exercise>

<quiz id="a2d1e216-81a8-4832-b59f-d73b6ff05a26"></quiz>

<programming-exercise name='4. Ruudukko' tmcname='viikko13-Viikko13Tehtava4'>

Ruudukossa on `n` &times; `n` ruutua,
ja jokainen ruutu on aluksi seinää.
Sitten ruudukkoon aletaan lisätä lattiaruutuja
yksi kerrallaan.
Tehtäväsi on pitää kirjaa,
montako huonetta ruudukossa on.
Kaksi lattiaruutua kuuluvat samaan huoneeseen,
jos ne ovat vierekkäin vaaka- tai pystysuunnassa.

Tee luokka `Ruudukko`, jossa on seuraavat metodit:

* `Ruudukko(int n)`: ruudukon koko annetaan konstruktorissa
* `void teeLattia(int y, int x)`:
  muuttaa kohdassa `(y,x)` olevan ruudun lattiaksi
  (jos se ei ole valmiiksi lattiaa)
* `int laskeHuoneet()`:
  ilmoittaa huoneiden määrän

Rajat:

- 1 &le; `n` &le; 500
- 1 &le; `x`, `y` &le; `n`
- metodia `teeLattia` kutsutaan enintään 10<sup>5</sup> kertaa
- metodia `laskeHuoneet` kutsutaan enintään 10<sup>5</sup> kertaa

Seuraava koodi esittelee luokan käyttämistä:

```java
Ruudukko r = new Ruudukko(4);
System.out.println(r.laskeHuoneet()); // 0
r.teeLattia(1,1);
r.teeLattia(1,3);
System.out.println(r.laskeHuoneet()); // 2
r.teeLattia(1,2);
System.out.println(r.laskeHuoneet()); // 1
r.teeLattia(3,3);
System.out.println(r.laskeHuoneet()); // 2
```

</programming-exercise>


<programming-exercise name='5. Virittävät puut' tmcname='viikko13-Viikko13Tehtava5'>

Annettuna on verkko,
jossa on `n` solmua ja jokaisen
kahden solmun välillä on kaari
(eli verkko on _täydellinen_).
Tehtäväsi on laskea,
montako erilaista virittävää puuta
verkolle voidaan muodostaa siinä olevista kaarista.

Tee luokka `VirittavatPuut`, jossa on seuraavat metodit:

* `int laske(int n)`:
  palauttaa virittävien puiden määrän

Rajat:

- 1 &le; `n` &le; 8

Huomaa, että metodin laske tulee laskea tulos tyhjästä
(eli siinä ei saa olla suurten tapausten vastauksia sisällä).

Seuraava koodi esittelee luokan käyttämistä:

```java
VirittavatPuut v = new VirittavatPuut();
System.out.println(v.laske(2)); // 1
System.out.println(v.laske(3)); // 3
System.out.println(v.laske(4)); // 16
```

</programming-exercise>


<programming-exercise name='6. Yhteydet' tmcname='viikko13-Viikko13Tehtava6'>

Tietoverkossa on `n` konetta (numeroitu 1, 2, ..., `n`),
joiden välillä ei ole alussa yhteyksiä.
Verkkoon lisätään joka päivä yksi uusi yhteys.
Tehtäväsi on selvittää annetuista konepareista,
monenko päivän jälkeen niiden välille muodostui yhteys.

Tee luokka `Yhteydet`, jossa on seuraavat metodit:

* `Yhteydet(int n)`: koneiden määrä annetaan konstruktorissa
* `void yhdista(int a, int b)`:
  lisää yhteyden koneiden `a` ja `b` välille
* `int tutki(int x, int y)`:
  ilmoittaa, monenko päivän jälkeen koneiden `x` ja `y`
  välille muodostui yhteys (tai –1, jos näin ei tapahtunut koskaan)

Rajat:

- 1 &le; `n` &le; 10<sup>5</sup>
- ensin metodia `yhdista` kutsutaan enintään 10<sup>5</sup> kertaa
- sitten metodia `tutki` kutsutaan enintään 10<sup>5</sup> kertaa

Seuraava koodi esittelee luokan käyttämistä:

```java
Yhteydet y = new Yhteydet(6);
y.yhdista(1,2);
y.yhdista(1,3);
y.yhdista(4,6);
y.yhdista(2,6);
y.yhdista(2,3);
System.out.println(y.tutki(2,3)); // 2
System.out.println(y.tutki(3,5)); // -1
System.out.println(y.tutki(1,6)); // 4
```

</programming-exercise>
