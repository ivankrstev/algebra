# FAZA 7 — Lastne vrednosti, lastni vektorji, lastni podprostori in diagonalizacija

## Namen faze

Ta faza je zaključni spektralni del predmeta **Algebra II – Linearna algebra**. V priloženem gradivu se neposredno pojavi v **11. vajah** pri karakterističnem polinomu in v **12. vajah** pri lastnih vrednostih, lastnih vektorjih, lastnih podprostorih in diagonalizaciji.

Najpomembnejši tipi nalog iz priloženega gradiva so:

1. izračunati **karakteristični polinom** endomorfizma ali matrike;
2. poiskati **lastne vrednosti**;
3. rešiti enačbo $Ax=\lambda x$;
4. določiti **lastne podprostore**;
5. preveriti, ali je matrika **diagonalizabilna**;
6. poiskati diagonalno matriko $D$ in obrnljivo matriko $P$, za kateri velja
   $$
   A=PDP^{-1}.
   $$

Najbolj celovita naloga v priloženem gradivu je **12. vaje, naloga 68**, kjer je treba poiskati vse lastne vrednosti, vse lastne podprostore in nato izvesti popolno diagonalizacijo.

> **Opomba o virih:** med priloženimi datotekami so vaje 1–12, ne pa ločeni pretekli izpiti ali kolokviji. Zato je spodnja prioriteta izpitnih tipov določena po dejanskem poudarku v zaključnih vajah. Domače naloge, ki so v vajah navedene samo s številkami iz zbirk, niso vsebinsko analizirane, ker besedila teh nalog niso priložena.

---

## Kaj moram znati pred začetkom

Pred to fazo morajo biti dovolj avtomatizirane naslednje teme:

- **linearna preslikava** in **endomorfizem**;
- jedro in slika linearne preslikave;
- baza in dimenzija;
- matrika linearne preslikave v izbrani bazi;
- Gaussova eliminacija;
- determinant;
- obrnljivost matrike;
- prehod med bazami;
- podobnost matrik;
- invariantni podprostor;
- karakteristični polinom iz prejšnje faze.

Posebej pomembna je povezava:

$$
\ker(A-\lambda I)
$$

ker se skoraj vsaka naloga o lastnih vektorjih reducira na izračun jedra neke matrike.

---

## Pregled celotne snovi

### Jedro faze

- lastna vrednost;
- lastni vektor;
- lastni podprostor;
- karakteristični polinom;
- karakteristična enačba;
- algebraična večkratnost;
- geometrijska večkratnost;
- diagonalizabilnost;
- podobnost z diagonalno matriko;
- konstrukcija matrik $P$ in $D$;
- povezava med lastnimi vektorji in invariantnimi enorazsežnimi podprostori.

### Najpomembnejša veriga pojmov

$$
A
\longrightarrow
p_A(\lambda)
\longrightarrow
\lambda_i
\longrightarrow
\ker(A-\lambda_i I)
\longrightarrow
\text{lastni vektorji}
\longrightarrow
\text{baza iz lastnih vektorjev}
\longrightarrow
A=PDP^{-1}.
$$

Če ta veriga postane rutinska, je večina računskih nalog v tej fazi rešljiva po istem algoritmu.

---

# 1. Lastne vrednosti in lastni vektorji

## Definicija lastne vrednosti

Naj bo $V$ vektorski prostor nad poljem $F$ in

$$
A:V\to V
$$

endomorfizem.

Skalar $\lambda\in F$ je **lastna vrednost** endomorfizma $A$, če obstaja tak neničelni vektor $v\in V$, da velja

$$
A(v)=\lambda v.
$$

Vektor $v\neq 0$, ki zadošča tej enačbi, imenujemo **lastni vektor**, ki pripada lastni vrednosti $\lambda$.

### Kaj definicija pomeni geometrijsko

Če je $v$ lastni vektor, preslikava $A$ ne spremeni njegove smeri v smislu linearne premice skozi izhodišče; spremeni le skalarno velikost oziroma predznak:

$$
v\mapsto \lambda v.
$$

- $\lambda>1$: razteg;
- $0<\lambda<1$: skrčitev;
- $\lambda<0$: sprememba smeri in skaliranje;
- $\lambda=0$: vektor se preslika v ničelni vektor.

Če je $\lambda=0$ lastna vrednost, potem obstaja $v\neq 0$, za katerega velja

$$
Av=0.
$$

Zato:

$$
0\text{ je lastna vrednost}
\iff
\ker A\neq\{0\}
\iff
A\text{ ni injektiven}
\iff
A\text{ ni obrnljiv}.
$$

Za kvadratno matriko velja tudi:

$$
0\text{ je lastna vrednost}
\iff
\det A=0.
$$

---

## Matrična oblika definicije

Če endomorfizmu v neki bazi pripada matrika $A\in F^{n\times n}$, je enačba

$$
Av=\lambda v
$$

ekvivalentna

$$
(A-\lambda I)v=0.
$$

Neničelna rešitev obstaja natanko tedaj, ko je matrika $A-\lambda I$ singularna.

Zato:

$$
\lambda\text{ je lastna vrednost}
\iff
\det(A-\lambda I)=0.
$$

Enakovredno lahko uporabljamo

$$
\det(\lambda I-A)=0.
$$

Ničle so pri obeh konvencijah enake.

---

## Kako prepoznam nalogo

Tipični izrazi v navodilu:

- »Poiščite lastne vrednosti matrike.«
- »Poiščite vse $\lambda$ in $x\neq 0$, za katere velja $Ax=\lambda x$.«
- »Določite spekter matrike.«
- »Poiščite lastne vektorje.«
- »Ali je $0$ lastna vrednost?«

Osnovni odziv mora biti skoraj avtomatičen:

$$
\det(\lambda I-A)=0.
$$

---

## Pogoste napake

- V definiciji pozabiš pogoj **$v\neq 0$**.
- Enačbo $Av=\lambda v$ rešuješ za poljuben $\lambda$, ne da bi najprej poiskal lastne vrednosti.
- Za lastni vektor vzameš ničelni vektor.
- Zamenjaš lastno vrednost in lastni vektor.
- Pri $\lambda=0$ pozabiš, da iščeš
  $$
  \ker A.
  $$
- Pri determinantah izgubiš predznak. Če uporabljaš $\det(\lambda I-A)$ namesto $\det(A-\lambda I)$, so ničle iste, zato naj bo konvencija skozi celotno rešitev dosledna.

---

# 2. Karakteristični polinom

## Definicija

Za matriko $A\in F^{n\times n}$ definiramo **karakteristični polinom**

$$
p_A(\lambda)=\det(\lambda I-A).
$$

V nekaterih virih se uporablja

$$
\det(A-\lambda I).
$$

Ta dva polinoma se lahko razlikujeta za faktor $(-1)^n$, vendar imata enake ničle.

V tem poglavju uporabljamo:

$$
\boxed{p_A(\lambda)=\det(\lambda I-A)}.
$$

---

## Ključni izrek

Skalar $\lambda$ je lastna vrednost matrike $A$ natanko tedaj, ko je ničla karakterističnega polinoma:

$$
\boxed{
\lambda\text{ je lastna vrednost}
\iff
p_A(\lambda)=0
}
$$

### Dokaz

$$
\lambda\text{ je lastna vrednost}
$$

natanko tedaj, ko obstaja $v\neq 0$, da velja

$$
Av=\lambda v.
$$

To je ekvivalentno

$$
(A-\lambda I)v=0.
$$

Neničelna rešitev obstaja natanko tedaj, ko $A-\lambda I$ ni obrnljiva, torej

$$
\det(A-\lambda I)=0.
$$

Zato je $\lambda$ ničla karakterističnega polinoma.

---

## Lastnosti karakterističnega polinoma

Za $A\in F^{n\times n}$:

- $p_A$ je polinom stopnje $n$;
- njegove ničle so lastne vrednosti;
- podobni matriki imata isti karakteristični polinom;
- če je $A$ trikotna, so lastne vrednosti diagonalni elementi;
- če je $A$ diagonalna,
  $$
  A=\operatorname{diag}(a_1,\dots,a_n),
  $$
  potem
  $$
  p_A(\lambda)=\prod_{i=1}^n(\lambda-a_i).
  $$

### Uporabna standardna dopolnitev

Naslednji povezavi sta zelo uporabni za hitro preverjanje rezultata:

$$
\operatorname{tr}(A)=\lambda_1+\cdots+\lambda_n
$$

in

$$
\det A=\lambda_1\cdots\lambda_n,
$$

kjer lastne vrednosti štejemo z algebraičnimi večkratnostmi.

Ti dve formuli sta posebej uporabni kot **kontrola**, ne kot zamenjava za celoten postopek.

---

## Podobnost in karakteristični polinom

Če sta matriki podobni,

$$
B=P^{-1}AP,
$$

potem:

$$
p_B(\lambda)
=
\det(\lambda I-B).
$$

Ker

$$
\lambda I-B
=
P^{-1}(\lambda I-A)P,
$$

sledi

$$
\det(\lambda I-B)
=
\det(P^{-1})
\det(\lambda I-A)
\det(P)
=
\det(\lambda I-A).
$$

Torej:

$$
\boxed{p_B=p_A}.
$$

Zato podobni matriki imata iste lastne vrednosti z enakimi algebraičnimi večkratnostmi.

---

# 3. Lastni podprostori

## Definicija

Za lastno vrednost $\lambda$ definiramo **lastni podprostor**

$$
E_\lambda(A)
=
\{v\in V; Av=\lambda v\}.
$$

Ker je

$$
Av=\lambda v
\iff
(A-\lambda I)v=0,
$$

velja

$$
\boxed{
E_\lambda(A)=\ker(A-\lambda I)
}.
$$

To je ena najpomembnejših formul celotne faze.

---

## Zakaj je to podprostor

Ker je $A-\lambda I$ linearna preslikava, je njeno jedro vektorski podprostor.

Torej je $E_\lambda(A)$ vedno podprostor.

### Pomembna podrobnost

Lastni podprostor vsebuje tudi ničelni vektor, čeprav **ničelni vektor ni lastni vektor**.

Torej:

- $E_\lambda(A)$ = vsi lastni vektorji za $\lambda$ **in** ničelni vektor;
- lastni vektorji so vsi elementi
  $$
  E_\lambda(A)\setminus\{0\}.
  $$

---

## Kako ga izračunam

Za vsako lastno vrednost $\lambda$ rešim homogeni sistem

$$
(A-\lambda I)x=0.
$$

Rezultat zapišem kot linearno ogrinjačo:

$$
E_\lambda(A)=L\{v_1,\dots,v_k\}.
$$

Število baznih vektorjev je

$$
\dim E_\lambda(A).
$$

---

## Povezava z invariantnimi podprostori

Če je $v$ lastni vektor za $\lambda$, potem je enorazsežni podprostor

$$
L\{v\}
$$

invarianten za $A$, saj za vsak $c\in F$ velja

$$
A(cv)=cA(v)=c\lambda v\in L\{v\}.
$$

Pravzaprav je celoten lastni podprostor invarianten:

$$
A(E_\lambda)\subseteq E_\lambda.
$$

---

# 4. Algebraična in geometrijska večkratnost

> Pojma sta standardna teorija diagonalizacije. V priloženih zaključnih vajah nista poimensko razložena, vendar sta potrebna za sistematično razumevanje, zakaj se nekatere matrike diagonalizirajo in druge ne.

## Algebraična večkratnost

Če je

$$
p_A(\lambda)
=
(\lambda-\lambda_0)^m q(\lambda)
$$

in

$$
q(\lambda_0)\neq 0,
$$

je **algebraična večkratnost** lastne vrednosti $\lambda_0$ enaka

$$
m_a(\lambda_0)=m.
$$

---

## Geometrijska večkratnost

**Geometrijska večkratnost** je dimenzija lastnega podprostora:

$$
m_g(\lambda)
=
\dim E_\lambda(A)
=
\dim\ker(A-\lambda I).
$$

---

## Temeljna neenakost

Za vsako lastno vrednost velja:

$$
\boxed{
1\leq m_g(\lambda)\leq m_a(\lambda)
}
$$

Če je $\lambda$ lastna vrednost, je lastni podprostor neničeln, zato je geometrijska večkratnost vsaj $1$.

Geometrijska večkratnost pa ne more preseči algebraične večkratnosti.

---

## Zakaj je neenakost pomembna

Če ima neka lastna vrednost:

$$
m_g(\lambda)<m_a(\lambda),
$$

potem za to lastno vrednost nimamo dovolj linearno neodvisnih lastnih vektorjev.

To je tipičen razlog, da matrika **ni diagonalizabilna**.

---

## Posebej pomembna primera

### Vse lastne vrednosti so različne

Če ima matrika $A\in F^{n\times n}$ natanko $n$ različnih lastnih vrednosti, potem pripadajoči lastni vektorji tvorijo linearno neodvisno množico z $n$ elementi.

Zato je $A$ diagonalizabilna.

### Lastna vrednost se ponovi

Če se $\lambda$ v karakterističnem polinomu ponovi, to **še ne pomeni**, da matrika ni diagonalizabilna.

Treba je izračunati:

$$
\dim E_\lambda.
$$

Primer:

$$
m_a(\lambda)=2,\qquad m_g(\lambda)=2
$$

je povsem združljiv z diagonalizabilnostjo.

Toda:

$$
m_a(\lambda)=2,\qquad m_g(\lambda)=1
$$

pomeni, da matrika ni diagonalizabilna.

---

# 5. Linearna neodvisnost lastnih vektorjev

## Izrek

Lastni vektorji, ki pripadajo **paroma različnim lastnim vrednostim**, so linearno neodvisni.

### Posledica

Če ima $n\times n$ matrika $n$ različnih lastnih vrednosti, je diagonalizabilna.

---

## Dokaz za dva lastna vektorja

Naj bosta

$$
Av_1=\lambda_1v_1,
\qquad
Av_2=\lambda_2v_2,
$$

kjer je

$$
\lambda_1\neq\lambda_2.
$$

Predpostavimo

$$
\alpha v_1+\beta v_2=0.
$$

Na enačbo uporabimo $A$:

$$
\alpha\lambda_1v_1+\beta\lambda_2v_2=0.
$$

Prvo enačbo pomnožimo z $\lambda_1$:

$$
\alpha\lambda_1v_1+\beta\lambda_1v_2=0.
$$

Odštejemo:

$$
\beta(\lambda_2-\lambda_1)v_2=0.
$$

Ker je

$$
v_2\neq 0
$$

in

$$
\lambda_2-\lambda_1\neq 0,
$$

sledi

$$
\beta=0.
$$

Nato tudi

$$
\alpha=0.
$$

Torej sta $v_1$ in $v_2$ linearno neodvisna.

Za več lastnih vektorjev se dokaz razširi z indukcijo.

---

# 6. Diagonalizacija

## Definicija

Matrika $A\in F^{n\times n}$ je **diagonalizabilna nad poljem $F$**, če obstajata:

- obrnljiva matrika $P\in F^{n\times n}$;
- diagonalna matrika $D\in F^{n\times n}$,

tako da velja

$$
\boxed{
A=PDP^{-1}
}.
$$

Enakovredno:

$$
\boxed{
D=P^{-1}AP
}.
$$

To pomeni, da je $A$ podobna diagonalni matriki.

---

## Glavni izrek o diagonalizaciji

Naj bo $A:V\to V$ endomorfizem končnorazsežnega vektorskega prostora.

Naslednje trditve so ekvivalentne:

1. $A$ je diagonalizabilen.
2. Obstaja baza prostora $V$, sestavljena iz lastnih vektorjev endomorfizma $A$.
3. Vsota dimenzij vseh lastnih podprostorov je enaka $\dim V$.
4. Če karakteristični polinom razpade na linearne faktorje nad osnovnim poljem, potem za vsako lastno vrednost velja
   $$
   m_g(\lambda)=m_a(\lambda).
   $$

---

## Zakaj stolpci matrike $P$ morajo biti lastni vektorji

Naj bodo

$$
v_1,\dots,v_n
$$

linearno neodvisni lastni vektorji z lastnimi vrednostmi

$$
\lambda_1,\dots,\lambda_n.
$$

Postavimo

$$
P=
\begin{pmatrix}
| & | & & |\\
v_1 & v_2 & \cdots & v_n\\
| & | & & |
\end{pmatrix}
$$

in

$$
D=
\operatorname{diag}(\lambda_1,\dots,\lambda_n).
$$

Ker velja

$$
Av_i=\lambda_i v_i,
$$

dobimo

$$
AP=PD.
$$

Ker je $P$ obrnljiva:

$$
AP=PD
$$

pomeni

$$
A=PDP^{-1}.
$$

---

## Najpomembnejše pravilo pri sestavljanju $P$ in $D$

Vrstni red mora biti usklajen.

Če je prvi stolpec $P$ lastni vektor za $\lambda_1$, mora biti prvi diagonalni element $D$ enak $\lambda_1$.

Če je:

$$
P=
\begin{pmatrix}
|&|&|\\
v_3&v_1&v_2\\
|&|&|
\end{pmatrix},
$$

mora biti

$$
D=
\operatorname{diag}(\lambda_3,\lambda_1,\lambda_2).
$$

---

## Kriterij s številom lastnih vektorjev

Za $A\in F^{n\times n}$:

$$
\boxed{
A\text{ je diagonalizabilna}
\iff
A\text{ ima }n\text{ linearno neodvisnih lastnih vektorjev}.
}
$$

To je najbolj praktičen kriterij na izpitu.

---

## Polje je pomembno

Diagonalizabilnost je vedno treba razumeti **nad določenim poljem**.

Primer:

$$
A=
\begin{pmatrix}
0&-1\\
1&0
\end{pmatrix}.
$$

Karakteristični polinom je

$$
p_A(\lambda)=\lambda^2+1.
$$

Nad $\mathbb R$ nima ničel, zato matrika ni diagonalizabilna nad $\mathbb R$.

Nad $\mathbb C$ ima lastni vrednosti

$$
i,\qquad -i,
$$

ki sta različni, zato je diagonalizabilna nad $\mathbb C$.

---

# 7. Kako izberem metodo glede na obliko naloge

## Če je podana matrika in vprašajo samo lastne vrednosti

Uporabi:

$$
p_A(\lambda)=\det(\lambda I-A).
$$

Nato reši:

$$
p_A(\lambda)=0.
$$

Ne računaj lastnih podprostorov, če niso zahtevani.

---

## Če vprašajo vse rešitve enačbe $Ax=\lambda x$

Najprej določi dovoljene $\lambda$:

$$
\det(\lambda I-A)=0.
$$

Nato za vsak tak $\lambda$ reši:

$$
(A-\lambda I)x=0.
$$

V odgovor napiši:

$$
\lambda=\lambda_i,\qquad
x\in E_{\lambda_i}\setminus\{0\}.
$$

---

## Če vprašajo lastne podprostore

Za vsak $\lambda$ izračunaj:

$$
E_\lambda=\ker(A-\lambda I).
$$

Nato zapiši bazo:

$$
E_\lambda=L\{v_1,\dots,v_k\}.
$$

---

## Če vprašajo diagonalizacijo

Vedno naredi celotno zaporedje:

1. $p_A(\lambda)$;
2. lastne vrednosti;
3. algebraične večkratnosti;
4. baze lastnih podprostorov;
5. dimenzije lastnih podprostorov;
6. preveri, ali skupaj dobiš $n$ linearno neodvisnih lastnih vektorjev;
7. sestavi $P$;
8. sestavi $D$;
9. po želji preveri
   $$
   AP=PD.
   $$

---

## Če je matrika trikotna

Lastne vrednosti so takoj diagonalni elementi.

Za

$$
A=
\begin{pmatrix}
a&*&*\\
0&b&*\\
0&0&c
\end{pmatrix}
$$

velja

$$
p_A(\lambda)
=
(\lambda-a)(\lambda-b)(\lambda-c).
$$

Še vedno pa moraš za diagonalizacijo računati lastne podprostore, če se kakšna lastna vrednost ponovi.

---

## Če opaziš $A^2=I$

Iz

$$
Av=\lambda v
$$

sledi

$$
A^2v=\lambda^2v.
$$

Če je $A^2=I$, je

$$
v=\lambda^2v,
$$

zato mora za lastni vektor veljati

$$
\lambda^2=1.
$$

Torej so možne lastne vrednosti samo

$$
\lambda=\pm1.
$$

Nad poljem karakteristike, različne od $2$, lahko vsak vektor razcepimo:

$$
v=
\frac{v+Av}{2}
+
\frac{v-Av}{2}.
$$

Pri tem:

$$
\frac{v+Av}{2}\in E_1,
$$

in

$$
\frac{v-Av}{2}\in E_{-1}.
$$

Zato:

$$
V=E_1\oplus E_{-1}
$$

in tak endomorfizem je diagonalizabilen.

To je zelo uporabna bližnjica pri blokovni matriki iz 12. vaj.

---

# 8. Tip naloge: Karakteristični polinom linearne preslikave, podane s predpisom

## Kako jo prepoznam

Podana je preslikava na prostoru polinomov, matrik ali funkcij, ne pa neposredno matrika.

Najprej moraš izbrati oziroma uporabiti znano bazo, izračunati matriko preslikave in šele nato karakteristični polinom.

V 11. vajah je podan primer

$$
A:\mathbb R_2[x]\to\mathbb R_2[x],
\qquad
A(f)=f(0)+f.
$$

---

## Postopek

1. Izberi standardno bazo
   $$
   \Sigma=(1,x,x^2).
   $$
2. Izračunaj slike baznih vektorjev.
3. Zapiši koordinatne stolpce slik v bazi $\Sigma$.
4. Iz njih sestavi matriko $M_\Sigma^\Sigma(A)$.
5. Izračunaj
   $$
   p_A(\lambda)=\det(\lambda I-M).
   $$

---

## Pomembne formule

$$
M_\Sigma^\Sigma(A)
=
\begin{pmatrix}
|&|&|\\
X_\Sigma(A(1))&
X_\Sigma(A(x))&
X_\Sigma(A(x^2))\\
|&|&|
\end{pmatrix}.
$$

---

## Primer

Naj bo

$$
A:\mathbb R_2[x]\to\mathbb R_2[x],
\qquad
A(f)=f(0)+f.
$$

Poišči karakteristični polinom.

---

## Rešitev

V standardni bazi

$$
\Sigma=(1,x,x^2)
$$

velja:

$$
A(1)=1+1=2,
$$

$$
A(x)=x,
$$

$$
A(x^2)=x^2.
$$

Zato je

$$
M_\Sigma^\Sigma(A)
=
\begin{pmatrix}
2&0&0\\
0&1&0\\
0&0&1
\end{pmatrix}.
$$

Torej:

$$
p_A(\lambda)
=
\det
\begin{pmatrix}
\lambda-2&0&0\\
0&\lambda-1&0\\
0&0&\lambda-1
\end{pmatrix}.
$$

Dobimo:

$$
\boxed{
p_A(\lambda)
=
(\lambda-2)(\lambda-1)^2
}.
$$

Dodatno:

$$
\lambda=2,\quad E_2=L\{1\},
$$

$$
\lambda=1,\quad E_1=L\{x,x^2\}.
$$

Preslikava je diagonalizabilna.

---

## Pogoste napake

- Matriko napišeš brez navedbe baze.
- Slike baznih vektorjev daš v vrstice namesto v stolpce.
- Pri $A(1)$ pozabiš, da je
  $$
  1(0)=1.
  $$
- Pri $A(x)$ napačno izračunaš
  $$
  x(0)=0.
  $$

---

# 9. Tip naloge: Karakteristični polinom posebne blokovne matrike

## Kako jo prepoznam

Matrika ima očitno strukturo, npr.

$$
A=
\begin{pmatrix}
0&I\\
I&0
\end{pmatrix},
$$

kjer je $I$ identična matrika.

V 12. vajah je $I$ velikosti $2\times2$.

---

## Postopek

Možna sta dva pristopa:

1. neposredno računanje determinante;
2. izkoristiš delovanje matrike na blokovnih vektorjih.

Drugi pristop je hitrejši.

---

## Primer

Naj bo

$$
A=
\begin{pmatrix}
0&I\\
I&0
\end{pmatrix}
\in\mathbb R^{4\times4},
$$

kjer je $I\in\mathbb R^{2\times2}$.

Poišči karakteristični polinom.

---

## Rešitev

Vektor zapišimo v blokovni obliki

$$
\binom{u}{v},
\qquad
u,v\in\mathbb R^2.
$$

Velja:

$$
A\binom{u}{v}
=
\binom{v}{u}.
$$

Za lastno vrednost $\lambda$ mora veljati:

$$
\binom{v}{u}
=
\lambda
\binom{u}{v}.
$$

Torej:

$$
v=\lambda u,
\qquad
u=\lambda v.
$$

Sledi:

$$
u=\lambda^2u.
$$

Za neničelni lastni vektor:

$$
\lambda^2=1.
$$

Torej:

$$
\lambda=1
\quad\text{ali}\quad
\lambda=-1.
$$

Za $\lambda=1$:

$$
v=u,
$$

zato:

$$
E_1
=
\left\{
\binom{u}{u};
u\in\mathbb R^2
\right\},
$$

in

$$
\dim E_1=2.
$$

Za $\lambda=-1$:

$$
v=-u,
$$

zato:

$$
E_{-1}
=
\left\{
\binom{u}{-u};
u\in\mathbb R^2
\right\},
$$

in

$$
\dim E_{-1}=2.
$$

Ker je skupna dimenzija $4$, je:

$$
\boxed{
p_A(\lambda)
=
(\lambda-1)^2(\lambda+1)^2
=
(\lambda^2-1)^2
}.
$$

Matrika je tudi diagonalizabilna.

---

## Pogoste napake

- Iz $A^2=I$ sklepaš, da je karakteristični polinom samo $\lambda^2-1$. Pri matriki velikosti $4\times4$ mora biti stopnja karakterističnega polinoma $4$.
- Ne določiš večkratnosti lastnih vrednosti.
- Zamenjaš blokovna vektorja $u$ in $v$.

---

# 10. Tip naloge: Iz matrike poišči lastne vrednosti in odloči o diagonalizabilnosti

## Kako jo prepoznam

Podana je kvadratna matrika. Vprašanje zahteva lastne vrednosti ali pa diagonalizabilnost.

Primer iz 12. vaj:

$$
A=
\begin{pmatrix}
2&0&-1\\
6&8&-5\\
9&9&-7
\end{pmatrix}.
$$

---

## Postopek

1. Izračunaj
   $$
   p_A(\lambda)=\det(\lambda I-A).
   $$
2. Faktoriziraj.
3. Poišči lastne vrednosti in algebraične večkratnosti.
4. Če je zahtevana diagonalizabilnost, izračunaj vse lastne podprostore.
5. Primerjaj algebraične in geometrijske večkratnosti.

---

## Primer

Poišči lastne vrednosti matrike

$$
A=
\begin{pmatrix}
2&0&-1\\
6&8&-5\\
9&9&-7
\end{pmatrix}
$$

in preveri, ali je diagonalizabilna.

---

## Rešitev

Izračunamo:

$$
\lambda I-A
=
\begin{pmatrix}
\lambda-2&0&1\\
-6&\lambda-8&5\\
-9&-9&\lambda+7
\end{pmatrix}.
$$

Razvijemo po prvi vrstici:

$$
p_A(\lambda)
=
(\lambda-2)
\begin{vmatrix}
\lambda-8&5\\
-9&\lambda+7
\end{vmatrix}
+
\begin{vmatrix}
-6&\lambda-8\\
-9&-9
\end{vmatrix}.
$$

Prvi minor:

$$
(\lambda-8)(\lambda+7)+45
=
\lambda^2-\lambda-11.
$$

Drugi minor:

$$
54+9(\lambda-8)
=
9\lambda-18
=
9(\lambda-2).
$$

Zato:

$$
p_A(\lambda)
=
(\lambda-2)(\lambda^2-\lambda-11)
+
9(\lambda-2).
$$

$$
p_A(\lambda)
=
(\lambda-2)(\lambda^2-\lambda-2).
$$

$$
\boxed{
p_A(\lambda)
=
(\lambda-2)^2(\lambda+1)
}.
$$

Lastni vrednosti sta:

$$
\boxed{\lambda_1=2,\qquad \lambda_2=-1}.
$$

Za $\lambda=2$ rešimo:

$$
(A-2I)x=0.
$$

Dobimo:

$$
E_2=L\{(-1,1,0)\},
$$

zato:

$$
m_g(2)=1.
$$

Toda iz karakterističnega polinoma:

$$
m_a(2)=2.
$$

Torej:

$$
m_g(2)<m_a(2).
$$

Zato:

$$
\boxed{A\text{ ni diagonalizabilna}.}
$$

Za popolnost:

$$
E_{-1}=L\{(1,1,3)\}.
$$

---

## Pogoste napake

- Ker sta samo dve različni lastni vrednosti pri matriki $3\times3$, takoj sklepaš, da matrika ni diagonalizabilna. To ni dovolj.
- Ker je $\lambda=2$ dvojna ničla, avtomatično predpostaviš dva linearno neodvisna lastna vektorja.
- Ne izračunaš $\dim E_2$.
- Pri determinantah izgubiš ponovljeni faktor $(\lambda-2)$.

---

# 11. Tip naloge: Reši enačbo $Ax=\lambda x$

## Kako jo prepoznam

Navodilo je zapisano neposredno kot:

$$
Ax=\lambda x,
$$

pri čemer sta neznana tako $\lambda$ kot tudi neničelni vektor $x$.

V 12. vajah nastopi matrika

$$
A=
\begin{pmatrix}
2&1&-1\\
-2&-1&-4\\
0&0&-5
\end{pmatrix}.
$$

---

## Postopek

1. Poišči vse $\lambda$ iz
   $$
   \det(\lambda I-A)=0.
   $$
2. Za vsak $\lambda$ posebej reši
   $$
   (A-\lambda I)x=0.
   $$
3. V odgovoru izključi ničelni vektor.

---

## Primer

Poišči vse $\lambda\in\mathbb R$ in vse neničelne stolpce $x\in\mathbb R^3$, za katere velja

$$
\begin{pmatrix}
2&1&-1\\
-2&-1&-4\\
0&0&-5
\end{pmatrix}
x
=
\lambda x.
$$

---

## Rešitev

Izračunamo:

$$
\lambda I-A
=
\begin{pmatrix}
\lambda-2&-1&1\\
2&\lambda+1&4\\
0&0&\lambda+5
\end{pmatrix}.
$$

Zato:

$$
p_A(\lambda)
=
(\lambda+5)
\begin{vmatrix}
\lambda-2&-1\\
2&\lambda+1
\end{vmatrix}.
$$

$$
p_A(\lambda)
=
(\lambda+5)
\left(
(\lambda-2)(\lambda+1)+2
\right).
$$

$$
p_A(\lambda)
=
(\lambda+5)\lambda(\lambda-1).
$$

Torej:

$$
\lambda\in\{-5,0,1\}.
$$

### Za $\lambda=-5$

Rešimo:

$$
(A+5I)x=0.
$$

Dobimo:

$$
E_{-5}=L\{(0,1,1)\}.
$$

Zato:

$$
x=t(0,1,1),
\qquad
t\neq0.
$$

### Za $\lambda=0$

Rešimo:

$$
Ax=0.
$$

Dobimo:

$$
E_0=L\{(-1,2,0)\}.
$$

Zato:

$$
x=t(-1,2,0),
\qquad
t\neq0.
$$

### Za $\lambda=1$

Rešimo:

$$
(A-I)x=0.
$$

Dobimo:

$$
E_1=L\{(-1,1,0)\}.
$$

Zato:

$$
x=t(-1,1,0),
\qquad
t\neq0.
$$

Končni odgovor:

$$
\boxed{
\begin{aligned}
\lambda&=-5,&x&=t(0,1,1),\ t\neq0,\\
\lambda&=0,&x&=t(-1,2,0),\ t\neq0,\\
\lambda&=1,&x&=t(-1,1,0),\ t\neq0.
\end{aligned}
}
$$

Ker so tri lastne vrednosti različne, je matrika tudi diagonalizabilna.

---

## Pogoste napake

- Za vsak realni $\lambda$ poskušaš reševati sistem.
- Pozabiš izključiti $t=0$.
- Napišeš samo en lastni vektor, čeprav naloga sprašuje po vseh $x$.
- Ne ločiš med lastnim vektorjem in lastnim podprostorom.

---

# 12. Tip naloge: Popolna diagonalizacija $A=PDP^{-1}$

## Kako jo prepoznam

Naloga zahteva:

- vse lastne vrednosti;
- vse lastne podprostore;
- dokaz oziroma preverjanje diagonalizabilnosti;
- matriki $P$ in $D$.

To je najcelovitejši tip naloge v tej fazi.

---

## Splošni postopek

1. Izračunaj karakteristični polinom:
   $$
   p_A(\lambda)=\det(\lambda I-A).
   $$
2. Faktoriziraj.
3. Zapiši lastne vrednosti in algebraične večkratnosti.
4. Za vsako $\lambda$ izračunaj:
   $$
   E_\lambda=\ker(A-\lambda I).
   $$
5. Seštej dimenzije lastnih podprostorov.
6. Če je vsota enaka $n$, izberi bazo vsakega lastnega podprostora.
7. Vse lastne vektorje zloži kot stolpce v $P$.
8. Lastne vrednosti v istem vrstnem redu zapiši na diagonalo $D$.
9. Preveri:
   $$
   AP=PD.
   $$

---

## Primer iz 12. vaj

Naj bo

$$
A=
\begin{pmatrix}
1&1&0&1\\
0&1&1&0\\
1&-1&-2&1\\
1&0&-1&1
\end{pmatrix}.
$$

Poišči vse lastne vrednosti in lastne podprostore ter diagonaliziraj matriko.

---

## Rešitev

### 1. Karakteristični polinom

$$
\lambda I-A
=
\begin{pmatrix}
\lambda-1&-1&0&-1\\
0&\lambda-1&-1&0\\
-1&1&\lambda+2&-1\\
-1&0&1&\lambda-1
\end{pmatrix}.
$$

Razvoj po drugi vrstici da:

$$
p_A(\lambda)
=
(\lambda-1)\lambda(\lambda^2-3)
+
\lambda(\lambda-3).
$$

Izpostavimo $\lambda$:

$$
p_A(\lambda)
=
\lambda
\left(
(\lambda-1)(\lambda^2-3)+\lambda-3
\right).
$$

Po poenostavitvi:

$$
p_A(\lambda)
=
\lambda^2(\lambda^2-\lambda-2).
$$

Torej:

$$
\boxed{
p_A(\lambda)
=
\lambda^2(\lambda-2)(\lambda+1)
}.
$$

Lastne vrednosti so:

$$
\boxed{
\lambda=-1,\quad
\lambda=0,\quad
\lambda=2
}.
$$

Algebraične večkratnosti:

$$
m_a(-1)=1,
$$

$$
m_a(0)=2,
$$

$$
m_a(2)=1.
$$

---

### 2. Lastni podprostor za $\lambda=-1$

Rešimo:

$$
(A+I)x=0.
$$

Po Gaussovi eliminaciji dobimo:

$$
\begin{pmatrix}
1&0&0&0\\
0&1&0&1\\
0&0&1&-2\\
0&0&0&0
\end{pmatrix}.
$$

Torej:

$$
x_1=0,
$$

$$
x_2=-x_4,
$$

$$
x_3=2x_4.
$$

Postavimo $x_4=t$:

$$
x=t(0,-1,2,1).
$$

Zato:

$$
\boxed{
E_{-1}
=
L\{(0,-1,2,1)\}
}.
$$

---

### 3. Lastni podprostor za $\lambda=0$

Rešimo:

$$
Ax=0.
$$

Po Gaussovi eliminaciji:

$$
\begin{pmatrix}
1&0&-1&1\\
0&1&1&0\\
0&0&0&0\\
0&0&0&0
\end{pmatrix}.
$$

Torej:

$$
x_1-x_3+x_4=0,
$$

$$
x_2+x_3=0.
$$

Naj bo:

$$
x_3=s,
\qquad
x_4=t.
$$

Potem:

$$
x_1=s-t,
$$

$$
x_2=-s.
$$

Zato:

$$
x
=
s(1,-1,1,0)
+
t(-1,0,0,1).
$$

Torej:

$$
\boxed{
E_0
=
L\{
(1,-1,1,0),
(-1,0,0,1)
\}
}.
$$

In:

$$
\dim E_0=2.
$$

---

### 4. Lastni podprostor za $\lambda=2$

Rešimo:

$$
(A-2I)x=0.
$$

Po Gaussovi eliminaciji:

$$
\begin{pmatrix}
1&0&0&-\frac32\\
0&1&0&-\frac12\\
0&0&1&-\frac12\\
0&0&0&0
\end{pmatrix}.
$$

Torej:

$$
x_1=\frac32x_4,
$$

$$
x_2=\frac12x_4,
$$

$$
x_3=\frac12x_4.
$$

Izberemo $x_4=2t$:

$$
x=t(3,1,1,2).
$$

Zato:

$$
\boxed{
E_2=L\{(3,1,1,2)\}
}.
$$

---

### 5. Preverjanje diagonalizabilnosti

Dimenzije lastnih podprostorov so:

$$
\dim E_{-1}=1,
$$

$$
\dim E_0=2,
$$

$$
\dim E_2=1.
$$

Zato:

$$
1+2+1=4.
$$

Imamo štiri linearno neodvisne lastne vektorje.

Torej:

$$
\boxed{A\text{ je diagonalizabilna}.}
$$

---

### 6. Konstrukcija $P$ in $D$

Izberimo:

$$
v_1=(0,-1,2,1),
$$

$$
v_2=(1,-1,1,0),
$$

$$
v_3=(-1,0,0,1),
$$

$$
v_4=(3,1,1,2).
$$

Pripadajoče lastne vrednosti so:

$$
-1,\quad0,\quad0,\quad2.
$$

Zato:

$$
P=
\begin{pmatrix}
0&1&-1&3\\
-1&-1&0&1\\
2&1&0&1\\
1&0&1&2
\end{pmatrix}
$$

in

$$
D=
\begin{pmatrix}
-1&0&0&0\\
0&0&0&0\\
0&0&0&0\\
0&0&0&2
\end{pmatrix}.
$$

Ker so stolpci $P$ baza iz lastnih vektorjev, je $P$ obrnljiva. Dejansko:

$$
\det P=-6\neq0.
$$

Velja:

$$
AP=PD.
$$

Zato:

$$
\boxed{
A=PDP^{-1}
}.
$$

---

## Kaj je pri tej nalogi najbolj pomembno

Na izpitu ni dovolj napisati samo lastnih vrednosti.

Za popolno diagonalizacijo mora biti jasno razvidno:

- kako si dobil karakteristični polinom;
- kako si dobil vsak lastni podprostor;
- zakaj imaš dovolj lastnih vektorjev;
- kateri stolpec $P$ pripada kateri diagonalni vrednosti v $D$.

---

## Pogoste napake

- Za $\lambda=0$ najdeš samo en lastni vektor, čeprav je lastni podprostor dvorazsežen.
- Napačno sklepaš, da dvojna lastna vrednost pomeni nedagonalizabilnost.
- Stolpci $P$ in diagonalni elementi $D$ niso v istem vrstnem redu.
- V $P$ daš vektorje kot vrstice.
- Pozabiš preveriti, da je $P$ obrnljiva.
- Zapišeš
  $$
  A=P^{-1}DP
  $$
  namesto pravilne zveze za izbrano konvencijo
  $$
  A=PDP^{-1}.
  $$

---

# 13. Hiter algoritem za pisni izpit

Ko vidiš nalogo o lastnih vrednostih, si na rob napiši:

$$
\boxed{
p_A
\to
\lambda
\to
E_\lambda
\to
\dim E_\lambda
\to
P,D
}
$$

Nato delaj po vrsti.

## Minimalni zapis, ki mora biti v rešitvi

### Korak 1

$$
p_A(\lambda)
=
\det(\lambda I-A)
=
\dots
$$

### Korak 2

$$
p_A(\lambda)
=
(\lambda-\lambda_1)^{m_1}\cdots
(\lambda-\lambda_k)^{m_k}.
$$

### Korak 3

$$
E_{\lambda_i}
=
\ker(A-\lambda_iI)
=
L\{\dots\}.
$$

### Korak 4

$$
\sum_i\dim E_{\lambda_i}=n
$$

ali pa pokažeš, kje dimenzij primanjkuje.

### Korak 5

Če je diagonalizabilna:

$$
P=(v_1|\cdots|v_n),
$$

$$
D=\operatorname{diag}(\lambda_1,\dots,\lambda_n),
$$

$$
A=PDP^{-1}.
$$

---

# 14. Kontrolni seznam za računanje brez napak

Preden oddaš nalogo, preveri:

1. Ali je stopnja $p_A$ enaka velikosti matrike?
2. Ali se vsota algebraičnih večkratnosti ujema z $n$?
3. Ali je vsak bazni vektor $E_\lambda$ res rešitev
   $$
   (A-\lambda I)v=0?
   $$
4. Ali za vsak izbrani lastni vektor velja
   $$
   Av=\lambda v?
   $$
5. Ali je skupno število stolpcev $P$ enako $n$?
6. Ali so stolpci $P$ linearno neodvisni?
7. Ali je vrstni red lastnih vrednosti v $D$ enak vrstnemu redu stolpcev $P$?
8. Ali velja
   $$
   AP=PD?
   $$

---

# 15. Ustni del — osnovne definicije

## Ustno vprašanje

**Vprašanje:** Kaj je lastna vrednost endomorfizma?

**Kratek odgovor:** Skalar $\lambda\in F$ je lastna vrednost endomorfizma $A:V\to V$, če obstaja neničelni vektor $v\in V$, da velja

$$
A(v)=\lambda v.
$$

Tak $v$ imenujemo lastni vektor za $\lambda$.

**Profesor lahko dodatno vpraša:** Zakaj zahtevamo $v\neq0$?

**Odgovor:** Ker za ničelni vektor velja $A(0)=\lambda0$ za vsak $\lambda$, zato brez pogoja $v\neq0$ definicija ne bi razlikovala lastnih vrednosti.

---

## Ustno vprašanje

**Vprašanje:** Kaj je lastni podprostor?

**Kratek odgovor:** Za lastno vrednost $\lambda$ je lastni podprostor

$$
E_\lambda(A)
=
\{v\in V; A(v)=\lambda v\}.
$$

Enakovredno:

$$
E_\lambda(A)=\ker(A-\lambda I).
$$

**Profesor lahko dodatno vpraša:** Ali je ničelni vektor lastni vektor?

**Odgovor:** Ne. Je pa element vsakega lastnega podprostora.

---

## Ustno vprašanje

**Vprašanje:** Zakaj je lastni podprostor res vektorski podprostor?

**Kratek odgovor:** Ker velja

$$
E_\lambda(A)=\ker(A-\lambda I),
$$

jedro linearne preslikave pa je vedno vektorski podprostor.

**Profesor lahko dodatno vpraša:** Ali je $E_\lambda$ invarianten za $A$?

**Odgovor:** Da. Če je $v\in E_\lambda$, potem je $Av=\lambda v\in E_\lambda$.

---

# 16. Ustni del — karakteristični polinom

## Ustno vprašanje

**Vprašanje:** Definiraj karakteristični polinom matrike.

**Kratek odgovor:**

Za $A\in F^{n\times n}$ je

$$
p_A(\lambda)=\det(\lambda I-A).
$$

Njegove ničle so lastne vrednosti matrike.

**Profesor lahko dodatno vpraša:** Kaj če definiramo $p_A(\lambda)=\det(A-\lambda I)$?

**Odgovor:** Polinoma se razlikujeta za faktor $(-1)^n$, zato imata enake ničle in posledično iste lastne vrednosti.

---

## Ustno vprašanje

**Vprašanje:** Dokaži, da je $\lambda$ lastna vrednost natanko tedaj, ko je $p_A(\lambda)=0$.

**Kratek odgovor:**

$$
\lambda\text{ lastna}
\iff
\exists v\neq0:\ Av=\lambda v
$$

$$
\iff
\exists v\neq0:\ (A-\lambda I)v=0
$$

$$
\iff
\ker(A-\lambda I)\neq\{0\}
$$

$$
\iff
A-\lambda I\text{ ni obrnljiva}
$$

$$
\iff
\det(A-\lambda I)=0.
$$

**Profesor lahko dodatno vpraša:** Kaj to pomeni za $\lambda=0$?

**Odgovor:** $0$ je lastna vrednost natanko tedaj, ko je $A$ singularna oziroma $\det A=0$.

---

## Ustno vprašanje

**Vprašanje:** Zakaj imajo podobne matrike isti karakteristični polinom?

**Kratek odgovor:** Če je

$$
B=P^{-1}AP,
$$

potem

$$
\lambda I-B
=
P^{-1}(\lambda I-A)P.
$$

Zato:

$$
\det(\lambda I-B)
=
\det(P^{-1})
\det(\lambda I-A)
\det(P)
=
\det(\lambda I-A).
$$

**Profesor lahko dodatno vpraša:** Kaj sledi za lastne vrednosti?

**Odgovor:** Podobni matriki imata iste lastne vrednosti z enakimi algebraičnimi večkratnostmi.

---

# 17. Ustni del — algebraična in geometrijska večkratnost

## Ustno vprašanje

**Vprašanje:** Kaj je algebraična večkratnost lastne vrednosti?

**Kratek odgovor:** Če je

$$
p_A(\lambda)
=
(\lambda-\lambda_0)^m q(\lambda)
$$

in $q(\lambda_0)\neq0$, je algebraična večkratnost $\lambda_0$ enaka $m$.

**Profesor lahko dodatno vpraša:** Kaj je geometrijska večkratnost?

**Odgovor:**

$$
m_g(\lambda_0)
=
\dim E_{\lambda_0}
=
\dim\ker(A-\lambda_0I).
$$

---

## Ustno vprašanje

**Vprašanje:** Kakšna je povezava med algebraično in geometrijsko večkratnostjo?

**Kratek odgovor:** Za vsako lastno vrednost velja

$$
1\leq m_g(\lambda)\leq m_a(\lambda).
$$

**Profesor lahko dodatno vpraša:** Zakaj je ta neenakost pomembna za diagonalizacijo?

**Odgovor:** Če za neko lastno vrednost velja

$$
m_g(\lambda)<m_a(\lambda),
$$

nimamo dovolj linearno neodvisnih lastnih vektorjev, zato matrika ni diagonalizabilna.

---

# 18. Ustni del — diagonalizacija

## Ustno vprašanje

**Vprašanje:** Kaj pomeni, da je matrika diagonalizabilna?

**Kratek odgovor:** Matrika $A$ je diagonalizabilna, če obstajata obrnljiva matrika $P$ in diagonalna matrika $D$, da velja

$$
A=PDP^{-1}.
$$

Enakovredno:

$$
D=P^{-1}AP.
$$

**Profesor lahko dodatno vpraša:** Kaj predstavljajo stolpci $P$?

**Odgovor:** Stolpci $P$ so baza prostora, sestavljena iz lastnih vektorjev matrike $A$.

---

## Ustno vprašanje

**Vprašanje:** Navedi glavni kriterij za diagonalizabilnost.

**Kratek odgovor:** Matrika $A\in F^{n\times n}$ je diagonalizabilna natanko tedaj, ko ima $n$ linearno neodvisnih lastnih vektorjev.

**Profesor lahko dodatno vpraša:** Kako kriterij zapišemo z lastnimi podprostori?

**Odgovor:**

$$
A\text{ je diagonalizabilna}
\iff
\sum_\lambda\dim E_\lambda=n,
$$

ob predpostavki, da karakteristični polinom razpade na linearne faktorje nad osnovnim poljem.

---

## Ustno vprašanje

**Vprašanje:** Zakaj $n$ različnih lastnih vrednosti zagotavlja diagonalizabilnost?

**Kratek odgovor:** Lastni vektorji, ki pripadajo različnim lastnim vrednostim, so linearno neodvisni. Če imamo $n$ različnih lastnih vrednosti, dobimo $n$ linearno neodvisnih lastnih vektorjev, ki tvorijo bazo.

**Profesor lahko dodatno vpraša:** Ali je obratna trditev resnična?

**Odgovor:** Ne. Diagonalizabilna matrika ima lahko ponovljene lastne vrednosti, če so lastni podprostori dovolj veliki.

---

# 19. Ustni del — dokaz kriterija diagonalizabilnosti

## Ustno vprašanje

**Vprašanje:** Dokaži, da je $A$ diagonalizabilna natanko tedaj, ko obstaja baza iz lastnih vektorjev.

**Kratek odgovor:**

Če obstaja baza

$$
(v_1,\dots,v_n)
$$

iz lastnih vektorjev in

$$
Av_i=\lambda_iv_i,
$$

ima matrika endomorfizma v tej bazi obliko

$$
D=
\operatorname{diag}(\lambda_1,\dots,\lambda_n).
$$

Zato je $A$ podobna diagonalni matriki.

Obratno, če

$$
D=P^{-1}AP
$$

in je $D$ diagonalna, stolpci $P$ predstavljajo novo bazo, v kateri je matrika $A$ diagonalna. Zato vsak bazni vektor preide v svoj skalarni večkratnik in je lastni vektor.

**Profesor lahko dodatno vpraša:** Zakaj je $P$ obrnljiva?

**Odgovor:** Ker so njeni stolpci bazni vektorji in so zato linearno neodvisni.

---

# 20. Ustni del — povezave z drugimi temami predmeta

## Lastni podprostor in jedro

Najpomembnejša povezava:

$$
E_\lambda(A)
=
\ker(A-\lambda I).
$$

Profesor lahko od te točke nadaljuje z vprašanji o:

- jedru;
- rangu;
- injektivnosti;
- dimenziji.

Po izreku o rangu in ničelnosti:

$$
\dim E_\lambda
=
n-\operatorname{rang}(A-\lambda I).
$$

---

## Lastni vektor in invarianten podprostor

Če je $v$ lastni vektor, je

$$
L\{v\}
$$

invarianten.

Profesor lahko vpraša obrat:

> Ali je vsak enorazsežni invarianten podprostor lastni podprostor za neko lastno vrednost?

Da. Če je $U=L\{v\}$ enorazsežen in invarianten, potem je

$$
Av\in U,
$$

zato obstaja $\lambda$, da velja

$$
Av=\lambda v.
$$

Torej je $v$ lastni vektor.

---

## Diagonalizacija in sprememba baze

Diagonalizacija ni »spreminjanje matrike v drugo preslikavo«.

Endomorfizem ostane isti. Spremeni se baza.

Če je $\Sigma$ začetna baza in $\Delta$ baza iz lastnih vektorjev, potem:

$$
M_\Delta^\Delta(A)=D
$$

je diagonalna.

Matrika $P$ je povezana s prehodom med bazama.

---

## Lastna vrednost $0$ in obrnljivost

Za kvadratno matriko so ekvivalentne trditve:

$$
0\text{ ni lastna vrednost}
$$

$$
\iff
\ker A=\{0\}
$$

$$
\iff
A\text{ je injektivna}
$$

$$
\iff
A\text{ je surjektivna}
$$

$$
\iff
A\text{ je obrnljiva}
$$

$$
\iff
\det A\neq0.
$$

To je pomembna povezava med fazo o linearnih preslikavah in spektralno teorijo.

---

# 21. Pogoste izpitne napake

## 1. »Ponovljena lastna vrednost pomeni, da matrika ni diagonalizabilna.«

Napačno.

Pravilno je preveriti:

$$
m_g(\lambda)
\stackrel{?}{=}
m_a(\lambda).
$$

---

## 2. »Različne lastne vrednosti pomenijo ortogonalne lastne vektorje.«

Napačno za splošno matriko.

Pravilna splošna trditev je samo:

> Lastni vektorji za različne lastne vrednosti so linearno neodvisni.

Ortogonalnost zahteva dodatne predpostavke, npr. pri realnih simetričnih matrikah.

---

## 3. Ničelni vektor kot lastni vektor

Ničelni vektor ni lastni vektor.

---

## 4. Napačno sestavljena matrika $P$

Lastni vektorji morajo biti **stolpci**.

---

## 5. Neusklajen vrstni red v $P$ in $D$

Če je tretji stolpec $P$ lastni vektor za $\lambda=-1$, mora biti tretji diagonalni element $D$ enak $-1$.

---

## 6. Pozabljen osnovni prostor

Matrika je lahko diagonalizabilna nad $\mathbb C$, ne pa nad $\mathbb R$.

---

## 7. Prehitro računanje lastnih vektorjev

Najprej poišči lastne vrednosti iz determinante. Šele nato rešuj sisteme.

---

## 8. Premalo lastnih vektorjev za večkratno lastno vrednost

Če je

$$
m_a(\lambda)=3,
$$

moraš za diagonalizabilnost iz tega lastnega podprostora dobiti tri linearno neodvisne lastne vektorje.

---

# 22. Kaj je najbolj pomembno memorirati

## Definicije

Natančno moraš znati:

- lastna vrednost;
- lastni vektor;
- lastni podprostor;
- karakteristični polinom;
- algebraična večkratnost;
- geometrijska večkratnost;
- diagonalizabilna matrika;
- podobni matriki.

---

## Formule

$$
Av=\lambda v
$$

$$
(A-\lambda I)v=0
$$

$$
p_A(\lambda)=\det(\lambda I-A)
$$

$$
\lambda\text{ lastna}
\iff
p_A(\lambda)=0
$$

$$
E_\lambda(A)=\ker(A-\lambda I)
$$

$$
m_g(\lambda)=\dim E_\lambda(A)
$$

$$
1\leq m_g(\lambda)\leq m_a(\lambda)
$$

$$
A=PDP^{-1}
$$

$$
D=P^{-1}AP
$$

$$
AP=PD
$$

---

## Izreki

Znati moraš povedati:

1. Lastni vektorji za različne lastne vrednosti so linearno neodvisni.
2. $A$ je diagonalizabilna natanko tedaj, ko obstaja baza iz lastnih vektorjev.
3. Če ima $n\times n$ matrika $n$ različnih lastnih vrednosti, je diagonalizabilna.
4. Za vsako lastno vrednost velja
   $$
   1\leq m_g(\lambda)\leq m_a(\lambda).
   $$
5. Podobni matriki imata isti karakteristični polinom.
6. $\lambda$ je lastna vrednost natanko tedaj, ko
   $$
   \det(A-\lambda I)=0.
   $$

---

# 23. Naloge za samostojno reševanje

## Srednje težke naloge

**Naloga 1.**

Za matriko

$$
A=
\begin{pmatrix}
3&1\\
0&1
\end{pmatrix}
$$

poišči:

- karakteristični polinom;
- lastne vrednosti;
- lastne podprostore;
- matriki $P$ in $D$, če je matrika diagonalizabilna.

---

**Naloga 2.**

Na prostoru $\mathbb R_2[x]$ definiramo

$$
T(p)(x)=p(-x)+p(0).
$$

Glede na bazo

$$
\Sigma=(1,x,x^2)
$$

poišči:

- matriko $M_\Sigma^\Sigma(T)$;
- karakteristični polinom;
- lastne vrednosti;
- lastne podprostore;
- odloči o diagonalizabilnosti.

---

**Naloga 3.**

Za matriko

$$
A=
\begin{pmatrix}
2&0&0\\
1&2&0\\
0&0&-1
\end{pmatrix}
$$

določi vse lastne vrednosti in lastne podprostore ter odloči, ali je diagonalizabilna.

---

**Naloga 4.**

Za parameter $t\in\mathbb R$ naj bo

$$
A_t=
\begin{pmatrix}
1&t\\
0&1
\end{pmatrix}.
$$

Za katere vrednosti $t$ je $A_t$ diagonalizabilna?

---

**Naloga 5.**

Naj bo $A:V\to V$ endomorfizem realnega končnorazsežnega vektorskega prostora in naj velja

$$
A^2=I.
$$

Dokaži, da so edine možne lastne vrednosti $\pm1$ in da je $A$ diagonalizabilen.

Namig: za poljuben $v\in V$ uporabi vektorja

$$
\frac{v+Av}{2}
\qquad\text{in}\qquad
\frac{v-Av}{2}.
$$

---

**Naloga 6.**

Naj bo

$$
R=
\begin{pmatrix}
0&-1\\
1&0
\end{pmatrix}.
$$

Določi:

- karakteristični polinom;
- lastne vrednosti nad $\mathbb R$;
- lastne vrednosti nad $\mathbb C$;
- diagonalizabilnost nad $\mathbb R$ in nad $\mathbb C$.

---

## Težke / izpitne naloge

**Naloga 7.**

Za matriko

$$
B=
\begin{pmatrix}
4&0&-2\\
1&2&-1\\
1&0&1
\end{pmatrix}
$$

poišči:

- karakteristični polinom;
- vse lastne vrednosti;
- vse lastne podprostore;
- algebraične in geometrijske večkratnosti;
- diagonalizacijo $B=PDP^{-1}$.

---

**Naloga 8.**

Naj bo

$$
A=
\begin{pmatrix}
3&-2&6&-4\\
-5&-6&-12&2\\
3&6&8&0\\
7&10&18&-2
\end{pmatrix}.
$$

Poišči:

- karakteristični polinom;
- vse lastne vrednosti;
- baze vseh lastnih podprostorov;
- odloči o diagonalizabilnosti;
- če je diagonalizabilna, poišči eno možno matriko $P$ in pripadajočo $D$.

---

**Naloga 9.**

Na prostoru $\mathbb R_2[x]$ definiramo endomorfizem

$$
S(p)=p+p'.
$$

Glede na standardno bazo

$$
(1,x,x^2)
$$

poišči:

- matriko endomorfizma;
- karakteristični polinom;
- lastne vrednosti;
- lastni podprostor oziroma lastne podprostore;
- odloči o diagonalizabilnosti.

---

**Naloga 10.**

Naj bo $A\in\mathbb R^{n\times n}$ diagonalizabilna in

$$
A=PDP^{-1}.
$$

Dokaži, da za vsak $k\in\mathbb N$ velja

$$
A^k=PD^kP^{-1}.
$$

Nato pojasni, zakaj je diagonalizacija uporabna pri računanju visokih potenc matrik.

---

**Naloga 11.**

Dokaži, da so lastni vektorji, ki pripadajo paroma različnim lastnim vrednostim, linearno neodvisni.

---

**Naloga 12.**

Naj bo $A\in\mathbb R^{4\times4}$ in

$$
p_A(\lambda)
=
(\lambda-1)^2(\lambda+2)^2.
$$

Znano je:

$$
\dim E_1=2.
$$

Odgovori:

1. Kakšne so možne vrednosti $\dim E_{-2}$?
2. Kdaj je $A$ diagonalizabilna?
3. Če je $\dim E_{-2}=1$, koliko linearno neodvisnih lastnih vektorjev ima lahko največ?

---

# 24. Odgovori

## Odgovori za srednje težke naloge

**1.**

$$
p_A(\lambda)=(\lambda-3)(\lambda-1).
$$

$$
E_3=L\{(1,0)\},
\qquad
E_1=L\{(1,-2)\}.
$$

Ena možnost:

$$
P=
\begin{pmatrix}
1&1\\
0&-2
\end{pmatrix},
\qquad
D=
\begin{pmatrix}
3&0\\
0&1
\end{pmatrix}.
$$

---

**2.**

$$
M_\Sigma^\Sigma(T)
=
\begin{pmatrix}
2&0&0\\
0&-1&0\\
0&0&1
\end{pmatrix}.
$$

$$
p_T(\lambda)
=
(\lambda-2)(\lambda+1)(\lambda-1).
$$

$$
E_2=L\{1\},
\qquad
E_{-1}=L\{x\},
\qquad
E_1=L\{x^2\}.
$$

$T$ je diagonalizabilen.

---

**3.**

$$
p_A(\lambda)
=
(\lambda-2)^2(\lambda+1).
$$

$$
E_2=L\{(0,1,0)\},
\qquad
E_{-1}=L\{(0,0,1)\}.
$$

Ker je

$$
m_a(2)=2,
\qquad
m_g(2)=1,
$$

matrika ni diagonalizabilna.

---

**4.**

$$
\boxed{t=0}.
$$

Za $t=0$ je $A_t=I$.

Za $t\neq0$ je edina lastna vrednost $1$, njen lastni podprostor pa je enorazsežen.

---

**5.**

Možni lastni vrednosti sta:

$$
\boxed{\lambda=\pm1}.
$$

Za vsak $v$:

$$
v=
\frac{v+Av}{2}
+
\frac{v-Av}{2},
$$

pri čemer prvi člen pripada $E_1$, drugi pa $E_{-1}$.

Zato:

$$
V=E_1\oplus E_{-1},
$$

torej je $A$ diagonalizabilen.

---

**6.**

$$
p_R(\lambda)=\lambda^2+1.
$$

Nad $\mathbb R$ ni lastnih vrednosti in matrika ni diagonalizabilna.

Nad $\mathbb C$:

$$
\lambda_1=i,
\qquad
\lambda_2=-i.
$$

Ker sta različni, je matrika diagonalizabilna nad $\mathbb C$.

---

## Odgovori za težke / izpitne naloge

**7.**

$$
p_B(\lambda)
=
(\lambda-3)(\lambda-2)^2.
$$

$$
E_3=L\{(2,1,1)\}.
$$

$$
E_2=L\{(0,1,0),(1,0,1)\}.
$$

$$
m_a(3)=m_g(3)=1,
$$

$$
m_a(2)=m_g(2)=2.
$$

Matrika je diagonalizabilna.

Ena možnost:

$$
P=
\begin{pmatrix}
2&0&1\\
1&1&0\\
1&0&1
\end{pmatrix},
\qquad
D=
\begin{pmatrix}
3&0&0\\
0&2&0\\
0&0&2
\end{pmatrix}.
$$

---

**8.**

$$
p_A(\lambda)
=
(\lambda+1)\lambda(\lambda-2)^2.
$$

$$
E_{-1}=L\{(-1,-1,1,1)\}.
$$

$$
E_0=L\{(-2,1,0,-2)\}.
$$

$$
E_2
=
L\{
(0,-1,1,2),
(2,0,-1,-1)
\}.
$$

Matrika je diagonalizabilna.

Ena možnost:

$$
P=
\begin{pmatrix}
-1&-2&0&2\\
-1&1&-1&0\\
1&0&1&-1\\
1&-2&2&-1
\end{pmatrix},
$$

$$
D=
\operatorname{diag}(-1,0,2,2).
$$

---

**9.**

$$
M=
\begin{pmatrix}
1&1&0\\
0&1&2\\
0&0&1
\end{pmatrix}.
$$

$$
p_S(\lambda)=(\lambda-1)^3.
$$

Edina lastna vrednost je:

$$
\lambda=1.
$$

$$
E_1=L\{1\}.
$$

Ker je

$$
m_g(1)=1<3=m_a(1),
$$

endomorfizem ni diagonalizabilen.

---

**10.**

$$
A^k
=
(PDP^{-1})^k
=
PD^kP^{-1}.
$$

Ključni vmesni rezultat je:

$$
P^{-1}P=I.
$$

Ker je $D$ diagonalna:

$$
D^k=
\operatorname{diag}
(\lambda_1^k,\dots,\lambda_n^k).
$$

---

**11.**

Ključna ideja: iz linearne zveze

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0
$$

uporabi $A$ in nato odštej primerno večkratnik prvotne zveze. Dokaz se zaključi z indukcijo.

---

**12.**

Možne vrednosti:

$$
\dim E_{-2}\in\{1,2\}.
$$

$A$ je diagonalizabilna natanko tedaj, ko:

$$
\dim E_{-2}=2.
$$

Če je:

$$
\dim E_{-2}=1,
$$

lahko dobimo največ:

$$
2+1=3
$$

linearno neodvisne lastne vektorje.

---

# 25. Zadnja ponovitev pred izpitom

Če imaš samo 30 minut za ponovitev te faze, ponovi v tem vrstnem redu:

1. definicija lastne vrednosti;
2. formula
   $$
   (A-\lambda I)v=0;
   $$
3. karakteristični polinom;
4. formula
   $$
   E_\lambda=\ker(A-\lambda I);
   $$
5. algebraična in geometrijska večkratnost;
6. kriterij diagonalizabilnosti;
7. konstrukcija $P$ in $D$;
8. dokaz, da so lastni vektorji za različne lastne vrednosti linearno neodvisni;
9. dokaz
   $$
   \lambda\text{ lastna}
   \iff
   \det(A-\lambda I)=0;
   $$
10. popolna rešitev ene naloge tipa 68.

---

# 26. Faza je zaključena, ko znam ...

- [ ] natančno definirati **lastno vrednost** in **lastni vektor**;
- [ ] razložiti, zakaj ničelni vektor ni lastni vektor;
- [ ] natančno definirati **lastni podprostor**;
- [ ] uporabiti zvezo
  $$
  E_\lambda(A)=\ker(A-\lambda I);
  $$
- [ ] definirati **karakteristični polinom**;
- [ ] izračunati karakteristični polinom matrik velikosti $2\times2$, $3\times3$ in tipičnih $4\times4$ primerov;
- [ ] prepoznati bližnjice pri diagonalnih, trikotnih in blokovnih matrikah;
- [ ] poiskati vse lastne vrednosti kot ničle karakterističnega polinoma;
- [ ] za vsako lastno vrednost pravilno rešiti sistem
  $$
  (A-\lambda I)x=0;
  $$
- [ ] zapisati lastni podprostor kot linearno ogrinjačo baze;
- [ ] razlikovati med **lastnim vektorjem** in **lastnim podprostorom**;
- [ ] določiti **algebraično večkratnost**;
- [ ] določiti **geometrijsko večkratnost**;
- [ ] uporabiti neenakost
  $$
  1\leq m_g(\lambda)\leq m_a(\lambda);
  $$
- [ ] prepoznati, da ponovljena lastna vrednost sama po sebi ne pomeni nedagonalizabilnosti;
- [ ] odločiti, ali je matrika diagonalizabilna;
- [ ] razložiti kriterij »$n$ linearno neodvisnih lastnih vektorjev«;
- [ ] sestaviti matriko $P$ iz lastnih vektorjev;
- [ ] sestaviti diagonalno matriko $D$ v pravilnem vrstnem redu;
- [ ] zapisati in uporabiti
  $$
  A=PDP^{-1};
  $$
- [ ] hitro preveriti diagonalizacijo z zvezo
  $$
  AP=PD;
  $$
- [ ] pojasniti, da diagonalizacija predstavlja spremembo baze;
- [ ] pojasniti povezavo med lastnimi vektorji in invariantnimi enorazsežnimi podprostori;
- [ ] pojasniti povezavo med lastno vrednostjo $0$, jedrom, determinanto in obrnljivostjo;
- [ ] pojasniti, zakaj je osnovno polje pomembno za obstoj lastnih vrednosti in diagonalizacijo;
- [ ] na ustnem brez zapiskov povedati dokaz
  $$
  \lambda\text{ je lastna vrednost}
  \iff
  \det(A-\lambda I)=0;
  $$
- [ ] dokazati, da so lastni vektorji za različne lastne vrednosti linearno neodvisni;
- [ ] dokazati kriterij: endomorfizem je diagonalizabilen natanko tedaj, ko obstaja baza iz lastnih vektorjev;
- [ ] dokazati, da podobni matriki imata isti karakteristični polinom;
- [ ] ustno pojasniti razliko med algebraično in geometrijsko večkratnostjo;
- [ ] brez pomoči rešiti popolno nalogo tipa:
  $$
  A
  \to
  p_A
  \to
  \lambda_i
  \to
  E_{\lambda_i}
  \to
  P,D;
  $$
- [ ] pri popolni diagonalizaciji jasno utemeljiti, zakaj je $P$ obrnljiva;
- [ ] pri pisanju rešitve pokazati dovolj vmesnih korakov, da je razviden postopek, ne le končni rezultat;
- [ ] pravilno odgovoriti na tipična ustna vprašanja iz tega poglavja brez gledanja v zapiske.
