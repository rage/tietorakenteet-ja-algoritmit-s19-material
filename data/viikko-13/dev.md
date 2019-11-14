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

<programming-exercise name='5. Virittävät puut' tmcname='viikko13-Viikko13Tehtava5'>

Annettuna on suuntaamaton verkko,
jossa on solmuja ja kaaria.
Tehtäväsi on laskea,
montako virittävää puuta verkolle voidaan muodostaa kaarista.

Tee luokka `VirittavatPuut`, jossa on seuraavat metodit:

* `VirittavatPuut(int n)`: solmujen määrä annetaan konstruktorissa
* `void lisaaKaari(int a, int b)`:
  lisää kaaren solmujen `a` ja `b` välille
* `int laske()`:
  palauttaa virittävien puiden määrän

Rajat:

- 1 &le; `n` &le; 100
- ensin metodia `lisaaKaari` kutsutaan enintään 100 kertaa
- lopuksi metodia `laske` kutsutaan kerran
- vastaus on enintään 10<sup>6</sup>

Seuraava koodi esittelee luokan käyttämistä:

```java
VirittavatPuut v = new VirittavatPuut(5);
v.lisaaKaari(1,2);
v.lisaaKaari(2,3);
v.lisaaKaari(3,4);
v.lisaaKaari(1,4);
v.lisaaKaari(4,5);
System.out.println(v.laske()); // 4
```

</programming-exercise>


<programming-exercise name='6. Yhteydet' tmcname='viikko13-Viikko13Tehtava6'>

Tietoverkossa on `n` konetta (numeroitu 1, 2, ..., `n`),
joiden välillä ei ole alussa yhteyksiä.
Verkkoon lisätään joka päivä yksi uusi yhteys.
Tehtäväsi on selvittää konepareista,
monenko päivän jälkeen niiden välillä on yhteys.

Tee luokka `Yhteydet`, jossa on seuraavat metodit:

* `Yhteydet(int n)`: koneiden määrä annetaan konstruktorissa
* `void yhdista(int a, int b)`:
  lisää yhteyden koneiden `a` ja `b` välille
* `int tutki(int x, int y)`:
  ilmoittaa, monenko päivän jälkeen koneiden `x` ja `y` välillä on yhteys
  (tai –1, jos näin ei ole koskaan)

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
System.out.println(y.tutki(2,3)); 2
System.out.println(y.tutki(3,5)); -1
System.out.println(y.tutki(1,6)); 4
```

</programming-exercise>
