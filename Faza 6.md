# FAZA 6 — Invariantni podprostori, projektorji, nilpotentne preslikave in karakteristični polinom

## Namen faze

V tej fazi povežemo znanje o **podprostorih**, **linearnih preslikavah**, **matrikah endomorfizmov** in **spremembah baze** ter pripravimo podlago za lastne vrednosti, lastne vektorje in diagonalizacijo.

Glavne teme so:

1. **invariantni podprostori**,
2. preverjanje invariantnosti podprostora, podanega z ogrodjem, bazo, linearnimi enačbami ali parametrom,
3. povezava enorazsežnih invariantnih podprostorov z lastnimi vektorji,
4. **projektorji**,
5. jedro in zaloga vrednosti projektorja,
6. direktna vsota pri projektorjih,
7. **nilpotentni endomorfizmi**,
8. red oziroma indeks nilpotentnosti,
9. **karakteristični polinom**,
10. računanje karakterističnega polinoma iz matrike, pri trikotnih in bločnih matrikah ter iz predpisa preslikave,
11. povezava karakterističnega polinoma z lastnimi vrednostmi.

V priloženih 11. vajah so te teme obravnavane neposredno in zaporedoma: naloge 59–61 obravnavajo invariantnost, naloga 62 projektor, naloga 63 nilpotentnost in naloga 64 karakteristični polinom. Na 12. vajah se karakteristični polinom nadaljuje z nalogo 65, nato pa se začnejo lastne vrednosti in diagonalizacija.

> V priloženih datotekah ni ločenih preteklih izpitov ali kolokvijev. Prioriteta v tem poglavju zato temelji predvsem na 11. in začetku 12. vaj ter na priporočenih domačih nalogah.

---

## Predznanje

Pred začetkom te faze moraš znati:

- kaj je **vektorski podprostor**,
- določiti bazo in dimenzijo podprostora,
- kaj je **linearna preslikava** in kaj je **endomorfizem**,
- računati matriko linearne preslikave,
- množiti matrike,
- računati determinante,
- določiti jedro in zalogo vrednosti,
- uporabljati linearno kombinacijo in ogrodje,
- razumeti podobnost matrik.

**Endomorfizem** vektorskega prostora $V$ je linearna preslikava

$$
A:V\to V.
$$

---

## 1. Invariantni podprostori

### Definicija

Naj bo $A:V\to V$ endomorfizem in $U\leq V$ podprostor. Podprostor $U$ je **invarianten za $A$**, če velja

$$
A(U)\subseteq U.
$$

To pomeni

$$
u\in U\Longrightarrow A(u)\in U.
$$

Pomembno je, da zahtevamo

$$
\boxed{A(U)\subseteq U}
$$

in ne nujno

$$
A(U)=U.
$$

### Intuitivni pomen

Če začnemo z $u\in U$, potem so tudi

$$
A(u),\ A^2(u),\ A^3(u),\ldots
$$

vsi elementi podprostora $U$.

### Kriterij z generatorji

Če je

$$
U=L\{u_1,\ldots,u_k\},
$$

potem velja

$$
\boxed{U\text{ je invarianten za }A\iff A(u_i)\in U\text{ za vsak }i.}
$$

#### Dokaz

Za poljuben

$$
u=\alpha_1u_1+\cdots+\alpha_ku_k
$$

zaradi linearnosti velja

$$
A(u)=\alpha_1A(u_1)+\cdots+\alpha_kA(u_k).
$$

Če vsak $A(u_i)$ pripada $U$, pripada $U$ tudi njihova linearna kombinacija.

### Enorazsežni invariantni podprostor

Če je

$$
U=L\{u\},\qquad u\neq0,
$$

je $U$ invarianten natanko tedaj, ko obstaja $\lambda$, da

$$
A(u)=\lambda u.
$$

Torej

$$
\boxed{L\{u\}\text{ je invarianten}\iff u\text{ je lastni vektor za }A.}
$$

---

## 2. Kako preverjamo invariantnost

| Podprostor je podan kot | Najboljša metoda |
|---|---|
| $U=L\{u_1,\ldots,u_k\}$ | izračunaj $A(u_i)$ |
| $U=\{x;\text{ linearni pogoji}\}$ | vzemi splošen $u\in U$ in preveri pogoje za $A(u)$ |
| podprostor vsebuje parameter | po preslikavi zahtevaj, da pogoj velja za vse proste spremenljivke |
| $\dim U=1$ | preveri, ali je slika generatorja njegov skalarni večkratnik |
| prostor funkcij/polinomov | preslikaj generatorje in preveri, ali ostanejo v njihovem linearnem ovoju |

---

## 3. Tip naloge: invariantnost podprostora, podanega z enačbami

### Kako jo prepoznam

Podprostor je podan na primer kot

$$
U=\{(x,y,z,w)\in\mathbb R^4;\ x-y=0,\ w=0\}.
$$

### Postopek

1. Zapiši splošen element $u\in U$.
2. Uporabi pogoje, ki definirajo $U$.
3. Izračunaj $A(u)$.
4. Preveri, ali koordinate $A(u)$ ponovno izpolnjujejo iste pogoje.

### Primer iz 11. vaj

Endomorfizmu $A:\mathbb R^4\to\mathbb R^4$ v običajni bazi pripada matrika

$$
A=
\begin{pmatrix}
-1&2&-3&4\\
0&1&-3&4\\
0&0&-2&4\\
0&0&0&2
\end{pmatrix}.
$$

Preverimo invariantnost

$$
U_1=\{(x,y,z,w)\in\mathbb R^4;\ x-y=0,\ w=0\}.
$$

### Rešitev

Naj bo $u\in U_1$. Ker velja $x=y$ in $w=0$, lahko pišemo

$$
u=(t,t,z,0).
$$

Izračunamo

$$
A
\begin{pmatrix}
t\\t\\z\\0
\end{pmatrix}
=
\begin{pmatrix}
-t+2t-3z\\
t-3z\\
-2z\\
0
\end{pmatrix}
=
\begin{pmatrix}
t-3z\\
t-3z\\
-2z\\
0
\end{pmatrix}.
$$

Za dobljeni vektor velja $x'-y'=0$ in $w'=0$, zato

$$
A(u)\in U_1.
$$

Torej

$$
\boxed{A(U_1)\subseteq U_1}
$$

in $U_1$ je invarianten za $A$.

### Pogoste napake

- preverjanje samo enega konkretnega vektorja,
- zahteva $A(u)=u$ namesto $A(u)\in U$,
- preverjanje le dela pogojev, ki definirajo $U$.

---

## 4. Tip naloge: določi parameter za invariantnost

### Kako jo prepoznam

Podprostor je odvisen od parametra, na primer

$$
U_\alpha=\{(x,y,z,w);\ x-\alpha y=0\}.
$$

### Postopek

1. Iz pogoja izrazi eno spremenljivko, na primer $x=\alpha y$.
2. Vzemi splošen element podprostora.
3. Izračunaj njegovo sliko.
4. Za sliko zahtevaj isti pogoj.
5. Enačba mora veljati za **vse** proste spremenljivke.
6. Zato morajo biti vsi njihovi koeficienti enaki $0$.

### Primer iz 11. vaj

Za isto matriko $A$ določimo $\alpha$, da bo

$$
U_2=\{(x,y,z,w)\in\mathbb R^4;\ x-\alpha y=0\}
$$

invarianten.

### Rešitev

Za $u\in U_2$ velja $x=\alpha y$, zato vzamemo

$$
u=(\alpha y,y,z,w).
$$

Slika je

$$
A(u)=
\begin{pmatrix}
(-\alpha+2)y-3z+4w\\
y-3z+4w\\
-2z+4w\\
2w
\end{pmatrix}.
$$

Za invariantnost mora veljati

$$
x'-\alpha y'=0.
$$

Zato

$$
(-\alpha+2)y-3z+4w-\alpha(y-3z+4w)=0.
$$

Poenostavimo:

$$
(2-2\alpha)y+3(\alpha-1)z+4(1-\alpha)w=0.
$$

Oziroma

$$
(1-\alpha)(2y-3z+4w)=0.
$$

Ker mora veljati za vse $y,z,w$, sledi

$$
\boxed{\alpha=1}.
$$

### Primer, kjer parameter ne obstaja

Naj bo

$$
U_3=\{(x,y,z,w);\ x-\beta z=0\}.
$$

Vzamemo $u=(\beta z,y,z,w)$. Po preslikavi zahtevamo

$$
x'-\beta z'=0.
$$

Dobimo

$$
2y+(\beta-3)z+4(1-\beta)w=0.
$$

Koeficient pri $y$ je vedno $2\neq0$, zato

$$
\boxed{\text{tak }\beta\text{ ne obstaja}.}
$$

### Pogoste napake

- pogoj preveriš le za posebno izbiro parametrov,
- pozabiš, da mora enačba veljati za vse elemente podprostora,
- predpostaviš, da parameter nujno obstaja.

---

## 5. Tip naloge: enorazsežni invariantni podprostor

### Kako jo prepoznam

Podprostor ima obliko

$$
U=L\{u\}
$$

ali

$$
U=\{tu;\ t\in\mathbb R\}.
$$

### Postopek

Izračunaj $A(u)$. Če obstaja $\lambda$, da

$$
A(u)=\lambda u,
$$

je $U$ invarianten.

### Primer iz 11. vaj

Naj bo

$$
U=\{(a,0,a);\ a\in\mathbb R\}=L\{(1,0,1)\}.
$$

Za preslikavo

$$
A(x,y,z)=(-z,y,-x)
$$

velja

$$
A(1,0,1)=(-1,0,-1)=-1(1,0,1).
$$

Zato je $U$ invarianten.

### Izpitna bližnjica

$$
\boxed{A(u)\stackrel{?}{=}\lambda u}
$$

---

## 6. Tip naloge: invariantni podprostori funkcij

### Kako jo prepoznam

Vektorski prostor je sestavljen iz funkcij ali polinomov, endomorfizem pa je na primer odvajanje.

### Postopek

Če je

$$
U=L\{f_1,\ldots,f_k\},
$$

preveri

$$
D(f_i)\in U
$$

za vse generatorje.

### Primer

Naj bo

$$
V=L\{\sin x,\cos x,e^x,1\}
$$

in $D(f)=f'$.

Za

$$
U=L\{\sin x,e^x\}
$$

velja

$$
D(\sin x)=\cos x\notin L\{\sin x,e^x\},
$$

zato $U$ ni invarianten.

Po drugi strani je

$$
L\{\sin x,\cos x\}
$$

invarianten, ker

$$
D(\sin x)=\cos x,
$$

$$
D(\cos x)=-\sin x.
$$

---

## 7. Ustni del — invariantni podprostori

### Ustno vprašanje

**Vprašanje:** Kaj je invarianten podprostor?

**Kratek odgovor:** Naj bo $A:V\to V$ endomorfizem. Podprostor $U\leq V$ je invarianten za $A$, če

$$
A(U)\subseteq U.
$$

**Profesor lahko dodatno vpraša:** Ali mora veljati $A(U)=U$?

**Odgovor:** Ne. Za invariantnost zadostuje $A(U)\subseteq U$.

### Ustno vprašanje

**Vprašanje:** Kako preverimo invariantnost, če poznamo bazo podprostora?

**Kratek odgovor:** Če je

$$
U=L\{u_1,\ldots,u_k\},
$$

je dovolj preveriti

$$
A(u_i)\in U
$$

za vse generatorje.

**Profesor lahko dodatno vpraša:** Zakaj?

**Odgovor:** Zaradi linearnosti:

$$
A\left(\sum_i\alpha_i u_i\right)=\sum_i\alpha_iA(u_i).
$$

### Ustno vprašanje

**Vprašanje:** Kakšna je povezava med enorazsežnim invariantnim podprostorom in lastnim vektorjem?

**Kratek odgovor:** Če je $U=L\{u\}$ in $u\neq0$, je $U$ invarianten natanko tedaj, ko obstaja $\lambda$, da

$$
A(u)=\lambda u.
$$

---

## 8. Projektorji

### Definicija

Endomorfizem

$$
P:V\to V
$$

je **projektor**, če

$$
\boxed{P^2=P}.
$$

To pomeni

$$
P(P(v))=P(v)
$$

za vsak $v\in V$.

Lastnost $P^2=P$ imenujemo **idempotentnost**.

### Delovanje na zalogi vrednosti

Če je $u\in\operatorname{Im}P$, obstaja $v$, da je $u=P(v)$. Zato

$$
P(u)=P(P(v))=P^2(v)=P(v)=u.
$$

Torej

$$
\boxed{P|_{\operatorname{Im}P}=id.}
$$

### Delovanje na jedru

Če je $u\in\ker P$, potem

$$
P(u)=0.
$$

### Temeljni izrek o projektorjih

Za projektor $P:V\to V$ velja

$$
\boxed{V=\operatorname{Im}P\oplus\ker P.}
$$

### Dokaz

Za poljuben $v\in V$ zapišemo

$$
v=P(v)+(v-P(v)).
$$

Prvi člen pripada $\operatorname{Im}P$. Za drugega:

$$
P(v-P(v))=P(v)-P^2(v)=0,
$$

zato

$$
v-P(v)\in\ker P.
$$

Torej

$$
V=\operatorname{Im}P+\ker P.
$$

Če je $u\in\operatorname{Im}P\cap\ker P$, potem hkrati velja

$$
P(u)=u
$$

in

$$
P(u)=0,
$$

zato $u=0$. Torej je vsota direktna.

### Posledica

Če je $\dim V=n$, potem

$$
\boxed{\dim(\operatorname{Im}P)+\dim(\ker P)=n.}
$$

### Pomembna opomba

Projektor ni nujno ortogonalna projekcija. Algebraični pogoj je samo

$$
P^2=P.
$$

---

## 9. Tip naloge: preveri, ali je endomorfizem projektor

### Kako jo prepoznam

Podan je predpis ali matrika endomorfizma in vprašanje, ali je projektor.

### Postopek

Izračunaj

$$
P^2=P\circ P.
$$

Če velja

$$
P^2=P,
$$

je projektor.

### Primer iz 11. vaj

Naj bo

$$
P(x,y)=(x-y,0).
$$

Potem

$$
P^2(x,y)=P(x-y,0)=(x-y,0)=P(x,y).
$$

Zato

$$
\boxed{P^2=P}
$$

in $P$ je projektor.

### Pogoste napake

- preverjanje $P^2=I$ namesto $P^2=P$,
- domneva, da mora biti projektor ortogonalen,
- kvadriranje koordinat namesto računanja kompozicije.

---

## 10. Ustni del — projektorji

### Ustno vprašanje

**Vprašanje:** Kaj je projektor?

**Kratek odgovor:** Projektor je endomorfizem $P:V\to V$, za katerega velja

$$
P^2=P.
$$

### Ustno vprašanje

**Vprašanje:** Kako projektor deluje na svoji zalogi vrednosti?

**Kratek odgovor:** Kot identiteta.

**Profesor lahko dodatno vpraša:** Dokaži.

**Odgovor:** Če je $u=P(v)$, potem

$$
P(u)=P(P(v))=P^2(v)=P(v)=u.
$$

### Ustno vprašanje

**Vprašanje:** Kakšna je povezava med jedrom in zalogo vrednosti projektorja?

**Kratek odgovor:**

$$
\boxed{V=\operatorname{Im}P\oplus\ker P.}
$$

### Ustno vprašanje

**Vprašanje:** Kakšna je matrika projektorja v bazi, prilagojeni $\operatorname{Im}P$ in $\ker P$?

**Kratek odgovor:**

$$
\begin{pmatrix}
I_r&0\\
0&0
\end{pmatrix}.
$$

---

## 11. Nilpotentne preslikave

### Definicija

Endomorfizem

$$
N:V\to V
$$

je **nilpotenten**, če obstaja $k\geq1$, da

$$
\boxed{N^k=0}.
$$

To pomeni, da za vsak $v\in V$ velja

$$
N^k(v)=0.
$$

### Red oziroma indeks nilpotentnosti

Najmanjši $k\geq1$, za katerega velja

$$
N^k=0,
$$

imenujemo **red** oziroma **indeks nilpotentnosti**.

Torej mora veljati

$$
N^k=0,
$$

in

$$
N^{k-1}\neq0.
$$

---

## 12. Tip naloge: določi nilpotentnost in njen red

### Kako jo prepoznam

Podan je predpis, ki postopoma premika oziroma briše koordinate, na primer

$$
N(x,y,z)=(0,x,y).
$$

### Postopek

Računaj zaporedoma

$$
N,\ N^2,\ N^3,\ldots
$$

dokler ne dobiš ničelne preslikave. Nato preveri, da prejšnja potenca še ni ničelna.

### Primer iz 11. vaj

Naj bo

$$
A:\mathbb C^3\to\mathbb C^3,
$$

$$
A(x,y,z)=(0,x,y).
$$

Potem

$$
A^2(x,y,z)=A(0,x,y)=(0,0,x),
$$

in

$$
A^3(x,y,z)=A(0,0,x)=(0,0,0).
$$

Torej

$$
A^3=0.
$$

Toda

$$
A^2(1,0,0)=(0,0,1)\neq0,
$$

zato je

$$
\boxed{\operatorname{ind}(A)=3.}
$$

### Matrični pogled

Matrika je

$$
M_A=
\begin{pmatrix}
0&0&0\\
1&0&0\\
0&1&0
\end{pmatrix},
$$

pri čemer velja

$$
M_A^3=0,
$$

in

$$
M_A^2\neq0.
$$

---

## 13. Lastnosti nilpotentnega endomorfizma

Če je $N^k=0$, potem

$$
\ker N\subseteq\ker N^2\subseteq\cdots\subseteq\ker N^k=V.
$$

Hkrati

$$
V\supseteq\operatorname{Im}N\supseteq\operatorname{Im}N^2\supseteq\cdots\supseteq\operatorname{Im}N^k=\{0\}.
$$

### Povezava z lastnimi vrednostmi

Če je $v\neq0$ lastni vektor nilpotentnega $N$ in

$$
N(v)=\lambda v,
$$

potem

$$
N^k(v)=\lambda^kv.
$$

Ker je $N^k=0$, dobimo

$$
0=\lambda^kv.
$$

Ker je $v\neq0$, mora biti

$$
\boxed{\lambda=0.}
$$

Nilpotentni endomorfizem ima lahko samo lastno vrednost $0$.

---

## 14. Ustni del — nilpotentnost

### Ustno vprašanje

**Vprašanje:** Kaj pomeni, da je endomorfizem nilpotenten?

**Kratek odgovor:** Obstaja $k\geq1$, da

$$
N^k=0.
$$

### Ustno vprašanje

**Vprašanje:** Kaj je red oziroma indeks nilpotentnosti?

**Kratek odgovor:** Najmanjši $k\geq1$, za katerega velja

$$
N^k=0.
$$

Pri tem mora biti

$$
N^{k-1}\neq0.
$$

### Ustno vprašanje

**Vprašanje:** Kakšne so lahko lastne vrednosti nilpotentnega endomorfizma?

**Kratek odgovor:** Samo $0$.

**Profesor lahko dodatno vpraša:** Dokaži.

**Odgovor:** Če $Nv=\lambda v$, potem

$$
0=N^kv=\lambda^kv.
$$

Ker $v\neq0$, je $\lambda=0$.

---

## 15. Karakteristični polinom

### Definicija

Naj bo $A:V\to V$ endomorfizem končnorazsežnega prostora in naj matrika $M$ predstavlja $A$ v neki urejeni bazi.

V teh zapiskih uporabljamo konvencijo

$$
\boxed{p_A(\lambda)=\det(\lambda I-M).}
$$

Če je $\dim V=n$, je $p_A$ moničen polinom stopnje $n$.

### Zelo pomembno glede predznaka

V literaturi lahko srečaš tudi

$$
\det(M-\lambda I).
$$

Za liho dimenzijo se definiciji razlikujeta za predznak. Na izpitu uporabljaj isto konvencijo kot profesor oziroma gradivo.

### Osnovne lastnosti

Če je $M\in F^{n\times n}$, potem

$$
\deg p_A=n.
$$

Konstantni člen je

$$
p_A(0)=\det(-M)=(-1)^n\det M.
$$

Če je matrika zgornje ali spodnje trikotna, potem

$$
\boxed{p_A(\lambda)=\prod_{i=1}^n(\lambda-a_{ii}).}
$$

---

## 16. Karakteristični polinom je neodvisen od baze

Če sta matriki $M$ in $N$ podobni, torej

$$
N=P^{-1}MP,
$$

potem

$$
\lambda I-N=P^{-1}(\lambda I-M)P.
$$

Zato

$$
\begin{aligned}
p_N(\lambda)
&=\det(\lambda I-N)\\
&=\det(P^{-1})\det(\lambda I-M)\det(P)\\
&=\det(\lambda I-M).
\end{aligned}
$$

Torej

$$
\boxed{p_N(\lambda)=p_M(\lambda).}
$$

Karakteristični polinom je lastnost endomorfizma, ne izbire baze.

---

## 17. Tip naloge: karakteristični polinom iz predpisa preslikave

### Kako jo prepoznam

Podan je endomorfizem na prostoru, na primer $\mathbb R_n[x]$, ne pa njegova matrika.

### Postopek

1. Izberi običajno bazo.
2. Izračunaj slike baznih vektorjev.
3. Koordinatne stolpce slik postavi v matriko.
4. Izračunaj
   $$
   p_A(\lambda)=\det(\lambda I-M_A).
   $$

### Primer iz 11. vaj

Naj bo

$$
A:\mathbb R_2[x]\to\mathbb R_2[x],
$$

$$
A(f)=f(0)+f.
$$

Vzamemo bazo

$$
\Sigma=\{1,x,x^2\}.
$$

Velja

$$
A(1)=2,
$$

$$
A(x)=x,
$$

$$
A(x^2)=x^2.
$$

Zato

$$
M_A=
\begin{pmatrix}
2&0&0\\
0&1&0\\
0&0&1
\end{pmatrix}.
$$

Torej

$$
p_A(\lambda)=
\det
\begin{pmatrix}
\lambda-2&0&0\\
0&\lambda-1&0\\
0&0&\lambda-1
\end{pmatrix}
$$

in zato

$$
\boxed{p_A(\lambda)=(\lambda-1)^2(\lambda-2).}
$$

---

## 18. Tip naloge: karakteristični polinom trikotne matrike

### Kako jo prepoznam

Matrika je zgornje ali spodnje trikotna.

### Pomembna formula

$$
\boxed{p_M(\lambda)=(\lambda-a_{11})\cdots(\lambda-a_{nn}).}
$$

### Primer

Za

$$
A=
\begin{pmatrix}
-1&2&-3&4\\
0&1&-3&4\\
0&0&-2&4\\
0&0&0&2
\end{pmatrix}
$$

dobimo neposredno

$$
\boxed{p_A(\lambda)=(\lambda+1)(\lambda-1)(\lambda+2)(\lambda-2).}
$$

---

## 19. Tip naloge: karakteristični polinom matrike s posebno strukturo

### Kako jo prepoznam

Matrika ima bločno obliko, veliko ničel ali ponavljajoče se bloke.

### Primer iz 12. vaj

Naj bo

$$
A=
\begin{pmatrix}
0&I\\
I&0
\end{pmatrix},
$$

kjer je $I$ identična matrika $2\times2$.

Tedaj

$$
A=
\begin{pmatrix}
0&0&1&0\\
0&0&0&1\\
1&0&0&0\\
0&1&0&0
\end{pmatrix}.
$$

Imamo

$$
\lambda I-A=
\begin{pmatrix}
\lambda&0&-1&0\\
0&\lambda&0&-1\\
-1&0&\lambda&0\\
0&-1&0&\lambda
\end{pmatrix}.
$$

Po primerni preureditvi dobimo dva enaka bloka

$$
\begin{pmatrix}
\lambda&-1\\
-1&\lambda
\end{pmatrix}.
$$

Zato

$$
p_A(\lambda)=
\left(
\det
\begin{pmatrix}
\lambda&-1\\
-1&\lambda
\end{pmatrix}
\right)^2
=(\lambda^2-1)^2.
$$

Torej

$$
\boxed{p_A(\lambda)=(\lambda^2-1)^2.}
$$

---

## 20. Kako karakteristični polinom vodi do lastnih vrednosti

Za neničelni $v$ iščemo

$$
A(v)=\lambda v.
$$

To je ekvivalentno

$$
(A-\lambda I)v=0.
$$

Neničelna rešitev obstaja natanko tedaj, ko je $A-\lambda I$ singularna, torej

$$
\det(A-\lambda I)=0.
$$

Pri naši konvenciji je to ekvivalentno

$$
\boxed{p_A(\lambda)=0.}
$$

Ničle karakterističnega polinoma so lastne vrednosti.

---

## 21. Ustni del — karakteristični polinom

### Ustno vprašanje

**Vprašanje:** Kaj je karakteristični polinom endomorfizma?

**Kratek odgovor:** Če matrika $M$ predstavlja endomorfizem $A$ v neki bazi, definiramo

$$
p_A(\lambda)=\det(\lambda I-M).
$$

### Ustno vprašanje

**Vprašanje:** Ali je karakteristični polinom odvisen od izbire baze?

**Kratek odgovor:** Ne. Matriki istega endomorfizma v različnih bazah sta podobni, podobni matriki pa imata isti karakteristični polinom.

**Profesor lahko dodatno vpraša:** Dokaži.

**Odgovor:** Če $N=P^{-1}MP$, potem

$$
\lambda I-N=P^{-1}(\lambda I-M)P,
$$

zato

$$
\det(\lambda I-N)=\det(\lambda I-M).
$$

### Ustno vprašanje

**Vprašanje:** Kakšna je stopnja karakterističnega polinoma?

**Kratek odgovor:** Če je $\dim V=n$, je

$$
\deg p_A=n.
$$

### Ustno vprašanje

**Vprašanje:** Kako najhitreje izračunaš karakteristični polinom trikotne matrike?

**Kratek odgovor:**

$$
p_A(\lambda)=\prod_{i=1}^n(\lambda-a_{ii}).
$$

### Ustno vprašanje

**Vprašanje:** Kakšna je povezava med karakterističnim polinomom in lastnimi vrednostmi?

**Kratek odgovor:** $\lambda$ je lastna vrednost natanko tedaj, ko

$$
p_A(\lambda)=0.
$$

---

## 22. Pomembne povezave med koncepti

### Invariantni podprostor in omejitev endomorfizma

Če je $U$ invarianten za $A$, lahko definiramo

$$
A|_U:U\to U.
$$

### Enorazsežna invariantnost in lastni vektorji

$$
L\{v\}\text{ invarianten}\iff Av=\lambda v.
$$

### Projektor in direktna vsota

$$
V=\operatorname{Im}P\oplus\ker P.
$$

Na $\operatorname{Im}P$ projektor deluje kot identiteta, na $\ker P$ pa kot nič.

### Projektor in invariantni podprostori

Tako $\operatorname{Im}P$ kot $\ker P$ sta invariantna za $P$.

### Nilpotentnost in invariantnost jeder

$$
\ker N\subseteq\ker N^2\subseteq\cdots.
$$

### Nilpotentnost in lastne vrednosti

Nilpotenten endomorfizem ima lahko samo lastno vrednost

$$
\boxed{0}.
$$

### Karakteristični polinom in podobnost

Če je

$$
B=P^{-1}AP,
$$

potem

$$
p_B(\lambda)=p_A(\lambda).
$$

---

## 23. Kaj moram znati iz originalnih vaj

### Obvezno

Iz **11. vaj** ponovno reši:

- **Naloga 59(a)** — dokaz invariantnosti,
- **Naloga 59(b)** — parameter $\alpha$,
- **Naloga 59(c)** — preverjanje obstoja parametra $\beta$,
- **Naloga 59(d)** — odločitev, ali je podprostor invarianten,
- **Naloga 60** — enorazsežni invariantni podprostor,
- **Naloga 61** — invariantnost pri operatorju odvajanja,
- **Naloga 62** — projektor,
- **Naloga 63** — nilpotentnost,
- **Naloga 64** — karakteristični polinom preslikave na polinomskem prostoru.

Iz **12. vaj** v okviru te faze obvezno reši:

- **Nalogo 65** — karakteristični polinom bločne matrike.

Naloge 66–68 so že primarno del naslednje faze: lastne vrednosti, lastni podprostori in diagonalizacija.

---

## 24. Najpogostejše napake celotne faze

### Invariantni podprostori

- zamenjava $A(U)\subseteq U$ z $A(U)=U$,
- preverjanje samo enega naključnega vektorja,
- nepreverjanje vseh enačb podprostora,
- pri parametrih pozabiš, da mora pogoj veljati za vse proste spremenljivke,
- pri enorazsežnem prostoru ne uporabiš pogoja $A(u)=\lambda u$.

### Projektorji

- uporaba $P^2=I$ namesto $P^2=P$,
- predpostavka, da mora biti projektor ortogonalen,
- zamenjava $\ker P$ in $\operatorname{Im}P$.

### Nilpotentnost

- preverjanje $N^k(v)=0$ samo za en vektor,
- nepreverjanje minimalnosti indeksa,
- zamenjava nilpotentnosti z idempotentnostjo.

### Karakteristični polinom

- napačna konvencija predznaka,
- napačen zapis $\lambda I-A$,
- pri preslikavi pozabiš najprej sestaviti matriko,
- slike baznih vektorjev postaviš v vrstice namesto v stolpce,
- pri trikotni matriki po nepotrebnem razvijaš determinanto,
- ne preveriš pravilne stopnje polinoma.

---

## 25. Hiter pregled formul

### Invariantnost

$$
\boxed{U\text{ invarianten za }A\iff A(U)\subseteq U.}
$$

Če je

$$
U=L\{u_1,\ldots,u_k\},
$$

zadošča

$$
\boxed{A(u_i)\in U\quad\forall i.}
$$

Za $\dim U=1$:

$$
\boxed{U=L\{u\}\text{ invarianten}\iff A(u)=\lambda u.}
$$

### Projektor

$$
\boxed{P^2=P}
$$

$$
\boxed{V=\operatorname{Im}P\oplus\ker P}
$$

### Nilpotentnost

$$
\boxed{N^k=0}
$$

pri čemer je za indeks $k$ še

$$
N^{k-1}\neq0.
$$

### Karakteristični polinom

$$
\boxed{p_A(\lambda)=\det(\lambda I-M_A)}
$$

Za trikotno matriko

$$
\boxed{p_A(\lambda)=\prod_{i=1}^n(\lambda-a_{ii}).}
$$

Lastne vrednosti dobimo iz

$$
\boxed{p_A(\lambda)=0.}
$$

---

## 26. Minimalni postopek na izpitu

### Če vidiš besedo »invarianten«

- z bazo ali ogrodjem → preslikaj generatorje,
- z enačbami → vzemi splošen element in ponovno preveri enačbe,
- enorazsežno → preveri skalarni večkratnik,
- parameter → po preslikavi enači koeficiente s $0$.

### Če vidiš besedo »projektor«

Takoj preveri

$$
\boxed{P^2\stackrel{?}{=}P}.
$$

### Če vidiš besedo »nilpotenten«

Računaj

$$
A^2,A^3,\ldots
$$

dokler ne dobiš $A^k=0$, nato preveri $A^{k-1}\neq0$.

### Če vidiš »karakteristični polinom«

Če je matrika podana:

$$
p_A(\lambda)=\det(\lambda I-A).
$$

Če je podan predpis:

$$
\text{predpis}\to\text{matrika v bazi}\to\det(\lambda I-A).
$$

Če je matrika trikotna:

$$
p_A(\lambda)=\prod_i(\lambda-a_{ii}).
$$

---

## 27. Naloge za samostojno reševanje

### Srednje težke naloge

**Naloga 1.**

Naj bo

$$
A=
\begin{pmatrix}
1&1&0\\
0&2&0\\
0&0&-1
\end{pmatrix}
$$

in

$$
U=L\{(1,1,0),(0,0,1)\}.
$$

Preveri, ali je $U$ invarianten za $A$.

**Naloga 2.**

Naj bo

$$
A=
\begin{pmatrix}
1&1&0\\
0&2&0\\
0&0&3
\end{pmatrix}.
$$

Določi $\alpha\in\mathbb R$, za katerega je

$$
U_\alpha=\{(x,y,z)\in\mathbb R^3;\ x-\alpha y=0\}
$$

invarianten za $A$.

**Naloga 3.**

Naj bo

$$
P:\mathbb R^3\to\mathbb R^3,
$$

$$
P(x,y,z)=(x-y,0,z).
$$

1. Preveri, ali je $P$ projektor.
2. Poišči bazo $\ker P$.
3. Poišči bazo $\operatorname{Im}P$.

**Naloga 4.**

Naj bo

$$
N:\mathbb R^4\to\mathbb R^4,
$$

$$
N(x,y,z,w)=(0,x,y,z).
$$

Določi, ali je $N$ nilpotenten, in če je, določi njegov red nilpotentnosti.

**Naloga 5.**

Naj bo

$$
A:\mathbb R_2[x]\to\mathbb R_2[x],
$$

$$
A(f)=f+f(1).
$$

Poišči matriko $A$ glede na običajno bazo $\{1,x,x^2\}$ in karakteristični polinom $p_A(\lambda)$.

**Naloga 6.**

Izračunaj karakteristični polinom matrike

$$
A=
\begin{pmatrix}
3&1&2&0\\
0&-1&4&1\\
0&0&2&5\\
0&0&0&2
\end{pmatrix}.
$$

### Težke / izpitne naloge

**Naloga 7.**

Naj bo

$$
A=
\begin{pmatrix}
1&2&1\\
0&2&0\\
0&0&3
\end{pmatrix}.
$$

Določi $\alpha,\beta\in\mathbb R$, da bo

$$
U_{\alpha,\beta}=\{(x,y,z)\in\mathbb R^3;\ x-\alpha y-\beta z=0\}
$$

invarianten za $A$.

**Naloga 8.**

Naj bo

$$
U=L\{(1,1,0),(0,0,1)\}
$$

in

$$
W=L\{(1,-1,0)\}.
$$

Velja

$$
\mathbb R^3=U\oplus W.
$$

Poišči predpis in matriko projektorja $P$ na $U$ vzdolž $W$, tako da je

$$
\operatorname{Im}P=U,
$$

in

$$
\ker P=W.
$$

**Naloga 9.**

Za $t\in\mathbb R$ naj bo

$$
N_t=
\begin{pmatrix}
0&1&0\\
0&0&t\\
0&0&0
\end{pmatrix}.
$$

Določi:

1. za katere $t$ je $N_t$ nilpotentna,
2. red nilpotentnosti glede na $t$.

**Naloga 10.**

Naj bo

$$
A=
\begin{pmatrix}
0&I_3\\
I_3&0
\end{pmatrix}
\in\mathbb R^{6\times6}.
$$

Izračunaj karakteristični polinom $p_A(\lambda)$ brez neposrednega razvoja determinante $6\times6$.

---

## 28. Odgovori

**1.**

$$
A(1,1,0)=(2,2,0)=2(1,1,0),
$$

$$
A(0,0,1)=(0,0,-1)=-(0,0,1).
$$

Zato

$$
\boxed{U\text{ je invarianten}.}
$$

**2.**

$$
\boxed{\alpha=1}.
$$

**3.**

$$
\boxed{P^2=P}
$$

zato je $P$ projektor.

$$
\boxed{\ker P=L\{(1,1,0)\}}
$$

$$
\boxed{\operatorname{Im}P=L\{(1,0,0),(0,0,1)\}}
$$

**4.**

$$
N^4=0,\qquad N^3\neq0.
$$

Zato

$$
\boxed{N\text{ je nilpotenten reda }4.}
$$

**5.**

$$
M_A=
\begin{pmatrix}
2&1&1\\
0&1&0\\
0&0&1
\end{pmatrix}
$$

in

$$
\boxed{p_A(\lambda)=(\lambda-2)(\lambda-1)^2.}
$$

**6.**

$$
\boxed{p_A(\lambda)=(\lambda-3)(\lambda+1)(\lambda-2)^2.}
$$

**7.**

$$
\boxed{\alpha=2,\qquad\beta=\frac12.}
$$

**8.**

$$
\boxed{P(x,y,z)=\left(\frac{x+y}{2},\frac{x+y}{2},z\right)}
$$

in

$$
\boxed{
M_P=
\begin{pmatrix}
\frac12&\frac12&0\\
\frac12&\frac12&0\\
0&0&1
\end{pmatrix}.
}
$$

**9.**

$N_t$ je nilpotentna za vsak $t\in\mathbb R$.

Če $t\neq0$:

$$
\boxed{\operatorname{ind}(N_t)=3}.
$$

Če $t=0$:

$$
\boxed{\operatorname{ind}(N_0)=2}.
$$

**10.**

$$
\boxed{p_A(\lambda)=(\lambda^2-1)^3.}
$$

---

## 29. Faza je zaključena, ko znam ...

- [ ] natančno definirati **invariantni podprostor**;
- [ ] povedati pogoj $A(U)\subseteq U$;
- [ ] pojasniti razliko med $A(U)\subseteq U$ in $A(U)=U$;
- [ ] preveriti invariantnost podprostora, podanega z bazo ali ogrodjem;
- [ ] dokazati, da je dovolj preveriti slike generatorskih vektorjev;
- [ ] preveriti invariantnost podprostora, podanega z linearnimi enačbami;
- [ ] določiti parameter, pri katerem je podprostor invarianten;
- [ ] prepoznati primer, ko tak parameter ne obstaja;
- [ ] hitro preveriti invariantnost enorazsežnega podprostora;
- [ ] razložiti povezavo $L\{v\}$ invarianten $\iff Av=\lambda v$;
- [ ] preveriti invariantnost podprostorov funkcij pri operatorju odvajanja;
- [ ] natančno definirati **projektor**;
- [ ] brez razmišljanja povedati $P^2=P$;
- [ ] iz predpisa ali matrike preveriti, ali je preslikava projektor;
- [ ] pojasniti, zakaj projektor na svoji zalogi vrednosti deluje kot identiteta;
- [ ] dokazati $V=\operatorname{Im}P\oplus\ker P$;
- [ ] pojasniti, da projektor ni nujno ortogonalna projekcija;
- [ ] natančno definirati **nilpotentni endomorfizem**;
- [ ] natančno definirati **red oziroma indeks nilpotentnosti**;
- [ ] z zaporednim računanjem $A^2,A^3,\ldots$ določiti red nilpotentnosti;
- [ ] preveriti minimalnost reda nilpotentnosti;
- [ ] razložiti, zakaj ima nilpotentni endomorfizem lahko samo lastno vrednost $0$;
- [ ] natančno definirati **karakteristični polinom**;
- [ ] uporabljati konvencijo $p_A(\lambda)=\det(\lambda I-A)$;
- [ ] sestaviti matriko endomorfizma iz njegovega predpisa;
- [ ] izračunati karakteristični polinom preslikave na prostoru polinomov;
- [ ] hitro izračunati karakteristični polinom diagonalne ali trikotne matrike;
- [ ] izkoristiti ničle in bločno strukturo matrike namesto nepotrebnega razvoja determinante;
- [ ] preveriti, da ima karakteristični polinom pravilno stopnjo;
- [ ] dokazati, da je karakteristični polinom neodvisen od izbire baze;
- [ ] pojasniti povezavo med podobnostjo matrik in karakterističnim polinomom;
- [ ] razložiti, zakaj lastne vrednosti dobimo iz enačbe $p_A(\lambda)=0$;
- [ ] samostojno rešiti naloge 59–64 iz 11. vaj;
- [ ] samostojno rešiti nalogo 65 iz 12. vaj;
- [ ] ustno brez zapiskov odgovoriti na definicije invariantnega podprostora, projektorja, nilpotentnosti in karakterističnega polinoma;
- [ ] ustno reproducirati dokaz kriterija invariantnosti na generatorjih;
- [ ] ustno reproducirati dokaz $V=\operatorname{Im}P\oplus\ker P$;
- [ ] ustno reproducirati dokaz neodvisnosti karakterističnega polinoma od baze;
- [ ] jasno razložiti povezavo med invariantnimi podprostori, lastnimi vektorji, karakterističnim polinomom in lastnimi vrednostmi, preden nadaljujem na **Fazo 7 — lastne vrednosti, lastni vektorji in diagonalizacija**.
