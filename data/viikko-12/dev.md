---
path: '/viikko-12-dev'
title: 'Viikko 12: Suunnatut syklittömät verkot'
overview: true
---

Viikon 12 tehtävien deadline: su 8.12. klo 23:59

## Tehtävät

<quiz id=""></quiz>

<programming-exercise name='2. Kurssit' tmcname='viikko12-Viikko12Tehtava2'>

Sinulle annetaan tiedot yliopiston kursseista
ja niiden esitietovaatimuksista,
ja tehtäväsi on etsiä järjestys,
jossa voit suorittaa kaikki kurssit vaatimusten mukaisesti.

Tee luokka `Kurssit`, jossa on seuraavat metodit:

* `void lisaaKurssi(String s)`:
  lisää suoritettavaksi kurssin nimeltä `s`
* `void lisaaVaatimus(String a, String b)`:
  määrittää, että kurssi `a` tulee suorittaa ennen kurssia `b`
* `ArrayList<String> muodosta()`:
  ilmoittaa tavan suorittaa kurssit vaatimusten mukaisesti
  (tai `null` jos tämä on mahdotonta)

Rajat:

- jokaisen kurssin nimi muodostuu neljästä kirjaimesta A–Z
- ensin metodia `lisaaKurssi` kutsutaan enintään 100 kertaa
- sitten metodia `lisaaVaatimus` kutsutaan enintään 5000 kertaa
- lopuksi kutsutaan kerran metodia `muodosta`

Seuraava koodi esittelee luokan käyttämistä:

```java
Kurssit k = new Kurssit();
k.lisaaKurssi("OHPE");
k.lisaaKurssi("OHJA");
k.lisaaKurssi("TIRA");
k.lisaaKurssi("OHTE");
k.lisaaVaatimus("OHPE","OHJA");
k.lisaaVaatimus("OHJA","TIRA");
k.lisaaVaatimus("OHJA","OHTE");
System.out.println(k.muodosta()); // [OHPE, OHJA, OHTE, TIRA]
```

</programming-exercise>

<programming-exercise name='3. Reitit' tmcname='viikko12-Viikko12Tehtava3'>

Annettuna on suunnattu syklitön verkko,
jossa on `n` solmua (numeroitu 1, 2, ..., `n`).
Tehtäväsi on laskea,
montako erilaista reittiä on
solmusta 1 solmuun `n`.

Tee luokka `Reitit`, jossa on seuraavat metodit:

* `Reitit(int n)`: konstruktorissa annetaan solmujen määrä
* `void lisaaKaari(int a, int b)`:
  lisää kaaren solmusta `a` solmuun `b`
* `long laske()`: ilmoittaa reittien määrän

Rajat:

- 1 &le; `n` &le; 100
- ensin metodia `lisaaKaari` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `laske`
- vastaus mahtuu aina `long`-muuttujaan

Seuraava koodi esittelee luokan käyttämistä:

```java
Reitit r = new Reitit(5);
r.lisaaKaari(1,2);
r.lisaaKaari(2,3);
r.lisaaKaari(2,4);
r.lisaaKaari(3,5);
r.lisaaKaari(4,5);
System.out.println(r.laske()); // 2
```

</programming-exercise>

<programming-exercise name='4. Yhtenäisyys' tmcname='viikko12-Viikko12Tehtava4'>

Annettuna on suunnattu verkko,
jossa on `n` solmua (numeroitu 1, 2, ..., `n`).
Tehtäväsi on selvittää,
onko verkko vahvasti yhtenäinen.

Tee luokka `Yhtenaisyys`, jossa on seuraavat metodit:

* `Yhtenaisyys(int n)`: konstruktorissa annetaan solmujen määrä
* `void lisaaKaari(int a, int b)`:
  lisää kaaren solmusta `a` solmuun `b`
* `boolean tutki()`: palauttaa `true`, jos verkko on vahvasti yhtenäinen,
  ja muuten `false`

Rajat:

- 1 &le; `n` &le; 100
- ensin metodia `lisaaKaari` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `tutki`

Seuraava koodi esittelee luokan käyttämistä:

```java
Yhtenaisyys a = new Yhtenaisyys(3);
a.lisaaKaari(1,2);
a.lisaaKaari(2,3);
a.lisaaKaari(3,1);
System.out.println(a.tutki()); // true
Yhtenaisyys b = new Yhtenaisyys(3);
b.lisaaKaari(1,2);
b.lisaaKaari(2,3);
b.lisaaKaari(1,3);
System.out.println(b.tutki()); // false
```

</programming-exercise>


<programming-exercise name='5. Suunnat' tmcname='viikko12-Viikko12Tehtava5'>

Annettuna on suuntaamaton verkko,
jossa on `n` solmua (numeroitu 1, 2, ..., `n`).
Tehtäväsi on valita jokaiselle kaarelle suunta niin,
että tuloksena oleva verkko on syklitön.

Tee luokka `Suunnat`, jossa on seuraavat metodit:

* `Suunnat(int n)`: solmujen määrä annetaan konstruktorissa
* `void lisaaKaari(int a, int b)`:
  lisää kaaren solmusta `a` solmuun `b`
* `int[] muodosta()`: palauttaa taulukossa jokaisen kaaren suunnan
  lisäysjärjestyksessä (1 tarkoittaa `a`&rightarrow;`b` ja –1 tarkoittaa `b`&rightarrow;`a`)
  tai `null`, jos ratkaisua ei ole olemassa

Rajat:

- 1 &le; `n` &le; 100
- ensin metodia `lisaaKaari` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `muodosta()`

Voit muodostaa minkä tahansa kelvollisen ratkaisun.

Seuraava koodi esittelee luokan käyttämistä:

```java
Suunnat s = new Suunnat(3);
s.lisaaKaari(1,2);
s.lisaaKaari(2,3);
s.lisaaKaari(3,1);
System.out.println(Arrays.toString(s.muodosta())); // [1, 1, -1]
```

</programming-exercise>

<programming-exercise name='6. Järjestykset' tmcname='viikko12-Viikko12Tehtava6'>

Annettuna on suunnattu syklitön verkko,
jossa on `n` solmua (numeroitu 1, 2, ..., `n`).
Tehtäväsi on laskea,
montako erilaista topologista järjestystä
verkolle voidaan muodostaa.

Tee luokka `Jarjestykset`, jossa on seuraavat metodit:

* `Jarjestykset(int n)`: konstruktorissa annetaan solmujen määrä
* `void lisaaKaari(int a, int b)`:
  lisää kaaren solmusta `a` solmuun `b`
* `int laske()`: ilmoittaa järjestysten määrän

Rajat:

- 1 &le; `n` &le; 100
- ensin metodia `lisaaKaari` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `laske`
- vastaus on aina enintään 10<sup>6</sup>

Seuraava koodi esittelee luokan käyttämistä:

```java
Jarjestykset j = new Jarjestykset(5);
j.lisaaKaari(1,2);
j.lisaaKaari(1,3);
j.lisaaKaari(2,3);
j.lisaaKaari(2,5);
System.out.println(j.laske()); // 10
```

</programming-exercise>
