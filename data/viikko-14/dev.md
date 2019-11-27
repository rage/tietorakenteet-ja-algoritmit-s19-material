---
path: '/viikko-14-dev'
title: 'Viikko 14: Maksimivirtaus'
overview: true
---

Viikon 14 tehtävien deadline: su 22.12. klo 23:59

## Tehtävät

<quiz id="a2f06d00-81c0-4d59-b23c-d763cfcc7d53"></quiz>

<programming-exercise name='2. Maksimivirtaus' tmcname='viikko14-Viikko14Tehtava2'>

Annettuna on suunnattu painotettu verkko,
jossa on `n` solmua,
jotka on numeroitu 1, 2, ..., `n`.
Tehtäväsi on määrittää maksimivirtaus
solmusta 1 solmuun `n`.

Tee luokka `Maksimivirtaus`, jossa on seuraavat metodit:

* `Maksimivirtaus(int n)`: solmujen määrä annetaan konstuktorissa
* `void lisaaKaari(int a, int b, int p)`:
  lisää verkkoon solmusta `a` solmuun `b` kaaren,
  jonka paino on `p`
* `int laske()`:
  ilmoittaa maksimivirtauksen suuruuden

Rajat:

- 1 &le; `n` &le; 100
- 1 &le; `p` &le; 10<sup>6</sup>
- ensin metodia `lisaaKaari` kutsutaan enintään 1000 kertaa
- sitten metodia `laske` kutsutaan tasan kerran

Seuraava koodi esittelee luokan käyttämistä:

```java
Maksimivirtaus m = new Maksimivirtaus(5);
m.lisaaKaari(1,2,4);
m.lisaaKaari(1,3,6);
m.lisaaKaari(2,3,8);
m.lisaaKaari(2,4,3);
m.lisaaKaari(3,5,4);
m.lisaaKaari(4,5,5);
System.out.println(m.laske()); // 7
```

</programming-exercise>

<programming-exercise name='3. Tanssiaiset' tmcname='viikko14-Viikko14Tehtava3'>

Kumpulan ja Viikin opiskelijat järjestävät tanssiaiset.
Kumpulasta tulee `n` osallistujaa
ja Viikistä tulee `m` osallistujaa
(numeroitu 1, 2, 3, ...).
Tanssiparin muodostavat Kumpulan ja Viikin opiskelija,
ja jokainen opiskelija voi kuulua enintään yhteen pariin.

Tehtäväsi on muodostaa mahdollisimman monta tanssiparia,
kun tiedät, ketkä opiskelijat suostuvat tanssimaan keskenään.

Tee luokka `Tanssiaiset`, jossa on seuraavat metodit:

* `Tanssiaiset(int n, int m)`: osallistujien määrät annetaan konstruktorissa
* `void lisaaPari(int a, int b)`:
  ilmaisee, että Kumpulan opiskelija `a` ja
  Viikin opiskelija `b` suostuvat tanssimaan keskenään
* `ArrayList<Pari> muodosta()`:
  muodostaa mahdollisimman suuren määrän tanssipareja

Rajat:

- 1 &le; `n`, `m` &le; 100
- ensin metodia `lisaaPari` kutsutaan enintään 1000 kertaa
- lopuksi metodia `muodosta` kutsutaan tasan kerran

Luokka `Pari` on annettu tehtäväpohjassa.
Voit muodostaa minkä tahansa kelvollisen ratkaisun.

Seuraava koodi esittelee luokan käyttämistä:

```java
Tanssiaiset t = new Tanssiaiset(2,3);
t.lisaaPari(1,2);
t.lisaaPari(1,3);
t.lisaaPari(2,1);
t.lisaaPari(2,2);
t.lisaaPari(2,3);
System.out.println(t.muodosta()); // [(1,3), (2,2)]
```

</programming-exercise>

<programming-exercise name='4. Polkupeite' tmcname='viikko14-Viikko14Tehtava4'>

Annettuna on suunnattu syklitön verkko,
jossa on `n` solmua,
jotka on numeroitu 1, 2, ..., `n`.
Tehtäväsi on muodostaa verkon pienin polkupeite
eli joukko polkuja verkossa niin,
että jokainen solmu kuuluu
tasaan yhteen polkuun.

Tee luokka `Polkupeite`, jossa on seuraavat metodit:

* `Polkupeite(int n)`: solmujen määrä annetaan konstuktorissa
* `void lisaaKaari(int a, int b)`:
  lisää verkkoon kaaren solmusta `a` solmuun `b`
* `ArrayList<Polku> muodosta()`:
  muodostaa mahdollisimman pienen polkupeitteen

Rajat:

- 1 &le; `n` &le; 100
- ensin metodia `lisaaKaari` kutsutaan enintään 1000 kertaa
- sitten metodia `muodosta` kutsutaan tasan kerran

Luokka `Polku` on annettu tehtäväpohjassa.
Voit muodostaa minkä tahansa kelvollisen ratkaisun.

Seuraava koodi esittelee luokan käyttämistä:

```java
Polkupeite p = new Polkupeite(5);
p.lisaaKaari(1,2);
p.lisaaKaari(2,3);
p.lisaaKaari(3,4);
p.lisaaKaari(5,2);
p.lisaaKaari(5,3);
System.out.println(p.muodosta()); // [1->2, 5->3->4]
```

</programming-exercise>

<quiz id="b2de3e4f-8e70-41ee-9e9e-ec724b46c37a"></quiz>

<programming-exercise name='6. Ruudukko' tmcname='viikko14-Viikko14Tehtava6'>

Annettuna on `n`x`n`-ruudukko,
jonka jokaisen ruutu on valkoinen (0) tai musta (1).
Jokaisella siirrolla voit muuttaa tietyn
vaaka- tai pystyrivin kaikki ruudut valkoisiksi.
Mikä on pienin määrä siirtoja,
joilla saat koko ruudukon valkoiseksi?

Tee luokka `Ruudukko`, jossa on seuraavat metodit:

* `ArrayList<Siirto> muodosta(int[][] ruudukko)`:
  kuvaa siirrot, joiden jälkeen koko ruudukko on valkoinen

Rajat:

- 1 &le; `n` &le; 100

Luokka `Siirto` on annettu tehtäväpohjassa.
Voit muodostaa minkä tahansa kelvollisen ratkaisun.

Seuraava koodi esittelee luokan käyttämistä:

```java
Ruudukko r = new Ruudukko();
int[][] x = {{1,0,0},
             {0,1,1},
             {1,0,0}};
System.out.println(r.muodosta(x)); // [(V,2), (P,1)]
```

</programming-exercise>
