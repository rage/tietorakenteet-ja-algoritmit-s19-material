---
path: "/bittien-kasittely"
title: "Bittien käsittely"
hidden: false
information_page: true
---

Kokonaisluvut (kuten `int` ja `long`) on tallennettu
tietokoneessa sisäisesti bitteinä,
minkä ansiosta kokonaislukua voi käyttää
pienenä taulukkona, jonka jokainen alkio on 0 tai 1.
Tällaisesta taulukosta voidaan käyttää nimeä
_bittitaulukko_ tai _bittivektori_.

Esimerkiksi `int`-tyypin koko on 32 bittiä,
joten `int`-lukua voidaan käyttää taulukkona,
jossa on 32 bittiä. Esimerkiksi luku 81 vastaa
seuraavaa taulukkoa:

```
10001010000000000000000000000000
```

<p>Tämä johtuu siitä, että 81 = 2<sup>0</sup> + 2<sup>4</sup> + 2<sup>6</sup>
eli taulukon kohdissa 0, 4 ja 6 on bitti 1 ja muissa kohdissa on bitti 0.

## Bittioperaatiot

Bittisiirto `1<<x` tuottaa luvun, jossa kohdassa `x` on bitti 1
ja kaikissa muissa kohdissa on bitti 0.
Esimerkiksi `1<<4` vastaa seuraavaa taulukkoa:

```
00001000000000000000000000000000
```

Bittitaulukkoa voi muuttaa ja tutkia bittisiirtojen
sekä operaatioiden _and_ (`&`), _or_ (`|`)  ja _xor_ (`^`) avulla.
Tavallisia operaatiota ovat:

* `t|(1<<x)`: asettaa taulukossa `t` kohdan `x` bitiksi 1
* `t&(1<<x)`: tutkii taulukossa `t` kohdassa `x` olevaa bittiä
  (kyseinen bitti on 0, jos lausekkeen arvo on 0, ja muuten 1)
* `t^(1<<x)`: muuttaa taulukossa `t` kohdan `x` bitin käänteiseksi

## Esimerkki

Seuraava esimerkki näyttää samanlaisen koodin toteutettuna ensin
perinteiseen tapaan taulukolla ja sitten bittitaulukolla:

```java
int[] t = new int[20];
t[1] = 1;
t[5] = 1;
t[8] = 1;
if (t[4] == 1) {
    // ...
}
```

```java
int t = 0;
t |= (1<<1);
t |= (1<<5);
t |= (1<<8);
if ((t&(1<<4)) != 0) {
    // ...
}
```

## Miksi käyttää bittejä?

Bittitaulukon etuna on,
että kokonaista taulukkoa voi käsitellä yhtä helposti
kuin yksittäistä kokonaislukua.
Esimerkiksi on helppoa kopioida taulukoita
ja vertailla niiden sisältöä.

Tavallisessa taulukossa kopiointi ja vertailu
täytyy tehdä alkio kerrallaan
(Javassa on myös valmiita metodeita tähän,
mutta ne toimivat pohjimmiltaan näin):

```java
// kopiointi
for (int i = 0; i < 20; i++) {
    a[i] = b[i];
}
// vertailu
boolean samat = true;
for (int i = 0; i < 20; i++) {
    if (a[i] != b[i]) samat = false;
}
```

Bittitaulukossa sen sijaan kopiointi ja vertailu sujuvat helpommin:

```java
// kopiointi
a = b;
// vertailu
boolean samat = (a == b);
```

Bittitaulukko voi nopeuttaa koodin toimintaa monikymmenkertaisesti.
Myös tilaa säästyy, koska jokainen alkio vie tilaa vain yhden bitin.
