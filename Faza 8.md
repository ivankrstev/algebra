# FAZA 8 — Pisni izpit: mešana vadba

## Namen faze

Ta faza ni več namenjena prvemu učenju snovi, ampak **povezovanju vseh ključnih metod v izpitno celoto**. Cilj je, da pri novi nalogi hitro prepoznam tip problema, izberem pravilno metodo, izvedem račun brez nepotrebnih korakov in zapišem dovolj utemeljitve, da je rešitev primerna za pisni izpit.

Poglavje temelji predvsem na priloženih **Vajah 1–12** pri predmetu *Algebra II – Linearna algebra, študijsko leto 2025/2026*. V priloženih datotekah ni ločenih preteklih izpitov ali kolokvijev, zato so prioritete določene po pogostosti in poudarkih v vajah, ne po statistiki nepriloženih izpitov.

Največ teže imajo sklopi:

1. **vektorski podprostori, baze, linearna neodvisnost in dimenzija**,
2. **vsota in presek podprostorov**,
3. **linearne preslikave, jedro, slika, rang, injektivnost in surjektivnost**,
4. **koordinate, urejene baze, prehodne matrike in matrike linearnih preslikav**,
5. **karakteristični polinom, lastne vrednosti, lastni podprostori in diagonalizacija**.

Manj pogosto, vendar še vedno pomembno:

- grupe in kolobarji,
- linearni funkcionali in izomorfizmi,
- invariantni podprostori,
- projektorji,
- nilpotentni endomorfizmi.

---

## Kako uporabljam to poglavje

Pri vsaki nalogi najprej naredim tri stvari:

1. **Prepoznam objekt:** podprostor, preslikava, matrika, baza, endomorfizem ...
2. **Prepoznam zahtevo:** dokaz, baza, dimenzija, jedro, koordinate, lastne vrednosti ...
3. **Izberem standardno metodo:** Gaussova eliminacija, rešitev homogenega sistema, determinantna enačba, sprememba baze ...

Na pisnem izpitu se izogibam slepemu računanju. Vsak daljši račun naj se začne s kratkim matematičnim stavkom, ki pove, **kaj računam in zakaj**.

Primer:

> Za jedro rešimo sistem $A x=0$.

ali:

> Lastne vrednosti so ničle karakterističnega polinoma $p_A(\lambda)=\det(\lambda I-A)$.

---

## Prioritetni zemljevid gradiva

| Prioriteta | Tip naloge | Priloženo gradivo |
|---|---|---|
| zelo visoka | podprostor, baza, dimenzija | 4. in 5. vaje |
| zelo visoka | linearna neodvisnost, ogrodje | 4. in 5. vaje |
| zelo visoka | vsota in presek podprostorov | 5. in 6. vaje |
| zelo visoka | jedro, slika, rang | 7. in 10. vaje |
| zelo visoka | koordinatni stolpci in sprememba baze | 8. in 9. vaje |
| zelo visoka | matrika linearne preslikave | 9. in 10. vaje |
| zelo visoka | lastne vrednosti in diagonalizacija | 11. in 12. vaje |
| visoka | injektivnost, surjektivnost, izomorfizem | 7. in 8. vaje |
| visoka | invariantni podprostori | 11. vaje |
| srednja | linearni funkcionali | 7. in 8. vaje |
| srednja | projektorji, nilpotentnost | 11. vaje |
| nižja, a možna | grupe in kolobarji | 1.–3. vaje |

---

# 1. Algebraične strukture: hitra izpitna ponovitev

Ta sklop je v priloženem gradivu zgoščen predvsem v 1.–3. vajah. Za mešani izpit ga obravnavam kot **sekundarno prioriteto**, vendar moram znati definicije in standardni postopek preverjanja grupe.

## Ključne definicije

### Dvomestna notranja operacija

Preslikava

$$
\circ:S\times S\to S
$$

je **dvomestna notranja operacija** na $S$.

Ključna zahteva je **zaprtost**:

$$
a,b\in S \Longrightarrow a\circ b\in S.
$$

### Grupa

Množica $G$ z notranjo operacijo $\circ$ je grupa, če velja:

1. asociativnost,
2. obstoj nevtralnega elementa $e$,
3. vsak element ima obrat.

Če dodatno velja

$$
a\circ b=b\circ a,
$$

je grupa **komutativna oziroma Abelova**.

### Kolobar

Za kolobar $(R,+,\cdot)$ moram preveriti predvsem:

- $(R,+)$ je Abelova grupa,
- množenje je asociativno,
- veljata distributivnostna zakona.

Če je v definiciji predmeta zahtevana tudi multiplikativna identiteta, jo moram posebej navesti.

---

## Tip naloge: preverjanje, ali je dana struktura grupa

**Kako jo prepoznam**

Podana je množica $G$ in nenavadna operacija, npr.

$$
a\circ b=(a+3)(b+3)-3.
$$

Takšne naloge so neposredno v 2. vajah.

**Postopek**

1. Preverim zaprtost.
2. Preverim asociativnost.
3. Izračunam nevtralni element.
4. Za splošen $a$ izračunam obrat.
5. Če je potrebno, preverim komutativnost.

**Primer**

Naj bo

$$
G=\mathbb R\setminus\{-3\},
\qquad
a\circ b=(a+3)(b+3)-3.
$$

Preveri, ali je $(G,\circ)$ grupa.

**Rešitev**

Za $a,b\in G$ sta $a+3\neq 0$ in $b+3\neq 0$, zato

$$
(a\circ b)+3=(a+3)(b+3)\neq 0.
$$

Torej $a\circ b\neq -3$ in operacija je notranja.

Asociativnost sledi iz

$$
((a\circ b)\circ c)+3
=
(a+3)(b+3)(c+3)
=
(a\circ(b\circ c))+3.
$$

Nevtralni element $e$ določa enačba

$$
(a+3)(e+3)-3=a.
$$

Ker je $a+3\neq0$,

$$
e+3=1,
\qquad
e=-2.
$$

Obrat $b$ elementa $a$ določa

$$
(a+3)(b+3)-3=-2,
$$

zato

$$
(a+3)(b+3)=1
$$

in

$$
b=\frac{1}{a+3}-3.
$$

Ta element pripada $G$. Operacija je tudi komutativna. Zato je $(G,\circ)$ Abelova grupa.

**Pogoste napake**

- preverim identiteto, ne preverim pa zaprtosti;
- za obrat izračunam izraz, ne preverim pa, ali pripada $G$;
- asociativnost sklepam samo iz komutativnosti;
- zamenjam nevtralni element običajnega seštevanja z nevtralnim elementom dane operacije.

---

### Ustno vprašanje

**Vprašanje:** Kaj je grupa?

**Kratek odgovor:** Grupa je množica $G$ z asociativno notranjo operacijo, nevtralnim elementom in obratnim elementom za vsak element $G$.

**Profesor lahko dodatno vpraša:** Zakaj je nevtralni element enoličen?

**Odgovor:** Če sta $e$ levi in $f$ desni nevtralni element, potem

$$
e=e\circ f=f.
$$

---

# 2. Vektorski podprostori, baza in dimenzija

To je eden temeljnih in najpogostejših sklopov v 4. in 5. vajah.

## Ključna teorija

Naj bo $V$ vektorski prostor nad poljem $F$.

Podmnožica $U\subseteq V$ je **vektorski podprostor**, če je neprazna in je zaprta za linearne kombinacije:

$$
u,v\in U,\ \alpha,\beta\in F
\Longrightarrow
\alpha u+\beta v\in U.
$$

V praksi je pogosto dovolj preveriti:

1. $0\in U$,
2. $u,v\in U\Rightarrow u+v\in U$,
3. $\alpha\in F,\ u\in U\Rightarrow \alpha u\in U$.

Če je množica podana z **homogenim sistemom linearnih enačb**, je avtomatično podprostor:

$$
U=\{x\in F^n; Ax=0\}=\ker A.
$$

Če je pogoj nehomogen,

$$
Ax=b,\qquad b\neq 0,
$$

množica praviloma ni podprostor, ker ne vsebuje ničelnega vektorja.

---

## Tip naloge: preveri podprostor, poišči bazo in dimenzijo

**Kako jo prepoznam**

Množica je podana parametrsko ali z linearnimi enačbami in vprašanje zahteva:

- ali je podprostor,
- bazo,
- dimenzijo.

**Postopek**

1. Če je množica podana z enačbami, preverim homogenost.
2. Izrazim splošen element s prostimi parametri.
3. Zapišem ga kot linearno kombinacijo vektorjev.
4. Preverim linearno neodvisnost dobljenih generatorjev.
5. Zapišem bazo in dimenzijo.

**Primer**

Iz 4. vaj:

$$
U=\{(2z,w,z); z,w\in\mathbb C\}.
$$

Določi bazo in dimenzijo.

**Rešitev**

Za vsak $(2z,w,z)\in U$ velja

$$
(2z,w,z)
=
z(2,0,1)+w(0,1,0).
$$

Zato

$$
U=L\{(2,0,1),(0,1,0)\}.
$$

Vektorja sta linearno neodvisna, saj

$$
\alpha(2,0,1)+\beta(0,1,0)=0
$$

da iz druge komponente $\beta=0$, iz tretje pa $\alpha=0$.

Torej je baza

$$
\mathcal B=\{(2,0,1),(0,1,0)\}
$$

in

$$
\dim U=2.
$$

**Pogoste napake**

- iz parametrskega zapisa prepišem generatorje, ne preverim pa njihove neodvisnosti;
- pri nehomogeni enačbi pozabim preveriti ničelni vektor;
- zamenjam število parametrov s dimenzijo, če parametri niso neodvisni.

---

## Tip naloge: določi parameter, da je množica podprostor

**Kako jo prepoznam**

V pogoju nastopa parameter in množica je zaradi konstante lahko afina namesto linearna.

**Primer**

Iz 5. vaj:

$$
U=
\{(x,y,z)\in\mathbb R^3;
x-t(y+2z-2)=4\}.
$$

Določi $t$, da bo $U$ podprostor, nato poišči bazo.

**Rešitev**

Enačbo preuredimo:

$$
x-ty-2tz+2t=4.
$$

Za podprostor mora enačbo izpolnjevati $(0,0,0)$, zato

$$
2t=4,
$$

torej

$$
t=2.
$$

Tedaj je

$$
x-2y-4z=0,
$$

zato

$$
x=2y+4z.
$$

Splošen element je

$$
(x,y,z)
=
y(2,1,0)+z(4,0,1).
$$

Baza je

$$
\{(2,1,0),(4,0,1)\},
$$

zato

$$
\dim U=2.
$$

**Kako prepoznam najhitrejšo pot**

Če je v definiciji množice konstanta, najprej vstavim ničelni vektor. To pogosto takoj določi parameter ali pokaže, da množica ni podprostor.

---

## Definicije, ki jih moram znati natančno

### Linearna kombinacija

Vektor $v$ je linearna kombinacija vektorjev $v_1,\dots,v_k$, če obstajajo skalarji $\alpha_1,\dots,\alpha_k$, da

$$
v=\alpha_1v_1+\cdots+\alpha_kv_k.
$$

### Linearna ogrinjača

$$
L\{v_1,\dots,v_k\}
=
\left\{
\sum_{i=1}^k\alpha_i v_i;\ \alpha_i\in F
\right\}.
$$

### Linearna neodvisnost

Vektorji $v_1,\dots,v_k$ so linearno neodvisni, če iz

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0
$$

sledi

$$
\alpha_1=\cdots=\alpha_k=0.
$$

### Baza

**Baza** je linearno neodvisno ogrodje prostora.

### Dimenzija

Če je $V$ končnorazsežen, je

$$
\dim V
$$

število vektorjev v katerikoli bazi prostora $V$.

---

## Tip naloge: linearna neodvisnost, ogrodje in baza

**Kako jo prepoznam**

Podana je množica vektorjev ali polinomov in treba je odločiti:

- ali je linearno neodvisna,
- ali generira prostor,
- ali je baza.

**Postopek**

1. Vektorje pretvorim v koordinatne stolpce glede na naravno bazo.
2. Sestavim matriko s temi stolpci.
3. Z Gaussovo eliminacijo določim rang.
4. Primerjam rang s številom vektorjev in z dimenzijo prostora.

Če ima prostor dimenzijo $n$ in imam natanko $n$ vektorjev, je dovolj preveriti samo eno od naslednjega:

- linearno neodvisnost,
- da generirajo celoten prostor.

**Primer**

V $R_2[x]$ vzemi

$$
p_1=1+x,\qquad
p_2=x+x^2,\qquad
p_3=1+x^2.
$$

Glede na bazo $\{1,x,x^2\}$ imajo koordinatne stolpce

$$
[p_1]=
\begin{pmatrix}
1\\1\\0
\end{pmatrix},
\quad
[p_2]=
\begin{pmatrix}
0\\1\\1
\end{pmatrix},
\quad
[p_3]=
\begin{pmatrix}
1\\0\\1
\end{pmatrix}.
$$

Matrika je

$$
M=
\begin{pmatrix}
1&0&1\\
1&1&0\\
0&1&1
\end{pmatrix}.
$$

Ker je

$$
\det M=2\neq0,
$$

so polinomi linearno neodvisni. Ker so trije in

$$
\dim R_2[x]=3,
$$

so tudi baza prostora $R_2[x]$.

**Pogoste napake**

- pozabim, da je $\dim R_n[x]=n+1$;
- množica vsebuje ničelni vektor, pa jo kljub temu razglasim za linearno neodvisno;
- preverjam ogrodje z naključnimi primeri namesto za splošen vektor;
- zamenjam vrstice in stolpce brez dosledne interpretacije.

---

### Ustno vprašanje

**Vprašanje:** Kaj je baza vektorskega prostora?

**Kratek odgovor:** Baza je linearno neodvisno ogrodje vektorskega prostora.

**Profesor lahko dodatno vpraša:** Če ima $V$ dimenzijo $n$ in je $v_1,\dots,v_n$ linearno neodvisnih, kaj sledi?

**Odgovor:** Tvorijo bazo prostora $V$.

---

### Ustno vprašanje

**Vprašanje:** Zakaj imajo vse baze končnorazsežnega prostora enako število elementov?

**Kratek odgovor:** To je posledica izreka o zamenjavi oziroma Steinitzovega izreka: linearno neodvisna množica ne more imeti več elementov kot ogrodje. Če primerjamo dve bazi v obe smeri, dobimo enako število elementov.

**Profesor lahko dodatno vpraša:** Kaj pomeni dimenzija podprostora $U\leq V$?

**Odgovor:** Število elementov katerekoli baze $U$; za končnorazsežen $V$ velja $\dim U\leq\dim V$.

---

# 3. Vsota in presek podprostorov

Ta tip se pojavlja v 5. in 6. vajah in je pomembna povezava med bazami, linearnimi sistemi in dimenzijo.

## Ključne definicije

Za podprostora $U,W\leq V$ je

$$
U+W
=
\{u+w;\ u\in U,\ w\in W\}.
$$

Presek

$$
U\cap W
$$

je podprostor, ki vsebuje vektorje, ki pripadajo obema prostoroma.

Če

$$
U\cap W=\{0\},
$$

je vsota **direktna** in pišemo

$$
U\oplus W.
$$

## Najpomembnejša formula

Za končnorazsežna podprostora velja

$$
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
$$

Iz nje sledi tudi

$$
\dim(U\cap W)
=
\dim U+\dim W-\dim(U+W).
$$

Ker je $U+W\leq V$,

$$
\dim(U\cap W)
\geq
\dim U+\dim W-\dim V.
$$

---

## Tip naloge: poišči baze $U$, $W$, $U\cap W$ in $U+W$

**Kako jo prepoznam**

Podprostora sta podana z generatorji, pogosto v prostoru polinomov.

**Postopek**

1. Generatorje $U$ pretvorim v koordinatne stolpce in izberem bazo $U$.
2. Enako za $W$.
3. Za presek rešim

$$
u=w.
$$

Če sta

$$
u=U\alpha,\qquad w=W\beta,
$$

rešujem

$$
U\alpha-W\beta=0.
$$

4. Iz rešitev dobim bazo preseka.
5. Za vsoto uporabim unijo baz in izločim linearno odvisne vektorje ali uporabim dimenzijsko formulo.

**Primer iz 6. vaj**

Naj bo

$$
P=L\{1+x^2+2x^3,\ 2-x+x^2+2x^3,\ 1+x+x^2+x^3\}
$$

in

$$
R=L\{1+x^3,\ 3+x^3,\ 1+x\}.
$$

Glede na bazo $\{1,x,x^2,x^3\}$ so generatorji $P$:

$$
p_1=
\begin{pmatrix}
1\\0\\1\\2
\end{pmatrix},
\quad
p_2=
\begin{pmatrix}
2\\-1\\1\\2
\end{pmatrix},
\quad
p_3=
\begin{pmatrix}
1\\1\\1\\1
\end{pmatrix}.
$$

Ti trije vektorji so linearno neodvisni, zato

$$
\dim P=3.
$$

Za $R$ dobimo

$$
r_1=
\begin{pmatrix}
1\\0\\0\\1
\end{pmatrix},
\quad
r_2=
\begin{pmatrix}
3\\0\\0\\1
\end{pmatrix},
\quad
r_3=
\begin{pmatrix}
1\\1\\0\\0
\end{pmatrix},
$$

ki so prav tako linearno neodvisni, zato

$$
\dim R=3.
$$

Za presek rešimo

$$
\alpha_1p_1+\alpha_2p_2+\alpha_3p_3
=
\beta_1r_1+\beta_2r_2+\beta_3r_3.
$$

Po reševanju sistema dobimo dve neodvisni rešitvi, ki dajeta polinoma

$$
1-x^3
$$

in

$$
x-x^3.
$$

Zato

$$
P\cap R
=
L\{1-x^3,\ x-x^3\}
$$

in

$$
\dim(P\cap R)=2.
$$

Po dimenzijski formuli:

$$
\dim(P+R)
=
3+3-2=4.
$$

Ker je

$$
\dim R_3[x]=4,
$$

sledi

$$
P+R=R_3[x].
$$

**Pogoste napake**

- za $U+W$ seštejem baze po komponentah namesto da vzamem vse generatorje;
- za $U\cap W$ vzamem samo generatorje, ki so videti podobni;
- uporabim dimenzijsko formulo, ne da bi poznal eno od potrebnih dimenzij;
- pozabim, da lahko unija dveh baz vsebuje linearno odvisne vektorje.

---

## Tip naloge: dimenzijska formula brez računanja baz

**Primer iz 5. vaj**

Če je

$$
\dim V=6,\qquad
\dim W=7,\qquad
\dim(V\cap W)=3,
$$

potem

$$
\dim(V+W)
=
6+7-3=10.
$$

**Primer omejitve preseka**

Če je

$$
\dim X=45,\qquad
\dim U=32,\qquad
\dim W=41,
$$

potem

$$
\dim(U\cap W)
\geq
32+41-45=28.
$$

Hkrati

$$
\dim(U\cap W)\leq \min\{32,41\}=32.
$$

Zato

$$
28\leq\dim(U\cap W)\leq32.
$$

---

### Ustno vprašanje

**Vprašanje:** Povej dimenzijsko formulo za vsoto dveh podprostorov.

**Kratek odgovor:**

$$
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
$$

Velja za končnorazsežna podprostora.

**Profesor lahko dodatno vpraša:** Kdaj je vsota direktna?

**Odgovor:** Natanko tedaj, ko je

$$
U\cap W=\{0\}.
$$

Tedaj velja

$$
\dim(U\oplus W)=\dim U+\dim W.
$$

---

# 4. Linearne preslikave

V 6. in 7. vajah se začne glavni operativni del linearne algebre.

## Definicija

Preslikava

$$
A:V\to W
$$

je linearna, če za vse $u,v\in V$ in $\alpha,\beta\in F$ velja

$$
A(\alpha u+\beta v)
=
\alpha A(u)+\beta A(v).
$$

Ekvivalentno lahko preverjam:

$$
A(u+v)=A(u)+A(v)
$$

in

$$
A(\alpha u)=\alpha A(u).
$$

Vsaka linearna preslikava zadošča

$$
A(0)=0.
$$

To je pogosto najhitrejši test za nelinearnost.

---

## Tip naloge: preveri linearnost

**Kako jo prepoznam**

Podan je ekspliciten predpis, na primer

$$
A(x,y)=(x+1,y)
$$

ali

$$
A(x,y)=(2x,y).
$$

**Postopek**

1. Najprej preverim $A(0)$.
2. Če $A(0)\neq0$, preslikava ni linearna.
3. Če ta test ne odloči, preverim linearnost po definiciji.

**Primer**

$$
A(x,y)=(x+1,y).
$$

Ker

$$
A(0,0)=(1,0)\neq(0,0),
$$

$A$ ni linearna.

Za

$$
B(x,y)=(2x,y)
$$

pa velja

$$
B(\alpha(x_1,y_1)+\beta(x_2,y_2))
=
\alpha B(x_1,y_1)+\beta B(x_2,y_2),
$$

zato je $B$ linearna.

**Pogoste napake**

- preverim samo aditivnost;
- preslikavo z absolutno vrednostjo razglasim za linearno, ker je videti komponentna;
- ne uporabim hitrega testa $A(0)=0$.

---

## Tip naloge: preslikava je podana s slikami nekaj vektorjev

**Kako jo prepoznam**

Podane so slike

$$
A(v_1),\dots,A(v_k)
$$

in treba je izračunati $A(v)$ ali preveriti, ali taka linearna preslikava obstaja.

**Ključna ideja**

Linearna preslikava je enolično določena s slikami **baznih vektorjev**.

Če so podani vektorji linearno odvisni, morajo njihove slike spoštovati iste linearne relacije.

Če

$$
v_3=v_1+v_2,
$$

mora veljati

$$
A(v_3)=A(v_1)+A(v_2).
$$

**Primer iz 6. vaj**

Podano je:

$$
A(1+x)=(1,0),
$$

$$
A(x+x^2)=(0,-1),
$$

$$
A(1+x^2)=(1,5).
$$

Izračunaj

$$
A(1+x+x^2).
$$

Najprej izrazimo polinom:

$$
1+x+x^2
=
\frac12(1+x)
+
\frac12(x+x^2)
+
\frac12(1+x^2).
$$

Z linearnostjo:

$$
A(1+x+x^2)
=
\frac12(1,0)
+
\frac12(0,-1)
+
\frac12(1,5).
$$

Zato

$$
A(1+x+x^2)
=
(1,2).
$$

**Pogoste napake**

- seštevam slike, ne da bi najprej pravilno izrazil vhodni vektor;
- predpostavim, da so podani vektorji baza;
- pri linearno odvisnih vhodih ne preverim skladnosti slik.

---

### Ustno vprašanje

**Vprašanje:** Zakaj je linearna preslikava enolično določena s slikami baznih vektorjev?

**Kratek odgovor:** Vsak $v\in V$ ima glede na bazo $v_1,\dots,v_n$ enoličen zapis

$$
v=\sum_{i=1}^n\alpha_i v_i.
$$

Z linearnostjo je

$$
A(v)=\sum_{i=1}^n\alpha_iA(v_i),
$$

zato so slike vseh vektorjev enolično določene.

**Profesor lahko dodatno vpraša:** Ali lahko poljubno predpišemo slike linearno odvisnih vektorjev?

**Odgovor:** Ne. Slike morajo ohranjati vse linearne relacije med vhodnimi vektorji.

---

# 5. Jedro, slika, rang, injektivnost in surjektivnost

To je osrednji izpitni sklop 7. in 10. vaj.

## Definicije

Za linearno preslikavo

$$
A:V\to W
$$

je **jedro**

$$
\ker A
=
\{v\in V; A(v)=0\}.
$$

**Slika** oziroma zaloga vrednosti je

$$
\operatorname{Im}A
=
\{A(v);v\in V\}.
$$

**Rang** preslikave je

$$
\operatorname{rang}A
=
\dim(\operatorname{Im}A).
$$

**Ničelnost** je

$$
\dim(\ker A).
$$

## Izrek o rangu in ničelnosti

Če je $V$ končnorazsežen in

$$
A:V\to W
$$

linearna, potem

$$
\dim V
=
\dim(\ker A)
+
\dim(\operatorname{Im}A).
$$

### Posledice

$$
A\text{ je injektivna}
\iff
\ker A=\{0\}.
$$

Če je

$$
\dim V=\dim W<\infty,
$$

potem so za linearno $A:V\to W$ ekvivalentne trditve:

- $A$ je injektivna,
- $A$ je surjektivna,
- $A$ je bijektivna,
- matrika $A$ je obrnljiva.

---

## Tip naloge: iz matrike poišči jedro, sliko in rang

**Kako jo prepoznam**

Podana je matrika linearne preslikave.

**Postopek**

### Jedro

Rešim

$$
A x=0.
$$

Baza prostora rešitev je baza $\ker A$.

### Slika

Slika je linearna ogrinjača stolpcev matrike:

$$
\operatorname{Im}A=L\{a_1,\dots,a_n\}.
$$

Za bazo slike izberem linearno neodvisne **izvirne stolpce**, ki ustrezajo pivotnim stolpcem.

### Rang

$$
\operatorname{rang}A
=
\text{število pivotov}.
$$

**Primer iz 10. vaj**

Naj bo

$$
A=
\begin{pmatrix}
1&0&1\\
0&-1&1\\
2&2&0\\
0&-2&2
\end{pmatrix}.
$$

Po Gaussovi eliminaciji dobimo rang

$$
\operatorname{rang}A=2.
$$

Za jedro rešimo

$$
A
\begin{pmatrix}
x\\y\\z
\end{pmatrix}
=0.
$$

Dobimo

$$
x+z=0,
\qquad
-y+z=0,
$$

torej

$$
x=-z,\qquad y=z.
$$

Zato

$$
\ker A
=
L\{(-1,1,1)\}.
$$

Za sliko lahko vzamemo prva dva neodvisna stolpca:

$$
\operatorname{Im}A
=
L\left\{
\begin{pmatrix}
1\\0\\2\\0
\end{pmatrix},
\begin{pmatrix}
0\\-1\\2\\-2
\end{pmatrix}
\right\}.
$$

Preverba:

$$
\dim\ker A+\dim\operatorname{Im}A
=
1+2=3
=
\dim\mathbb R^3.
$$

**Pogoste napake**

- za bazo slike uporabim pivotne stolpce reducirane matrike namesto ustreznih stolpcev originalne matrike;
- jedro iščem z enačbo $Ax=b$ namesto $Ax=0$;
- rang zamenjam s številom vrstic;
- ne naredim preverbe z izrekom o rangu in ničelnosti.

---

## Tip naloge: rang in ničelnost brez eksplicitnega računanja

**Primer iz 7. vaj**

Naj bo

$$
A:R_5[x]\to\mathbb R^5
$$

linearna in

$$
\dim(\operatorname{Im}A)=2.
$$

Ker

$$
\dim R_5[x]=6,
$$

po izreku o rangu in ničelnosti:

$$
6=\dim(\ker A)+2.
$$

Zato

$$
\dim(\ker A)=4.
$$

**Kako jo prepoznam**

Če naloga poda samo:

- dimenzijo domene,
- rang,
- dimenzijo jedra,

najprej pomislim na

$$
\dim V=\operatorname{nullity}(A)+\operatorname{rank}(A).
$$

---

## Tip naloge: določi injektivnost ali surjektivnost

Za linearno preslikavo

$$
A:\mathbb R^n\to\mathbb R^m
$$

velja:

- injektivnost zahteva $\operatorname{rang}A=n$,
- surjektivnost zahteva $\operatorname{rang}A=m$.

Zato:

- če $n>m$, preslikava ne more biti injektivna;
- če $n<m$, ne more biti surjektivna.

To je pogosto mogoče ugotoviti **še preden računam matriko**.

---

### Ustno vprašanje

**Vprašanje:** Kaj je jedro linearne preslikave?

**Kratek odgovor:**

$$
\ker A=\{v\in V;A(v)=0\}.
$$

Je vektorski podprostor domene.

**Profesor lahko dodatno vpraša:** Dokaži, da je jedro podprostor.

**Odgovor:** Če sta $u,v\in\ker A$ in $\alpha,\beta\in F$, potem

$$
A(\alpha u+\beta v)
=
\alpha A(u)+\beta A(v)
=
0.
$$

Zato

$$
\alpha u+\beta v\in\ker A.
$$

---

### Ustno vprašanje

**Vprašanje:** Kdaj je linearna preslikava injektivna?

**Kratek odgovor:**

$$
A\text{ je injektivna}
\iff
\ker A=\{0\}.
$$

**Profesor lahko dodatno vpraša:** Dokaži smer $\ker A=\{0\}\Rightarrow A$ injektivna.

**Odgovor:** Če $A(u)=A(v)$, potem

$$
A(u-v)=0.
$$

Ker je jedro trivialno,

$$
u-v=0,
$$

zato $u=v$.

---

### Ustno vprašanje

**Vprašanje:** Povej izrek o rangu in ničelnosti.

**Kratek odgovor:** Če je $V$ končnorazsežen in $A:V\to W$ linearna, potem

$$
\dim V
=
\dim\ker A+\dim\operatorname{Im}A.
$$

**Profesor lahko dodatno vpraša:** Kaj iz tega sledi za endomorfizem končnorazsežnega prostora?

**Odgovor:** Pri $A:V\to V$ je injektivnost ekvivalentna surjektivnosti.

---

# 6. Linearni funkcionali in izomorfizmi

Ta sklop se pojavlja v 7. in 8. vajah.

## Linearni funkcional

Linearni funkcional je linearna preslikava

$$
f:V\to F.
$$

Če je

$$
f:\mathbb R^n\to\mathbb R,
$$

ima v standardnih koordinatah obliko

$$
f(x_1,\dots,x_n)
=
a_1x_1+\cdots+a_nx_n.
$$

Če je $f\neq0$, potem je

$$
\dim\ker f=n-1.
$$

---

## Tip naloge: določi funkcional iz njegovega jedra

**Primer po vzoru 7. vaj**

Naj bo

$$
\ker f
=
L\{(1,-1,0),(0,1,-1)\}.
$$

Poišči neničelni linearni funkcional $f:\mathbb R^3\to\mathbb R$.

Naj bo

$$
f(x,y,z)=ax+by+cz.
$$

Ker generatorja ležita v jedru:

$$
a-b=0,
$$

$$
b-c=0.
$$

Torej

$$
a=b=c.
$$

Zato je vsak ustrezen neničelni funkcional oblike

$$
f(x,y,z)=\lambda(x+y+z),
\qquad
\lambda\neq0.
$$

Če je zahtevana ena konkretna izbira:

$$
f(x,y,z)=x+y+z.
$$

---

## Izomorfizem

Vektorska prostora $V$ in $W$ sta izomorfna, če obstaja bijektivna linearna preslikava

$$
A:V\to W.
$$

Za končnorazsežna prostora nad istim poljem velja:

$$
V\cong W
\iff
\dim V=\dim W.
$$

---

### Ustno vprašanje

**Vprašanje:** Kdaj sta dva končnorazsežna vektorska prostora izomorfna?

**Kratek odgovor:** Če sta nad istim poljem, sta izomorfna natanko tedaj, ko imata enako dimenzijo.

**Profesor lahko dodatno vpraša:** Zakaj je $\mathbb R^3$ izomorfen $R_2[x]$?

**Odgovor:** Oba prostora imata dimenzijo $3$. Eksplicitni izomorfizem je na primer

$$
(a,b,c)\mapsto a+bx+cx^2.
$$

---

# 7. Koordinate vektorja v urejeni bazi

Vaje 8–10 dajejo temu sklopu velik poudarek. To je eden ključnih izpitnih tipov.

## Definicija

Naj bo

$$
\mathcal B=(b_1,\dots,b_n)
$$

urejena baza prostora $V$.

Če je

$$
v=\alpha_1b_1+\cdots+\alpha_nb_n,
$$

je koordinatni stolpec vektorja $v$ glede na $\mathcal B$

$$
[v]_{\mathcal B}
=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

Koordinatni stolpec je odvisen od **vrstnega reda baze**.

---

## Tip naloge: poišči koordinatni stolpec

**Kako jo prepoznam**

Podana je baza $\mathcal B$ in vektor $v$.

**Postopek**

Rešim sistem

$$
\alpha_1b_1+\cdots+\alpha_nb_n=v.
$$

Če v standardnih koordinatah sestavim matriko

$$
S_{\mathcal B}
=
\begin{pmatrix}
|&&|\\
b_1&\cdots&b_n\\
|&&|
\end{pmatrix},
$$

potem

$$
S_{\mathcal B}[v]_{\mathcal B}=[v]_{\text{std}}.
$$

Torej

$$
[v]_{\mathcal B}
=
S_{\mathcal B}^{-1}[v]_{\text{std}}.
$$

**Primer**

Naj bo

$$
\mathcal B=
\{(1,1,0),(0,1,1),(1,0,1)\}
$$

in

$$
v=(2,3,1).
$$

Rešujemo

$$
\alpha(1,1,0)+
\beta(0,1,1)+
\gamma(1,0,1)
=
(2,3,1).
$$

Sistem je

$$
\alpha+\gamma=2,
$$

$$
\alpha+\beta=3,
$$

$$
\beta+\gamma=1.
$$

Dobimo

$$
\alpha=2,\qquad
\beta=1,\qquad
\gamma=0.
$$

Zato

$$
[v]_{\mathcal B}
=
\begin{pmatrix}
2\\1\\0
\end{pmatrix}.
$$

**Pogoste napake**

- koordinatni stolpec zamenjam s samim vektorjem;
- ne upoštevam vrstnega reda baznih vektorjev;
- pri polinomih mešam koeficiente polinoma in koordinate v nenaravni bazi.

---

## Primer neposredno po vzoru 8. vaj

Če je v $R_3[x]$ baza

$$
\mathcal B=
\{1,\ 1+x,\ 1+x+x^2,\ x+x^3\}
$$

in velja

$$
[f]_{\mathcal B}
=
\begin{pmatrix}
1\\-1\\0\\1
\end{pmatrix},
$$

potem

$$
f
=
1-(1+x)+(x+x^3)
=
x^3.
$$

V bazi

$$
\mathcal C=\{1,x,2x^2,3x^3\}
$$

zato velja

$$
[f]_{\mathcal C}
=
\begin{pmatrix}
0\\0\\0\\\frac13
\end{pmatrix}.
$$

---

### Ustno vprašanje

**Vprašanje:** Kaj je koordinatni stolpec vektorja glede na urejeno bazo?

**Kratek odgovor:** Če je

$$
v=\alpha_1b_1+\cdots+\alpha_nb_n,
$$

potem je

$$
[v]_{\mathcal B}
=
(\alpha_1,\dots,\alpha_n)^T.
$$

**Profesor lahko dodatno vpraša:** Zakaj je zapis enoličen?

**Odgovor:** Ker je baza linearno neodvisna.

---

# 8. Prehodne matrike in sprememba baze

## Osnovna matrika baze

Če so bazni vektorji zapisani v standardnih koordinatah, definiramo

$$
S_{\mathcal B}
=
\begin{pmatrix}
|&&|\\
b_1&\cdots&b_n\\
|&&|
\end{pmatrix}.
$$

Tedaj

$$
[v]_{\text{std}}
=
S_{\mathcal B}[v]_{\mathcal B}.
$$

In

$$
[v]_{\mathcal B}
=
S_{\mathcal B}^{-1}[v]_{\text{std}}.
$$

Za dve bazi $\mathcal B$ in $\mathcal C$:

$$
[v]_{\mathcal C}
=
S_{\mathcal C}^{-1}S_{\mathcal B}[v]_{\mathcal B}.
$$

Zato je prehodna matrika iz koordinat v bazi $\mathcal B$ v koordinate v bazi $\mathcal C$:

$$
P_{\mathcal C\leftarrow\mathcal B}
=
S_{\mathcal C}^{-1}S_{\mathcal B}.
$$

---

## Tip naloge: izračunaj prehodno matriko

**Primer po vzoru 9. vaj**

Naj bo standardna baza $\mathcal E$ prostora $\mathbb R^2$ in

$$
\Delta=
\{(1,-1),(2,-1)\}.
$$

Matrika baze $\Delta$ je

$$
S_\Delta
=
\begin{pmatrix}
1&2\\
-1&-1
\end{pmatrix}.
$$

Ta matrika pretvarja $\Delta$-koordinate v standardne:

$$
[v]_{\mathcal E}
=
S_\Delta[v]_\Delta.
$$

Ker

$$
S_\Delta^{-1}
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix},
$$

velja

$$
[v]_\Delta
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}
[v]_{\mathcal E}.
$$

Za

$$
v=(3,-2)
$$

dobimo

$$
[v]_\Delta
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}
\begin{pmatrix}
3\\-2
\end{pmatrix}
=
\begin{pmatrix}
1\\1
\end{pmatrix}.
$$

Preverba:

$$
(1,-1)+(2,-1)=(3,-2).
$$

**Pogoste napake**

- zamenjam smer prehoda;
- uporabim $S_{\mathcal B}$ namesto $S_{\mathcal B}^{-1}$;
- ne napišem, ali matrika pretvarja $\mathcal B$-koordinate v standardne ali obratno.

**Izpitno pravilo**

Vedno najprej napišem eno kontrolno enačbo:

$$
[v]_{\text{std}}
=
S_{\mathcal B}[v]_{\mathcal B}.
$$

S tem preprečim večino napak s smerjo.

---

### Ustno vprašanje

**Vprašanje:** Kako se spremenijo koordinate vektorja pri spremembi baze?

**Kratek odgovor:** Če sta $\mathcal B$ in $\mathcal C$ bazi in sta $S_{\mathcal B}$ ter $S_{\mathcal C}$ matriki baznih vektorjev v standardnih koordinatah, potem

$$
[v]_{\mathcal C}
=
S_{\mathcal C}^{-1}S_{\mathcal B}[v]_{\mathcal B}.
$$

**Profesor lahko dodatno vpraša:** Zakaj je prehodna matrika obrnljiva?

**Odgovor:** Ker preslika en koordinatni sistem baze v drugega bijektivno; matriki $S_{\mathcal B}$ in $S_{\mathcal C}$ sta obrnljivi.

---

# 9. Matrika linearne preslikave glede na izbrani bazi

## Osnovna formula

Naj bo

$$
A:V\to W,
$$

$\mathcal B=(b_1,\dots,b_n)$ baza domene in $\mathcal C=(c_1,\dots,c_m)$ baza kodomene.

Matrika

$$
[A]_{\mathcal C\leftarrow\mathcal B}
$$

je določena z enačbo

$$
[A(v)]_{\mathcal C}
=
[A]_{\mathcal C\leftarrow\mathcal B}[v]_{\mathcal B}.
$$

Njeni stolpci so

$$
[A(b_1)]_{\mathcal C},
\dots,
[A(b_n)]_{\mathcal C}.
$$

Če je $M$ matrika $A$ v standardnih bazah, potem

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
S_{\mathcal C}^{-1}MS_{\mathcal B}.
$$

---

## Tip naloge: zamenjaj obe bazi

**Kako jo prepoznam**

Podana je matrika $M$ v standardnih bazah in novi bazi domene ter kodomene.

**Postopek**

1. Sestavim $S_{\mathcal B}$.
2. Sestavim $S_{\mathcal C}$.
3. Uporabim

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
S_{\mathcal C}^{-1}MS_{\mathcal B}.
$$

**Primer po vzoru 10. vaj**

Naj bo

$$
M=
\begin{pmatrix}
1&0&1\\
0&1&1\\
1&1&2
\end{pmatrix},
$$

$$
\mathcal B=
\{(1,1,0),(0,1,1),(1,0,0)\}
$$

in

$$
\mathcal C=
\{(1,0,1),(0,1,1),(0,0,1)\}.
$$

Potem

$$
S_{\mathcal B}
=
\begin{pmatrix}
1&0&1\\
1&1&0\\
0&1&0
\end{pmatrix},
$$

$$
S_{\mathcal C}
=
\begin{pmatrix}
1&0&0\\
0&1&0\\
1&1&1
\end{pmatrix}.
$$

Računamo

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
S_{\mathcal C}^{-1}MS_{\mathcal B}.
$$

Dobimo

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
\begin{pmatrix}
1&1&1\\
1&2&0\\
0&0&0
\end{pmatrix}.
$$

**Kontrola**

Rang se pri menjavi baz ne spremeni:

$$
\operatorname{rang}
[A]_{\mathcal C\leftarrow\mathcal B}
=
\operatorname{rang}M
=
2.
$$

---

## Kompozicija linearnih preslikav

Če

$$
A:U\to V,
\qquad
B:V\to W,
$$

potem

$$
[B\circ A]=[B][A],
$$

če so vmesne baze usklajene.

**Pomemben vrstni red**

Najprej deluje $A$, nato $B$, zato je produkt

$$
[B][A],
$$

ne obratno.

---

## Endomorfizem in podobnost matrik

Če je

$$
A:V\to V
$$

endomorfizem in $M_{\mathcal B}$ ter $M_{\mathcal C}$ njegovi matriki v dveh bazah, potem obstaja obrnljiva matrika $P$, da

$$
M_{\mathcal C}
=
P^{-1}M_{\mathcal B}P.
$$

Takšni matriki sta **podobni**.

Podobni matriki imata isti:

- karakteristični polinom,
- determinant,
- sled,
- lastne vrednosti.

---

### Ustno vprašanje

**Vprašanje:** Kako sestavimo matriko linearne preslikave glede na izbrani bazi?

**Kratek odgovor:** Stolpci matrike so koordinatni stolpci slik baznih vektorjev domene glede na bazo kodomene.

**Profesor lahko dodatno vpraša:** Kaj je formula za menjavo baze?

**Odgovor:** Če je $M$ matrika v standardnih bazah, potem

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
S_{\mathcal C}^{-1}MS_{\mathcal B}.
$$

---

### Ustno vprašanje

**Vprašanje:** Kaj pomeni, da sta matriki podobni?

**Kratek odgovor:** Matrika $B$ je podobna matriki $A$, če obstaja obrnljiva matrika $P$, da

$$
B=P^{-1}AP.
$$

**Profesor lahko dodatno vpraša:** Kaj podobnost pomeni konceptualno?

**Odgovor:** Matriki predstavljata isti endomorfizem glede na dve različni bazi.

---

# 10. Invariantni podprostori

Ta tip je izrecno poudarjen v 11. vajah.

## Definicija

Podprostor

$$
U\leq V
$$

je **invarianten** za endomorfizem

$$
A:V\to V
$$

če

$$
A(U)\subseteq U.
$$

Če je

$$
U=L\{u_1,\dots,u_k\},
$$

je dovolj preveriti

$$
A(u_i)\in U
$$

za vsak bazni vektor $u_i$.

Za enorazsežen prostor

$$
U=L\{u\}
$$

je invariantnost ekvivalentna pogoju

$$
A(u)=\lambda u
$$

za neki skalar $\lambda$.

Torej je vsak enorazsežen invarianten podprostor generiran z lastnim vektorjem.

---

## Tip naloge: preveri invariantnost

**Primer iz 11. vaj**

Naj bo

$$
U=L\{(1,0,1)\}\leq\mathbb R^3.
$$

Preverimo preslikavo

$$
A(x,y,z)=(-z,y,-x).
$$

Za generator velja

$$
A(1,0,1)=(-1,0,-1)=-1(1,0,1).
$$

Zato

$$
A(U)\subseteq U
$$

in $U$ je invarianten.

**Pogoste napake**

- preverjam samo en naključen vektor iz večrazsežnega podprostora;
- zamenjam pogoj $A(U)\subseteq U$ z $A(U)=U$;
- za enorazsežen podprostor ne opazim povezave z lastnim vektorjem.

---

### Ustno vprašanje

**Vprašanje:** Kaj je invarianten podprostor?

**Kratek odgovor:** Podprostor $U\leq V$ je invarianten za endomorfizem $A$, če

$$
A(U)\subseteq U.
$$

**Profesor lahko dodatno vpraša:** Kakšna je povezava med enorazsežnimi invariantnimi podprostori in lastnimi vektorji?

**Odgovor:** Če je $U=L\{v\}$ in $v\neq0$, je $U$ invarianten natanko tedaj, ko je $v$ lastni vektor.

---

# 11. Projektorji in nilpotentne preslikave

## Projektor

Endomorfizem $P$ je projektor, če

$$
P^2=P.
$$

### Značilne lastnosti

Za projektor velja:

$$
V=\operatorname{Im}P\oplus\ker P.
$$

Lastne vrednosti projektorja so lahko samo

$$
0,\qquad1.
$$

---

## Tip naloge: preveri projektor

**Primer po vzoru 11. vaj**

Naj bo

$$
P(x,y)=(x-y,0).
$$

Potem

$$
P^2(x,y)
=
P(x-y,0)
=
(x-y,0)
=
P(x,y).
$$

Torej je $P$ projektor.

---

## Nilpotentnost

Endomorfizem $N$ je nilpotenten, če obstaja $k\geq1$, da

$$
N^k=0.
$$

Najmanjši tak $k$ je **indeks nilpotentnosti**.

Nilpotentna preslikava ima samo lastno vrednost

$$
0.
$$

---

## Tip naloge: določi indeks nilpotentnosti

**Primer iz 11. vaj**

$$
N(x,y,z)=(0,x,y).
$$

Potem

$$
N^2(x,y,z)=(0,0,x),
$$

in

$$
N^3(x,y,z)=(0,0,0).
$$

Ker

$$
N^2\neq0
$$

in

$$
N^3=0,
$$

je indeks nilpotentnosti enak

$$
3.
$$

---

### Ustno vprašanje

**Vprašanje:** Kaj je projektor?

**Kratek odgovor:** Endomorfizem $P$ je projektor, če

$$
P^2=P.
$$

**Profesor lahko dodatno vpraša:** Katere so njegove možne lastne vrednosti?

**Odgovor:** Če je $Pv=\lambda v$, potem

$$
P^2v=\lambda^2v
$$

in zaradi $P^2=P$ velja

$$
\lambda^2=\lambda.
$$

Zato

$$
\lambda\in\{0,1\}.
$$

---

### Ustno vprašanje

**Vprašanje:** Kaj pomeni, da je endomorfizem nilpotenten?

**Kratek odgovor:** Obstaja $k\geq1$, da

$$
A^k=0.
$$

**Profesor lahko dodatno vpraša:** Katere lastne vrednosti ima nilpotenten endomorfizem?

**Odgovor:** Samo $0$.

---

# 12. Karakteristični polinom

Karakteristični polinom je neposredna priprava na lastne vrednosti in diagonalizacijo.

## Definicija

Za $A\in F^{n\times n}$ definiramo

$$
p_A(\lambda)
=
\det(\lambda I-A).
$$

Nekateri zapiski uporabljajo

$$
\det(A-\lambda I).
$$

Ničle so iste, polinoma pa se lahko razlikujeta za faktor $(-1)^n$. Na izpitu moram biti dosleden s konvencijo predmeta.

## Lastnosti

- stopnja $p_A$ je $n$;
- lastne vrednosti so ničle $p_A$;
- podobni matriki imata isti karakteristični polinom;
- za trikotno matriko so lastne vrednosti diagonalni elementi.

---

## Tip naloge: iz preslikave sestavi matriko in izračunaj karakteristični polinom

**Primer iz 11. vaj**

Naj bo

$$
A:R_2[x]\to R_2[x],
\qquad
A(f)=f(0)+f.
$$

Zapišimo

$$
f=a+bx+cx^2.
$$

Tedaj

$$
A(f)=a+(a+bx+cx^2)=2a+bx+cx^2.
$$

Glede na bazo

$$
\{1,x,x^2\}
$$

je matrika

$$
[A]
=
\begin{pmatrix}
2&0&0\\
0&1&0\\
0&0&1
\end{pmatrix}.
$$

Zato

$$
p_A(\lambda)
=
\det
\begin{pmatrix}
\lambda-2&0&0\\
0&\lambda-1&0\\
0&0&\lambda-1
\end{pmatrix}
$$

in

$$
p_A(\lambda)
=
(\lambda-2)(\lambda-1)^2.
$$

---

### Ustno vprašanje

**Vprašanje:** Kaj je karakteristični polinom?

**Kratek odgovor:** Za kvadratno matriko $A$ je

$$
p_A(\lambda)=\det(\lambda I-A).
$$

**Profesor lahko dodatno vpraša:** Zakaj je $\lambda$ lastna vrednost natanko tedaj, ko je $p_A(\lambda)=0$?

**Odgovor:** Enačba

$$
Av=\lambda v
$$

za neničelni $v$ je ekvivalentna

$$
(\lambda I-A)v=0.
$$

Neničelna rešitev obstaja natanko tedaj, ko je $\lambda I-A$ singularna, torej ko

$$
\det(\lambda I-A)=0.
$$

---

# 13. Lastne vrednosti in lastni podprostori

To je osrednja tema 12. vaj.

## Definicije

Skalar $\lambda$ je **lastna vrednost** endomorfizma $A$, če obstaja $v\neq0$, da

$$
Av=\lambda v.
$$

Tak $v$ je **lastni vektor**.

Lastni podprostor za $\lambda$ je

$$
E_\lambda
=
\ker(A-\lambda I).
$$

### Algebraična večkratnost

Algebraična večkratnost $\lambda$ je njena večkratnost kot ničle karakterističnega polinoma.

### Geometrijska večkratnost

$$
g_\lambda
=
\dim E_\lambda.
$$

Vedno velja

$$
1\leq g_\lambda\leq a_\lambda.
$$

---

## Tip naloge: poišči lastne vrednosti in lastne podprostore

**Kako jo prepoznam**

Podana je kvadratna matrika $A$ in zahtevane so:

- lastne vrednosti,
- lastni vektorji,
- lastni podprostori.

**Postopek**

1. Izračunam

$$
p_A(\lambda)=\det(\lambda I-A).
$$

2. Rešim

$$
p_A(\lambda)=0.
$$

3. Za vsak $\lambda$ rešim

$$
(A-\lambda I)x=0.
$$

4. Zapišem bazo $E_\lambda$.

---

## Primer po vzoru 12. vaj

Naj bo

$$
A=
\begin{pmatrix}
2&0&-1\\
6&8&-5\\
9&9&-7
\end{pmatrix}.
$$

Karakteristični polinom se razcepi kot

$$
p_A(\lambda)
=
(\lambda-2)^2(\lambda+1).
$$

Zato sta lastni vrednosti

$$
\lambda_1=2,
\qquad
\lambda_2=-1.
$$

Za vsako posebej rešim

$$
(A-\lambda I)x=0.
$$

Pri zapisu končnega rezultata moram podati bazo vsakega lastnega podprostora, ne samo lastnih vrednosti.

---

## Pomembne lastnosti

Če so

$$
\lambda_1,\dots,\lambda_k
$$

paroma različne lastne vrednosti, so pripadajoči lastni vektorji

$$
v_1,\dots,v_k
$$

linearno neodvisni.

Posledica:

Če ima matrika $A\in F^{n\times n}$ $n$ različnih lastnih vrednosti v $F$, je diagonalizabilna.

Obrat ne velja: diagonalizabilna matrika ima lahko ponovljene lastne vrednosti.

---

### Ustno vprašanje

**Vprašanje:** Kaj je lastni podprostor za lastno vrednost $\lambda$?

**Kratek odgovor:**

$$
E_\lambda=\ker(A-\lambda I).
$$

**Profesor lahko dodatno vpraša:** Ali ničelni vektor šteje kot lastni vektor?

**Odgovor:** Ne. Lastni podprostor vsebuje ničelni vektor, vendar je lastni vektor po definiciji neničeln.

---

### Ustno vprašanje

**Vprašanje:** Kakšna je povezava med algebraično in geometrijsko večkratnostjo?

**Kratek odgovor:** Za vsako lastno vrednost velja

$$
1\leq g_\lambda\leq a_\lambda.
$$

Pri diagonalizabilni matriki velja

$$
g_\lambda=a_\lambda
$$

za vsako lastno vrednost.

---

# 14. Diagonalizacija

Diagonalizacija združi skoraj vse prejšnje teme: baze, matrike, lastne vrednosti, lastne podprostore in podobnost.

## Definicija

Matrika $A$ je diagonalizabilna nad poljem $F$, če obstajata diagonalna matrika $D$ in obrnljiva matrika $P$, da

$$
A=PDP^{-1}.
$$

Ekvivalentno:

$$
D=P^{-1}AP.
$$

Stolpci $P$ so lastni vektorji, razporejeni v istem vrstnem redu kot pripadajoče lastne vrednosti na diagonali $D$.

## Ključni kriterij

$A\in F^{n\times n}$ je diagonalizabilna natanko tedaj, ko ima $n$ linearno neodvisnih lastnih vektorjev.

Ekvivalentno:

$$
\sum_\lambda \dim E_\lambda=n.
$$

---

## Tip naloge: popolna diagonalizacija

**Kako jo prepoznam**

Naloga zahteva:

- lastne vrednosti,
- lastne podprostore,
- matriki $P$ in $D$,
- preverbo

$$
A=PDP^{-1}.
$$

**Postopek**

1. Izračunam $p_A$.
2. Določim lastne vrednosti in algebraične večkratnosti.
3. Za vsak $\lambda$ izračunam $E_\lambda$.
4. Seštejem dimenzije lastnih podprostorov.
5. Če je vsota $n$, izberem bazo iz lastnih vektorjev.
6. Stolpce postavim v $P$.
7. V isti vrstni red v $D$ vpišem lastne vrednosti.

---

## Reprezentativni primer iz 12. vaj

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

Karakteristični polinom je

$$
p_A(\lambda)
=
\lambda^2(\lambda-2)(\lambda+1).
$$

Lastne vrednosti so

$$
2,\quad -1,\quad 0.
$$

Za $\lambda=2$ dobimo lastni vektor, na primer

$$
v_2=
\begin{pmatrix}
3\\1\\1\\2
\end{pmatrix}.
$$

Za $\lambda=-1$ lahko vzamemo

$$
v_{-1}
=
\begin{pmatrix}
0\\-1\\2\\1
\end{pmatrix}.
$$

Za $\lambda=0$ dobimo dvorazsežen lastni podprostor, na primer

$$
E_0
=
L\left\{
\begin{pmatrix}
1\\-1\\1\\0
\end{pmatrix},
\begin{pmatrix}
-1\\0\\0\\1
\end{pmatrix}
\right\}.
$$

Skupaj imamo štiri linearno neodvisne lastne vektorje, zato je $A$ diagonalizabilna.

Izberimo

$$
P=
\begin{pmatrix}
3&0&1&-1\\
1&-1&-1&0\\
1&2&1&0\\
2&1&0&1
\end{pmatrix}.
$$

Ker je

$$
\det P=6\neq0,
$$

je $P$ obrnljiva.

Ustrezna diagonalna matrika je

$$
D=
\begin{pmatrix}
2&0&0&0\\
0&-1&0&0\\
0&0&0&0\\
0&0&0&0
\end{pmatrix}.
$$

Tedaj

$$
A=PDP^{-1}.
$$

**Pogoste napake**

- v $P$ postavim lastne vektorje v drugem vrstnem redu kot lastne vrednosti v $D$;
- za ponovljeno lastno vrednost najdem samo en lastni vektor in avtomatično sklepam diagonalizabilnost;
- algebraično večkratnost zamenjam z dimenzijo lastnega podprostora;
- če karakteristični polinom nad danim poljem ne razpade, vseeno trdim, da je matrika diagonalizabilna nad tem poljem.

---

### Ustno vprašanje

**Vprašanje:** Kdaj je matrika diagonalizabilna?

**Kratek odgovor:** Natanko tedaj, ko obstaja baza prostora, sestavljena iz lastnih vektorjev, oziroma ko ima $n$ linearno neodvisnih lastnih vektorjev.

**Profesor lahko dodatno vpraša:** Zakaj so stolpci matrike $P$ lastni vektorji?

**Odgovor:** Iz

$$
AP=PD
$$

sledi po stolpcih

$$
Av_i=\lambda_i v_i.
$$

---

### Ustno vprašanje

**Vprašanje:** Ali matrika z večkratno lastno vrednostjo nujno ni diagonalizabilna?

**Kratek odgovor:** Ne. Pomembna je dimenzija lastnega podprostora. Za vsako lastno vrednost mora biti geometrijska večkratnost enaka algebraični.

**Profesor lahko dodatno vpraša:** Daj primer diagonalizabilne matrike z večkratno lastno vrednostjo.

**Odgovor:** Identiteta $I_n$ ima eno lastno vrednost $1$ algebraične večkratnosti $n$, lastni podprostor pa je celoten prostor dimenzije $n$.

---

# 15. Kako prepoznam metodo v 20 sekundah

| Oblika naloge | Prva metoda |
|---|---|
| »Ali je $U$ podprostor?« | preveri $0\in U$ in zaprtost za linearne kombinacije |
| »Poišči bazo/dimenzijo« | parametrizacija ali Gaussova eliminacija |
| »Ali so vektorji LN / baza?« | matrika stolpcev, rang/determinanta |
| »Poišči $U\cap W$« | reši $U\alpha=W\beta$ |
| »Poišči $U+W$« | združi generatorje, izloči odvisne |
| »Ali je preslikava linearna?« | najprej $A(0)$, nato definicija |
| »Poišči jedro« | reši $Ax=0$ |
| »Poišči sliko/rang« | stolpci matrike + pivoti |
| »Injektivna?« | $\ker A=\{0\}$ ali rang = dim domene |
| »Surjektivna?« | rang = dim kodomene |
| »Koordinate v bazi« | $S_\mathcal Bc=v$ |
| »Sprememba baze« | $S_\mathcal C^{-1}S_\mathcal B$ |
| »Matrika preslikave v novih bazah« | $S_\mathcal C^{-1}MS_\mathcal B$ |
| »Invarianten podprostor« | preveri slike baznih generatorjev |
| »Projektor« | izračunaj $P^2$ |
| »Nilpotenten« | računaj potence do ničelne |
| »Lastne vrednosti« | $\det(\lambda I-A)=0$ |
| »Lastni vektorji« | $(A-\lambda I)x=0$ |
| »Diagonalizacija« | lastne vrednosti + dimenzije lastnih podprostorov |

---

# 16. Kaj mora biti vidno v izpitni rešitvi

## Pri Gaussovi eliminaciji

Ni treba zapisati vsake elementarne operacije, vendar mora biti jasno:

- katero matriko reduciram,
- kakšna je reducirana oblika,
- kako iz nje preberem rang ali rešitve.

## Pri jedru

Ne napišem samo baze. Napišem vsaj:

$$
Ax=0
$$

in ključni sistem oziroma reducirano matriko.

## Pri sliki

Napišem, iz katerih **originalnih stolpcev** dobim bazo.

## Pri spremembi baze

Napišem smer:

$$
[v]_{\text{std}}=S_\mathcal B[v]_\mathcal B.
$$

## Pri lastnih vrednostih

Napišem:

$$
p_A(\lambda)=\det(\lambda I-A)
$$

in faktorizacijo.

## Pri diagonalizaciji

Napišem:

1. lastne vrednosti,
2. baze lastnih podprostorov,
3. razlog, zakaj je matrika diagonalizabilna,
4. $P$ in $D$ v usklajenem vrstnem redu.

---

# 17. Najpomembnejše povezave med koncepti

## Podprostor in jedro

Vsako jedro linearne preslikave je podprostor:

$$
\ker A\leq V.
$$

Homogeni sistem

$$
Ax=0
$$

zato definira podprostor.

## Slika in stolpci matrike

Če je $A$ matrika preslikave v standardnih bazah, je

$$
\operatorname{Im}A
$$

prostor, generiran s stolpci $A$.

## Rang in dimenzija

$$
\operatorname{rang}A
=
\dim(\operatorname{Im}A).
$$

Skupaj z jedrom:

$$
\dim V
=
\dim\ker A+\operatorname{rang}A.
$$

## Lastni podprostor in jedro

$$
E_\lambda
=
\ker(A-\lambda I).
$$

Torej se iskanje lastnih vektorjev reducira na že znano metodo iskanja jedra.

## Invariantni podprostori in lastni vektorji

Če je

$$
U=L\{v\},
$$

je $U$ invarianten natanko tedaj, ko je $v$ lastni vektor.

## Sprememba baze in podobnost

Matriki istega endomorfizma v različnih bazah sta podobni:

$$
B=P^{-1}AP.
$$

Diagonalizacija je zato posebna izbira baze, v kateri je matrika diagonalna.

## Diagonalizacija in lastna baza

$$
A=PDP^{-1}
$$

pomeni, da stolpci $P$ tvorijo bazo iz lastnih vektorjev.

---

# 18. Teoretični mini-paket za ustni izpit

Naslednje definicije moram znati povedati **brez zapiskov in brez računanja**.

## Natančne definicije

- dvomestna notranja operacija,
- grupa,
- kolobar,
- vektorski prostor,
- vektorski podprostor,
- linearna kombinacija,
- linearna ogrinjača,
- linearna neodvisnost,
- baza,
- dimenzija,
- vsota in presek podprostorov,
- direktna vsota,
- linearna preslikava,
- jedro,
- slika,
- rang,
- linearni funkcional,
- izomorfizem,
- urejena baza,
- koordinatni stolpec,
- matrika linearne preslikave,
- podobni matriki,
- invarianten podprostor,
- projektor,
- nilpotentna preslikava,
- karakteristični polinom,
- lastna vrednost,
- lastni vektor,
- lastni podprostor,
- diagonalizabilnost.

## Izreki, ki jih moram znati formulirati

1. **Izrek o rangu in ničelnosti**

$$
\dim V=\dim\ker A+\dim\operatorname{Im}A.
$$

2. **Dimenzijska formula**

$$
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
$$

3. **Kriterij injektivnosti**

$$
A\text{ injektivna}
\iff
\ker A=\{0\}.
$$

4. **Linearna preslikava je določena s slikami baze.**

5. **Lastni vektorji pri različnih lastnih vrednostih so linearno neodvisni.**

6. **Kriterij diagonalizabilnosti**

$$
A\text{ diagonalizabilna}
\iff
V\text{ ima bazo iz lastnih vektorjev}.
$$

7. **Podobni matriki predstavljata isti endomorfizem v različnih bazah.**

---

## Dokazi, ki jih moram znati reproducirati

### Dokaz: $\ker A$ je podprostor

Vzemi

$$
u,v\in\ker A,
\qquad
\alpha,\beta\in F.
$$

Potem

$$
A(\alpha u+\beta v)
=
\alpha A(u)+\beta A(v)=0.
$$

Zato

$$
\alpha u+\beta v\in\ker A.
$$

### Dokaz: $\operatorname{Im}A$ je podprostor

Naj bosta

$$
y_1=A(u),\qquad y_2=A(v).
$$

Tedaj

$$
\alpha y_1+\beta y_2
=
A(\alpha u+\beta v)
\in\operatorname{Im}A.
$$

### Dokaz: injektivnost in trivialno jedro

Če je $A$ injektivna in $A(v)=0=A(0)$, sledi $v=0$.

Obratno, če je $\ker A=\{0\}$ in $A(u)=A(v)$, potem

$$
A(u-v)=0,
$$

zato

$$
u=v.
$$

### Dokaz: različne lastne vrednosti dajejo linearno neodvisne lastne vektorje

Za dva lastna vektorja naj velja

$$
Av_1=\lambda_1v_1,
\qquad
Av_2=\lambda_2v_2,
\qquad
\lambda_1\neq\lambda_2.
$$

Če

$$
\alpha v_1+\beta v_2=0,
$$

uporabimo $A$ in odštejemo $\lambda_1$-krat prvotno enačbo:

$$
\beta(\lambda_2-\lambda_1)v_2=0.
$$

Ker je $v_2\neq0$ in $\lambda_2\neq\lambda_1$, je $\beta=0$, nato tudi $\alpha=0$.

Za več lastnih vektorjev se dokaz nadaljuje z indukcijo.

---

# 19. Izpitna strategija za mešano nalogo

Če dobim dolgo nalogo, ki povezuje več sklopov, uporabljam naslednji vrstni red.

## Primer strukture

Podana je linearna preslikava

$$
A:\mathbb R^3\to\mathbb R^4
$$

z matriko in dodatnimi bazami.

Naloga lahko zahteva:

1. $\ker A$,
2. $\operatorname{Im}A$,
3. rang,
4. koordinate baznih vektorjev,
5. matriko v novih bazah.

**Optimalni vrstni red reševanja:**

1. Gaussova eliminacija matrike.
2. Iz iste redukcije preberem rang in jedro.
3. Iz pivotnih stolpcev originalne matrike preberem bazo slike.
4. Šele nato rešujem koordinatne sisteme.
5. Matriko v novih bazah izračunam z

$$
S_{\mathcal C}^{-1}MS_{\mathcal B}.
$$

Tako istega računanja ne ponavljam večkrat.

---

# 20. Pogoste napake na celotnem pisnem izpitu

- $\dim R_n[x]$ zapišem kot $n$ namesto $n+1$.
- V množici kandidatov za bazo pustim ničelni vektor.
- Iz generatorjev avtomatično sklepam, da so baza.
- Pri sliki uporabim stolpce reducirane matrike.
- Zamenjam domeno in kodomeno pri dimenziji matrike.
- Pri kompoziciji zamenjam vrstni red množenja matrik.
- Pri spremembi baze zamenjam smer prehoda.
- Pri lastnem vektorju dopustim $v=0$.
- Pri ponovljeni lastni vrednosti ne izračunam dimenzije lastnega podprostora.
- Pri diagonalizaciji ne uskladim vrstnega reda stolpcev $P$ in diagonale $D$.
- Za invariantnost zahtevam $A(U)=U$, čeprav je potreben samo $A(U)\subseteq U$.
- Za projektor preverim $P^2=I$ namesto $P^2=P$.
- Pri nilpotentnosti ne preverim, da je prejšnja potenca neničelna, če se sprašuje po indeksu.
- Uporabim determinantni test za nekvadratno matriko.
- Iz velikosti matrike napačno sklepam rang brez dejanskega preverjanja.

---

# 21. Naloge za samostojno reševanje

Pri teh nalogah ne uporabljam zapiskov. Če se zataknem, najprej pogledam samo naslov ustreznega tipa naloge, ne rešenega primera.

## Srednje težke naloge

**Naloga 1.**

Določi, za kateri $t\in\mathbb R$ je množica

$$
U_t=
\{(x,y,z)\in\mathbb R^3;
x-2y+z=t\}
$$

vektorski podprostor. Za ta $t$ poišči bazo in dimenzijo.

---

**Naloga 2.**

V prostoru $R_2[x]$ preveri, ali je množica

$$
\{1+x,\ x+x^2,\ 1+x^2\}
$$

baza.

---

**Naloga 3.**

Naj bo

$$
U=L\{(1,0,1),(0,1,1)\}
$$

in

$$
W=L\{(1,0,0),(0,1,1)\}
$$

v $\mathbb R^3$.

Poišči baze za

$$
U\cap W
$$

in

$$
U+W.
$$

Določi vse relevantne dimenzije.

---

**Naloga 4.**

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
\qquad
A(x,y,z)=(x+y,y+z).
$$

Poišči:

1. $\ker A$,
2. $\operatorname{Im}A$,
3. rang,
4. ali je $A$ injektivna,
5. ali je $A$ surjektivna.

---

**Naloga 5.**

Naj bo

$$
\mathcal B=
\{(1,1,0),(0,1,1),(1,0,1)\}.
$$

Določi

$$
[(2,3,1)]_{\mathcal B}.
$$

---

**Naloga 6.**

Naj bo

$$
\Delta=\{(1,-1),(2,-1)\}
$$

baza $\mathbb R^2$.

1. Poišči matriko, ki pretvarja $\Delta$-koordinate v standardne.
2. Poišči matriko, ki pretvarja standardne koordinate v $\Delta$-koordinate.
3. Določi $[(3,-2)]_\Delta$.

---

**Naloga 7.**

Naj bo

$$
A=
\begin{pmatrix}
2&1\\
0&3
\end{pmatrix}.
$$

Poišči:

1. karakteristični polinom,
2. lastne vrednosti,
3. baze lastnih podprostorov,
4. matriki $P$ in $D$ za diagonalizacijo.

---

**Naloga 8.**

Naj bo

$$
N:\mathbb R^3\to\mathbb R^3,
\qquad
N(x,y,z)=(0,x,y).
$$

Določi indeks nilpotentnosti in vse lastne vrednosti.

---

## Težke / izpitne naloge

**Naloga 9.**

Naj bo linearna preslikava

$$
A:\mathbb R^3\to\mathbb R^3
$$

v standardni bazi podana z matriko

$$
M=
\begin{pmatrix}
1&0&1\\
0&1&1\\
1&1&2
\end{pmatrix}.
$$

Naj bosta

$$
\mathcal B=
\{(1,1,0),(0,1,1),(1,0,0)\}
$$

in

$$
\mathcal C=
\{(1,0,1),(0,1,1),(0,0,1)\}.
$$

Določi:

1. bazo $\ker A$,
2. bazo $\operatorname{Im}A$,
3. rang,
4. matriko $[A]_{\mathcal C\leftarrow\mathcal B}$.

---

**Naloga 10.**

Naj bo

$$
A=
\begin{pmatrix}
2&0&0\\
0&2&1\\
0&0&3
\end{pmatrix}.
$$

Poišči vse lastne vrednosti in lastne podprostore. Preveri diagonalizabilnost in, če je mogoče, poišči $P$ in $D$, da

$$
A=PDP^{-1}.
$$

---

**Naloga 11.**

Naj bo

$$
A=
\begin{pmatrix}
2&1&0\\
0&2&0\\
0&0&3
\end{pmatrix}.
$$

Določi karakteristični polinom, lastne podprostore in odloči, ali je $A$ diagonalizabilna.

---

**Naloga 12.**

Naj bo

$$
A:\mathbb R^3\to\mathbb R^3,
\qquad
A(x,y,z)=(x+y,2y,3z).
$$

Za

$$
U_a=
\{(x,y,z)\in\mathbb R^3;x=ay\}
$$

določi vse $a\in\mathbb R$, za katere je $U_a$ invarianten za $A$.

---

**Naloga 13.**

Naj bo $f:\mathbb R^3\to\mathbb R$ neničelni linearni funkcional, za katerega velja

$$
\ker f=
\{(x,y,z);x+y+z=0\}
$$

in

$$
f(1,0,0)=2.
$$

Določi $f$.

---

**Naloga 14.**

Naj bodo

$$
v_1=(1,0),
\qquad
v_2=(0,1),
\qquad
v_3=(1,1).
$$

Ali obstaja linearna preslikava

$$
A:\mathbb R^2\to\mathbb R^2
$$

za katero velja

$$
A(v_1)=(1,2),
$$

$$
A(v_2)=(2,-1),
$$

$$
A(v_3)=(3,1)?
$$

Če obstaja, jo določi. Če ne, jasno navedi razlog.

---

**Naloga 15.**

Naj bo

$$
U=
L\{1+x,\ x+x^2\}
$$

in

$$
W=
L\{1+x^2,\ x+x^2\}
$$

v $R_2[x]$.

Poišči:

1. bazo $U$,
2. bazo $W$,
3. bazo $U\cap W$,
4. bazo $U+W$,
5. vse štiri dimenzije.

---

**Naloga 16.**

Naj bo

$$
A=
\begin{pmatrix}
0&1&0\\
0&0&1\\
0&0&0
\end{pmatrix}.
$$

1. Dokaži, da je $A$ nilpotentna.
2. Določi indeks nilpotentnosti.
3. Določi karakteristični polinom.
4. Določi lastne vrednosti in lastni podprostor.
5. Odloči, ali je $A$ diagonalizabilna.

---

# 22. Odgovori

**1.**

$$
t=0.
$$

Tedaj

$$
U_0=\{(x,y,z);x-2y+z=0\}.
$$

Ena baza je

$$
\{(2,1,0),(-1,0,1)\},
$$

in

$$
\dim U_0=2.
$$

---

**2.**

Da. Determinanta koordinatne matrike glede na $\{1,x,x^2\}$ je

$$
2\neq0.
$$

Zato je množica baza $R_2[x]$.

---

**3.**

$$
U\cap W=L\{(0,1,1)\},
$$

$$
\dim(U\cap W)=1.
$$

$$
U+W=\mathbb R^3,
$$

na primer baza

$$
\{(1,0,1),(0,1,1),(1,0,0)\}.
$$

$$
\dim U=\dim W=2,
\qquad
\dim(U+W)=3.
$$

---

**4.**

$$
\ker A=L\{(1,-1,1)\}.
$$

$$
\operatorname{Im}A=\mathbb R^2.
$$

$$
\operatorname{rang}A=2.
$$

$A$ ni injektivna in je surjektivna.

---

**5.**

$$
[(2,3,1)]_{\mathcal B}
=
\begin{pmatrix}
2\\1\\0
\end{pmatrix}.
$$

---

**6.**

$$
S_\Delta=
\begin{pmatrix}
1&2\\
-1&-1
\end{pmatrix}.
$$

$$
S_\Delta^{-1}
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}.
$$

$$
[(3,-2)]_\Delta
=
\begin{pmatrix}
1\\1
\end{pmatrix}.
$$

---

**7.**

$$
p_A(\lambda)
=
(\lambda-2)(\lambda-3).
$$

$$
E_2=L\{(1,0)\},
$$

$$
E_3=L\{(1,1)\}.
$$

Ena izbira:

$$
P=
\begin{pmatrix}
1&1\\
0&1
\end{pmatrix},
\qquad
D=
\begin{pmatrix}
2&0\\
0&3
\end{pmatrix}.
$$

---

**8.**

$$
N^2(x,y,z)=(0,0,x),
$$

$$
N^3=0,
$$

zato je indeks nilpotentnosti $3$.

Edina lastna vrednost je

$$
0.
$$

---

**9.**

$$
\ker A=L\{(-1,-1,1)\}.
$$

$$
\operatorname{Im}A
=
L\{(1,0,1),(0,1,1)\}.
$$

$$
\operatorname{rang}A=2.
$$

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
\begin{pmatrix}
1&1&1\\
1&2&0\\
0&0&0
\end{pmatrix}.
$$

---

**10.**

Lastni vrednosti:

$$
2,\qquad3.
$$

$$
E_2=L\{(1,0,0),(0,1,0)\}.
$$

$$
E_3=L\{(0,1,1)\}.
$$

Matrika je diagonalizabilna.

Ena izbira:

$$
P=
\begin{pmatrix}
1&0&0\\
0&1&1\\
0&0&1
\end{pmatrix},
\qquad
D=
\begin{pmatrix}
2&0&0\\
0&2&0\\
0&0&3
\end{pmatrix}.
$$

---

**11.**

$$
p_A(\lambda)
=
(\lambda-2)^2(\lambda-3).
$$

$$
E_2=L\{(1,0,0)\},
$$

$$
E_3=L\{(0,0,1)\}.
$$

Ker je skupna dimenzija lastnih podprostorov

$$
1+1=2<3,
$$

$A$ ni diagonalizabilna.

---

**12.**

$$
a=1.
$$

---

**13.**

$$
f(x,y,z)=2(x+y+z).
$$

---

**14.**

Da, ker

$$
v_3=v_1+v_2
$$

in

$$
(3,1)=(1,2)+(2,-1).
$$

Preslikava je

$$
A(x,y)
=
x(1,2)+y(2,-1)
=
(x+2y,2x-y).
$$

---

**15.**

$$
\dim U=2,
\qquad
\dim W=2.
$$

$$
U\cap W=L\{x+x^2\}.
$$

$$
\dim(U\cap W)=1.
$$

$$
U+W=R_2[x],
$$

na primer baza

$$
\{1+x,\ x+x^2,\ 1+x^2\}.
$$

$$
\dim(U+W)=3.
$$

---

**16.**

$$
A^3=0,
\qquad
A^2\neq0.
$$

Indeks nilpotentnosti je $3$.

$$
p_A(\lambda)=\lambda^3.
$$

Edina lastna vrednost je

$$
0.
$$

$$
E_0=\ker A=L\{(1,0,0)\}.
$$

Matrika ni diagonalizabilna.

---

# 23. Faza je zaključena, ko znam ...

- [ ] v manj kot minuto prepoznati tip linearnoalgebraične naloge;
- [ ] preveriti, ali je množica vektorski podprostor;
- [ ] iz parametrskega ali enačbenega zapisa poiskati bazo in dimenzijo;
- [ ] preveriti linearno neodvisnost, ogrodje in bazo;
- [ ] uporabljati dejstvo $\dim R_n[x]=n+1$;
- [ ] izračunati $U\cap W$ z reševanjem sistema;
- [ ] izračunati $U+W$ iz generatorjev;
- [ ] uporabiti formulo
  $$
  \dim(U+W)=\dim U+\dim W-\dim(U\cap W);
  $$
- [ ] preveriti linearnost preslikave;
- [ ] določiti linearno preslikavo iz slik baznih vektorjev;
- [ ] preveriti skladnost slik linearno odvisnih vhodnih vektorjev;
- [ ] iz matrike izračunati $\ker A$;
- [ ] iz matrike izračunati $\operatorname{Im}A$;
- [ ] pravilno izbrati pivotne stolpce iz originalne matrike;
- [ ] izračunati rang;
- [ ] uporabiti izrek
  $$
  \dim V=\dim\ker A+\dim\operatorname{Im}A;
  $$
- [ ] prepoznati injektivnost iz jedra ali ranga;
- [ ] prepoznati surjektivnost iz ranga;
- [ ] po dimenzijah domene in kodomene takoj izločiti nemogočo injektivnost ali surjektivnost;
- [ ] določiti linearni funkcional iz pogojev na jedru in vrednostih;
- [ ] razložiti, kdaj sta končnorazsežna prostora izomorfna;
- [ ] izračunati koordinatni stolpec v nestandardni urejeni bazi;
- [ ] rekonstruirati vektor iz koordinatnega stolpca;
- [ ] sestaviti matriko baze $S_{\mathcal B}$;
- [ ] brez zamenjave smeri uporabljati
  $$
  [v]_{\mathrm{std}}=S_{\mathcal B}[v]_{\mathcal B};
  $$
- [ ] izračunati prehodno matriko med dvema bazama;
- [ ] izračunati matriko linearne preslikave v novih bazah;
- [ ] uporabiti
  $$
  [A]_{\mathcal C\leftarrow\mathcal B}
  =
  S_{\mathcal C}^{-1}MS_{\mathcal B};
  $$
- [ ] pravilno množiti matrike pri kompoziciji linearnih preslikav;
- [ ] definirati podobnost matrik;
- [ ] razložiti povezavo med podobnostjo in spremembo baze;
- [ ] preveriti invariantnost podprostora;
- [ ] prepoznati enorazsežen invarianten podprostor kot lastno smer;
- [ ] preveriti projektor z enačbo $P^2=P$;
- [ ] določiti indeks nilpotentnosti;
- [ ] izračunati karakteristični polinom;
- [ ] poiskati vse lastne vrednosti;
- [ ] za vsako lastno vrednost izračunati lastni podprostor;
- [ ] razlikovati algebraično in geometrijsko večkratnost;
- [ ] odločiti, ali je matrika diagonalizabilna;
- [ ] konstruirati $P$ in $D$ tako, da
  $$
  A=PDP^{-1};
  $$
- [ ] preveriti, da sta vrstni red stolpcev $P$ in vrstni red lastnih vrednosti v $D$ usklajena;
- [ ] natančno definirati: podprostor, linearno neodvisnost, bazo, dimenzijo, linearno preslikavo, jedro, sliko, rang, koordinatni stolpec, invariantni podprostor, lastno vrednost, lastni vektor in diagonalizabilnost;
- [ ] brez zapiskov povedati izrek o rangu in ničelnosti;
- [ ] brez zapiskov povedati dimenzijsko formulo za vsoto podprostorov;
- [ ] dokazati, da sta $\ker A$ in $\operatorname{Im}A$ podprostora;
- [ ] dokazati kriterij
  $$
  A\text{ injektivna}\iff\ker A=\{0\};
  $$
- [ ] razložiti, zakaj je linearna preslikava določena s slikami baze;
- [ ] povedati in razložiti kriterij diagonalizabilnosti;
- [ ] dokazati, da so lastni vektorji pri različnih lastnih vrednostih linearno neodvisni;
- [ ] na ustnem jasno povezati
  $$
  E_\lambda=\ker(A-\lambda I);
  $$
- [ ] na ustnem razložiti, da je diagonalizacija sprememba v bazo iz lastnih vektorjev;
- [ ] rešiti vsaj 80–90 % zgornjih samostojnih nalog brez zapiskov;
- [ ] rešiti vsaj dve daljši mešani nalogi zapored brez konceptualne napake;
- [ ] zapisati rešitev dovolj kratko za izpit, vendar z vidnimi ključnimi enačbami, pogoji in utemeljitvami.
