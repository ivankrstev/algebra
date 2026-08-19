# FAZA 1 — Vektorski prostori in podprostori

> **Obseg faze:** vektorski prostori, vektorski podprostori, preverjanje podprostora, parametrični opis podprostora, osnovno določanje baze in dimenzije podprostora ter tipični protiprimeri.
>
> Faza temelji predvsem na **3. in 4. vajah**, kjer se začnejo vektorski prostori in sistematično preverjanje podprostorov. Za zahtevnejši tip naloge s parametrom je vključena tudi naloga 22 iz 5. vaj. Med priloženimi datotekami ni ločenih preteklih izpitov ali kolokvijev, zato je prioriteta določena po priloženih vajah.

---

## Kaj moram znati v tej fazi

Po zaključku faze moram obvladati:

- definicijo **vektorskega prostora** nad poljem $F$;
- osnovne aksiome vektorskega prostora;
- standardne primere vektorskih prostorov:
  - $\mathbb R^n$,
  - $\mathbb C^n$,
  - prostori matrik,
  - prostori polinomov;
- definicijo **vektorskega podprostora**;
- hiter kriterij za preverjanje podprostora;
- prepoznavanje homogenih linearnih pogojev;
- razlikovanje med:
  - linearnim pogojem,
  - afinim pogojem,
  - nelinearnim pogojem,
  - neenačbo;
- dokazovanje, da je množica podprostor;
- dokazovanje, da množica **ni** podprostor s kratkim protiprimerom;
- parametrični zapis podprostora;
- osnovno določanje baze in dimenzije iz parametričnega zapisa;
- podprostore matrik:
  - diagonalne,
  - simetrične,
  - antisimetrične,
  - skalarne matrike,
  - matrike s homogenimi linearnimi pogoji;
- razložiti teorijo na ustnem izpitu in dokazati osnovni kriterij za podprostor.

---

# 1. Vektorski prostor

## 1.1 Osnovna ideja

Vektorski prostor je množica objektov, ki jih imenujemo **vektorji**, na katerih sta definirani:

1. seštevanje vektorjev;
2. množenje vektorjev s skalarji.

Skalarji prihajajo iz nekega polja $F$, na primer:

- $F=\mathbb R$,
- $F=\mathbb C$.

Pomembno je, **nad katerim poljem** obravnavamo prostor.

Na primer:

$$
\mathbb C
$$

je:

- enorazsežen vektorski prostor nad $\mathbb C$;
- dvorazsežen vektorski prostor nad $\mathbb R$.

---

## 1.2 Definicija vektorskega prostora

Naj bo $F$ polje in $V$ neprazna množica.

Množica $V$ je **vektorski prostor nad poljem $F$**, če sta definirani operaciji

$$
+:V\times V\to V
$$

in

$$
\cdot:F\times V\to V,
$$

ki zadoščata aksiomom vektorskega prostora.

Za vse $u,v,w\in V$ in $\alpha,\beta\in F$ velja:

### Seštevanje

1. **Asociativnost**

$$
(u+v)+w=u+(v+w)
$$

2. **Komutativnost**

$$
u+v=v+u
$$

3. **Ničelni vektor**

Obstaja $0\in V$, da za vsak $v\in V$ velja

$$
v+0=v.
$$

4. **Nasprotni vektor**

Za vsak $v\in V$ obstaja $-v\in V$, da

$$
v+(-v)=0.
$$

### Množenje s skalarjem

5. **Distributivnost glede na seštevanje vektorjev**

$$
\alpha(u+v)=\alpha u+\alpha v
$$

6. **Distributivnost glede na seštevanje skalarjev**

$$
(\alpha+\beta)v=\alpha v+\beta v
$$

7. **Asociativnost množenja s skalarji**

$$
\alpha(\beta v)=(\alpha\beta)v
$$

8. **Nevtralni skalar**

$$
1v=v.
$$

---

## 1.3 Posledice aksiomov

Iz aksiomov sledijo pomembne lastnosti:

$$
0_Fv=0_V
$$

$$
\alpha 0_V=0_V
$$

$$
(-1)v=-v
$$

$$
(-\alpha)v=-(\alpha v)
$$

Če velja

$$
\alpha v=0,
$$

potem je

$$
\alpha=0
$$

ali

$$
v=0.
$$

Te lastnosti običajno uporabljamo brez ponovnega dokazovanja.

---

# 2. Standardni vektorski prostori

## 2.1 Prostor $\mathbb R^n$

$$
\mathbb R^n
=
\{(x_1,\ldots,x_n);x_i\in\mathbb R\}
$$

z običajnim seštevanjem in množenjem s skalarji je vektorski prostor nad $\mathbb R$.

Na primer:

$$
\mathbb R^3
=
\{(x,y,z);x,y,z\in\mathbb R\}.
$$

---

## 2.2 Prostor $\mathbb C^n$

$$
\mathbb C^n
$$

je vektorski prostor nad $\mathbb C$.

To je pomembno pri nalogi 15 iz vaj, kjer je

$$
U=\{(2z,w,z);z,w\in\mathbb C\}.
$$

Naloga zahteva dokaz, da je $U$ vektorski prostor nad $\mathbb C$, in določitev njegove dimenzije.

---

## 2.3 Prostor matrik

Množica vseh matrik velikosti $m\times n$ z realnimi elementi

$$
\mathbb R^{m\times n}
$$

je vektorski prostor nad $\mathbb R$.

Operaciji sta običajni:

$$
(A+B)_{ij}=A_{ij}+B_{ij}
$$

in

$$
(\lambda A)_{ij}=\lambda A_{ij}.
$$

---

## 2.4 Prostor polinomov

Prostor

$$
\mathbb R_n[x]
$$

vsebuje vse realne polinome stopnje največ $n$:

$$
p(x)=a_0+a_1x+\cdots+a_nx^n.
$$

Je vektorski prostor nad $\mathbb R$.

---

# 3. Vektorski podprostor

## 3.1 Definicija

Naj bo $V$ vektorski prostor nad poljem $F$.

Podmnožica

$$
U\subseteq V
$$

je **vektorski podprostor prostora $V$**, če je $U$ z istima operacijama seštevanja in množenja s skalarji sama vektorski prostor nad $F$.

Pišemo:

$$
U\leq V.
$$

---

# 4. Najpomembnejši kriterij za podprostor

Če je $V$ že znan vektorski prostor, **ni treba ponovno preverjati vseh osmih aksiomov**.

Uporabimo kriterij za podprostor.

## Izrek — kriterij za podprostor

Naj bo $V$ vektorski prostor nad $F$ in $U\subseteq V$.

Tedaj je $U$ podprostor prostora $V$ natanko tedaj, ko:

1. $U\neq\varnothing$;
2. za vse $u,v\in U$ in vse $\alpha,\beta\in F$ velja

$$
\alpha u+\beta v\in U.
$$

To je najuporabnejša oblika kriterija na izpitu.

---

## Ekvivalentna oblika

Lahko preverjamo tudi:

1. $0\in U$;
2. če $u,v\in U$, potem

$$
u+v\in U;
$$

3. če $u\in U$ in $\lambda\in F$, potem

$$
\lambda u\in U.
$$

---

## Najhitrejši vrstni red preverjanja

Ko dobiš množico $U$, preverjaj v tem vrstnem redu:

### 1. Ali je $0\in U$?

Če ni:

$$
\boxed{U\text{ ni podprostor}}
$$

in lahko takoj končaš.

### 2. Ali je pogoj homogen in linearen?

Na primer:

$$
x-2y+3z=0
$$

je zelo dober znak.

Toda:

$$
x-2y+3z=4
$$

ni homogen.

### 3. Ali je množica zaprta za množenje s skalarji?

Posebej preveri $\lambda=-1$.

To hitro izloči pogoje tipa:

$$
x\geq0.
$$

### 4. Ali je zaprta za seštevanje?

To pogosto izloči nelinearne pogoje, kot so:

$$
xy=0,
$$

$$
|x|=|y|,
$$

$$
\det A=0.
$$

---

# 5. Homogeni linearni pogoji

## 5.1 Najpomembnejši vzorec

Množica rešitev homogenega linearnega sistema je podprostor.

Na primer:

$$
U=
\{(x,y,z)\in\mathbb R^3;x-2y+3z=0\}.
$$

Če $u,v\in U$, potem

$$
u_1-2u_2+3u_3=0
$$

in

$$
v_1-2v_2+3v_3=0.
$$

Za $\alpha,\beta\in\mathbb R$ velja

$$
(\alpha u_1+\beta v_1)
-2(\alpha u_2+\beta v_2)
+3(\alpha u_3+\beta v_3)
$$

$$
=
\alpha(u_1-2u_2+3u_3)
+
\beta(v_1-2v_2+3v_3)
=0.
$$

Zato

$$
\alpha u+\beta v\in U.
$$

Torej

$$
U\leq\mathbb R^3.
$$

---

## 5.2 Matrična oblika

Homogeni sistem

$$
Ax=0
$$

ima množico rešitev, ki je vedno vektorski podprostor.

Nasprotno množica rešitev

$$
Ax=b
$$

za $b\neq0$ praviloma ni podprostor, ker ničelni vektor običajno ni rešitev.

---

# 6. Kako prepoznati tip pogoja

| Pogoj | Tipično podprostor? | Kaj preveriti |
|---|---:|---|
| $x+y-z=0$ | da | homogen linearen pogoj |
| $x+y-z=5$ | ne | $0$ ne pripada množici |
| $x=2y$ | da | enako kot $x-2y=0$ |
| $xy=0$ | ne | ni zaprtost za seštevanje |
| $x^2+y^2=1$ | ne | $0$ ni v množici |
| $x\geq0$ | ne | ni zaprto za negativne skalarje |
| $|x|=|y|$ | običajno ne | unija več linearnih množic |
| $A^T=A$ | da | linearen pogoj |
| $A^T=-A$ | da | linearen pogoj |
| $\det A=0$ | ne | singularne matrike niso zaprte za seštevanje |
| $A=\lambda I$ | da | skalarne matrike |
| $A^2=A$ | praviloma ne | nelinearen pogoj |

---

# 7. Minimalno o bazi in dimenziji za to fazo

Baze in dimenzijo bomo sistematično obravnavali v naslednji fazi, vendar ju potrebujemo že pri nekaterih nalogah iz 4. vaj.

## Parametrični zapis

Če lahko vsak element $u\in U$ zapišemo kot

$$
u
=
s_1v_1+\cdots+s_kv_k,
$$

potem množica

$$
\{v_1,\ldots,v_k\}
$$

generira $U$.

Če so ti vektorji tudi linearno neodvisni, tvorijo **bazo**.

Takrat:

$$
\dim U=k.
$$

### Hitra ideja

Če ima parametrični opis $k$ resnično neodvisnih prostih parametrov, je pogosto

$$
\dim U=k.
$$

Toda vedno preveri, da pripadajoči generatorski vektorji niso med seboj linearno odvisni.

---

# 8. Tip naloge: Parametrično podan podprostor

Ta tip se neposredno pojavi v nalogi 15 iz 4. vaj.

## Kako jo prepoznam

Množica ima obliko

$$
U=
\{v(s,t,\ldots);s,t,\ldots\in F\}.
$$

Komponente vektorja so linearno odvisne od parametrov.

---

## Postopek

1. Ugotovi, v katerem znanem vektorskem prostoru leži $U$.
2. Vzemi poljubna elementa $u,v\in U$.
3. Izračunaj

$$
\alpha u+\beta v.
$$

4. Pokaži, da rezultat ponovno dobi enako parametrično obliko.
5. Za bazo izpostavi parametre.
6. Preveri linearno neodvisnost generatorskih vektorjev.
7. Določi dimenzijo.

---

## Primer

Naj bo

$$
U=
\{(2z,w,z);z,w\in\mathbb C\}.
$$

Dokaži, da je $U$ vektorski podprostor prostora $\mathbb C^3$, in določi $\dim U$.

---

## Rešitev

Naj bosta

$$
u=(2z_1,w_1,z_1)\in U
$$

in

$$
v=(2z_2,w_2,z_2)\in U.
$$

Za poljubna $\alpha,\beta\in\mathbb C$ dobimo

$$
\alpha u+\beta v
=
(2\alpha z_1+2\beta z_2,\,
\alpha w_1+\beta w_2,\,
\alpha z_1+\beta z_2).
$$

Zapišemo:

$$
\alpha u+\beta v
=
\left(
2(\alpha z_1+\beta z_2),
\alpha w_1+\beta w_2,
\alpha z_1+\beta z_2
\right).
$$

Ker sta

$$
\alpha z_1+\beta z_2\in\mathbb C
$$

in

$$
\alpha w_1+\beta w_2\in\mathbb C,
$$

je

$$
\alpha u+\beta v\in U.
$$

Torej

$$
U\leq\mathbb C^3.
$$

Nato:

$$
(2z,w,z)
=
z(2,0,1)+w(0,1,0).
$$

Zato

$$
U=
L\{(2,0,1),(0,1,0)\}.
$$

Vektorja sta linearno neodvisna, zato tvorita bazo.

Torej:

$$
\boxed{
\dim_{\mathbb C}U=2
}
$$

in ena od baz je

$$
\boxed{
\{(2,0,1),(0,1,0)\}.
}
$$

---

## Pogoste napake

- Pozabiš napisati, da so skalarji $\alpha,\beta\in\mathbb C$.
- Preverjaš vseh osem aksiomov namesto kriterija za podprostor.
- Rečeš samo, da ima množica dva parametra, zato je dimenzija $2$, ne da bi preveril neodvisnost pripadajočih vektorjev.
- Zamenjaš dimenzijo nad $\mathbb C$ z dimenzijo nad $\mathbb R$.

---

# 9. Tip naloge: Množice v $\mathbb R^n$ z različnimi pogoji

To je osrednji tip naloge 16 iz 4. vaj.

## Kako jo prepoznam

Dobiš več množic, kot so:

$$
x_1-x_n=0,
$$

$$
x_1-x_n=1,
$$

$$
x_1x_n=0,
$$

$$
x_1\geq0.
$$

Naloga preverja, ali znaš razlikovati med **linearnimi homogenimi** in drugimi pogoji.

---

## Postopek

Za vsako množico:

1. preveri $0$;
2. poišči najkrajši možni razlog za odgovor;
3. če je pogoj homogen linearen, dokaži zaprtost;
4. če ni, najdi kratek protiprimer.

---

## Primer iz vaj

Za $n\geq2$ obravnavamo:

$$
U_1=
\{x\in\mathbb R^n;x_1-x_n=0\},
$$

$$
U_2=
\{x\in\mathbb R^n;x_1-x_n=1\},
$$

$$
U_3=
\{x\in\mathbb R^n;x_1x_n=0\},
$$

$$
U_4=
\left\{
x\in\mathbb R^n;
\frac{x_1}{x_n}=0
\right\},
$$

$$
U_5=
\{x\in\mathbb R^n;x_1\geq0\}.
$$

---

## Rešitev za $U_1$

Pogoj

$$
x_1-x_n=0
$$

je homogen in linearen.

Naj bosta $u,v\in U_1$. Tedaj

$$
u_1-u_n=0,
$$

$$
v_1-v_n=0.
$$

Za $\alpha,\beta\in\mathbb R$:

$$
(\alpha u_1+\beta v_1)
-
(\alpha u_n+\beta v_n)
$$

$$
=
\alpha(u_1-u_n)
+
\beta(v_1-v_n)
=0.
$$

Torej

$$
\boxed{U_1\leq\mathbb R^n}.
$$

---

## Rešitev za $U_2$

Za ničelni vektor velja

$$
0-0=0\neq1.
$$

Zato

$$
0\notin U_2.
$$

Torej

$$
\boxed{U_2\text{ ni podprostor}.}
$$

---

## Rešitev za $U_3$

Pogoj

$$
x_1x_n=0
$$

je nelinearen.

Vzemimo

$$
u=(1,0,\ldots,0)
$$

in

$$
v=(0,\ldots,0,1).
$$

Tedaj

$$
u_1u_n=0
$$

in

$$
v_1v_n=0,
$$

zato $u,v\in U_3$.

Toda:

$$
u+v=(1,0,\ldots,0,1)
$$

in

$$
(u+v)_1(u+v)_n=1.
$$

Zato

$$
u+v\notin U_3.
$$

Torej

$$
\boxed{U_3\text{ ni podprostor}.}
$$

---

## Rešitev za $U_4$

Da je izraz

$$
\frac{x_1}{x_n}
$$

definiran, mora veljati

$$
x_n\neq0.
$$

Ničelni vektor zato ne pripada $U_4$.

Torej

$$
\boxed{U_4\text{ ni podprostor}.}
$$

---

## Rešitev za $U_5$

Vektor

$$
u=(1,0,\ldots,0)
$$

pripada $U_5$, saj

$$
u_1=1\geq0.
$$

Toda za skalar $-1$ dobimo

$$
-u=(-1,0,\ldots,0),
$$

ki ne pripada $U_5$.

Torej množica ni zaprta za množenje s skalarji:

$$
\boxed{U_5\text{ ni podprostor}.}
$$

---

## Končni odgovor

$$
\boxed{
U_1\text{ je podprostor, }
U_2,U_3,U_4,U_5\text{ pa niso.}
}
$$

---

## Pogoste napake

- Pri $U_3$ sklepaš, da je podprostor samo zato, ker desna stran vsebuje $0$.
- Pri $U_5$ preverjaš samo seštevanje in pozabiš na negativne skalarje.
- Pri $U_2$ pišeš dolg dokaz, čeprav že $0\notin U_2$ zaključi nalogo.
- Pri $U_4$ pozabiš, da mora biti imenovalec neničeln.

---

# 10. Tip naloge: Geometrijske in nelinearne množice v $\mathbb R^2$

Naloga 17 iz vaj primerja prazno množico, krožnico, poltrak, množico $|a|=|b|$ in premico $b=-a$.

## Kako jo prepoznam

Pogoji pogosto opisujejo:

- premico;
- krožnico;
- poltrak;
- unijo premic;
- krivuljo.

Za podprostor $\mathbb R^2$ mora geometrijsko množica vsebovati izhodišče ter biti zaprta za vse realne skalarje.

---

## Primer

Katera izmed naslednjih množic je podprostor $\mathbb R^2$?

### (a) $\varnothing$

Ni podprostor, ker

$$
0\notin\varnothing.
$$

### (b)

$$
U=
\{(a,b);a^2+b^2=1\}.
$$

Ničelni vektor ne pripada množici:

$$
0^2+0^2\neq1.
$$

Ni podprostor.

### (c)

$$
U=
\{(a,a);a\geq0\}.
$$

Vektor

$$
(1,1)\in U,
$$

vendar

$$
-(1,1)=(-1,-1)\notin U.
$$

Ni podprostor.

### (d)

$$
U=
\{(a,b);|a|=|b|\}.
$$

Vektorja

$$
(1,1)\in U
$$

in

$$
(1,-1)\in U.
$$

Toda

$$
(1,1)+(1,-1)=(2,0)
$$

in

$$
|2|\neq|0|.
$$

Zato ni podprostor.

### (e)

$$
U=
\{(a,-a);a\in\mathbb R\}.
$$

Zapišemo:

$$
(a,-a)=a(1,-1).
$$

Torej

$$
U=L\{(1,-1)\}
$$

in zato

$$
\boxed{U\leq\mathbb R^2}.
$$

---

## Končni odgovor

$$
\boxed{\text{Podprostor je samo množica (e).}}
$$

---

## Pogoste napake

- Množico $|a|=|b|$ zamenjaš z eno samo premico. Dejansko vsebuje:

$$
b=a
$$

ali

$$
b=-a.
$$

Gre za unijo dveh premic, ki ni podprostor.

- Misliš, da je vsak geometrijski objekt skozi izhodišče podprostor.
- Ne preveriš zaprtosti za seštevanje.

---

# 11. Tip naloge: Podprostori matrik

V domači nalogi 4. vaj je podanih deset različnih množic matrik, med drugim obrnljive matrike, simetrične, antisimetrične, skalarne matrike in matrike z linearnimi ter nelinearnimi pogoji.

Naj bo

$$
V=\mathbb R^{2\times2}.
$$

Splošno matriko zapišemo kot

$$
A=
\begin{pmatrix}
a&b\\
c&d
\end{pmatrix}.
$$

---

## 11.1 Obrnljive matrike

$$
U_1=
\{A\in V;A\text{ je obrnljiva}\}.
$$

Ničelna matrika ni obrnljiva:

$$
0\notin U_1.
$$

Zato:

$$
\boxed{U_1\text{ ni podprostor}.}
$$

---

## 11.2 Neobrnljive matrike

$$
U_2=
\{A\in V;A\text{ ni obrnljiva}\}.
$$

Ničelna matrika sicer pripada $U_2$, vendar množica ni zaprta za seštevanje.

Vzemimo

$$
A=
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix},
\qquad
B=
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix}.
$$

Obe sta neobrnljivi, toda

$$
A+B=
\begin{pmatrix}
1&0\\
0&1
\end{pmatrix}
=I
$$

je obrnljiva.

Torej:

$$
\boxed{U_2\text{ ni podprostor}.}
$$

---

## 11.3 Pogoj $c=0$

$$
U_3=
\left\{
\begin{pmatrix}
a&b\\
c&d
\end{pmatrix};
c=0
\right\}.
$$

To je homogen linearen pogoj.

Če imata matriki $A,B$ spodnji levi element enak $0$, ga ima tudi

$$
\alpha A+\beta B.
$$

Zato:

$$
\boxed{U_3\leq V}.
$$

---

## 11.4 Pogoj $c-d=0$

$$
U_4=
\{A\in V;c-d=0\}.
$$

Pogoj je homogen linearen.

Zato:

$$
\boxed{U_4\leq V}.
$$

---

## 11.5 Simetrične matrike

$$
U_5=
\{A\in V;A^T=A\}.
$$

Naj bosta $A,B\in U_5$.

Tedaj:

$$
A^T=A,
\qquad
B^T=B.
$$

Za $\alpha,\beta\in\mathbb R$:

$$
(\alpha A+\beta B)^T
=
\alpha A^T+\beta B^T
$$

$$
=
\alpha A+\beta B.
$$

Zato:

$$
\boxed{U_5\leq V}.
$$

---

## 11.6 Antisimetrične matrike

$$
U_6=
\{A\in V;A^T=-A\}.
$$

Za $A,B\in U_6$:

$$
A^T=-A,
\qquad
B^T=-B.
$$

Tedaj:

$$
(\alpha A+\beta B)^T
=
\alpha A^T+\beta B^T
$$

$$
=
-\alpha A-\beta B
$$

$$
=
-(\alpha A+\beta B).
$$

Zato:

$$
\boxed{U_6\leq V}.
$$

Za realno antisimetrično matriko $2\times2$ velja:

$$
A=
\begin{pmatrix}
0&a\\
-a&0
\end{pmatrix}.
$$

---

## 11.7 Pogoj $abcd=0$

$$
U_7=
\{A\in V;abcd=0\}.
$$

Gre za nelinearen pogoj.

Vzemimo:

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
1&1
\end{pmatrix}.
$$

Za obe velja produkt vseh štirih elementov $0$.

Toda:

$$
A+B=
\begin{pmatrix}
1&1\\
2&2
\end{pmatrix}
$$

in produkt elementov je

$$
1\cdot1\cdot2\cdot2=4\neq0.
$$

Zato:

$$
\boxed{U_7\text{ ni podprostor}.}
$$

---

## 11.8 Skalarne matrike

$$
U_8=
\{A\in V;A=\lambda I,\lambda\in\mathbb R\}.
$$

Če

$$
A=\lambda I
$$

in

$$
B=\mu I,
$$

potem

$$
\alpha A+\beta B
=
(\alpha\lambda+\beta\mu)I.
$$

Zato:

$$
\boxed{U_8\leq V}.
$$

---

## 11.9 Vsota vseh elementov je $0$

$$
U_9=
\{A\in V;a+b+c+d=0\}.
$$

Gre za homogen linearen pogoj, zato:

$$
\boxed{U_9\leq V}.
$$

---

## 11.10 Diagonalne idempotentne matrike

$$
U_{10}
=
\{A\in V;b=c=0,\ A^2=A\}.
$$

Pogoj

$$
A^2=A
$$

je nelinearen.

Na primer:

$$
I\in U_{10}.
$$

Toda:

$$
2I\notin U_{10},
$$

ker

$$
(2I)^2=4I\neq2I.
$$

Množica ni zaprta za množenje s skalarji.

Torej:

$$
\boxed{U_{10}\text{ ni podprostor}.}
$$

---

## Povzetek matričnih podprostorov

$$
\boxed{
U_3,U_4,U_5,U_6,U_8,U_9
\text{ so podprostori.}
}
$$

$$
\boxed{
U_1,U_2,U_7,U_{10}
\text{ niso podprostori.}
}
$$

---

# 12. Tip naloge: Dokaži, da je množica matrik vektorski prostor

V 3. vajah je podan prostor diagonalnih matrik

$$
V=
\left\{
\begin{pmatrix}
a&0\\
0&b
\end{pmatrix};
a,b\in\mathbb R
\right\},
$$

za katerega je treba pokazati, da je vektorski prostor nad $\mathbb R$.

## Kako jo prepoznam

Množica je podmnožica že znanega prostora matrik.

Najboljši pristop je:

$$
V\subseteq\mathbb R^{2\times2}
$$

in nato uporaba kriterija za podprostor.

---

## Postopek

1. Opazimo, da je $\mathbb R^{2\times2}$ že vektorski prostor.
2. Pokažemo, da je dana množica njegov podprostor.
3. Preverimo linearno kombinacijo.

---

## Rešitev

Naj bosta

$$
A=
\begin{pmatrix}
a&0\\
0&b
\end{pmatrix}
$$

in

$$
B=
\begin{pmatrix}
c&0\\
0&d
\end{pmatrix}
$$

elementa $V$.

Za $\alpha,\beta\in\mathbb R$:

$$
\alpha A+\beta B
=
\begin{pmatrix}
\alpha a+\beta c&0\\
0&\alpha b+\beta d
\end{pmatrix}.
$$

Ker sta

$$
\alpha a+\beta c\in\mathbb R
$$

in

$$
\alpha b+\beta d\in\mathbb R,
$$

velja

$$
\alpha A+\beta B\in V.
$$

Množica je neprazna, saj vsebuje ničelno matriko.

Zato:

$$
\boxed{
V\leq\mathbb R^{2\times2}
}
$$

in je $V$ vektorski prostor nad $\mathbb R$.

Poleg tega:

$$
\begin{pmatrix}
a&0\\
0&b
\end{pmatrix}
=
a
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix}
+
b
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix},
$$

zato je ena od baz:

$$
\left\{
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix},
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix}
\right\},
$$

in

$$
\boxed{\dim V=2.}
$$

---

# 13. Tip naloge: Poišči parameter, da množica postane podprostor

Ta tip se pojavi v nalogi 22 iz 5. vaj:

$$
U=
\{(x,y,z)\in\mathbb R^3;
x-t(y+2z-2)=4\}.
$$

Treba je določiti $t$, da bo $U$ podprostor.

## Kako jo prepoznam

V definiciji množice se pojavi parameter $t$ in naloga sprašuje:

- za kateri $t$ je množica podprostor;
- za kateri $t$ vsebuje izhodišče;
- za kateri $t$ postane pogoj homogen.

---

## Najhitrejša metoda

Podprostor mora vsebovati ničelni vektor.

Zato najprej vstavimo:

$$
(x,y,z)=(0,0,0).
$$

---

## Rešitev

Imamo:

$$
x-t(y+2z-2)=4.
$$

Vstavimo ničelni vektor:

$$
0-t(0+0-2)=4.
$$

Torej:

$$
2t=4
$$

in zato:

$$
\boxed{t=2}.
$$

Preverimo.

Za $t=2$:

$$
x-2(y+2z-2)=4.
$$

Razširimo:

$$
x-2y-4z+4=4.
$$

Dobimo:

$$
x-2y-4z=0.
$$

To je homogen linearen pogoj, zato množica res predstavlja podprostor.

Torej:

$$
\boxed{t=2}.
$$

Če želimo tudi bazo:

$$
x=2y+4z.
$$

Naj bo

$$
y=s,\qquad z=r.
$$

Tedaj:

$$
(x,y,z)
=
(2s+4r,s,r)
$$

$$
=
s(2,1,0)+r(4,0,1).
$$

Zato:

$$
\boxed{
U=L\{(2,1,0),(4,0,1)\}
}
$$

in

$$
\boxed{\dim U=2}.
$$

---

## Pomemben trik

Pri nalogi

$$
a_1x_1+\cdots+a_nx_n=c
$$

je za podprostor nujno:

$$
c=0.
$$

Če je $c$ odvisen od parametra, najprej poišči parameter, pri katerem desna stran postane $0$.

---

## Pogoste napake

- Takoj začneš preverjati zaprtost, namesto da vstaviš $0$.
- Pozabiš razširiti oklepaje.
- Določiš parameter iz napačnega pogoja.
- Po ugotovitvi, da $0\in U$, avtomatično sklepaš, da je $U$ podprostor. Še vedno mora biti pogoj linearen oziroma moraš preveriti zaprtost.

---

# 14. Kaj praviloma NI podprostor

## 14.1 Množica brez ničelnega vektorja

Če

$$
0\notin U,
$$

potem:

$$
\boxed{U\text{ ni podprostor}.}
$$

Primer:

$$
x+y=1.
$$

---

## 14.2 Neenačbe

Primer:

$$
U=\{(x,y);x\geq0\}.
$$

Če

$$
(1,0)\in U,
$$

potem

$$
-(1,0)=(-1,0)\notin U.
$$

---

## 14.3 Nelinearni pogoji

Primer:

$$
xy=0.
$$

Primer:

$$
x^2+y^2=0.
$$

Pozor: nelinearen zapis **ne pomeni avtomatično**, da množica ni podprostor.

Na primer nad $\mathbb R$:

$$
x^2+y^2=0
$$

pomeni

$$
x=y=0,
$$

zato je množica

$$
\{(0,0)\},
$$

ki je podprostor.

Vedno preveri dejansko množico.

---

## 14.4 Fiksna neničelna konstanta

Primer:

$$
x+y=4.
$$

Ničelni vektor ne zadošča pogoju.

---

## 14.5 Unija podprostorov

Če sta $U$ in $W$ podprostora, potem

$$
U\cup W
$$

praviloma **ni** podprostor.

Izjema je, če velja:

$$
U\subseteq W
$$

ali

$$
W\subseteq U.
$$

---

# 15. Presek podprostorov

## Izrek

Če sta $U,W\leq V$, potem je

$$
U\cap W
$$

vedno podprostor prostora $V$.

### Dokaz

Ker sta $U$ in $W$ podprostora:

$$
0\in U
$$

in

$$
0\in W.
$$

Zato:

$$
0\in U\cap W.
$$

Naj bosta

$$
u,v\in U\cap W.
$$

Tedaj:

$$
u,v\in U
$$

in

$$
u,v\in W.
$$

Za $\alpha,\beta\in F$:

$$
\alpha u+\beta v\in U
$$

in

$$
\alpha u+\beta v\in W.
$$

Zato:

$$
\alpha u+\beta v\in U\cap W.
$$

Torej:

$$
\boxed{U\cap W\leq V}.
$$

---

# 16. Kako izbrati metodo na izpitu

## Če vidim ...

### Homogeno linearno enačbo

Na primer:

$$
2x-y+3z=0.
$$

Uporabim:

> **kriterij za podprostor** oziroma dejstvo, da je množica rešitev homogenega linearnega sistema podprostor.

---

### Enačbo z neničelno konstanto

Na primer:

$$
2x-y+3z=5.
$$

Najprej preverim:

$$
0\notin U.
$$

Takoj zaključim.

---

### Neenačbo

Na primer:

$$
x\geq0.
$$

Poskusim skalar:

$$
-1.
$$

---

### Produkt komponent

Na primer:

$$
xy=0.
$$

Poskusim najti dva elementa, katerih vsota ne pripada množici.

---

### Absolutne vrednosti

Na primer:

$$
|x|=|y|.
$$

Poskusim najti dva elementa iz različnih vej množice.

---

### Pogoj na matriki

Najprej vprašam:

> Ali se pogoj obnaša linearno glede na $A+B$ in $\lambda A$?

Dobri pogoji:

$$
A^T=A,
$$

$$
A^T=-A,
$$

$$
a+b+c+d=0.
$$

Sumljivi pogoji:

$$
\det A=0,
$$

$$
A^2=A,
$$

$$
A\text{ je obrnljiva}.
$$

---

### Parametrični zapis

Na primer:

$$
(s+2t,3s,t).
$$

Izpostavim parametre:

$$
s(1,3,0)+t(2,0,1).
$$

To takoj pokaže strukturo podprostora.

---

# 17. Najpogostejše napake

## Napaka 1 — preverim samo $0\in U$

To je samo **nujen**, ne zadosten pogoj.

$$
0\in U
$$

še ne pomeni, da je $U$ podprostor.

Primer:

$$
U=\{(x,y)\in\mathbb R^2;xy=0\}.
$$

---

## Napaka 2 — vsaka enačba z desno stranjo $0$ je linearna

Ne.

$$
xy=0
$$

ima desno stran $0$, vendar ni linearna enačba.

---

## Napaka 3 — zamešam linearni in afini pogoj

$$
x+y=0
$$

je homogen linearen pogoj.

$$
x+y=1
$$

je afini pogoj.

---

## Napaka 4 — pozabim na polje

Če je prostor nad $\mathbb C$, morajo biti skalarji pri preverjanju podprostora iz $\mathbb C$.

---

## Napaka 5 — pri dokazovanju nepodprostora delam preveč

Za dokaz, da nekaj **ni** podprostor, zadostuje en kršen pogoj.

Na primer:

$$
0\notin U
$$

je dovolj.

---

## Napaka 6 — trdim, da nelinearen pogoj avtomatično pomeni nepodprostor

Vedno preveri dejansko množico.

---

## Napaka 7 — pri matricah uporabljam determinant, če ni potrebno

Pri pogojih

$$
A^T=A
$$

ali

$$
A^T=-A
$$

je najlažje direktno uporabiti lastnosti transponiranja.

---

## Napaka 8 — zamenjam podprostor in podmnožico

Vsak podprostor je podmnožica:

$$
U\leq V\Rightarrow U\subseteq V.
$$

Vsaka podmnožica pa ni podprostor.

---

# 18. Ustni / teoretični del

## Ustno vprašanje

**Vprašanje:** Kaj je vektorski prostor?

**Kratek odgovor:**  
Vektorski prostor nad poljem $F$ je neprazna množica $V$ z operacijama seštevanja vektorjev in množenja s skalarji iz $F$, ki zadoščata aksiomom asociativnosti in komutativnosti seštevanja, obstoju ničelnega in nasprotnega vektorja ter štirim aksiomom za množenje s skalarji.

**Profesor lahko dodatno vpraša:** Naštej aksiome za množenje s skalarji.

**Odgovor:**

$$
\alpha(u+v)=\alpha u+\alpha v,
$$

$$
(\alpha+\beta)u=\alpha u+\beta u,
$$

$$
\alpha(\beta u)=(\alpha\beta)u,
$$

$$
1u=u.
$$

---

## Ustno vprašanje

**Vprašanje:** Kaj je vektorski podprostor?

**Kratek odgovor:**  
Če je $V$ vektorski prostor nad $F$, je $U\subseteq V$ njegov vektorski podprostor, če je $U$ z operacijama, podedovanima iz $V$, sama vektorski prostor nad $F$.

Pišemo:

$$
U\leq V.
$$

**Profesor lahko dodatno vpraša:** Kaj mora nujno vsebovati vsak podprostor?

**Odgovor:**  
Ničelni vektor:

$$
0\in U.
$$

---

## Ustno vprašanje

**Vprašanje:** Navedi kriterij za podprostor.

**Kratek odgovor:**  
Podmnožica $U$ vektorskega prostora $V$ je podprostor natanko tedaj, ko je neprazna in je zaprta za linearne kombinacije dveh svojih elementov:

$$
u,v\in U,\quad
\alpha,\beta\in F
\Rightarrow
\alpha u+\beta v\in U.
$$

**Profesor lahko dodatno vpraša:** Zakaj ni treba preverjati vseh aksiomov vektorskega prostora?

**Odgovor:**  
Ker so asociativnost, komutativnost in distributivnosti podedovane iz prostora $V$. Preveriti moramo predvsem, da operaciji ne vodita iz množice $U$.

---

## Ustno vprašanje

**Vprašanje:** Dokaži kriterij za podprostor.

**Kratek odgovor:**  
Če je $U$ podprostor, je seveda neprazen in zaprt za linearne kombinacije.

Obratno naj bo $U\neq\varnothing$ in naj velja zaprtost za linearne kombinacije.

Izberemo $u\in U$. Za $\alpha=\beta=0$ dobimo

$$
0u+0u=0\in U.
$$

Za $u\in U$ in skalar $-1$ dobimo

$$
-u\in U.
$$

Za $\alpha=\beta=1$ dobimo

$$
u+v\in U.
$$

Ostali aksiomi so podedovani iz $V$. Zato je $U$ vektorski prostor.

---

## Ustno vprašanje

**Vprašanje:** Zakaj mora podprostor vsebovati ničelni vektor?

**Kratek odgovor:**  
Če $u\in U$, je zaradi zaprtosti za množenje s skalarji tudi

$$
0u=0\in U.
$$

**Profesor lahko dodatno vpraša:** Ali je pogoj $0\in U$ dovolj?

**Odgovor:**  
Ne. Na primer množica

$$
\{(x,y)\in\mathbb R^2;xy=0\}
$$

vsebuje $0$, vendar ni zaprta za seštevanje.

---

## Ustno vprašanje

**Vprašanje:** Ali je množica rešitev homogenega linearnega sistema podprostor?

**Kratek odgovor:**  
Da. Če

$$
Ax=0
$$

in

$$
Ay=0,
$$

potem za $\alpha,\beta\in F$:

$$
A(\alpha x+\beta y)
=
\alpha Ax+\beta Ay
=0.
$$

Zato je množica rešitev zaprta za linearne kombinacije.

**Profesor lahko dodatno vpraša:** Kaj pa sistem $Ax=b$ za $b\neq0$?

**Odgovor:**  
Praviloma ne predstavlja podprostora, ker ničelni vektor ni rešitev:

$$
A0=0\neq b.
$$

---

## Ustno vprašanje

**Vprašanje:** Ali je presek dveh podprostorov podprostor?

**Kratek odgovor:**  
Da.

Če

$$
U,W\leq V,
$$

potem

$$
U\cap W\leq V.
$$

**Profesor lahko dodatno vpraša:** Zakaj?

**Odgovor:**  
Če sta $u,v\in U\cap W$, sta hkrati v $U$ in $W$. Ker sta oba prostora zaprta za linearne kombinacije, je

$$
\alpha u+\beta v
$$

hkrati v $U$ in $W$, torej v $U\cap W$.

---

## Ustno vprašanje

**Vprašanje:** Ali je unija dveh podprostorov podprostor?

**Kratek odgovor:**  
Na splošno ne.

Na primer v $\mathbb R^2$:

$$
U=L\{(1,0)\},
$$

$$
W=L\{(0,1)\}.
$$

Velja

$$
(1,0)\in U\cup W
$$

in

$$
(0,1)\in U\cup W,
$$

vendar

$$
(1,1)\notin U\cup W.
$$

**Profesor lahko dodatno vpraša:** Kdaj je $U\cup W$ podprostor?

**Odgovor:**  
Natanko tedaj, ko je eden od podprostorov vsebovan v drugem:

$$
U\subseteq W
$$

ali

$$
W\subseteq U.
$$

---

## Ustno vprašanje

**Vprašanje:** Zakaj so simetrične matrike podprostor?

**Kratek odgovor:**  
Če

$$
A^T=A
$$

in

$$
B^T=B,
$$

potem:

$$
(\alpha A+\beta B)^T
=
\alpha A^T+\beta B^T
=
\alpha A+\beta B.
$$

Zato so zaprte za linearne kombinacije.

---

## Ustno vprašanje

**Vprašanje:** Zakaj množica obrnljivih matrik ni podprostor?

**Kratek odgovor:**  
Ker ničelna matrika ni obrnljiva, zato množica ne vsebuje ničelnega vektorja.

---

## Ustno vprašanje

**Vprašanje:** Zakaj množica singularnih oziroma neobrnljivih matrik ni podprostor?

**Kratek odgovor:**  
Ker ni zaprta za seštevanje. Na primer:

$$
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix}
$$

in

$$
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix}
$$

sta singularni, njuna vsota pa je $I$, ki je obrnljiva.

---

## Ustno vprašanje

**Vprašanje:** Kaj pomeni dimenzija podprostora?

**Kratek odgovor:**  
Dimenzija končnorazsežnega podprostora je število vektorjev v njegovi bazi.

**Profesor lahko dodatno vpraša:** Kako jo vidiš iz parametričnega zapisa?

**Odgovor:**  
Če dobimo $k$ linearno neodvisnih generatorskih vektorjev, je dimenzija $k$.

---

# 19. Dokazi, ki jih moram znati

Za ustni izpit je priporočljivo znati reproducirati vsaj naslednje dokaze.

## Dokaz 1 — kriterij za podprostor

Znati:

$$
U\neq\varnothing
$$

in

$$
u,v\in U,\ \alpha,\beta\in F
\Rightarrow
\alpha u+\beta v\in U.
$$

Iz tega izpeljati:

- $0\in U$;
- $-u\in U$;
- $u+v\in U$.

---

## Dokaz 2 — presek podprostorov je podprostor

Znati dokazati:

$$
U,W\leq V
\Rightarrow
U\cap W\leq V.
$$

---

## Dokaz 3 — množica rešitev homogenega sistema je podprostor

Če:

$$
Ax=0,
$$

potem uporabimo linearnost matričnega množenja:

$$
A(\alpha x+\beta y)
=
\alpha Ax+\beta Ay
=0.
$$

---

## Dokaz 4 — simetrične matrike tvorijo podprostor

Ključna lastnost:

$$
(\alpha A+\beta B)^T
=
\alpha A^T+\beta B^T.
$$

---

# 20. Hitri izpitni obrazci

## Dokaz, da JE podprostor

Na izpitu lahko pogosto napišeš:

> Naj bosta $u,v\in U$ in $\alpha,\beta\in F$. Preverimo linearno kombinacijo $\alpha u+\beta v$. Ker ta ponovno zadošča definicijskemu pogoju množice $U$, velja $\alpha u+\beta v\in U$. Ker je $U\neq\varnothing$, po kriteriju za podprostor sledi $U\leq V$.

---

## Dokaz, da NI podprostor — ničelni vektor

> Ker ničelni vektor ne zadošča pogoju množice $U$, velja $0\notin U$. Vsak podprostor mora vsebovati ničelni vektor, zato $U$ ni podprostor.

---

## Dokaz, da NI podprostor — seštevanje

> Najdemo $u,v\in U$, za katera $u+v\notin U$. Torej $U$ ni zaprta za seštevanje in zato ni podprostor.

---

## Dokaz, da NI podprostor — skalar

> Najdemo $u\in U$ in $\lambda\in F$, za katera $\lambda u\notin U$. Torej $U$ ni zaprta za množenje s skalarji in zato ni podprostor.

---

# 21. Srednje težke naloge

## Naloga 1

Naj bo

$$
U=
\{(3s-t,s+2t,t);s,t\in\mathbb R\}.
$$

Dokaži, da je $U$ podprostor $\mathbb R^3$. Poišči bazo in dimenzijo $U$.

---

## Naloga 2

Naj bo

$$
W=
\{(x,y,z,w)\in\mathbb R^4;
x-2y+z=0,\ y+w=0\}.
$$

Dokaži, da je $W$ podprostor ter poišči njegovo bazo in dimenzijo.

---

## Naloga 3

Za vsako množico ugotovi, ali je podprostor $\mathbb R^2$:

### (a)

$$
U_1=\{(x,y);x+y=1\}
$$

### (b)

$$
U_2=\{(x,y);xy=0\}
$$

### (c)

$$
U_3=\{(x,y);y=3x\}
$$

### (d)

$$
U_4=\{(x,y);x\geq y\}.
$$

---

## Naloga 4

Naj bo

$$
S=
\{A\in\mathbb R^{2\times2};A^T=A\}.
$$

Dokaži, da je $S$ podprostor. Poišči bazo in dimenzijo.

---

## Naloga 5

Naj bo

$$
T=
\left\{
\begin{pmatrix}
a&b\\
c&d
\end{pmatrix}
\in\mathbb R^{2\times2};
a+d=0
\right\}.
$$

Določi bazo in dimenzijo $T$.

---

## Naloga 6

Naj bo

$$
U=
\{p\in\mathbb R_2[x];p(1)=0\}.
$$

Dokaži, da je $U$ podprostor $\mathbb R_2[x]$ ter določi eno njegovo bazo in dimenzijo.

---

## Naloga 7

Naj bo

$$
U_t=
\{(x,y,z)\in\mathbb R^3;
x+ty-2z=3-t\}.
$$

Določi $t\in\mathbb R$, za katerega je $U_t$ podprostor. Za ta $t$ poišči eno bazo.

---

## Naloga 8

Naj bo

$$
D=
\{A\in\mathbb R^{2\times2};
A\text{ je diagonalna in }A^2=A\}.
$$

Ugotovi, ali je $D$ podprostor.

---

# 22. Težke / izpitne naloge

## Naloga 9

Za $n\geq2$ naj bo

$$
U=
\{(x_1,\ldots,x_n)\in\mathbb R^n;
x_1-x_n=0\}.
$$

Dokaži, da je $U$ podprostor, poišči njegovo bazo in določi dimenzijo.

---

## Naloga 10

Naj bo

$$
U=
\{A\in\mathbb R^{2\times2};
A^T=A,\ \operatorname{tr}(A)=0\}.
$$

Dokaži, da je $U$ podprostor, in poišči njegovo bazo ter dimenzijo.

---

## Naloga 11

Naj bo

$$
U=
\{p\in\mathbb R_3[x];
p(1)=0,\ p(-1)=0\}.
$$

Dokaži, da je $U$ podprostor. Poišči bazo in dimenzijo.

---

## Naloga 12

Naj bo

$$
U=
\{(x,y,z)\in\mathbb R^3;xz=y^2\}.
$$

Ugotovi, ali je $U$ podprostor. Odgovor utemelji z najkrajšim možnim protiprimerom.

---

## Naloga 13

Naj bo

$$
S=
\{A\in\mathbb R^{2\times2};\det A=0\}.
$$

Ugotovi, ali je $S$ podprostor $\mathbb R^{2\times2}$.

---

## Naloga 14

Za $t\in\mathbb R$ naj bo

$$
U_t=
\{(x,y,z)\in\mathbb R^3;
x-ty=0,\ z-tx=0\}.
$$

Za katere vrednosti $t$ je $U_t$ podprostor?

Za splošen $t$ poišči njegovo bazo in dimenzijo.

---

# 23. Odgovori

## Srednje težke naloge

**1.**

$$
U=
L\{(3,1,0),(-1,2,1)\}
$$

$$
\dim U=2.
$$

---

**2.**

$$
W=
L\{(2,1,0,-1),(-1,0,1,0)\}
$$

$$
\dim W=2.
$$

---

**3.**

$$
U_1:\text{ ni podprostor}
$$

$$
U_2:\text{ ni podprostor}
$$

$$
U_3:\text{ je podprostor}
$$

$$
U_4:\text{ ni podprostor}.
$$

Za $U_2$ lahko uporabiš:

$$
(1,0),(0,1)\in U_2,
$$

vendar

$$
(1,1)\notin U_2.
$$

---

**4.**

Vsaka simetrična matrika ima obliko

$$
\begin{pmatrix}
a&b\\
b&d
\end{pmatrix}.
$$

Ena baza je:

$$
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
\right\}.
$$

$$
\dim S=3.
$$

---

**5.**

Ker je $d=-a$:

$$
T=
\left\{
\begin{pmatrix}
a&b\\
c&-a
\end{pmatrix}
\right\}.
$$

Ena baza je:

$$
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
\right\}.
$$

$$
\dim T=3.
$$

---

**6.**

$$
p(x)=a+bx+cx^2,
$$

$$
a+b+c=0.
$$

Ena baza:

$$
\boxed{\{x-1,x^2-1\}}
$$

$$
\dim U=2.
$$

---

**7.**

$$
\boxed{t=3}
$$

Pogoj postane:

$$
x+3y-2z=0.
$$

Ena baza:

$$
\boxed{\{(-3,1,0),(2,0,1)\}}.
$$

---

**8.**

$$
\boxed{D\text{ ni podprostor}.}
$$

Namig:

$$
I\in D,
$$

vendar

$$
2I\notin D.
$$

---

## Težke / izpitne naloge

**9.**

$$
x_1=x_n.
$$

Ena baza:

$$
\boxed{
\{e_1+e_n,e_2,\ldots,e_{n-1}\}
}
$$

$$
\boxed{\dim U=n-1}.
$$

---

**10.**

Matrike imajo obliko:

$$
\begin{pmatrix}
a&b\\
b&-a
\end{pmatrix}.
$$

Ena baza:

$$
\boxed{
\left\{
\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix},
\begin{pmatrix}
0&1\\
1&0
\end{pmatrix}
\right\}
}
$$

$$
\boxed{\dim U=2}.
$$

---

**11.**

Ker imata polinoma ničli $1$ in $-1$:

$$
p(x)=(x^2-1)(a+bx).
$$

Ena baza:

$$
\boxed{\{x^2-1,x^3-x\}}
$$

$$
\boxed{\dim U=2}.
$$

---

**12.**

$$
\boxed{U\text{ ni podprostor}.}
$$

Na primer:

$$
(1,0,0),(0,0,1)\in U,
$$

vendar

$$
(1,0,1)\notin U.
$$

---

**13.**

$$
\boxed{S\text{ ni podprostor}.}
$$

Uporabi:

$$
A=
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix},
\qquad
B=
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix}.
$$

Obe imata determinant $0$, toda

$$
A+B=I
$$

ima determinant $1$.

---

**14.**

$$
\boxed{\text{Za vsak }t\in\mathbb R\text{ je }U_t\text{ podprostor}.}
$$

Iz:

$$
x=ty
$$

in

$$
z=tx
$$

sledi:

$$
z=t^2y.
$$

Zato:

$$
U_t
=
L\{(t,1,t^2)\}
$$

in

$$
\boxed{\dim U_t=1}.
$$

---

# 24. Faza je zaključena, ko znam ...

- [ ] Točno definirati **vektorski prostor nad poljem $F$**.
- [ ] Našteti vseh osem osnovnih aksiomov vektorskega prostora.
- [ ] Razložiti razliko med **vektorjem** in **skalarjem**.
- [ ] Prepoznati standardne vektorske prostore $\mathbb R^n$, $\mathbb C^n$, $\mathbb R^{m\times n}$ in $\mathbb R_n[x]$.
- [ ] Točno definirati **vektorski podprostor**.
- [ ] Zapisati in uporabiti kriterij
  $$
  u,v\in U,\quad \alpha,\beta\in F
  \Rightarrow
  \alpha u+\beta v\in U.
  $$
- [ ] Dokazati kriterij za podprostor.
- [ ] Vedno najprej preveriti, ali velja $0\in U$.
- [ ] Prepoznati homogen linearen pogoj, kot je
  $$
  a_1x_1+\cdots+a_nx_n=0.
  $$
- [ ] Razložiti, zakaj množica rešitev homogenega sistema $Ax=0$ tvori podprostor.
- [ ] Razložiti, zakaj sistem $Ax=b$ za $b\neq0$ praviloma ne določa podprostora.
- [ ] Prepoznati afine pogoje tipa
  $$
  x+y=1
  $$
  in jih hitro zavrniti s preverjanjem ničelnega vektorja.
- [ ] Prepoznati nelinearne pogoje tipa $xy=0$, $A^2=A$ ali $\det A=0$.
- [ ] Za dokaz, da množica ni podprostor, najti čim krajši protiprimer.
- [ ] Preveriti zaprtost za seštevanje.
- [ ] Preveriti zaprtost za množenje s skalarji.
- [ ] Uporabiti skalar $-1$ za hitro preverjanje pogojev z neenačbami.
- [ ] Iz parametričnega zapisa izpostaviti generatorske vektorje.
- [ ] Iz enostavnega parametričnega zapisa določiti bazo in dimenzijo.
- [ ] Dokazati, da so diagonalne matrike podprostor.
- [ ] Dokazati, da so simetrične matrike podprostor.
- [ ] Dokazati, da so antisimetrične matrike podprostor.
- [ ] Razložiti, zakaj obrnljive matrike ne tvorijo podprostora.
- [ ] Razložiti, zakaj neobrnljive matrike ne tvorijo podprostora.
- [ ] Prepoznati skalarne matrike $A=\lambda I$ kot podprostor.
- [ ] Rešiti nalogo s parametrom, kjer mora pogoj postati homogen.
- [ ] Dokazati, da je presek dveh podprostorov ponovno podprostor.
- [ ] Razložiti, zakaj unija dveh podprostorov praviloma ni podprostor.
- [ ] Navesti pogoj, kdaj je $U\cup W$ vendarle podprostor.
- [ ] Na ustnem izpitu brez zapiskov odgovoriti na vprašanje: **Kaj je vektorski prostor?**
- [ ] Na ustnem izpitu brez zapiskov odgovoriti na vprašanje: **Kaj je vektorski podprostor?**
- [ ] Na ustnem izpitu brez zapiskov navesti in dokazati **kriterij za podprostor**.
- [ ] Na ustnem izpitu dokazati, da je množica rešitev homogenega linearnega sistema podprostor.
- [ ] Na ustnem izpitu dokazati, da je presek podprostorov podprostor.
- [ ] Pri novi nalogi v nekaj sekundah prepoznati, ali naj uporabim **ničelni vektor**, **zaprtost za seštevanje**, **zaprtost za skalarje** ali popoln kriterij.
- [ ] Samostojno rešiti vse srednje naloge tega poglavja brez gledanja rešitev.
- [ ] Samostojno rešiti vsaj večino težkih/izpitnih nalog in pravilno utemeljiti vsak odgovor.
