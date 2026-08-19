# FAZA 3 — Vsota in presek podprostorov, dimenzijska formula

## Namen faze

V tej fazi moraš obvladati računanje in razumevanje naslednjih objektov:

- vsota podprostorov $U+W$,
- presek podprostorov $U\cap W$,
- baze in razsežnosti vsote ter preseka,
- dimenzijska formula,
- meje za $\dim(U\cap W)$ in $\dim(U+W)$,
- direktna vsota $U\oplus W$,
- dopolnilo podprostora,
- računanje z generatorji, linearnimi enačbami, polinomi in matrikami.

Glavni cilj je, da znaš pri podprostorih, podanih na različne načine, sistematično določiti:

$$
\boxed{
\mathcal B_U,\quad
\mathcal B_W,\quad
\mathcal B_{U\cap W},\quad
\mathcal B_{U+W}
}
$$

ter njihove razsežnosti.

## Podlaga v priloženem gradivu

Ta faza temelji predvsem na:

- **5. vajah, naloge 25–27**: dimenzijska formula, možne razsežnosti preseka in splošne ocene;
- **5. vajah, naloga 23**: dopolnilo podprostora;
- **6. vajah, naloga 28**: konkretno računanje baz prostorov $P$, $R$, $P\cap R$ in $P+R$ v prostoru polinomov.

V priloženih datotekah ni ločenih preteklih izpitov ali kolokvijev, zato je prioriteta tipov nalog določena po priloženih vajah.

## Priporočeni vrstni red učenja

1. Nauči se definicij $U+W$ in $U\cap W$.
2. Razumi, zakaj sta oba objekta podprostora.
3. Nauči se dimenzijsko formulo.
4. Nauči se iz formule dobiti ocene za možne razsežnosti.
5. Nauči se računati vsoto iz generatorjev.
6. Nauči se računati presek iz generatorjev.
7. Nauči se računati presek podprostorov, podanih z enačbami.
8. Nauči se direktne vsote in dopolnila.
9. Reši kombinirane naloge, kjer moraš določiti baze vseh štirih prostorov.
10. Ponovi dokaze in ustna vprašanja.

---

## 1. Presek podprostorov

### Definicija

Naj bosta $U,W\leq V$. **Presek** podprostorov $U$ in $W$ je

$$
U\cap W
=
\{v\in V;\ v\in U\text{ in }v\in W\}.
$$

Torej $U\cap W$ vsebuje natanko tiste vektorje, ki pripadajo **obema** podprostoroma.

### Pomembna lastnost

Če sta $U$ in $W$ podprostora prostora $V$, je tudi

$$
U\cap W\leq V.
$$

#### Kratek dokaz

Ker sta $U$ in $W$ podprostora, velja $0\in U$ in $0\in W$, zato

$$
0\in U\cap W.
$$

Naj bosta $u,v\in U\cap W$ in $\alpha,\beta\in F$. Potem sta $u,v$ hkrati v $U$ in $W$. Ker sta oba prostora zaprta za linearne kombinacije,

$$
\alpha u+\beta v\in U
$$

in

$$
\alpha u+\beta v\in W.
$$

Zato

$$
\alpha u+\beta v\in U\cap W.
$$

Sledi $U\cap W\leq V$.

### Razsežnost preseka

Vedno velja

$$
0\leq \dim(U\cap W)\leq \min\{\dim U,\dim W\}.
$$

Če je

$$
U\cap W=\{0\},
$$

potem je

$$
\dim(U\cap W)=0.
$$

Če je $U\leq W$, potem

$$
U\cap W=U.
$$

---

## 2. Vsota podprostorov

### Definicija

Naj bosta $U,W\leq V$. **Vsota** podprostorov $U$ in $W$ je

$$
U+W
=
\{u+w;\ u\in U,\ w\in W\}.
$$

### Pomembna lastnost

Velja

$$
U+W\leq V.
$$

#### Kratek dokaz

Ker je

$$
0=0+0,
$$

velja $0\in U+W$.

Naj bosta

$$
x=u_1+w_1,\qquad y=u_2+w_2
$$

elementa $U+W$. Za $\alpha,\beta\in F$ dobimo

$$
\alpha x+\beta y
=
(\alpha u_1+\beta u_2)+(\alpha w_1+\beta w_2).
$$

Ker je prvi oklepaj v $U$, drugi pa v $W$, velja

$$
\alpha x+\beta y\in U+W.
$$

### Vsota kot linearna ogrinjača

Če sta $U$ in $W$ podprostora, potem

$$
\boxed{
U+W=L(U\cup W)
}
$$

oziroma: $U+W$ je najmanjši podprostor prostora $V$, ki vsebuje tako $U$ kot $W$.

Če je

$$
U=L\{u_1,\dots,u_r\}
$$

in

$$
W=L\{w_1,\dots,w_s\},
$$

potem

$$
\boxed{
U+W=L\{u_1,\dots,u_r,w_1,\dots,w_s\}.
}
$$

Generatorje samo združimo, nato pa izločimo linearno odvisne.

### Razsežnost vsote

Vedno velja

$$
\max\{\dim U,\dim W\}
\leq
\dim(U+W)
\leq
\dim U+\dim W.
$$

Če je ambientni prostor $V$ končnorazsežen, velja tudi

$$
\dim(U+W)\leq\dim V.
$$

---

## 3. Zelo pomembno: $U+W$ ni isto kot $U\cup W$

To je ena najpogostejših konceptualnih napak.

- $U\cup W$ vsebuje elemente, ki so v $U$ **ali** v $W$.
- $U+W$ vsebuje vse vektorje oblike $u+w$.

V splošnem velja

$$
U\cup W\subseteq U+W,
$$

vendar običajno

$$
U\cup W\neq U+W.
$$

### Kdaj je $U\cup W$ podprostor?

Za dva podprostora velja

$$
\boxed{
U\cup W\text{ je podprostor}
\iff
U\leq W\text{ ali }W\leq U.
}
$$

---

## 4. Dimenzijska formula

### Izrek

Naj bosta $U$ in $W$ končnorazsežna podprostora vektorskega prostora $V$. Potem velja

$$
\boxed{
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
}
$$

Enakovredno:

$$
\boxed{
\dim U+\dim W
=
\dim(U+W)+\dim(U\cap W).
}
$$

### Kdaj jo lahko uporabim?

Ko poznaš tri od štirih količin

$$
\dim U,\qquad
\dim W,\qquad
\dim(U+W),\qquad
\dim(U\cap W),
$$

lahko četrto neposredno izračunaš.

V nalogah iz tega predmeta se formula uporablja za končnorazsežne podprostore.

### Dokaz dimenzijske formule

Naj bo

$$
\mathcal B_0=\{z_1,\dots,z_k\}
$$

baza prostora $U\cap W$.

Bazo preseka dopolnimo do baze prostora $U$:

$$
\mathcal B_U
=
\{z_1,\dots,z_k,u_1,\dots,u_r\}.
$$

Prav tako jo dopolnimo do baze prostora $W$:

$$
\mathcal B_W
=
\{z_1,\dots,z_k,w_1,\dots,w_s\}.
$$

Potem je

$$
\mathcal B
=
\{z_1,\dots,z_k,u_1,\dots,u_r,w_1,\dots,w_s\}
$$

baza prostora $U+W$.

Zato

$$
\dim(U+W)=k+r+s.
$$

Po drugi strani:

$$
\dim U=k+r,
$$

$$
\dim W=k+s,
$$

$$
\dim(U\cap W)=k.
$$

Torej

$$
\dim U+\dim W-\dim(U\cap W)
=
(k+r)+(k+s)-k
=
k+r+s.
$$

Zato

$$
\boxed{
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
}
$$

### Intuicija

Pri vsoti $\dim U+\dim W$ smo vektorje iz preseka prešteli dvakrat, zato moramo

$$
\dim(U\cap W)
$$

enkrat odšteti.

To je analogno principu vključitev–izključitev za dve množici.

---

## 5. Meje za razsežnost preseka

Iz dimenzijske formule

$$
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W)
$$

in pogoja

$$
\dim(U+W)\leq\dim V
$$

dobimo

$$
\dim(U\cap W)
\geq
\dim U+\dim W-\dim V.
$$

Ker razsežnost ne more biti negativna:

$$
\boxed{
\dim(U\cap W)
\geq
\max\{0,\dim U+\dim W-\dim V\}.
}
$$

Po drugi strani:

$$
\boxed{
\dim(U\cap W)
\leq
\min\{\dim U,\dim W\}.
}
$$

Skupaj:

$$
\boxed{
\max\{0,\dim U+\dim W-\dim V\}
\leq
\dim(U\cap W)
\leq
\min\{\dim U,\dim W\}.
}
$$

### Meje za vsoto

Prav tako:

$$
\boxed{
\max\{\dim U,\dim W\}
\leq
\dim(U+W)
\leq
\min\{\dim V,\dim U+\dim W\}.
}
$$

---

## 6. Direktna vsota

### Definicija

Vsota

$$
U+W
$$

je **direktna**, če

$$
U\cap W=\{0\}.
$$

Tedaj pišemo

$$
\boxed{
U\oplus W.
}
$$

### Ekvivalentni pogoji

Za podprostora $U,W\leq V$ so ekvivalentne naslednje trditve:

1. $U+W$ je direktna vsota.
2. $U\cap W=\{0\}$.
3. Vsak $v\in U+W$ se na **en sam način** zapiše kot

$$
v=u+w,
\qquad
u\in U,\quad w\in W.
$$

### Razsežnost direktne vsote

Če je

$$
U\cap W=\{0\},
$$

je

$$
\dim(U\cap W)=0,
$$

zato dimenzijska formula postane

$$
\boxed{
\dim(U\oplus W)=\dim U+\dim W.
}
$$

Če poleg tega velja

$$
V=U+W,
$$

dobimo

$$
\boxed{
V=U\oplus W
}
$$

in

$$
\boxed{
\dim V=\dim U+\dim W.
}
$$

### Hiter test v končnorazsežnem prostoru

Če že veš, da

$$
U\cap W=\{0\}
$$

in

$$
\dim U+\dim W=\dim V,
$$

potem avtomatično

$$
V=U\oplus W.
$$

---

## 7. Dopolnilo podprostora

### Definicija

Naj bo $U\leq V$. Podprostor $W\leq V$ je **dopolnilo** prostora $U$ v $V$, če

$$
\boxed{
V=U\oplus W.
}
$$

To pomeni hkrati:

$$
U+W=V
$$

in

$$
U\cap W=\{0\}.
$$

Če je $V$ končnorazsežen, mora veljati

$$
\boxed{
\dim W=\dim V-\dim U.
}
$$

### Pomembno

Dopolnilo praviloma **ni enolično**.

---

# Kako prepoznam metodo v nalogi?

| Oblika naloge | Najhitrejša metoda |
|---|---|
| Podane so samo razsežnosti | Dimenzijska formula |
| Sprašujejo po najmanjši/največji možni razsežnosti | Meje za presek in vsoto |
| $U$ in $W$ sta podana z generatorji | Generatorje pretvori v stolpce; uporabi rang/Gaussa |
| Iščeš $U+W$ | Združi generatorje $U$ in $W$ ter izberi LN podmnožico |
| Iščeš $U\cap W$ iz generatorjev | Reši $Ua=Wb$ oziroma $Ua-Wb=0$ |
| Podprostora sta podana z enačbami | Za presek reši vse enačbe hkrati |
| Sprašujejo, ali je vsota direktna | Preveri $U\cap W=\{0\}$ |
| Sprašujejo po dopolnilu | Preveri $U+W=V$ in $U\cap W=\{0\}$ |
| Delaš s polinomi | Polinome zapiši s koeficientnimi stolpci |
| Delaš z matrikami | Matrike obravnavaj kot vektorje njihovih koeficientov |

---

# Tipi nalog in rešeni primeri

## Tip naloge 1: Izračun razsežnosti vsote iz dimenzijske formule

### Kako jo prepoznam

Naloga poda:

- $\dim U$,
- $\dim W$,
- $\dim(U\cap W)$,

in zahteva $\dim(U+W)$.

### Postopek

1. Zapiši dimenzijsko formulo.
2. Vstavi podatke.
3. Izračunaj.

### Pomembna formula

$$
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
$$

### Primer

Naj bosta podprostora $V$ in $W$ nekega vektorskega prostora taka, da

$$
\dim V=6,\qquad
\dim W=7,\qquad
\dim(V\cap W)=3.
$$

Določi $\dim(V+W)$.

### Rešitev

Uporabimo dimenzijsko formulo:

$$
\begin{aligned}
\dim(V+W)
&=
\dim V+\dim W-\dim(V\cap W)\\
&=
6+7-3\\
&=
10.
\end{aligned}
$$

Zato

$$
\boxed{\dim(V+W)=10.}
$$

### Pogoste napake

- uporabiš $6+7+3$ namesto $6+7-3$;
- zamenjaš ambientni prostor z enim od podprostorov;
- pozabiš, da se presek odšteje, ker je bil pri seštevanju razsežnosti preštet dvakrat.

---

## Tip naloge 2: Najmanjša in največja možna razsežnost preseka

### Kako jo prepoznam

Podani so:

$$
\dim V,\qquad
\dim U,\qquad
\dim W,
$$

ni pa podan $U\cap W$.

Naloga sprašuje po možnih vrednostih $\dim(U\cap W)$.

### Postopek

1. Za spodnjo mejo uporabi $\dim(U+W)\leq\dim V$.
2. Za zgornjo mejo uporabi $U\cap W\leq U$ in $U\cap W\leq W$.

### Pomembna formula

$$
\boxed{
\max\{0,\dim U+\dim W-\dim V\}
\leq
\dim(U\cap W)
\leq
\min\{\dim U,\dim W\}.
}
$$

### Primer

Naj bo

$$
\dim V=45,\qquad
\dim U=32,\qquad
\dim W=41.
$$

Določi najmanjšo in največjo možno razsežnost $U\cap W$.

### Rešitev

Ker

$$
\dim(U+W)\leq45,
$$

velja

$$
32+41-\dim(U\cap W)\leq45.
$$

Torej

$$
73-\dim(U\cap W)\leq45,
$$

zato

$$
\dim(U\cap W)\geq28.
$$

Hkrati

$$
\dim(U\cap W)
\leq
\min\{32,41\}
=
32.
$$

Zato

$$
\boxed{
28\leq\dim(U\cap W)\leq32.
}
$$

### Pogoste napake

- za spodnjo mejo vzameš samo $0$ in pozabiš omejitev ambientnega prostora;
- napišeš zgornjo mejo $41$, čeprav je manjši podprostor razsežnosti $32$;
- sklepaš, da mora biti presek natanko $\dim U+\dim W-\dim V$; to je le najmanjša možna vrednost.

---

## Tip naloge 3: Presoja pravilne splošne trditve o razsežnostih

### Kako jo prepoznam

Naloga poda samo $\dim U$ in $\dim W$ ter več trditev, na primer o:

- $\dim(U+W)$,
- $\dim(U\cap W)$,
- $\dim V$,
- vključevanju enega prostora v drugega.

### Ključne neenakosti

$$
\dim(U+W)\leq\dim U+\dim W
$$

in

$$
\dim(U\cap W)\leq\min\{\dim U,\dim W\}.
$$

### Primer

Naj bosta

$$
\dim U=8,\qquad
\dim W=5.
$$

Kaj lahko vedno zagotovo trdimo?

### Rešitev

Iz dimenzijske formule:

$$
\dim(U+W)
=
8+5-\dim(U\cap W).
$$

Ker

$$
\dim(U\cap W)\geq0,
$$

dobimo

$$
\boxed{
\dim(U+W)\leq13.
}
$$

O razsežnosti ambientnega prostora brez dodatnih podatkov ne moremo sklepati, da je natanko ali vsaj $13$.

---

## Tip naloge 4: Vsota podprostorov, podanih z generatorji

### Kako jo prepoznam

Podprostora sta podana kot

$$
U=L\{u_1,\dots,u_r\},
$$

$$
W=L\{w_1,\dots,w_s\}.
$$

Iščeš bazo $U+W$.

### Postopek

1. Združi vse generatorje:

$$
U+W
=
L\{u_1,\dots,u_r,w_1,\dots,w_s\}.
$$

2. Vektorje zapiši kot stolpce matrike.
3. Z Gaussovo eliminacijo določi rang oziroma pivotne stolpce.
4. Iz **izvirnih** generatorjev izberi pripadajoče linearno neodvisne vektorje.
5. Ti tvorijo bazo $U+W$.

### Pomembno

Generatorji združene množice niso nujno baza. Lahko so linearno odvisni.

---

## Tip naloge 5: Presek podprostorov, podanih z generatorji

### Kako jo prepoznam

Imaš

$$
U=L\{u_1,\dots,u_r\},
\qquad
W=L\{w_1,\dots,w_s\},
$$

in iščeš $U\cap W$.

### Osnovna ideja

Vektor $v$ pripada preseku natanko tedaj, ko ga lahko zapišemo na oba načina:

$$
v
=
a_1u_1+\cdots+a_ru_r
=
b_1w_1+\cdots+b_sw_s.
$$

Zato rešujemo

$$
a_1u_1+\cdots+a_ru_r
-
b_1w_1-\cdots-b_sw_s
=
0.
$$

V matrični obliki:

$$
\boxed{
\begin{pmatrix}
U & -W
\end{pmatrix}
\begin{pmatrix}
a\\
b
\end{pmatrix}
=
0.
}
$$

### Postopek

1. Uvedi koeficiente za linearno kombinacijo v $U$.
2. Uvedi druge koeficiente za linearno kombinacijo v $W$.
3. Enači obe linearni kombinaciji.
4. Reši homogeni sistem.
5. Rešitve vstavi nazaj v eno od linearnih kombinacij.
6. Iz dobljenih vektorjev izberi bazo preseka.

### Pogoste napake

- uporabiš iste koeficiente na obeh straneh;
- iščeš presek generatorjev namesto preseka prostorov;
- rešitev sistema za koeficiente napačno razglasiš za vektor preseka;
- ne vstaviš parametrov nazaj v linearno kombinacijo.

---

## Tip naloge 6: Kombinirana naloga s polinomi — baze $P$, $R$, $P\cap R$ in $P+R$

### Kako jo prepoznam

Podprostora polinomov sta podana kot linearni ogrinjači več polinomov, naloga pa zahteva baze:

$$
P,\qquad R,\qquad P\cap R,\qquad P+R.
$$

To je osrednji tip naloge iz 6. vaj.

### Ključni trik

Polinom

$$
a_0+a_1x+a_2x^2+a_3x^3
$$

identificiramo s koeficientnim stolpcem

$$
\begin{pmatrix}
a_0\\
a_1\\
a_2\\
a_3
\end{pmatrix}.
$$

Potem nalogo rešujemo kot običajno nalogo v $\mathbb R^4$.

### Primer

Naj bo

$$
P
=
L\{
1+x^2+2x^3,\,
2-x+x^2+2x^3,\,
1+x+x^2+x^3
\},
$$

$$
R
=
L\{
1+x^3,\,
3+x^3,\,
1+x
\}.
$$

Poišči baze prostorov

$$
P,\qquad R,\qquad P\cap R,\qquad P+R.
$$

### Rešitev

Označimo:

$$
p_1=1+x^2+2x^3,
$$

$$
p_2=2-x+x^2+2x^3,
$$

$$
p_3=1+x+x^2+x^3.
$$

Njihovi koeficientni stolpci so

$$
[p_1]=
\begin{pmatrix}
1\\0\\1\\2
\end{pmatrix},
\qquad
[p_2]=
\begin{pmatrix}
2\\-1\\1\\2
\end{pmatrix},
\qquad
[p_3]=
\begin{pmatrix}
1\\1\\1\\1
\end{pmatrix}.
$$

Ti trije stolpci so linearno neodvisni, zato

$$
\boxed{
\mathcal B_P=\{p_1,p_2,p_3\},
\qquad
\dim P=3.
}
$$

Za $R$ označimo:

$$
r_1=1+x^3,\qquad
r_2=3+x^3,\qquad
r_3=1+x.
$$

Koeficientni stolpci so

$$
[r_1]=
\begin{pmatrix}
1\\0\\0\\1
\end{pmatrix},
\qquad
[r_2]=
\begin{pmatrix}
3\\0\\0\\1
\end{pmatrix},
\qquad
[r_3]=
\begin{pmatrix}
1\\1\\0\\0
\end{pmatrix}.
$$

Tudi ti so linearno neodvisni, zato

$$
\boxed{
\mathcal B_R=\{r_1,r_2,r_3\},
\qquad
\dim R=3.
}
$$

Za presek zahtevamo

$$
ap_1+bp_2+cp_3
=
dr_1+er_2+fr_3.
$$

Po primerjavi koeficientov dobimo sistem

$$
\begin{aligned}
a+2b+c&=d+3e+f,\\
-b+c&=f,\\
a+b+c&=0,\\
2a+2b+c&=d+e.
\end{aligned}
$$

Splošna rešitev je

$$
\begin{aligned}
a&=-2t-s,\\
b&=t,\\
c&=t+s,\\
d&=-2t-s,\\
e&=t,\\
f&=s.
\end{aligned}
$$

Vektor preseka je zato

$$
\begin{aligned}
ap_1+bp_2+cp_3
&=
t(-2p_1+p_2+p_3)
+s(-p_1+p_3)\\
&=
t(1-x^3)+s(x-x^3).
\end{aligned}
$$

Torej

$$
\boxed{
P\cap R
=
L\{1-x^3,\ x-x^3\}.
}
$$

in

$$
\boxed{
\dim(P\cap R)=2.
}
$$

Sedaj uporabimo dimenzijsko formulo:

$$
\begin{aligned}
\dim(P+R)
&=
\dim P+\dim R-\dim(P\cap R)\\
&=
3+3-2\\
&=
4.
\end{aligned}
$$

Ker je

$$
P+R\leq\mathbb R_3[x]
$$

in

$$
\dim\mathbb R_3[x]=4,
$$

sledi

$$
\boxed{
P+R=\mathbb R_3[x].
}
$$

Za bazo vsote lahko vzamemo na primer

$$
\boxed{
\mathcal B_{P+R}
=
\{p_1,p_2,p_3,r_1\}.
}
$$

Ti štirje polinomi so linearno neodvisni, zato tvorijo bazo $\mathbb R_3[x]$.

### Kontrola rezultata

Vedno preveri:

$$
\dim(P+R)+\dim(P\cap R)
=
4+2
=
6,
$$

in

$$
\dim P+\dim R
=
3+3
=
6.
$$

Formula se ujema.

### Pogoste napake

- za $\mathbb R_3[x]$ uporabiš samo tri koordinate; pravilno so štiri: $1,x,x^2,x^3$;
- avtomatično razglasiš vse združene generatorje za bazo vsote;
- pri preseku enačiš samo generatorje med seboj;
- po izračunu preseka ne preveriš dimenzijske formule.

---

## Tip naloge 7: Presek podprostorov, podanih z enačbami

### Kako jo prepoznam

Podprostora sta podana s pogoji, na primer

$$
U=\{x\in\mathbb R^n;\ Ax=0\},
$$

$$
W=\{x\in\mathbb R^n;\ Bx=0\}.
$$

### Postopek

Za presek mora vektor izpolnjevati **oba** sistema:

$$
Ax=0
$$

in

$$
Bx=0.
$$

Zato rešimo

$$
\boxed{
\begin{pmatrix}
A\\
B
\end{pmatrix}
x=0.
}
$$

### Primer

Naj bo

$$
U
=
\{(x,y,z)\in\mathbb R^3;\ x+y+z=0\},
$$

$$
W
=
\{(x,y,z)\in\mathbb R^3;\ x-y=0\}.
$$

Poišči $U\cap W$ in $U+W$.

### Rešitev

Za presek rešimo

$$
\begin{cases}
x+y+z=0,\\
x-y=0.
\end{cases}
$$

Iz druge enačbe:

$$
y=x.
$$

Zato

$$
2x+z=0,
$$

torej

$$
z=-2x.
$$

Sledi

$$
(x,y,z)=x(1,1,-2).
$$

Zato

$$
\boxed{
U\cap W=L\{(1,1,-2)\},
\qquad
\dim(U\cap W)=1.
}
$$

Oba prostora sta ravnini skozi izhodišče, zato

$$
\dim U=\dim W=2.
$$

Po dimenzijski formuli:

$$
\dim(U+W)=2+2-1=3.
$$

Ker je $U+W\leq\mathbb R^3$,

$$
\boxed{
U+W=\mathbb R^3.
}
$$

### Pogoste napake

- za presek rešuješ samo enega od sistemov;
- zamenjaš presek z vsoto;
- po rešitvi sistema ne zapišeš baze.

---

## Tip naloge 8: Ugotavljanje, ali je vsota direktna

### Kako jo prepoznam

Naloga vsebuje:

- izraz $U\oplus W$,
- vprašanje, ali je vsota direktna,
- vprašanje o enoličnosti zapisa $v=u+w$.

### Postopek

Najhitreje preveri:

$$
\boxed{
U\cap W=\{0\}.
}
$$

Če je presek neničeln, vsota ni direktna.

Če moraš dokazati še

$$
V=U\oplus W,
$$

preveri tudi

$$
U+W=V.
$$

V končnorazsežnem primeru lahko po $U\cap W=\{0\}$ preveriš

$$
\dim U+\dim W=\dim V.
$$

### Primer

Naj bo

$$
U=L\{(1,0,0),(0,1,0)\},
$$

$$
W=L\{(0,0,1)\}
$$

v $\mathbb R^3$.

Ker je

$$
U\cap W=\{0\},
$$

je vsota direktna.

Poleg tega

$$
\dim U+\dim W=2+1=3=\dim\mathbb R^3.
$$

Torej

$$
\boxed{
\mathbb R^3=U\oplus W.
}
$$

---

## Tip naloge 9: Iskanje dopolnila podprostora

### Kako jo prepoznam

Naloga poda $U\leq V$ in sprašuje, kateri podprostor $W$ je njegovo **dopolnilo**.

### Postopek

Preveri dva pogoja:

$$
U\cap W=\{0\},
$$

$$
U+W=V.
$$

Pri končnorazsežnih prostorih najprej uporabi filter

$$
\dim W=\dim V-\dim U.
$$

### Primer

Naj bo

$$
U
=
\{p\in\mathbb R_2[x];\ p(2)=0\}.
$$

Kateri enorazsežni podprostor je lahko dopolnilo $U$?

Ker je pogoj $p(2)=0$ ena neodvisna linearna enačba v prostoru razsežnosti $3$,

$$
\dim U=2.
$$

Dopolnilo mora imeti razsežnost

$$
3-2=1.
$$

Vzemimo

$$
W=L\{x^2\}.
$$

Ker

$$
x^2(2)=4\neq0,
$$

velja $x^2\notin U$. Ker je $W$ enorazsežen,

$$
U\cap W=\{0\}.
$$

Poleg tega

$$
\dim U+\dim W=2+1=3=\dim\mathbb R_2[x].
$$

Zato

$$
\boxed{
\mathbb R_2[x]=U\oplus L\{x^2\}.
}
$$

### Pogoste napake

- preveriš samo pravilno razsežnost dopolnila;
- izbereš enorazsežen prostor, ki je že vsebovan v $U$;
- misliš, da ima podprostor samo eno možno dopolnilo.

---

# Hitra strategija za pisni izpit

Če vidiš nalogo o $U$, $W$, $U\cap W$ in $U+W$, uporabi naslednji vrstni red.

### Če so podane samo razsežnosti

Takoj napiši:

$$
\boxed{
\dim(U+W)=\dim U+\dim W-\dim(U\cap W).
}
$$

### Če sta prostora podana z generatorji

Najprej določi baze in razsežnosti $U$ ter $W$.

Za vsoto:

$$
U+W=L(\mathcal B_U\cup\mathcal B_W).
$$

Za presek:

$$
Ua=Wb.
$$

Ko najdeš presek, uporabi dimenzijsko formulo kot kontrolo.

### Če sta prostora podana z enačbami

Za presek združi vse enačbe.

Za vsoto je pogosto lažje:

1. določiti baze $U$ in $W$;
2. združiti baze;
3. izločiti linearno odvisne vektorje.

### Če naloga vsebuje besedo »direktna«

Takoj pomisli na:

$$
\boxed{
U\cap W=\{0\}.
}
$$

### Če vsebuje besedo »dopolnilo«

Takoj pomisli na:

$$
\boxed{
V=U\oplus W.
}
$$

---

# Kontrolne formule

## Osnovne definicije

$$
U\cap W
=
\{v;\ v\in U\text{ in }v\in W\}.
$$

$$
U+W
=
\{u+w;\ u\in U,\ w\in W\}.
$$

## Dimenzijska formula

$$
\boxed{
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
}
$$

## Meje za presek

$$
\boxed{
\max\{0,\dim U+\dim W-\dim V\}
\leq
\dim(U\cap W)
\leq
\min\{\dim U,\dim W\}.
}
$$

## Meje za vsoto

$$
\boxed{
\max\{\dim U,\dim W\}
\leq
\dim(U+W)
\leq
\min\{\dim V,\dim U+\dim W\}.
}
$$

## Direktna vsota

$$
\boxed{
U+W=U\oplus W
\iff
U\cap W=\{0\}.
}
$$

Če je vsota direktna:

$$
\boxed{
\dim(U\oplus W)=\dim U+\dim W.
}
$$

## Dopolnilo

$$
\boxed{
W\text{ je dopolnilo }U
\iff
V=U\oplus W.
}
$$

---

# Najpogostejše napake

- Zamenjava $U+W$ in $U\cup W$.
- Prepričanje, da je $U\cup W$ vedno podprostor.
- Združene generatorje avtomatično razglasiš za bazo vsote.
- Za $U\cap W$ iščeš samo skupne generatorje.
- Pri metodi $Ua=Wb$ ne uporabiš neodvisnih koeficientov na obeh straneh.
- Rešitve sistema za koeficiente zamenjaš z dejanskimi vektorji preseka.
- Pozabiš odšteti $\dim(U\cap W)$ v dimenzijski formuli.
- Pozabiš omejitev $\dim(U+W)\leq\dim V$.
- Pri direktni vsoti preveriš samo $U+W=V$, ne pa $U\cap W=\{0\}$.
- Pri dopolnilu preveriš samo razsežnost.
- Pri polinomih izpustiš konstantni člen ali kakšno potenco.
- Pri matrikah ne obravnavaš vseh matričnih koeficientov kot koordinat.
- Ne uporabiš dimenzijske formule za kontrolo rezultata.

---

# Povezave z drugimi koncepti

## Linearna neodvisnost

Če velja

$$
U\cap W=\{0\},
$$

potem lahko bazo $U$ in bazo $W$ združimo in dobimo linearno neodvisno množico.

Če poleg tega $U+W=V$, je združena množica baza prostora $V$.

## Baza in dimenzija

Dimenzijska formula je neposredna posledica tega, kako bazo preseka dopolnimo do baz $U$ in $W$.

## Linearne preslikave

V naslednjih fazah se pojavljata jedro in slika linearne preslikave. Oba sta podprostora, zato se tehnike iz te faze neposredno uporabljajo tudi tam.

## Rang in ničelnost

Kasnejša formula

$$
\dim V
=
\dim\ker A+\dim\operatorname{Im}A
$$

je po obliki sorodna razcepu prostora na podprostore, čeprav gre za drug izrek.

## Diagonalizacija

Pri diagonalizaciji prostor pogosto razstavimo na direktno vsoto lastnih podprostorov. Zato je razumevanje direktnih vsot pomembno tudi za zaključni del predmeta.

---

# Ustni / teoretični del

## Ustno vprašanje 1

**Vprašanje:** Kaj je presek dveh podprostorov?

**Kratek odgovor:** Presek podprostorov $U,W\leq V$ je

$$
U\cap W=\{v\in V;\ v\in U\text{ in }v\in W\}.
$$

Presek dveh podprostorov je vedno podprostor.

**Profesor lahko dodatno vpraša:** Zakaj je $U\cap W$ podprostor?

**Odgovor:** Ker vsebuje ničelni vektor in je zaprt za linearne kombinacije: če sta $u,v\in U\cap W$, potem sta v obeh podprostorih, zato je za vsak $\alpha,\beta$ tudi $\alpha u+\beta v$ v obeh, torej v $U\cap W$.

---

## Ustno vprašanje 2

**Vprašanje:** Kaj je vsota dveh podprostorov?

**Kratek odgovor:**

$$
U+W=\{u+w;\ u\in U,\ w\in W\}.
$$

To je najmanjši podprostor, ki vsebuje $U$ in $W$.

**Profesor lahko dodatno vpraša:** Kako določiš generatorje $U+W$?

**Odgovor:** Če sta $U=L\{u_1,\dots,u_r\}$ in $W=L\{w_1,\dots,w_s\}$, potem

$$
U+W=L\{u_1,\dots,u_r,w_1,\dots,w_s\}.
$$

---

## Ustno vprašanje 3

**Vprašanje:** Ali je $U\cup W$ vedno podprostor?

**Kratek odgovor:** Ne.

**Profesor lahko dodatno vpraša:** Kdaj je $U\cup W$ podprostor?

**Odgovor:**

$$
U\cup W\text{ je podprostor}
\iff
U\leq W\text{ ali }W\leq U.
$$

Če nobeden ni vsebovan v drugem, vzamemo $u\in U\setminus W$ in $w\in W\setminus U$. Tedaj $u+w$ ne more pripadati niti samo $U$ niti samo $W$, zato unija ni zaprta za seštevanje.

---

## Ustno vprašanje 4

**Vprašanje:** Povej dimenzijsko formulo za vsoto dveh podprostorov.

**Kratek odgovor:** Za končnorazsežna podprostora $U$ in $W$ velja

$$
\boxed{
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
}
$$

**Profesor lahko dodatno vpraša:** Zakaj odštejemo razsežnost preseka?

**Odgovor:** Ker so bazne smeri iz $U\cap W$ pri vsoti $\dim U+\dim W$ preštete dvakrat.

---

## Ustno vprašanje 5

**Vprašanje:** Dokaži dimenzijsko formulo.

**Kratek odgovor:** Vzamemo bazo

$$
\{z_1,\dots,z_k\}
$$

prostora $U\cap W$. Dopolnimo jo do baze $U$ z vektorji $u_1,\dots,u_r$ in do baze $W$ z vektorji $w_1,\dots,w_s$. Potem je

$$
\{z_1,\dots,z_k,u_1,\dots,u_r,w_1,\dots,w_s\}
$$

baza $U+W$. Zato

$$
\dim(U+W)=k+r+s,
$$

medtem ko

$$
\dim U=k+r,\qquad
\dim W=k+s,\qquad
\dim(U\cap W)=k.
$$

Od tod sledi formula.

**Profesor lahko dodatno vpraša:** Zakaj je združena množica linearno neodvisna?

**Odgovor:** Če njena linearna kombinacija da nič, prenesemo kombinacijo $w_j$ na drugo stran. Dobljeni vektor leži hkrati v $U$ in $W$, torej v $U\cap W$. Ker so $z_i$ baza preseka in ker sta razširjeni množici bazi $U$ oziroma $W$, morajo biti vsi koeficienti enaki nič.

---

## Ustno vprašanje 6

**Vprašanje:** Kakšne so možne razsežnosti $U\cap W$?

**Kratek odgovor:** Če sta $U,W\leq V$ in je $V$ končnorazsežen, potem

$$
\max\{0,\dim U+\dim W-\dim V\}
\leq
\dim(U\cap W)
\leq
\min\{\dim U,\dim W\}.
$$

**Profesor lahko dodatno vpraša:** Od kod dobimo spodnjo mejo?

**Odgovor:** Iz dimenzijske formule in neenakosti $\dim(U+W)\leq\dim V$.

---

## Ustno vprašanje 7

**Vprašanje:** Kaj je direktna vsota?

**Kratek odgovor:** Vsota $U+W$ je direktna, če

$$
U\cap W=\{0\}.
$$

Pišemo

$$
U\oplus W.
$$

**Profesor lahko dodatno vpraša:** Kaj je značilno za zapis elementov direktne vsote?

**Odgovor:** Vsak $v\in U\oplus W$ ima enoličen zapis

$$
v=u+w,
\qquad
u\in U,\quad w\in W.
$$

---

## Ustno vprašanje 8

**Vprašanje:** Dokaži enoličnost zapisa pri direktni vsoti.

**Kratek odgovor:** Naj bo

$$
u_1+w_1=u_2+w_2.
$$

Tedaj

$$
u_1-u_2=w_2-w_1.
$$

Leva stran je v $U$, desna v $W$, zato je ta vektor v $U\cap W$. Če je vsota direktna, je presek $\{0\}$, zato

$$
u_1=u_2,\qquad w_1=w_2.
$$

---

## Ustno vprašanje 9

**Vprašanje:** Kaj je dopolnilo podprostora?

**Kratek odgovor:** Podprostor $W$ je dopolnilo $U$ v $V$, če

$$
V=U\oplus W.
$$

Torej

$$
U+W=V
$$

in

$$
U\cap W=\{0\}.
$$

**Profesor lahko dodatno vpraša:** Kakšna je razsežnost dopolnila?

**Odgovor:** Če je $V$ končnorazsežen,

$$
\dim W=\dim V-\dim U.
$$

---

## Ustno vprašanje 10

**Vprašanje:** Kako iz generatorjev določiš presek $U\cap W$?

**Kratek odgovor:** Vektor preseka zapišem na oba načina,

$$
Ua=Wb,
$$

nato rešim homogeni sistem

$$
Ua-Wb=0.
$$

Dobljene koeficiente vstavim nazaj v eno od linearnih kombinacij in iz dobljenih vektorjev izberem bazo preseka.

**Profesor lahko dodatno vpraša:** Ali je ničelni prostor rešitev sistema že baza preseka?

**Odgovor:** Ne. Rešitve sistema so koeficienti linearnih kombinacij. Te koeficiente moramo najprej pretvoriti nazaj v dejanske vektorje prostora.

---

# Mini ustni povzetek za pomnjenje

Če moraš fazo povedati v manj kot minuti:

- $U\cap W$ vsebuje vektorje, ki so v obeh prostorih.
- $U+W=\{u+w\}$ in je enako linearni ogrinjači združenih generatorjev.
- Za končnorazsežna podprostora velja

$$
\dim(U+W)
=
\dim U+\dim W-\dim(U\cap W).
$$

- Vsota je direktna natanko tedaj, ko

$$
U\cap W=\{0\}.
$$

- $W$ je dopolnilo $U$ v $V$, če

$$
V=U\oplus W.
$$

- Pri generatorjih računamo presek z enačbo

$$
Ua=Wb.
$$

---

# Naloge za samostojno reševanje

## Srednje težke naloge

**Naloga 1.**

Naj bosta $U$ in $W$ podprostora nekega končnorazsežnega prostora in naj velja

$$
\dim U=7,\qquad
\dim W=5,\qquad
\dim(U\cap W)=2.
$$

Izračunaj $\dim(U+W)$.

---

**Naloga 2.**

Naj bo

$$
\dim V=12,\qquad
\dim U=8,\qquad
\dim W=7.
$$

Določi najmanjšo in največjo možno vrednost:

1. $\dim(U\cap W)$,
2. $\dim(U+W)$.

---

**Naloga 3.**

V $\mathbb R^3$ sta dana podprostora

$$
U=L\{(1,0,1),(0,1,1)\},
$$

$$
W=L\{(1,1,0),(1,-1,2)\}.
$$

Poišči bazo in razsežnost:

1. $U\cap W$,
2. $U+W$.

---

**Naloga 4.**

V $\mathbb R^4$ sta dana podprostora

$$
U
=
\{(x,y,z,w);\ x+y=0,\ z-w=0\},
$$

$$
W
=
\{(x,y,z,w);\ x-y=0,\ z+w=0\}.
$$

Določi $U\cap W$ in $U+W$. Ali je

$$
\mathbb R^4=U\oplus W?
$$

---

**Naloga 5.**

Naj bo

$$
U=\{p\in\mathbb R_2[x];\ p(1)=0\}.
$$

Poišči bazo $U$ in navedi eno dopolnilo $W$, za katerega velja

$$
\mathbb R_2[x]=U\oplus W.
$$

---

**Naloga 6.**

V $\mathbb R^3$ naj bo

$$
U=L\{(1,0,0),(0,1,0)\},
$$

$$
W=L\{(1,1,0),(0,0,1)\}.
$$

Določi $U\cap W$ in $U+W$. Ali je vsota direktna?

---

## Težke / izpitne naloge

**Naloga 7.**

V $\mathbb R_3[x]$ naj bo

$$
P
=
L\{1+x,\ x+x^2,\ x^2+x^3\},
$$

$$
R
=
L\{1+x^3,\ x+x^2,\ 1-x+x^3\}.
$$

Poišči baze in razsežnosti prostorov

$$
P,\qquad
R,\qquad
P\cap R,\qquad
P+R.
$$

---

**Naloga 8.**

V prostoru $\mathbb R^{2\times2}$ naj bo

$$
U=\{A;\ A^T=A\}
$$

prostor simetričnih matrik in

$$
W=\{A;\ \operatorname{tr}(A)=0\}.
$$

Poišči:

1. bazo in razsežnost $U$,
2. bazo in razsežnost $W$,
3. bazo in razsežnost $U\cap W$,
4. $U+W$.

Ali je vsota direktna?

---

**Naloga 9.**

Za $t\in\mathbb R$ naj bo

$$
U_t
=
L\{(1,t,0),(0,1,t)\}
$$

in

$$
W=L\{(1,0,-1)\}.
$$

Določi vse $t\in\mathbb R$, za katere velja

$$
\mathbb R^3=U_t\oplus W.
$$

---

**Naloga 10.**

V $\mathbb R_3[x]$ naj bo

$$
U
=
\{p;\ p(0)=0,\ p(1)=0\}.
$$

1. Poišči bazo in razsežnost $U$.
2. Poišči dvodimenzionalno dopolnilo $W$ prostora $U$.
3. Dokaži z razsežnostmi in presekom, da

$$
\mathbb R_3[x]=U\oplus W.
$$

---

# Odgovori

**1.**

$$
\boxed{\dim(U+W)=10.}
$$

**2.**

$$
\boxed{
3\leq\dim(U\cap W)\leq7
}
$$

in

$$
\boxed{
8\leq\dim(U+W)\leq12.
}
$$

**3.**

$$
\boxed{
U\cap W=L\{(1,0,1)\},
\qquad
\dim(U\cap W)=1.
}
$$

$$
\boxed{
U+W=\mathbb R^3,
\qquad
\dim(U+W)=3.
}
$$

Ena baza vsote je

$$
\{(1,0,1),(0,1,1),(1,1,0)\}.
$$

**4.**

$$
\boxed{
U\cap W=\{0\}.
}
$$

$$
\boxed{
U+W=\mathbb R^4.
}
$$

Zato

$$
\boxed{
\mathbb R^4=U\oplus W.
}
$$

**5.**

Ena možna baza:

$$
\boxed{
\mathcal B_U=\{x-1,\ x^2-x\}.
}
$$

Eno možno dopolnilo:

$$
\boxed{
W=L\{1\}.
}
$$

**6.**

$$
\boxed{
U\cap W=L\{(1,1,0)\}.
}
$$

$$
\boxed{
U+W=\mathbb R^3.
}
$$

Vsota **ni direktna**.

**7.**

$$
\boxed{\dim P=3,\qquad \dim R=3.}
$$

$$
\boxed{
P\cap R=L\{1+x^3,\ x+x^2\},
\qquad
\dim(P\cap R)=2.
}
$$

$$
\boxed{
P+R=\mathbb R_3[x],
\qquad
\dim(P+R)=4.
}
$$

**8.**

$$
\boxed{\dim U=3,\qquad \dim W=3.}
$$

Ena baza preseka:

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
\right\}.
}
$$

$$
\boxed{
\dim(U\cap W)=2,
\qquad
U+W=\mathbb R^{2\times2}.
}
$$

Vsota ni direktna.

**9.**

Determinanta matrike združenih generatorjev je

$$
t^2-1.
$$

Zato

$$
\boxed{
\mathbb R^3=U_t\oplus W
\iff
t\neq1\text{ in }t\neq-1.
}
$$

**10.**

$$
\boxed{
U=L\{x^2-x,\ x^3-x^2\},
\qquad
\dim U=2.
}
$$

Eno možno dopolnilo:

$$
\boxed{
W=L\{1,x\}.
}
$$

Velja

$$
\boxed{
\mathbb R_3[x]=U\oplus W.
}
$$

---

# Faza je zaključena, ko znam ...

- [ ] natančno definirati $U\cap W$;
- [ ] natančno definirati $U+W$;
- [ ] razložiti razliko med $U+W$ in $U\cup W$;
- [ ] dokazati, da je $U\cap W$ podprostor;
- [ ] dokazati, da je $U+W$ podprostor;
- [ ] povedati in pravilno uporabiti dimenzijsko formulo;
- [ ] navesti pogoje, pod katerimi uporabljamo dimenzijsko formulo;
- [ ] dokazati dimenzijsko formulo z bazo preseka;
- [ ] izračunati $\dim(U+W)$ iz $\dim U$, $\dim W$ in $\dim(U\cap W)$;
- [ ] izračunati $\dim(U\cap W)$ iz ostalih razsežnosti;
- [ ] določiti najmanjšo in največjo možno razsežnost $U\cap W$;
- [ ] določiti meje za $\dim(U+W)$;
- [ ] iz generatorjev določiti bazo in razsežnost $U+W$;
- [ ] iz generatorjev določiti $U\cap W$ z enačbo $Ua=Wb$;
- [ ] pravilno pretvoriti rešitve sistema za koeficiente v dejanske vektorje preseka;
- [ ] iz enačb podprostorov izračunati njihov presek;
- [ ] pri polinomih uporabiti koeficientne stolpce;
- [ ] pri matričnih prostorih uporabiti koordinate matričnih elementov;
- [ ] natančno definirati direktno vsoto;
- [ ] prepoznati pogoj $U\cap W=\{0\}$ za direktnost;
- [ ] dokazati enoličnost zapisa $v=u+w$ pri direktni vsoti;
- [ ] natančno definirati dopolnilo podprostora;
- [ ] poiskati eno možno dopolnilo podprostora;
- [ ] preveriti $V=U\oplus W$ z vsoto in presekom;
- [ ] uporabiti razsežnosti kot hiter test za direktno vsoto;
- [ ] samostojno rešiti nalogo tipa 28 iz 6. vaj: baze $P$, $R$, $P\cap R$ in $P+R$;
- [ ] pri vsakem računu preveriti rezultat z dimenzijsko formulo;
- [ ] ustno razložiti povezavo med presekom, vsoto, bazo in razsežnostjo;
- [ ] brez zapiskov odgovoriti na vseh 10 ustnih vprašanj iz tega poglavja.
