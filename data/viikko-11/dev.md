---
path: '/viikko-11-dev'
title: 'Viikko 11: Lyhimmät polut'
overview: true
---

Viikon 11 tehtävien deadline: su 31.11. klo 23:59

## Tehtävät

<programming-exercise name='1. Lyhin reitti I' tmcname='viikko11-Viikko11Tehtava1'>

Bittimaassa on `n` kaupunkia,
jotka on numeroitu 1, 2, ..., `n`.
Kaupunkien välillä on teitä,
joista kukin yhdistää kaksi kaupunkia
ja sitä voi kulkea molempiin suuntiin.
Tehtäväsi on selvittää lyhimmän reitin
pituus kaupungista `x` kaupunkiin `y`.

Tee luokka `LyhinReitti`, jossa on seuraavat metodit:

* `LyhinReitti(int n)`: kaupunkien määrä annetaan konstruktorissa
* `void lisaaTie(int a, int b, int p)`: lisää kaupunkien `a` ja `b` välille tien,
jonka pituus on `p`
* `int lyhinReitti(int x, int y)`: ilmoittaa lyhimmän reitin pituuden
  kaupungista `x` kaupunkiin `y`

Rajat:

- 1 &le; `n` &le; 500
- 1 &le; `p` &le; 1000
- ensin metodia `lisaaTie` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `lyhinReitti`

Seuraava koodi esittelee luokan käyttämistä:

```java
LyhinReitti l = new LyhinReitti(5);
l.lisaaYhteys(1,2,7);
l.lisaaYhteys(2,4,2);
l.lisaaYhteys(1,3,6);
l.lisaaYhteys(3,4,5);
l.lisaaYhteys(4,5,3);
System.out.println(l.lyhinReitti(1,5)); // 12
```

</programming-exercise>

<programming-exercise name='2. Lyhin reitti I' tmcname='viikko11-Viikko11Tehtava2'>

Bittimaassa on `n` kaupunkia,
jotka on numeroitu 1, 2, ..., `n`.
Kaupunkien välillä on teitä,
joista kukin yhdistää kaksi kaupunkia
ja sitä voi kulkea molempiin suuntiin.
Tehtäväsi on selvittää lyhin reitti
pituus kaupungista `x` kaupunkiin `y`.

Tee luokka `LyhinReitti`, jossa on seuraavat metodit:

* `LyhinReitti(int n)`: kaupunkien määrä annetaan konstruktorissa
* `void lisaaTie(int a, int b, int p)`: lisää kaupunkien `a` ja `b` välille tien,
jonka pituus on `p`
* `ArrayList<Integer> lyhinReitti(int x, int y)`: ilmoittaa lyhimmän reitin
  kaupungista `x` kaupunkiin `y` listana kaupunkeja
  (jos lyhimpiä reittejä on useita mahdollista, metodi voi palauttaa minkä
   tahansa niistä)

Rajat:

- 1 &le; `n` &le; 500
- 1 &le; `p` &le; 1000
- ensin metodia `lisaaTie` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `lyhinReitti`

Seuraava koodi esittelee luokan käyttämistä:

```java
LyhinReitti l = new LyhinReitti(5);
l.lisaaYhteys(1,2,7);
l.lisaaYhteys(2,4,2);
l.lisaaYhteys(1,3,6);
l.lisaaYhteys(3,4,5);
l.lisaaYhteys(4,5,3);
System.out.println(l.lyhinReitti(1,5)); // [1, 2, 4, 5]
```

</programming-exercise>

<quiz id=""></quiz>

<programming-exercise name='4. Kierrokset' tmcname='viikko11-Viikko11Tehtava4'>

Tehtäväsi on rakentaa suunnattu painotettu verkko,
jossa on `n` solmua (numeroitu 1, 2, ..., `n`)
ja jossa kurssikirjan
mukainen Bellman–Fordin algoritmi suorittaa
tasan `k` kierrosta,
kun haetaan lyhimpiä polkuja solmusta `1` alkaen.

Tee luokka `Kierrokset`, jossa on seuraavat metodit:

* `ArrayList<Kaari> muodosta(int n, int k)`:
  palauttaa kaarilistan, jonka mukaisesti Bellman–Fordin
  algoritmi käy läpi kaaria

Rajat:

- 1 &le; `k` < `n` &le; 100
- verkossa saa olla enintään 10<sup>5</sup> kaarta

Luokka `Kaari` on annettu tehtäväpohjassa.
Saat muodostaa minkä tahansa verkon,
joka täyttää tehtävänannon vaatimukset.

Seuraava koodi esittelee luokan käyttämistä:

```java
Kierrokset k = new Kierrokset();
ArrayList<Kaari> a = k.muodosta(4,2);
System.out.println(a); // [(1,2,5), (2,3,3), (3,4,4), (1,3,7)]
```

</programming-exercise>

<programming-exercise name='5. Onko polkua?' tmcname='viikko11-Viikko11Tehtava5'>

Annettuna on suunnattu painotettu verkko
ja tehtäväsi on selvittää,
onko _mielekäs_ tehtävä etsiä lyhin
polku solmusta `1` solmuun `n`.
Tehtävä on mielekäs,
jos polun pituudella on jokin alaraja
(eli millään polulla ei ole negatiivista sykliä).

Tee luokka `OnkoPolkua`, jossa on seuraavat metodit:

* `public OnkoPolkua(int n)`: solmujen määrä annetaan konstruktorissa
* `public void lisaaKaari(int a, int b, int p)`:
  lisää solmusta `a` solmuun `b` kaaren, jonka pituus on `p`
* `public boolean tutki()`: palauttaa `true`,
  jos tehtävä on mielekäs, ja muuten `false`

Rajat:

- 1 &le; `n` &le; 500
- –1000 &le; `p` &le; 1000
- ensin metodia `lisaaKaari` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `tutki`


Seuraava koodi esittelee luokan käyttämistä:

```java
OnkoPolkua x = new OnkoPolkua(4);
x.lisaaKaari(1,2,1);
x.lisaaKaari(2,3,1);
x.lisaaKaari(2,4,5);
x.lisaaKaari(4,2,-4);
System.out.println(x.tutki()); // true
OnkoPolkua y = new OnkoPolkua(4);
y.lisaaKaari(1,2,1);
y.lisaaKaari(2,3,1);
y.lisaaKaari(2,4,-4);
y.lisaaKaari(4,2,5);
System.out.println(y.tutki()); // false
```

</programming-exercise>

<programming-exercise name='6. Monta polkua' tmcname='viikko11-Viikko11Tehtava6'>

Tehtäväsi on rakentaa suunnattu painotettu verkko,
jossa on 100 solmua (numeroitu 1, 2, ..., 100)
ja jossa solmusta 1 solmuun 100 on tasan `x`
erilaista lyhintä polkua.

Tee luokka `MontaPolkua`, jossa on seuraavat metodit:

* `ArrayList<Kaari> muodosta(int x)`:
  palauttaa kaarilistan, joka kuvaa verkon rakenteen

Rajat:

- 1 &le; `x` &le; 10<sup>9</sup>
- verkossa saa olla enintään 10<sup>5</sup> kaarta

Luokka `Kaari` on annettu tehtäväpohjassa.
Saat muodostaa minkä tahansa verkon,
joka täyttää tehtävänannon vaatimukset.

Seuraava koodi esittelee luokan käyttämistä:

```java
Kierrokset k = new Kierrokset();
ArrayList<Kaari> a = k.muodosta(2);
System.out.println(a); // [(1,2,1),(2,100,2),(1,3,2),(3,100,1)]
```

</programming-exercise>
