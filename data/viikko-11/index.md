---
path: '/viikko-11'
title: 'Viikko 11: Lyhimmät polut'
overview: true
---

Viikon 11 tehtävien deadline: su 1.12. klo 23:59

## Tehtävät

<programming-exercise name='1. Lyhin reitti I' tmcname='viikko11-Viikko11Tehtava1'>

Bittimaassa on `n` kaupunkia,
jotka on numeroitu 1, 2, ..., `n`.
Kaupunkien välillä on kaksisuuntaisia teitä,
joilla on tietyt pituudet.
Tehtäväsi on selvittää lyhimmän reitin
pituus kaupungista `x` kaupunkiin `y`.

Tee luokka `LyhinReitti`, jossa on seuraavat metodit:

* `LyhinReitti(int n)`: kaupunkien määrä annetaan konstruktorissa
* `void lisaaTie(int a, int b, int p)`: lisää kaupunkien `a` ja `b` välille tien,
jonka pituus on `p`
* `int laske(int x, int y)`: ilmoittaa lyhimmän reitin pituuden
  kaupungista `x` kaupunkiin `y` (tai –1, jos mitään reittiä ei ole)

Rajat:

- 1 &le; `n` &le; 100
- 1 &le; `p` &le; 1000
- ensin metodia `lisaaTie` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `laske`

Seuraava koodi esittelee luokan käyttämistä:

```java
LyhinReitti l = new LyhinReitti(5);
l.lisaaTie(1,2,7);
l.lisaaTie(2,4,2);
l.lisaaTie(1,3,6);
l.lisaaTie(3,4,5);
l.lisaaTie(4,5,3);
System.out.println(l.laske(1,5)); // 12
```

</programming-exercise>

<programming-exercise name='2. Lyhin reitti II' tmcname='viikko11-Viikko11Tehtava2'>

Bittimaassa on `n` kaupunkia,
jotka on numeroitu 1, 2, ..., `n`.
Kaupunkien välillä on kaksisuuntaisia teitä,
joilla on tietyt pituudet.
Tehtäväsi on muodostaa lyhimmän reitin
kuvaus kaupungista `x` kaupunkiin `y`.

Tee luokka `LyhinReitti`, jossa on seuraavat metodit:

* `LyhinReitti(int n)`: kaupunkien määrä annetaan konstruktorissa
* `void lisaaTie(int a, int b, int p)`: lisää kaupunkien `a` ja `b` välille tien,
jonka pituus on `p`
* `ArrayList<Integer> muodosta(int x, int y)`: ilmoittaa lyhimmän reitin
  kaupungista `x` kaupunkiin `y` listana kaupunkeja
  (tai `null`, jos mitään reittiä ei ole)

Rajat:

- 1 &le; `n` &le; 100
- 1 &le; `p` &le; 1000
- ensin metodia `lisaaTie` kutsutaan enintään 10<sup>5</sup> kertaa
- lopuksi kutsutaan kerran metodia `muodosta`

Jos lyhimpiä reittejä on useita, voit palauttaa minkä tahansa niistä.

Seuraava koodi esittelee luokan käyttämistä:

```java
LyhinReitti l = new LyhinReitti(5);
l.lisaaTie(1,2,7);
l.lisaaTie(2,4,2);
l.lisaaTie(1,3,6);
l.lisaaTie(3,4,5);
l.lisaaTie(4,5,3);
System.out.println(l.muodosta(1,5)); // [1, 2, 4, 5]
```

</programming-exercise>

<quiz id="af0a9a8b-8b64-4012-b076-e7634dfa2a62"></quiz>

<programming-exercise name='4. Kierrokset' tmcname='viikko11-Viikko11Tehtava4'>

Tehtäväsi on rakentaa suunnattu painotettu verkko,
jossa on 100 solmua (numeroitu 1, 2, ..., 100)
ja jossa kurssikirjan
mukainen Bellmanin ja Fordin algoritmi suorittaa
tasan `x` kierrosta,
kun haetaan lyhimpiä polkuja solmusta 1 alkaen.

Huom!
Algoritmi käsittelee kierroksen aikana kaaret siinä
järjestyksessä kuin ne ovat listalla.
Tässä lasketaan mukaan myös viimeinen kierros,
jossa mikään etäisyys ei enää muutu.

Tee luokka `Kierrokset`, jossa on seuraavat metodit:

* `ArrayList<Kaari> muodosta(int x)`:
  palauttaa kaarilistan, jonka mukaisesti Bellmanin ja Fordin
  algoritmi käy läpi kaaria

Rajat:

- 1 &le; `x` &le; 100
- jokaisen kaaren pituuden tulee olla välillä 1...1000
- verkossa saa olla enintään 10<sup>5</sup> kaarta

Luokka `Kaari` on annettu tehtäväpohjassa.
Voit muodostaa minkä tahansa verkon,
joka täyttää tehtävänannon vaatimukset.

Seuraava koodi esittelee luokan käyttämistä:

```java
Kierrokset k = new Kierrokset();
ArrayList<Kaari> a = k.muodosta(3);
System.out.println(a); // [(1,2,5), (2,3,3), (3,4,4), (1,3,7)]
```

</programming-exercise>

<programming-exercise name='5. Onko polkua?' tmcname='viikko11-Viikko11Tehtava5'>

Annettuna on suunnattu painotettu verkko
ja tehtäväsi on selvittää,
onko solmusta 1 solmuun `n` olemassa lyhintä polkua.
Lyhintä polkua ei ole olemassa,
jos joko solmusta 1 ei pääse solmuun `n`
tai jotakin polkua solmusta 1 solmuun `n`
voi lyhentää loputtomasti negatiivisen painoisen kaaren avulla.

Tee luokka `OnkoPolkua`, jossa on seuraavat metodit:

* `OnkoPolkua(int n)`: solmujen määrä annetaan konstruktorissa
* `void lisaaKaari(int a, int b, int p)`:
  lisää solmusta `a` solmuun `b` kaaren, jonka pituus on `p`
* `boolean tutki()`: palauttaa `true`,
  jos lyhin polku on olemassa, ja muuten `false`

Rajat:

- 1 &le; `n` &le; 100
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
y.lisaaKaari(2,4,-5);
y.lisaaKaari(4,2,4);
System.out.println(y.tutki()); // false
```

</programming-exercise>

<programming-exercise name='6. Monta polkua' tmcname='viikko11-Viikko11Tehtava6'>

Tehtäväsi on rakentaa suunnattu painotettu verkko,
jossa on 100 solmua (numeroitu 1, 2, ..., 100)
ja solmusta 1 solmuun 100 on tasan `x`
erilaista lyhintä polkua.

Tee luokka `MontaPolkua`, jossa on seuraavat metodit:

* `ArrayList<Kaari> muodosta(int x)`:
  palauttaa kaarilistan, joka kuvaa verkon rakenteen

Rajat:

- 1 &le; `x` &le; 10<sup>9</sup>
- jokaisen kaaren pituuden tulee olla välillä 1...1000
- verkossa saa olla enintään 10<sup>5</sup> kaarta

Luokka `Kaari` on annettu tehtäväpohjassa.
Voit muodostaa minkä tahansa verkon,
joka täyttää tehtävänannon vaatimukset.

Seuraava koodi esittelee luokan käyttämistä:

```java
MontaPolkua m = new MontaPolkua();
System.out.println(m.muodosta(2)); // [(1,2,1), (2,100,2), (1,3,2), (3,100,1)]
```

</programming-exercise>
