# FAZA 2 — Linearna kombinacija, ogrodje, linearna neodvisnost, baza in dimenzija

## Kaj moraš obvladati v tej fazi

Ta faza temelji predvsem na **4. in 5. vajah** predmeta Algebra II – Linearna algebra. V 4. vajah se pojavita linearno izražanje in ogrodje, 5. vaje pa sistematično obravnavajo linearno neodvisnost, ogrodje, bazo, dimenzijo in dopolnjevanje do baze.

Po zaključku faze moraš znati:

- zapisati vektor kot **linearno kombinacijo** drugih vektorjev;
- določiti **linearno ogrinjačo** množice;
- preveriti, ali je množica **ogrodje** prostora;
- preveriti **linearno neodvisnost**;
- razlikovati med linearno odvisno in neodvisno množico;
- preveriti, ali je množica **baza**;
- poiskati **bazo podprostora**;
- izračunati **dimenzijo** prostora ali podprostora;
- iz ogrodja odstraniti odvečne vektorje;
- linearno neodvisno množico **dopolniti do baze**;
- uporabiti dimenzijo za hitrejše odločanje;
- natančno povedati glavne definicije, izreke in kratke dokaze na ustnem izpitu.

## 1. Osnovna slika celotne faze

Najpomembnejša povezava je:

$$
\boxed{
\text{linearna kombinacija}
\rightarrow
\text{linearna ogrinjača}
\rightarrow
\text{ogrodje}
\rightarrow
\text{baza}
\rightarrow
\text{dimenzija}
}
$$

Hkrati velja:

$$
\boxed{
\text{baza}=\text{linearno neodvisno ogrodje}
}
$$

Pri skoraj vsaki nalogi razmišljaš o dveh vprašanjih:

1. Ali dani vektorji generirajo dovolj velik prostor?
2. Ali je med njimi kakšen odvečen vektor?

- **generirajo in ni odvečnih** $\Rightarrow$ baza;
- **generirajo, vendar so odvečni** $\Rightarrow$ ogrodje, ne baza;
- **ne generirajo, vendar niso odvečni** $\Rightarrow$ linearno neodvisna množica, ne baza;
- **ne generirajo in so odvečni** $\Rightarrow$ niti ogrodje niti baza.

## 2. Linearna kombinacija

### Definicija

Naj bodo $v_1,\dots,v_k$ vektorji v vektorskem prostoru $V$ nad poljem $F$.

Vektor

$$
v=\alpha_1v_1+\alpha_2v_2+\cdots+\alpha_kv_k,
$$

kjer so $\alpha_1,\dots,\alpha_k\in F$, imenujemo **linearna kombinacija** vektorjev $v_1,\dots,v_k$.

Števila $\alpha_i$ so **koeficienti linearne kombinacije**.

### Kako prepoznam nalogo?

Vprašanje »Ali se $v$ linearno izraža z $v_1,\dots,v_k$?« pomeni:

$$
v=\alpha_1v_1+\cdots+\alpha_kv_k?
$$

Iščemo skalarje $\alpha_1,\dots,\alpha_k$. To je sistem linearnih enačb.

### Primer

Naj bodo

$$
v_1=(1,0,1),\qquad v_2=(0,1,1),\qquad v=(2,3,5).
$$

Iščemo $\alpha,\beta$:

$$
\alpha(1,0,1)+\beta(0,1,1)=(2,3,5).
$$

Dobimo

$$
(\alpha,\beta,\alpha+\beta)=(2,3,5),
$$

torej

$$
\alpha=2,\qquad \beta=3.
$$

Zato

$$
\boxed{v=2v_1+3v_2.}
$$

## 3. Linearna ogrinjača

### Definicija

Za

$$
S=\{v_1,\dots,v_k\}\subseteq V
$$

je **linearna ogrinjača**

$$
L(S)=L\{v_1,\dots,v_k\}
=
\left\{
\alpha_1v_1+\cdots+\alpha_kv_k;
\alpha_i\in F
\right\}.
$$

Vedno velja:

$$
L(S)\le V.
$$

Linearna ogrinjača je najmanjši podprostor prostora $V$, ki vsebuje $S$.

### Primer

Če sta

$$
v_1=(1,0,0),\qquad v_2=(0,1,0),
$$

potem

$$
L\{v_1,v_2\}
=
\{(a,b,0);a,b\in\mathbb R\}.
$$

To je ravnina $z=0$ v $\mathbb R^3$.

## 4. Ogrodje

### Definicija

Množica

$$
S=\{v_1,\dots,v_k\}\subseteq V
$$

je **ogrodje** prostora $V$, če

$$
L(S)=V.
$$

Vsak vektor $v\in V$ se mora dati zapisati kot linearna kombinacija elementov $S$.

### Kako preverim ogrodje?

Za poljuben $v\in V$ mora biti rešljiv sistem

$$
v=\alpha_1v_1+\cdots+\alpha_kv_k.
$$

V $\mathbb R^n$ lahko uporabimo matriko s stolpci $v_1,\dots,v_k$ in Gaussovo eliminacijo.

## 5. Linearna neodvisnost

### Definicija

Vektorji $v_1,\dots,v_k$ so **linearno neodvisni**, če iz

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0
$$

sledi

$$
\alpha_1=\cdots=\alpha_k=0.
$$

Homogeni sistem ima torej samo trivialno rešitev.

### Linearna odvisnost

Vektorji so **linearno odvisni**, če obstaja netrivialna rešitev:

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0,
$$

kjer je vsaj en $\alpha_i\ne0$.

Če na primer

$$
v_3=2v_1-v_2,
$$

potem

$$
2v_1-v_2-v_3=0,
$$

zato so $v_1,v_2,v_3$ linearno odvisni.

### Hitri kriteriji

- Če $0\in S$, je $S$ linearno odvisna.
- Če je $v_j=\lambda v_i$, sta $v_i,v_j$ linearno odvisna.
- Če ima $n$-razsežen prostor več kot $n$ vektorjev, so ti linearno odvisni.

## 6. Ogrodje in linearna neodvisnost nista ista stvar

### Primer 1

V $\mathbb R^2$:

$$
S=\{(1,0),(0,1),(1,1)\}.
$$

Množica je ogrodje, ker prva dva vektorja generirata $\mathbb R^2$.

Toda

$$
(1,1)=(1,0)+(0,1),
$$

zato je linearno odvisna.

### Primer 2

V $\mathbb R^3$:

$$
S=\{(1,0,0),(0,1,0)\}.
$$

Vektorja sta linearno neodvisna, vendar ne generirata $\mathbb R^3$.

## 7. Baza

### Definicija

Množica $B$ je **baza** vektorskega prostora $V$, če je hkrati:

1. linearno neodvisna;
2. ogrodje prostora $V$.

Torej:

$$
\boxed{
B\text{ je baza}
\iff
B\text{ je linearno neodvisno ogrodje.}
}
$$

Če je

$$
B=\{v_1,\dots,v_n\}
$$

baza, potem se vsak $v\in V$ zapiše na natanko en način:

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n.
$$

## 8. Dimenzija

### Definicija

Če ima končnorazsežen prostor $V$ bazo z $n$ elementi, definiramo

$$
\boxed{\dim V=n.}
$$

Vse baze istega končnorazsežnega prostora imajo enako število elementov.

### Standardne dimenzije

$$
\boxed{\dim\mathbb R^n=n}
$$

$$
\boxed{\dim\mathbb R_n[x]=n+1}
$$

$$
\boxed{\dim\mathbb R^{m\times n}=mn}
$$

Za polinome je standardna baza

$$
\{1,x,x^2,\dots,x^n\}.
$$

Zato na primer

$$
\dim\mathbb R_5[x]=6.
$$

## 9. Najpomembnejši izreki in bližnjice

Naj bo $\dim V=n$.

### Izrek 1

Vsaka linearno neodvisna množica v $V$ vsebuje največ $n$ vektorjev:

$$
|S|\le n.
$$

Zato:

$$
|S|>n
\Rightarrow
S\text{ je linearno odvisna.}
$$

### Izrek 2

Vsako ogrodje prostora $V$ vsebuje vsaj $n$ vektorjev:

$$
|S|\ge n.
$$

Zato:

$$
|S|<n
\Rightarrow
S\text{ ni ogrodje prostora }V.
$$

### Izrek 3 — ključna bližnjica

Če imamo v $n$-razsežnem prostoru natanko $n$ vektorjev, potem:

$$
\boxed{
\text{linearno neodvisni}
\iff
\text{ogrodje}
\iff
\text{baza}.
}
$$

Dovolj je torej preveriti samo linearno neodvisnost ali samo ogrodje.

### Izrek 4 — dopolnitev do baze

Vsako linearno neodvisno množico v končnorazsežnem vektorskem prostoru lahko dopolnimo do baze.

### Izrek 5 — iz ogrodja lahko izberemo bazo

Iz končnega ogrodja lahko odstranimo odvečne vektorje tako, da ostane baza.

## 10. Hitra tabela za izpit

| Podatek | Kaj takoj vem |
|---|---|
| $k>n$ | množica je linearno odvisna |
| $k<n$ | množica ni ogrodje $V$ |
| $k=n$ in množica je LN | množica je baza |
| $k=n$ in množica je ogrodje | množica je baza |
| množica vsebuje $0$ | linearno odvisna |
| en vektor je kombinacija drugih | linearno odvisna |
| množica je baza | vsak vektor ima enoličen zapis |


# Tipi nalog

## Tip naloge: Ali se vektor linearno izraža z danimi vektorji?

### Kako jo prepoznam

Naloga sprašuje:

- ali je $v\in L\{v_1,\dots,v_k\}$;
- ali se nek vektor linearno izraža z drugimi;
- poišči koeficiente linearne kombinacije.

### Postopek

1. Zapiši

$$
v=\alpha_1v_1+\cdots+\alpha_kv_k.
$$

2. Primerjaj komponente oziroma koeficiente.
3. Reši dobljeni sistem.
4. Če sistem ima rešitev, linearni izraz obstaja.
5. Če sistem nima rešitve, vektor ni v linearni ogrinjači.

### Primer

Dani sta matriki

$$
A=
\begin{pmatrix}
1&0\\
1&1
\end{pmatrix},
\qquad
B=
\begin{pmatrix}
0&1\\
-1&0
\end{pmatrix}.
$$

Preverimo, ali se

$$
C=
\begin{pmatrix}
2&1\\
1&2
\end{pmatrix}
$$

linearno izraža z $A$ in $B$.

### Rešitev

Iščemo $\alpha,\beta\in\mathbb R$:

$$
\alpha A+\beta B=C.
$$

Velja

$$
\alpha
\begin{pmatrix}
1&0\\
1&1
\end{pmatrix}
+
\beta
\begin{pmatrix}
0&1\\
-1&0
\end{pmatrix}
=
\begin{pmatrix}
\alpha&\beta\\
\alpha-\beta&\alpha
\end{pmatrix}.
$$

Primerjava da:

$$
\alpha=2,\qquad \beta=1,\qquad \alpha-\beta=1.
$$

Torej

$$
\boxed{
C=2A+B.
}
$$

### Pogoste napake

- primerjaš samo nekatere elemente matrike;
- ne preveriš vseh enačb sistema;
- zamenjaš pripadnost linearni ogrinjači z vprašanjem o bazi.

## Tip naloge: Ali je množica ogrodje?

### Kako jo prepoznam

- »Ali je množica ogrodje?«
- »Ali vektorji generirajo $V$?«
- »Določi $L(S)$.«

### Postopek

1. Najprej preveri dimenzijo.
2. Če je $k<n$, množica ne more biti ogrodje $n$-razsežnega prostora.
3. Sicer preveri, ali je poljuben $v\in V$ linearna kombinacija danih vektorjev.

### Primer

Naj bo

$$
S=\{(1,-1),(-2,2),(3,-3)\}.
$$

Velja

$$
(-2,2)=-2(1,-1),
$$

$$
(3,-3)=3(1,-1).
$$

Zato

$$
L(S)=L\{(1,-1)\}.
$$

To je samo premica, torej

$$
\boxed{
S\text{ ni ogrodje }\mathbb R^2.
}
$$

### Pogoste napake

- veliko število vektorjev ne pomeni avtomatično ogrodja;
- ne opaziš, da so vsi vektorji večkratniki istega vektorja.

## Tip naloge: Preveri linearno neodvisnost

### Postopek

Postavi:

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0.
$$

Če je edina rešitev trivialna, so vektorji linearno neodvisni.

### Primer

Naj bodo

$$
v_1=(1,1,0),\quad
v_2=(0,1,1),\quad
v_3=(1,2,1).
$$

Opazimo:

$$
v_1+v_2=v_3.
$$

Torej

$$
v_1+v_2-v_3=0
$$

je netrivialna linearna zveza.

Zato

$$
\boxed{
v_1,v_2,v_3\text{ so linearno odvisni.}
}
$$

### Pogoste napake

- pri preverjanju LN mora biti na desni ničelni vektor;
- dovolj je najti eno netrivialno zvezo za dokaz odvisnosti;
- če je v množici $0$, računanje ni potrebno.

## Tip naloge: Hkrati določi linearno neodvisnost, ogrodje in bazo

To je osrednji tip 5. vaj.

### Primer — množica $N_1\subseteq\mathbb R_5[x]$

Naj bo

$$
N_1=
\{
x-1,
x^2-x,
x^3-x^2,
x^4-x^3,
x^5-x^4
\}.
$$

Ker

$$
|N_1|=5<6=\dim\mathbb R_5[x],
$$

$N_1$ ni ogrodje in zato ni baza.

Za linearno neodvisnost postavimo:

$$
a_1(x-1)
+a_2(x^2-x)
+a_3(x^3-x^2)
+a_4(x^4-x^3)
+a_5(x^5-x^4)=0.
$$

Primerjava koeficientov od $x^5$ navzdol da:

$$
a_5=0,\quad
a_4=0,\quad
a_3=0,\quad
a_2=0,\quad
a_1=0.
$$

Zato

$$
\boxed{
N_1:\text{ LN da, ogrodje ne, baza ne.}
}
$$

### Primer — množica $N_3$

Naj bo

$$
N_3=\{0,1,x,2x^2,3x^3,4x^4,5x^5\}.
$$

Ker $0\in N_3$, je množica linearno odvisna.

Preostali neničelni polinomi pa generirajo $\mathbb R_5[x]$, zato:

$$
\boxed{
N_3:\text{ LN ne, ogrodje da, baza ne.}
}
$$

## Tip naloge: Poišči bazo prostora, definiranega s pogojem

### Postopek

1. Zapiši splošen element prostora.
2. Uporabi dane pogoje.
3. Izrazi odvisne koeficiente s prostimi parametri.
4. Zapiši splošen element kot linearno kombinacijo.
5. Iz generatorjev izberi linearno neodvisne.
6. Zapiši bazo in dimenzijo.

### Primer — polinomi

Naj bo

$$
V=\{p\in\mathbb R_3[x];p''=0\}.
$$

Splošen polinom:

$$
p(x)=a+bx+cx^2+dx^3.
$$

Ker

$$
p''(x)=2c+6dx,
$$

pogoj $p''=0$ pomeni

$$
c=d=0.
$$

Torej

$$
p(x)=a+bx,
$$

zato

$$
\boxed{
B=\{1,x\},\qquad \dim V=2.
}
$$

## Tip naloge: Poišči dimenzijo matričnega podprostora

### Primer

Naj bo

$$
U=
\{A\in\mathbb R^{2\times2};A^T=-A\}.
$$

Splošna matrika je

$$
A=
\begin{pmatrix}
a&b\\
c&d
\end{pmatrix}.
$$

Pogoj $A^T=-A$ da

$$
a=d=0,\qquad c=-b.
$$

Zato

$$
A=
b
\begin{pmatrix}
0&1\\
-1&0
\end{pmatrix}.
$$

Torej

$$
\boxed{
B_U=
\left\{
\begin{pmatrix}
0&1\\
-1&0
\end{pmatrix}
\right\},
\qquad
\dim U=1.
}
$$

## Tip naloge: Parameter mora biti tak, da dobimo podprostor; nato baza

Naj bo

$$
U=
\{
(x,y,z)\in\mathbb R^3;
x-t(y+2z-2)=4
\}.
$$

Za podprostor mora veljati $(0,0,0)\in U$.

Vstavimo:

$$
0-t(-2)=4,
$$

torej

$$
\boxed{t=2.}
$$

Pogoj postane

$$
x-2y-4z=0.
$$

Zato

$$
x=2y+4z.
$$

Če postavimo $y=s$, $z=r$, dobimo

$$
(x,y,z)=s(2,1,0)+r(4,0,1).
$$

Torej

$$
\boxed{
B_U=\{(2,1,0),(4,0,1)\},
\qquad
\dim U=2.
}
$$

## Tip naloge: Dopolni bazo podprostora do baze večjega prostora

Če imamo $k$ linearno neodvisnih vektorjev v $n$-razsežnem prostoru, moramo dodati še $n-k$ vektorjev in ohraniti linearno neodvisnost.

### Primer

Imamo

$$
B_U=\{(2,1,0),(4,0,1)\}.
$$

Ker je $\dim\mathbb R^3=3$, dodamo na primer

$$
e_1=(1,0,0).
$$

Dobimo bazo

$$
\boxed{
\{(2,1,0),(4,0,1),(1,0,0)\}.
}
$$

# Kako delati s polinomi

Polinom

$$
p(x)=a_0+a_1x+\cdots+a_nx^n
$$

lahko predstavimo z vektorjem koeficientov

$$
(a_0,a_1,\dots,a_n).
$$

Na primer:

$$
2-3x+x^3
\leftrightarrow
(2,-3,0,1).
$$

Tako lahko problem s polinomi rešujemo kot problem v $\mathbb R^{n+1}$.

# Kako delati z matrikami

Matriko

$$
A=
\begin{pmatrix}
a&b\\
c&d
\end{pmatrix}
$$

lahko identificiramo z vektorjem

$$
(a,b,c,d)\in\mathbb R^4.
$$

Zato

$$
\dim\mathbb R^{2\times2}=4.
$$

# Gaussova eliminacija kot univerzalna metoda

Za

$$
v_1,\dots,v_k\in\mathbb R^n
$$

zapišemo matriko s temi vektorji kot stolpci.

Po vrstičnem reduciranju lahko določimo:

- število linearno neodvisnih vektorjev;
- odvečne vektorje;
- ali vektorji generirajo celoten prostor;
- bazo njihove linearne ogrinjače.

**Pomembno:** pri izbiri baze iz originalnih vektorjev vzamemo pivotne stolpce **originalne matrike**, ne reducirane matrike.

# Kako prepoznam metodo v nalogi?

| Besedilo naloge | Kaj naredim |
|---|---|
| »linearno izrazite« | postavim linearno kombinacijo |
| »ali pripada $L\{\dots\}$« | rešim sistem za koeficiente |
| »ali je linearno neodvisna« | $\sum\alpha_iv_i=0$ |
| »ali je ogrodje« | preverim, ali $L(S)=V$ |
| »ali je baza« | preverim LN + ogrodje |
| natanko $\dim V$ vektorjev | dovolj je preveriti samo LN ali samo ogrodje |
| več vektorjev kot $\dim V$ | avtomatično linearno odvisni |
| manj vektorjev kot $\dim V$ | avtomatično niso ogrodje |
| »poišči bazo podprostora« | parametriziram splošen element |
| »dopolni do baze« | dodajam vektorje in ohranjam LN |
| prostor polinomov | primerjam koeficiente |
| prostor matrik | primerjam elemente matrik |

# Pogoste napake

## Napaka 1 — $\dim\mathbb R_n[x]=n$

Napačno.

$$
\boxed{
\dim\mathbb R_n[x]=n+1.
}
$$

## Napaka 2 — ogrodje pomeni linearno neodvisnost

Ne.

$$
L(S)=V
$$

pomeni ogrodje, ne pa nujno linearne neodvisnosti.

## Napaka 3 — veliko vektorjev pomeni bazo

Ne. Lahko so med seboj linearno odvisni.

## Napaka 4 — baza pomeni samo linearno neodvisnost

Ne.

$$
\boxed{
\text{baza}=\text{LN}+\text{ogrodje}.
}
$$

## Napaka 5 — ničelni vektor v bazi

Baza nikoli ne vsebuje ničelnega vektorja.

## Napaka 6 — ne uporabiš dimenzije

Pred računanjem vedno preveri $\dim V$ in število danih vektorjev.

## Napaka 7 — generatorje avtomatično razglasiš za bazo

Iz

$$
U=L\{v_1,v_2,v_3\}
$$

še ne sledi, da so $v_1,v_2,v_3$ baza.

# Pomembne povezave med pojmi

Ogrodje zagotavlja:

$$
\boxed{\text{obstoj linearnega zapisa}.}
$$

Linearna neodvisnost zagotavlja:

$$
\boxed{\text{enoličnost linearnega zapisa}.}
$$

Baza zagotavlja:

$$
\boxed{\text{obstoj + enoličnost}.}
$$


# Ustni / teoretični del

## Ustno vprašanje 1

**Vprašanje:** Kaj je linearna kombinacija vektorjev?

**Kratek odgovor:** Naj bodo $v_1,\dots,v_k\in V$ in $\alpha_1,\dots,\alpha_k\in F$. Vektor

$$
v=\alpha_1v_1+\cdots+\alpha_kv_k
$$

imenujemo linearna kombinacija vektorjev $v_1,\dots,v_k$.

**Profesor lahko dodatno vpraša:** Kaj je linearna ogrinjača?

**Odgovor:** $L(S)$ je množica vseh linearnih kombinacij elementov $S$.

## Ustno vprašanje 2

**Vprašanje:** Zakaj je $L(S)$ podprostor?

**Kratek odgovor:** Ker vsebuje ničelni vektor in je zaprta za linearne kombinacije. Če sta

$$
u=\sum_i\alpha_iv_i,\qquad
w=\sum_i\beta_iv_i,
$$

potem za $a,b\in F$ velja

$$
au+bw
=
\sum_i(a\alpha_i+b\beta_i)v_i\in L(S).
$$

**Profesor lahko dodatno vpraša:** Kakšna je posebna lastnost $L(S)$?

**Odgovor:** Je najmanjši podprostor prostora $V$, ki vsebuje $S$.

## Ustno vprašanje 3

**Vprašanje:** Kaj je ogrodje?

**Kratek odgovor:** $S\subseteq V$ je ogrodje prostora $V$, če

$$
L(S)=V.
$$

**Profesor lahko dodatno vpraša:** Ali je ogrodje nujno linearno neodvisno?

**Odgovor:** Ne. Lahko vsebuje odvečne vektorje.

## Ustno vprašanje 4

**Vprašanje:** Definirajte linearno neodvisnost.

**Kratek odgovor:** Vektorji $v_1,\dots,v_k$ so linearno neodvisni, če iz

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0
$$

sledi

$$
\alpha_1=\cdots=\alpha_k=0.
$$

**Profesor lahko dodatno vpraša:** Kaj pomeni linearna odvisnost?

**Odgovor:** Obstaja netrivialna linearna kombinacija danih vektorjev, ki je enaka ničelnemu vektorju.

## Ustno vprašanje 5

**Vprašanje:** Kako je linearna odvisnost povezana z izražanjem enega vektorja z drugimi?

**Kratek odgovor:** Končna množica je linearno odvisna natanko tedaj, ko se vsaj en njen vektor linearno izraža z ostalimi.

**Profesor lahko dodatno vpraša:** Dokažite eno smer.

**Odgovor:** Če

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0
$$

in je $\alpha_j\ne0$, potem

$$
v_j=
-\sum_{i\ne j}\frac{\alpha_i}{\alpha_j}v_i.
$$

## Ustno vprašanje 6

**Vprašanje:** Kaj je baza?

**Kratek odgovor:** Baza prostora $V$ je linearno neodvisno ogrodje prostora $V$.

$$
\boxed{
B\text{ baza}
\iff
B\text{ LN in }L(B)=V.
}
$$

**Profesor lahko dodatno vpraša:** Kaj baza zagotavlja glede zapisa vektorja?

**Odgovor:** Vsak vektor se glede na bazo izraža enolično.

## Ustno vprašanje 7

**Vprašanje:** Zakaj je zapis vektorja glede na bazo enoličen?

**Kratek odgovor:** Če

$$
v=\sum_i\alpha_iv_i=\sum_i\beta_iv_i,
$$

potem

$$
\sum_i(\alpha_i-\beta_i)v_i=0.
$$

Ker so bazni vektorji linearno neodvisni, sledi

$$
\alpha_i=\beta_i
$$

za vse $i$.

## Ustno vprašanje 8

**Vprašanje:** Kaj je dimenzija vektorskega prostora?

**Kratek odgovor:** Če je $V$ končnorazsežen, je $\dim V$ število elementov poljubne baze prostora $V$.

## Ustno vprašanje 9

**Vprašanje:** Kolikšna je dimenzija $\mathbb R_n[x]$?

**Kratek odgovor:**

$$
\boxed{\dim\mathbb R_n[x]=n+1.}
$$

## Ustno vprašanje 10

**Vprašanje:** Kolikšna je dimenzija $\mathbb R^{m\times n}$?

**Kratek odgovor:**

$$
\boxed{\dim\mathbb R^{m\times n}=mn.}
$$

## Ustno vprašanje 11

**Vprašanje:** Kaj lahko poveste o več kot $n$ vektorjih v $n$-razsežnem prostoru?

**Kratek odgovor:** Vedno so linearno odvisni.

**Profesor lahko dodatno vpraša:** Kaj pa manj kot $n$ vektorjev?

**Odgovor:** Ne morejo biti ogrodje celotnega prostora.

## Ustno vprašanje 12

**Vprašanje:** Naj bo $\dim V=n$ in naj bo $S$ množica natanko $n$ vektorjev. Kaj zadošča, da je $S$ baza?

**Kratek odgovor:** Dovolj je dokazati linearno neodvisnost ali da je $S$ ogrodje.

## Ustno vprašanje 13

**Vprašanje:** Ali lahko vsako linearno neodvisno množico dopolnimo do baze?

**Kratek odgovor:** Da, v končnorazsežnem prostoru.

**Profesor lahko dodatno vpraša:** Kaj lahko naredimo z odvisnim ogrodjem?

**Odgovor:** Odstranimo odvečne vektorje, dokler ne ostane baza.

# Dokazi, ki jih je smiselno znati

## Dokaz: baza daje enoličen zapis

Naj bo

$$
B=\{v_1,\dots,v_n\}
$$

baza prostora $V$.

Če imamo

$$
v=\sum_{i=1}^n\alpha_iv_i
$$

in

$$
v=\sum_{i=1}^n\beta_iv_i,
$$

potem

$$
0=\sum_{i=1}^n(\alpha_i-\beta_i)v_i.
$$

Ker je $B$ linearno neodvisna:

$$
\alpha_i-\beta_i=0
$$

za vse $i$.

Torej

$$
\boxed{\alpha_i=\beta_i.}
$$

## Dokaz: množica, ki vsebuje $0$, je linearno odvisna

Naj bo

$$
S=\{0,v_2,\dots,v_k\}.
$$

Potem

$$
1\cdot0+0v_2+\cdots+0v_k=0.
$$

Ker je koeficient $1$ neničeln, je kombinacija netrivialna.

## Dokaz: če se en vektor izraža z drugimi, je množica linearno odvisna

Če

$$
v_k=\alpha_1v_1+\cdots+\alpha_{k-1}v_{k-1},
$$

potem

$$
\alpha_1v_1+\cdots+\alpha_{k-1}v_{k-1}-v_k=0.
$$

Ker je koeficient pri $v_k$ enak $-1\ne0$, je množica linearno odvisna.

# Minimalni postopek za pisni izpit

1. Določi $\dim V$.
2. Preštej dane vektorje.
3. Preveri očitne odvisnosti: $0$, večkratniki, vsote.
4. Če ni očitno, postavi homogeni sistem

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0.
$$

5. Uporabi dimenzijo za zaključek o ogrodju ali bazi.

# Naloge za samostojno reševanje

## Srednje težke naloge

**Naloga 1.**

V prostoru $\mathbb R^2$ naj bo

$$
S=\{(1,1),(1,2)\}.
$$

Zapiši $v=(3,5)$ kot linearno kombinacijo elementov $S$.

**Naloga 2.**

V prostoru $\mathbb R^3$ je dana množica

$$
S=
\{(1,1,0),(0,1,1),(1,2,1)\}.
$$

Določi:

- ali je $S$ linearno neodvisna;
- ali je ogrodje $\mathbb R^3$;
- ali je baza $\mathbb R^3$;
- bazo $L(S)$;
- $\dim L(S)$.

**Naloga 3.**

V prostoru $\mathbb R_2[x]$ naj bo

$$
S=
\{1+x,\ x+x^2,\ 1+2x+x^2\}.
$$

Določi, ali je množica linearno neodvisna, ogrodje in baza.

**Naloga 4.**

Naj bo

$$
U=
\{
(x,y,z,w)\in\mathbb R^4;
x+y-z=0,\ w=2z
\}.
$$

Poišči bazo prostora $U$ in določi $\dim U$.

**Naloga 5.**

Naj bo

$$
U=
\{A\in\mathbb R^{2\times2};A^T=A\}.
$$

Poišči bazo prostora $U$ in izračunaj $\dim U$.

**Naloga 6.**

Množico

$$
S=
\{(1,1,0),(0,1,1)\}
$$

dopolni do baze prostora $\mathbb R^3$.

## Težke / izpitne naloge

**Naloga 7.**

Za kateri $a\in\mathbb R$ je množica

$$
S_a=
\{
(1,0,1),
(0,1,1),
(1,1,a)
\}
$$

baza prostora $\mathbb R^3$?

**Naloga 8.**

V prostoru $\mathbb R_2[x]$ je dana množica

$$
S_t=
\{
1+x,\ x+x^2,\ 1+tx+x^2
\}.
$$

Za katere $t\in\mathbb R$ je $S_t$ baza prostora $\mathbb R_2[x]$?

**Naloga 9.**

Naj bo

$$
U=
\{
p\in\mathbb R_3[x];
p(1)=0,\ p'(1)=0
\}.
$$

Poišči splošno obliko elementa $U$, bazo $U$ in $\dim U$.

**Naloga 10.**

Naj bo

$$
U=
\left\{
A\in\mathbb R^{2\times2};
\operatorname{tr}(A)=0
\right\}.
$$

Poišči bazo in dimenzijo prostora $U$.

**Naloga 11.**

V $\mathbb R^4$ naj bodo

$$
v_1=(1,2,0,1),\quad
v_2=(0,1,1,0),\quad
v_3=(1,3,1,1).
$$

Določi linearno neodvisnost, bazo njihove ogrinjače, dimenzijo in dopolnitev do baze $\mathbb R^4$.

**Naloga 12.**

V prostoru $\mathbb R_3[x]$ naj bodo

$$
p_1=1+x,\quad
p_2=x+x^2,\quad
p_3=x^2+x^3,\quad
p_4=1+x^3.
$$

Določi linearno neodvisnost, ogrodje, bazo, eno netrivialno zvezo in bazo njihove linearne ogrinjače.

# Odgovori

**1.**

$$
\boxed{(3,5)=(1,1)+2(1,2).}
$$

**2.**

$$
v_3=v_1+v_2.
$$

Zato je množica linearno odvisna, ni ogrodje $\mathbb R^3$ in ni baza.

$$
\boxed{
B=\{(1,1,0),(0,1,1)\},\qquad \dim L(S)=2.
}
$$

**3.**

$$
1+2x+x^2=(1+x)+(x+x^2).
$$

Zato je množica linearno odvisna, ni ogrodje in ni baza.

**4.**

$$
\boxed{
B_U=\{(-1,1,0,0),(1,0,1,2)\},\qquad \dim U=2.
}
$$

**5.**

$$
\boxed{
B_U=
\left\{
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix},
\begin{pmatrix}
0&1\\
1&0
\end{pmatrix},
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix}
\right\},
\qquad
\dim U=3.
}
$$

**6.**

Na primer:

$$
\boxed{
\{(1,1,0),(0,1,1),(1,0,0)\}.
}
$$

**7.**

$$
\boxed{a\ne2.}
$$

Za $a=2$ je tretji vektor vsota prvih dveh.

**8.**

$$
\boxed{t\ne2.}
$$

**9.**

$$
\boxed{
p(x)=(x-1)^2(a+bx).
}
$$

Ena baza je

$$
\boxed{
\{(x-1)^2,\ x(x-1)^2\},
\qquad
\dim U=2.
}
$$

**10.**

$$
A=
\begin{pmatrix}
a&b\\
c&-a
\end{pmatrix}.
$$

$$
\boxed{
B_U=
\left\{
\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix},
\begin{pmatrix}
0&1\\
0&0
\end{pmatrix},
\begin{pmatrix}
0&0\\
1&0
\end{pmatrix}
\right\},
\qquad
\dim U=3.
}
$$

**11.**

$$
v_3=v_1+v_2.
$$

Zato:

$$
\boxed{
B=\{v_1,v_2\},\qquad
\dim L\{v_1,v_2,v_3\}=2.
}
$$

Ena možna dopolnitev:

$$
\boxed{
\{v_1,v_2,(1,0,0,0),(0,0,0,1)\}.
}
$$

**12.**

$$
\boxed{
-p_1+p_2-p_3+p_4=0.
}
$$

Ena baza ogrinjače:

$$
\boxed{
\{p_1,p_2,p_3\},
\qquad
\dim L\{p_1,p_2,p_3,p_4\}=3.
}
$$

Množica ni ogrodje $\mathbb R_3[x]$ in ni baza.

# Faza je zaključena, ko znam ...

- [ ] Natančno definirati **linearno kombinacijo**.
- [ ] Natančno definirati **linearno ogrinjačo** $L(S)$.
- [ ] Natančno definirati **ogrodje**.
- [ ] Natančno definirati **linearno neodvisnost**.
- [ ] Razložiti razliko med linearno odvisnostjo in neodvisnostjo.
- [ ] Natančno definirati **bazo**.
- [ ] Natančno definirati **dimenzijo** končnorazsežnega prostora.
- [ ] Razložiti povezavo $\text{baza}=\text{LN}+\text{ogrodje}$.
- [ ] Razložiti, da ogrodje zagotavlja obstoj, LN pa enoličnost linearnega zapisa.
- [ ] Preveriti, ali se vektor linearno izraža z danimi vektorji.
- [ ] Izračunati koeficiente linearne kombinacije.
- [ ] Preveriti linearno neodvisnost s homogenim sistemom.
- [ ] Hitro prepoznati odvisnost zaradi ničelnega vektorja, večkratnikov ali očitne zveze.
- [ ] Preveriti, ali je množica ogrodje.
- [ ] Preveriti, ali je množica baza.
- [ ] Uporabiti dimenzijo za izločanje nepotrebnega računanja.
- [ ] Vedeti, da je več kot $n$ vektorjev v $n$-razsežnem prostoru linearno odvisnih.
- [ ] Vedeti, da manj kot $n$ vektorjev ne more biti ogrodje $n$-razsežnega prostora.
- [ ] Uporabiti dejstvo, da je $n$ linearno neodvisnih vektorjev v $n$-razsežnem prostoru avtomatično baza.
- [ ] Uporabiti dejstvo, da je ogrodje z natanko $n$ elementi avtomatično baza.
- [ ] Iz pogojev poiskati bazo podprostora vektorskega prostora.
- [ ] Iz pogojev na polinom poiskati bazo podprostora polinomov.
- [ ] Iz pogojev na matriko poiskati bazo matričnega podprostora.
- [ ] Pravilno uporabljati $\dim\mathbb R^n=n$.
- [ ] Pravilno uporabljati $\dim\mathbb R_n[x]=n+1$.
- [ ] Pravilno uporabljati $\dim\mathbb R^{m\times n}=mn$.
- [ ] Iz ogrodja odstraniti odvečne vektorje in dobiti bazo.
- [ ] Linearno neodvisno množico dopolniti do baze večjega prostora.
- [ ] Dokazati, da baza daje enoličen zapis.
- [ ] Dokazati, da je množica, ki vsebuje $0$, linearno odvisna.
- [ ] Dokazati povezavo med linearno odvisnostjo in izražanjem enega vektorja z ostalimi.
- [ ] Na ustnem izpitu brez zapiskov povedati definicije linearne kombinacije, ogrinjače, ogrodja, LN, baze in dimenzije.
- [ ] Na ustnem izpitu razložiti glavne izreke o številu vektorjev v $n$-razsežnem prostoru.
- [ ] Pri polinomih hitro preiti na njihove koeficiente.
- [ ] Pri matrikah razumeti, da jih lahko obravnavam kot vektorje njihovih komponent.
- [ ] Samostojno rešiti reprezentativne naloge iz 4. in 5. vaj.
- [ ] Brez pomoči pravilno rešiti vse srednje težke naloge iz tega poglavja.
- [ ] Brez pomoči pravilno rešiti večino težkih oziroma izpitnih nalog iz tega poglavja.
