---
path: '/viikko-09-dev'
title: 'Viikko 9: Dynaaminen ohjelmointi'
overview: true
---

Viikon 9 tehtävien deadline: su 17.11. klo 23:59

## Tehtävät

<programming-exercise name='1. Nopanheitto' tmcname='viikko09-Viikko09Tehtava1'>

Tehtäväsi on laskea, monellako tavalla voit saada summan `x`
heittämällä yhden tai useamman kerran noppaa.
Jokainen nopan heitto tuottaa silmäluvun 1–6.
Esimerkiksi jos `x` = 4, tapoja on kaikkiaan 8:
[1,1,1,1], [1,1,2], [1,2,1], [2,1,1], [2,2], [1,3], [3,1] ja [4].

Tee luokka `Nopanheitto`, jossa on seuraavat metodit:

* `long laske(int n)`: palauttaa heittotapojen määrän

Huomaa, että metodin `laske` tulee laskea tulos tyhjästä
(eli siinä ei saa olla suurten tapausten vastauksia sisällä).

Rajat:

- 1 &le; `n` &le; 50 (vastaus mahtuu tyyppiin `long`)

Seuraava koodi esittelee luokan käyttämistä:

```java
Nopanheitto n = new Nopanheitto();
System.out.println(n.laske(1)); // 1
System.out.println(n.laske(2)); // 2
System.out.println(n.laske(4)); // 8
System.out.println(n.laske(10)); // 492
```

</programming-exercise>

<programming-exercise name='2. Alijonot' tmcname='viikko09-Viikko09Tehtava2'>

Annettuna on taulukko lukuja ja
tehtäväsi on selvittää,
kuinka pitkä on pisin alijono,
jossa jokaisen peräkkäisen luvun ero on tasan 1.

Esimerkiksi taulukossa `[6,2,3,5,2,4,1,8]` vastaus on 4,
koska voimme muodostaa alijonon `[2,3,2,1]`.

Tee luokka `Alijonot`, jossa on seuraavat metodit:

* `int laske(int[] t)`: palauttaa pisimmän alijonon pituuden

Rajat:

- 1 &le; `n` &le; 1000
- jokainen taulukon luku on välillä 1...10<sup>9</sup>

Seuraava koodi esittelee luokan käyttämistä:

```java
Alijonot a = new Alijonot();
System.out.println(a.laske(new int[] {1,1,1,1,1,1,1,1})); // 1
System.out.println(a.laske(new int[] {1,2,3,4,1,2,3,4})); // 6
System.out.println(a.laske(new int[] {6,2,3,5,2,4,1,8})); // 4
```

</programming-exercise>

<programming-exercise name='3. Ruudukko' tmcname='viikko09-Viikko09Tehtava3'>

Annettuna on `n` &times; `n` -ruudukko,
jonka jokaisessa ruudussa on kokonaisluku.
Mikä on suurin mahdollinen summa,
jonka voit muodostaa kulkemalla vasemmasta yläkulmasta
oikeaan alakulmaan ja liikkumalla aina askeleen
alaspäin tai oikealle?

Tee luokka `Ruudukko`, jossa on seuraavat metodit:

* `int laske(int[][] t)`: selvittää suurimman summan

Rajat:

- 1 &le; `n` &le; 100
- jokainen ruudukon luku on välillä 1...100

Seuraava koodi esittelee luokan käyttämistä:

```java
Ruudukko r = new Ruudukko();
int[][] t = {{2,3,1},
             {1,4,5},
             {2,3,4}};
System.out.println(r.laske(t)); // 18
```

</programming-exercise>

<programming-exercise name='4. Kolikot' tmcname='viikko09-Viikko09Tehtava4'>

Sinulla on `n` kolikkoa, joista jokaisella on tietty arvo.
Montako eri rahamäärää voit muodostaa kolikoiden avulla?

Esimerkiksi jos kolikoita on 3 ja niiden arvot ovat 1, 1, ja 4,
voit muodostaa 5 eri rahamäärää:
1, 2, 4, 5 ja 6.

Tee luokka `Kolikot`, jossa on seuraavat metodit:

* `int laske(int[] t)`: ilmoittaa, montako eri rahamäärää voi muodostaa

Rajat:

- 1 &le; `n` &le; 100
- jokaisen kolikon arvo on kokonaisluku välillä 1...100

Seuraava koodi esittelee luokan käyttämistä:

```java
Kolikot k = new Kolikot();
System.out.println(k.laske(new int[] {1,1,4})); // 5
System.out.println(k.laske(new int[] {1,1,1,1})); // 4
System.out.println(k.laske(new int[] {1,2,3,4})); // 10
```

</programming-exercise>

<programming-exercise name='5. Tehtävät' tmcname='viikko09-Viikko09Tehtava5'>

Kurssilla on 14 viikkoa, joista jokaisella on 6 tehtävää.
Lisäksi jokaisella viikolla tulee ratkoa ainakin 3 tehtävää.
Monellako tavalla voit ratkoa tasan `x` tehtävää kurssilla?

Tee luokka `Tehtavat`, jossa on seuraavat metodit:

* `long laske(int x)`: laskee tapojen määrän

Huomaa, että metodin `laske` tulee laskea tulos tyhjästä
(eli siinä ei saa olla suurten tapausten vastauksia sisällä).

Rajat:

- 42 &le; `x` &le; 84 (vastaus mahtuu tyyppiin `long`)

Seuraava koodi esittelee luokan käyttämistä:

```java
Tehtavat t = new Tehtavat();
System.out.println(t.laske(42)); // 1
System.out.println(t.laske(50)); // 170261
System.out.println(t.laske(64)); // 24608948
System.out.println(t.laske(84)); // 1
```

</programming-exercise>

<programming-exercise name='6. Peli' tmcname='viikko09-Viikko09Tehtava6'>

Kahden pelaajan pelin alussa pinossa on `n` kolikkoa.
Joka siirrolla pelaaja jakaa pinon kahdeksi epätyhjäksi pinoksi
ja poistaa vähemmän kolikoita sisältävän pinon pelistä
(jos pinoissa on yhtä monta kolikkoa, voi poistaa kumman tahansa).
Pelaaja voittaa pelin, jos toinen pelaaja ei voi tehdä siirtoa.
Tehtäväsi on selvittää, kumpi pelaaja voittaa,
kun molemmat pelaavat optimaalisesti.

Esimerkiksi jos pinossa on alussa 5 kolikkoa,
aloittaja voittaa varmasti,
koska hän voi muodostaa 2 ja 3 kolikon pinot,
joista peliin jää 3 kolikon pino.
Tämän jälkeen vastustajalla on vain yksi
mahdollinen siirto, joka johtaa häviöön.

Tee luokka `Peli`, jossa on seuraavat metodit:

* `int voittaja(int n)`: ilmoittaa voittajan
(1 = aloittaja, 2 = vastustaja),
kun pinossa on aluksi `n` kolikkoa

Rajat:

- 1 &le; `n` &le; 10<sup>9</sup>
- metodia kutsutaan enintään 10<sup>6</sup> kertaa yhdessä testissä

Seuraava koodi esittelee luokan käyttämistä:

```java
Peli p = new Peli();
System.out.println(p.voittaja(2)); // 1
System.out.println(p.voittaja(3)); // 2
System.out.println(p.voittaja(5)); // 1
System.out.println(p.voittaja(7)); // 2
```

</programming-exercise>
