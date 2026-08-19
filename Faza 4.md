# FAZA 4 — Linearne preslikave, jedro, slika, rang in izomorfizmi

## 0. Obseg faze in viri

Ta faza je zgrajena predvsem po **Vajah 6–10** pri predmetu Algebra II – Linearna algebra (študijsko leto 2025/2026).

V priloženih datotekah ni ločenih preteklih izpitov ali kolokvijev, zato so prioritete določene po tipih nalog, ki se ponavljajo v vajah. Največ poudarka je na:

- preverjanju, ali je preslikava linearna,
- določanju linearne preslikave iz slik izbranih vektorjev,
- preverjanju, ali se podani predpis sploh lahko razširi do linearne preslikave,
- izračunu jedra, slike in ranga,
- uporabi izreka o rangu in ničelnosti,
- odločanju o injektivnosti in surjektivnosti,
- linearnih funkcionalih,
- izomorfizmih vektorskih prostorov,
- določanju jedra in slike iz matrike linearne preslikave,
- štetju injektivnih oziroma surjektivnih linearnih preslikav nad končnim poljem.

Teoretični del spodaj dopolnjuje naloge iz vaj s standardnimi izreki linearne algebre, ki jih moraš poznati za ustni del.

---

## 1. Kaj moraš ob koncu faze obvladati

Po zaključku faze moraš znati brez pomoči:

1. preveriti, ali je preslikava $A:V\to W$ linearna;
2. uporabiti lastnosti linearnosti za računanje slik linearnih kombinacij;
3. ugotoviti, ali podane slike vektorjev enolično določajo linearno preslikavo;
4. preveriti, ali se delno podan predpis lahko razširi do linearne preslikave;
5. izračunati $\ker A$;
6. izračunati $\operatorname{Im}A$;
7. določiti $\operatorname{rang}A$ in $\operatorname{null}A$;
8. uporabiti izrek
   $$
   \dim V=\dim\ker A+\dim\operatorname{Im}A;
   $$
9. odločiti, ali je preslikava injektivna, surjektivna ali bijektivna;
10. prepoznati in določati linearne funkcionale;
11. odločiti, ali sta dva končnorazsežna vektorska prostora izomorfna;
12. preveriti, ali je konkretna linearna preslikava izomorfizem;
13. iz matrike preslikave poiskati bazi jedra in slike;
14. ustno natančno povedati glavne definicije in izreke ter dokazati najpomembnejše povezave.

---

## 2. Zemljevid pojmov

Najpomembnejše povezave v tej fazi so:

$$
\boxed{
A:V\to W\text{ linearna}
}
$$

$$
\Downarrow
$$

$$
\ker A=\{v\in V;A(v)=0\},
\qquad
\operatorname{Im}A=\{A(v);v\in V\}
$$

$$
\Downarrow
$$

$$
\operatorname{null}A=\dim\ker A,
\qquad
\operatorname{rang}A=\dim\operatorname{Im}A
$$

$$
\Downarrow
$$

$$
\dim V=
\operatorname{null}A+
\operatorname{rang}A
$$

Poleg tega:

$$
A\text{ injektivna}
\iff
\ker A=\{0\}
$$

in če sta $V$ in $W$ končnorazsežna ter

$$
\dim V=\dim W,
$$

potem velja:

$$
A\text{ injektivna}
\iff
A\text{ surjektivna}
\iff
A\text{ bijektivna}.
$$

Bijektivna linearna preslikava je **izomorfizem**.

---

# 3. Linearne preslikave

## 3.1 Definicija

Naj bosta $V$ in $W$ vektorska prostora nad istim poljem $F$.

Preslikava

$$
A:V\to W
$$

je **linearna**, če za vse $u,v\in V$ in vse $\alpha,\beta\in F$ velja

$$
A(\alpha u+\beta v)
=
\alpha A(u)+\beta A(v).
$$

Enakovredno lahko preverjamo dve lastnosti:

### Aditivnost

$$
A(u+v)=A(u)+A(v).
$$

### Homogenost

$$
A(\alpha u)=\alpha A(u).
$$

Če veljata obe, je $A$ linearna.

---

## 3.2 Najhitrejši nujni testi linearnosti

Preden začneš dolg račun, preveri najprej:

### Test ničelnega vektorja

Vsaka linearna preslikava mora zadovoljiti

$$
A(0)=0.
$$

Če je

$$
A(0)\neq0,
$$

preslikava **ni linearna**.

To je najhitrejši način za zavrnitev preslikav z dodano konstanto, na primer

$$
A(x,y)=(x+1,y).
$$

Ker

$$
A(0,0)=(1,0)\neq(0,0),
$$

preslikava ni linearna.

### Pozor

Pogoj $A(0)=0$ je samo **nujen**, ne pa zadosten.

Na primer

$$
A(x,y)=(|x|,y)
$$

ima

$$
A(0,0)=(0,0),
$$

vendar ni linearna.

---

## 3.3 Osnovne posledice linearnosti

Če je $A:V\to W$ linearna, potem:

$$
A(0)=0,
$$

$$
A(-v)=-A(v),
$$

$$
A(u-v)=A(u)-A(v).
$$

Za poljubne vektorje $v_1,\dots,v_k$ in skalarje $\alpha_1,\dots,\alpha_k$ velja

$$
A\left(
\sum_{i=1}^{k}\alpha_i v_i
\right)
=
\sum_{i=1}^{k}\alpha_iA(v_i).
$$

To je ena najpomembnejših formul celotne faze.

Če znaš nek vektor izraziti kot linearno kombinacijo vektorjev, katerih slike poznaš, lahko takoj izračunaš njegovo sliko.

---

## 3.4 Endomorfizem

Linearna preslikava

$$
A:V\to V
$$

se imenuje **endomorfizem** prostora $V$.

Pri endomorfizmih sta domena in kodomena isti prostor.

---

## 3.5 Identiteta in ničelna preslikava

**Identična preslikava**

$$
\operatorname{id}_V:V\to V
$$

je definirana z

$$
\operatorname{id}_V(v)=v.
$$

**Ničelna preslikava**

$$
0:V\to W
$$

je definirana z

$$
0(v)=0
$$

za vsak $v\in V$.

Obe sta linearni.

---

## 3.6 Kako prepoznam linearen predpis

Tipični linearni izrazi so sestavljeni samo iz linearnih kombinacij koordinat.

Primer:

$$
A(x,y,z)
=
(2x-y+3z,\;x+4y).
$$

To je linearna preslikava, ker ni:

- konstantnega člena,
- absolutne vrednosti,
- potenc koordinat,
- produkta koordinat,
- eksponentne funkcije,
- trigonometrične funkcije koordinat.

### Tipični nelinearni znaki

Preslikava je zelo verjetno nelinearna, če vsebuje:

$$
x^2,\quad xy,\quad |x|,\quad e^x,\quad\sin x
$$

ali dodano neničelno konstanto.

Toda na izpitu moraš nelinearnost **dokazati s protiprimerom ali kršitvijo lastnosti**, ne samo napisati, da izraz "ni linearen".

---

## 3.7 Pogoste napake

- Preveriš samo $A(0)=0$ in skleneš, da je preslikava linearna.
- Pri preverjanju homogenosti uporabiš samo en skalar.
- Pozabiš, da morata biti domena in kodomena prostora nad istim poljem.
- Pri preslikavi polinomov zamenjaš polinom $p$ z njegovo vrednostjo $p(x)$.
- Nelinearnost razlagaš samo intuitivno brez konkretne kršitve aksioma.

---

## 3.8 Ustno vprašanje

### Ustno vprašanje

**Vprašanje:** Kaj je linearna preslikava?

**Kratek odgovor:** Preslikava $A:V\to W$ med vektorskima prostoroma nad istim poljem je linearna, če za vse $u,v\in V$ in $\alpha,\beta\in F$ velja

$$
A(\alpha u+\beta v)=\alpha A(u)+\beta A(v).
$$

**Profesor lahko dodatno vpraša:** Ali lahko definicijo razdeliš na dva pogoja?

**Odgovor:** Da. Linearnost je ekvivalentna aditivnosti

$$
A(u+v)=A(u)+A(v)
$$

in homogenosti

$$
A(\alpha u)=\alpha A(u).
$$

---

### Ustno vprašanje

**Vprašanje:** Dokaži, da za linearno preslikavo velja $A(0)=0$.

**Kratek odgovor:**

Ker je $0=0+0$, velja

$$
A(0)=A(0+0)=A(0)+A(0).
$$

Po odštevanju $A(0)$ dobimo

$$
A(0)=0.
$$

**Profesor lahko dodatno vpraša:** Ali iz $A(0)=0$ sledi linearnost?

**Odgovor:** Ne. To je nujen, ne pa zadosten pogoj. Na primer $A(x)=x^2$ ima $A(0)=0$, vendar ni linearna.

---

# 4. Linearna preslikava je določena s slikami baze

## 4.1 Ključni izrek

Naj bo

$$
\Sigma=\{v_1,\dots,v_n\}
$$

baza prostora $V$.

Če poljubno izberemo vektorje

$$
w_1,\dots,w_n\in W,
$$

potem obstaja **natanko ena** linearna preslikava

$$
A:V\to W
$$

za katero velja

$$
A(v_i)=w_i
$$

za vsak $i$.

To je zelo pomemben izrek za naloge, kjer so podane slike nekaterih vektorjev.

---

## 4.2 Zakaj je baza pomembna

Vsak $v\in V$ se glede na bazo $\Sigma$ enolično izrazi kot

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n.
$$

Zato mora zaradi linearnosti veljati

$$
A(v)
=
\alpha_1A(v_1)+\cdots+\alpha_nA(v_n).
$$

Če poznamo slike baznih vektorjev, poznamo preslikavo na celotnem prostoru.

---

## 4.3 Če podani vektorji niso baza

Tu je treba biti previden.

### Če so linearno neodvisni, vendar jih je premalo

Predpis lahko praviloma razširimo tako, da množico dopolnimo do baze in poljubno določimo slike dodatnih baznih vektorjev.

Razširitev navadno ni enolična.

### Če so linearno odvisni

Podane slike morajo spoštovati **iste linearne relacije**.

Če

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0,
$$

mora veljati

$$
\alpha_1A(v_1)+\cdots+\alpha_kA(v_k)=0.
$$

Če to ne velja, linearna preslikava s takimi slikami **ne obstaja**.

---

## 4.4 Ustno vprašanje

### Ustno vprašanje

**Vprašanje:** Zakaj je linearna preslikava enolično določena s slikami baznih vektorjev?

**Kratek odgovor:** Ker se vsak vektor prostora enolično izrazi kot linearna kombinacija baznih vektorjev. Če je

$$
v=\sum_{i=1}^{n}\alpha_iv_i,
$$

potem mora zaradi linearnosti veljati

$$
A(v)=\sum_{i=1}^{n}\alpha_iA(v_i).
$$

Zato za noben $v$ nimamo več svobode pri izbiri $A(v)$.

**Profesor lahko dodatno vpraša:** Kaj se zgodi, če podani vektorji niso linearno neodvisni?

**Odgovor:** Njihove slike morajo zadovoljiti vse iste linearne relacije. Če neka relacija med vhodnimi vektorji po preslikavi ni ohranjena, linearna preslikava ne obstaja.

---

# 5. Jedro linearne preslikave

## 5.1 Definicija

Za linearno preslikavo

$$
A:V\to W
$$

je **jedro** definirano kot

$$
\boxed{
\ker A
=
\{v\in V;A(v)=0\}.
}
$$

Jedro je torej množica vseh vektorjev domene, ki se preslikajo v ničelni vektor kodomene.

---

## 5.2 Jedro je podprostor

Vedno velja

$$
\ker A\leq V.
$$

### Dokaz

Ker je $A(0)=0$, velja

$$
0\in\ker A.
$$

Naj bosta $u,v\in\ker A$ in $\alpha,\beta\in F$.

Potem

$$
A(u)=0,\qquad A(v)=0.
$$

Zato

$$
A(\alpha u+\beta v)
=
\alpha A(u)+\beta A(v)
=
0.
$$

Torej

$$
\alpha u+\beta v\in\ker A.
$$

S tem je $\ker A$ podprostor.

---

## 5.3 Kako računamo jedro

Če je preslikava podana s predpisom

$$
A(x_1,\dots,x_n)=\cdots,
$$

postavimo

$$
A(x_1,\dots,x_n)=0
$$

in rešimo homogeni sistem.

Če je preslikava podana z matriko $M$, rešimo

$$
Mx=0.
$$

Rešitve zapišemo parametrično in iz njih izluščimo bazo jedra.

---

## 5.4 Ničelnost

**Ničelnost** oziroma **nullity** preslikave je

$$
\operatorname{null}A
=
\dim\ker A.
$$

V nekaterih zapiskih se namesto $\operatorname{null}A$ uporablja samo izraz **razsežnost jedra**.

---

# 6. Slika oziroma zaloga vrednosti

## 6.1 Definicija

Za linearno preslikavo

$$
A:V\to W
$$

je **slika** oziroma **zaloga vrednosti**

$$
\boxed{
\operatorname{Im}A
=
\{A(v);v\in V\}.
}
$$

Vedno velja

$$
\operatorname{Im}A\leq W.
$$

---

## 6.2 Slika je podprostor

Naj bosta

$$
y_1=A(v_1),\qquad y_2=A(v_2)
$$

elementa slike.

Potem za $\alpha,\beta\in F$ velja

$$
\alpha y_1+\beta y_2
=
\alpha A(v_1)+\beta A(v_2)
=
A(\alpha v_1+\beta v_2).
$$

Zato je tudi $\alpha y_1+\beta y_2$ v sliki.

---

## 6.3 Kako računamo sliko

Če poznamo bazo domene

$$
\Sigma=\{v_1,\dots,v_n\},
$$

potem

$$
\boxed{
\operatorname{Im}A
=
L\{A(v_1),\dots,A(v_n)\}.
}
$$

Vsi ti vektorji niso nujno linearno neodvisni.

Za bazo slike moramo iz njih odstraniti linearno odvisne vektorje.

---

## 6.4 Slika iz matrike

Če je matrika preslikave v standardnih bazah

$$
M=
\begin{pmatrix}
| & | & & |\\
c_1 & c_2 & \cdots & c_n\\
| & | & & |
\end{pmatrix},
$$

potem

$$
\operatorname{Im}A
=
L\{c_1,\dots,c_n\}.
$$

Bazo slike dobimo iz **pivotnih stolpcev originalne matrike**.

### Zelo pomembno

Če matriko vrstično reduciramo, pivotne stolpce določimo iz reducirane matrike, vendar za bazo slike vzamemo ustrezne stolpce **iz originalne matrike**, ne iz reducirane.

---

# 7. Rang

## 7.1 Definicija

**Rang** linearne preslikave je razsežnost njene slike:

$$
\boxed{
\operatorname{rang}A
=
\dim\operatorname{Im}A.
}
$$

Če je preslikava predstavljena z matriko $M$, potem velja

$$
\operatorname{rang}A=\operatorname{rang}M.
$$

Rang je število pivotov v reducirani matriki.

---

## 7.2 Osnovne omejitve

Če je

$$
A:V\to W
$$

in sta prostora končnorazsežna, potem

$$
0\leq\operatorname{rang}A
\leq
\min\{\dim V,\dim W\}.
$$

Zato preslikava

$$
A:\mathbb R^3\to\mathbb R^4
$$

ne more imeti ranga $4$.

Največji možni rang je $3$.

---

# 8. Izrek o rangu in ničelnosti

## 8.1 Izrek

Naj bo

$$
A:V\to W
$$

linearna preslikava in naj bo $V$ končnorazsežen.

Potem velja

$$
\boxed{
\dim V
=
\dim\ker A+
\dim\operatorname{Im}A.
}
$$

oziroma

$$
\boxed{
\dim V
=
\operatorname{null}A+
\operatorname{rang}A.
}
$$

### Pogoj za uporabo

Ključni pogoj je, da je **domena $V$ končnorazsežna**.

---

## 8.2 Izpeljava formule

Naj bo

$$
\{u_1,\dots,u_k\}
$$

baza jedra.

Dopolnimo jo do baze prostora $V$:

$$
\{u_1,\dots,u_k,v_1,\dots,v_r\}.
$$

Potem se da pokazati, da

$$
\{A(v_1),\dots,A(v_r)\}
$$

tvori bazo slike $\operatorname{Im}A$.

Zato

$$
\dim\ker A=k,
$$

$$
\dim\operatorname{Im}A=r,
$$

in ker ima baza prostora $V$ skupaj $k+r$ elementov,

$$
\dim V=k+r.
$$

Torej

$$
\dim V=
\dim\ker A+\dim\operatorname{Im}A.
$$

---

## 8.3 Najpogostejše preureditve

Če poznaš rang:

$$
\dim\ker A
=
\dim V-\operatorname{rang}A.
$$

Če poznaš jedro:

$$
\operatorname{rang}A
=
\dim V-\dim\ker A.
$$

### Pomembno

V formuli nastopa

$$
\dim V,
$$

torej razsežnost **domene**, ne kodomene.

---

## 8.4 Ustno vprašanje

### Ustno vprašanje

**Vprašanje:** Povej izrek o rangu in ničelnosti.

**Kratek odgovor:** Če je $A:V\to W$ linearna preslikava in je $V$ končnorazsežen, potem

$$
\dim V
=
\dim\ker A+
\dim\operatorname{Im}A.
$$

**Profesor lahko dodatno vpraša:** Kateri prostor mora biti končnorazsežen?

**Odgovor:** Domena $V$.

**Profesor lahko dodatno vpraša:** Kako bi dokazal izrek?

**Odgovor:** Izberem bazo jedra, jo dopolnim do baze $V$ in pokažem, da slike dodanih baznih vektorjev tvorijo bazo slike.

---

# 9. Injektivnost, surjektivnost in bijektivnost

## 9.1 Injektivnost

Preslikava $A:V\to W$ je **injektivna**, če

$$
A(u)=A(v)
\Longrightarrow
u=v.
$$

Za linearne preslikave velja izredno pomemben kriterij:

$$
\boxed{
A\text{ je injektivna}
\iff
\ker A=\{0\}.
}
$$

### Dokaz

Če je $A$ injektivna in $A(v)=0=A(0)$, potem

$$
v=0.
$$

Zato

$$
\ker A=\{0\}.
$$

Obratno naj bo $\ker A=\{0\}$ in

$$
A(u)=A(v).
$$

Potem

$$
A(u-v)=0,
$$

zato

$$
u-v\in\ker A.
$$

Ker je jedro trivialno,

$$
u-v=0,
$$

torej

$$
u=v.
$$

---

## 9.2 Surjektivnost

Preslikava $A:V\to W$ je **surjektivna**, če je vsak element kodomene slika nekega elementa domene:

$$
\forall w\in W\;\exists v\in V:
A(v)=w.
$$

To je ekvivalentno pogoju

$$
\boxed{
\operatorname{Im}A=W.
}
$$

V končnorazsežnem primeru:

$$
\boxed{
A\text{ surjektivna}
\iff
\operatorname{rang}A=\dim W.
}
$$

---

## 9.3 Bijektivnost

Preslikava je **bijektivna**, če je hkrati:

- injektivna,
- surjektivna.

Bijektivna linearna preslikava je izomorfizem.

---

## 9.4 Dimenzijski hitri testi

Naj bo

$$
A:V\to W
$$

linearna in naj bosta prostora končnorazsežna.

### Če je

$$
\dim V>\dim W,
$$

preslikava **ne more biti injektivna**.

Razlog:

$$
\operatorname{rang}A\leq\dim W<\dim V,
$$

zato po izreku o rangu in ničelnosti

$$
\dim\ker A>0.
$$

### Če je

$$
\dim V<\dim W,
$$

preslikava **ne more biti surjektivna**.

### Če je

$$
\dim V=\dim W,
$$

potem

$$
\boxed{
A\text{ injektivna}
\iff
A\text{ surjektivna}
\iff
A\text{ bijektivna}.
}
$$

---

## 9.5 Ustno vprašanje

### Ustno vprašanje

**Vprašanje:** Kako karakteriziraš injektivnost linearne preslikave z jedrom?

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

Torej $u-v\in\ker A=\{0\}$ in zato $u=v$.

---

### Ustno vprašanje

**Vprašanje:** Kdaj je linearna preslikava surjektivna?

**Kratek odgovor:** Natanko tedaj, ko je

$$
\operatorname{Im}A=W.
$$

Če je $W$ končnorazsežen, je to ekvivalentno

$$
\operatorname{rang}A=\dim W.
$$

**Profesor lahko dodatno vpraša:** Ali je lahko linearna preslikava $\mathbb R^2\to\mathbb R^3$ surjektivna?

**Odgovor:** Ne, ker je njen rang največ $2$, kodomena pa ima razsežnost $3$.

---

# 10. Linearni funkcionali

## 10.1 Definicija

**Linearni funkcional** na vektorskem prostoru $V$ nad poljem $F$ je linearna preslikava

$$
f:V\to F.
$$

Za

$$
V=\mathbb R^n
$$

ima vsak linearni funkcional obliko

$$
f(x_1,\dots,x_n)
=
a_1x_1+\cdots+a_nx_n.
$$

---

## 10.2 Jedro linearnega funkcionala

Če je $f$ neničelni linearni funkcional na končnorazsežnem prostoru $V$, potem je

$$
\operatorname{Im}f=F.
$$

Ker je kodomena enorazsežna,

$$
\operatorname{rang}f=1.
$$

Po izreku o rangu in ničelnosti:

$$
\dim\ker f
=
\dim V-1.
$$

Torej je jedro neničelnega funkcionala podprostor kodimenzije $1$.

Za

$$
f(x,y,z)=ax+by+cz
$$

je jedro ravnina skozi izhodišče:

$$
ax+by+cz=0.
$$

---

## 10.3 Kako določimo funkcional iz pogojev

Če je

$$
f:\mathbb R_2[x]\to\mathbb R,
$$

zapišemo

$$
f(1)=a,\qquad
f(x)=b,\qquad
f(x^2)=c.
$$

Za

$$
p(x)=\alpha+\beta x+\gamma x^2
$$

potem

$$
f(p)=\alpha a+\beta b+\gamma c.
$$

Podane pogoje prevedemo v linearni sistem za $a,b,c$.

---

# 11. Izomorfizmi

## 11.1 Definicija

Linearna preslikava

$$
A:V\to W
$$

je **izomorfizem**, če je bijektivna.

Če obstaja izomorfizem med $V$ in $W$, pišemo

$$
V\cong W.
$$

---

## 11.2 Ključni izrek za končnorazsežne prostore

Če sta $V$ in $W$ končnorazsežna vektorska prostora nad istim poljem, potem

$$
\boxed{
V\cong W
\iff
\dim V=\dim W.
}
$$

To je najhitrejši test pri nalogah tipa:

> Kateri prostor je izomorfen $\mathbb R^3$?

Ni treba konstruirati konkretnega izomorfizma, če je vprašanje samo o obstoju. Dovolj je izračunati dimenzijo.

---

## 11.3 Kako preverimo konkreten predpis

Če je podan konkreten

$$
A:V\to W,
$$

moraš preveriti:

1. da je $A$ linearna;
2. da je bijektivna.

Če sta

$$
\dim V=\dim W<\infty,
$$

je dovolj po linearnosti preveriti samo eno od lastnosti:

- injektivnost ali
- surjektivnost.

Pri matriki kvadratnega tipa lahko preveriš tudi

$$
\det M\neq0.
$$

To pomeni, da je matrika obrnljiva, zato je preslikava izomorfizem.

---

## 11.4 Inverz izomorfizma

Če je

$$
A:V\to W
$$

izomorfizem, obstaja

$$
A^{-1}:W\to V.
$$

Pomembno dejstvo:

> Inverz bijektivne linearne preslikave je prav tako linearen.

---

## 11.5 Ustno vprašanje

### Ustno vprašanje

**Vprašanje:** Kaj je izomorfizem vektorskih prostorov?

**Kratek odgovor:** Izomorfizem je bijektivna linearna preslikava med vektorskima prostoroma.

**Profesor lahko dodatno vpraša:** Kdaj sta končnorazsežna prostora izomorfna?

**Odgovor:** Če in samo če imata enako dimenzijo, ob predpostavki, da sta prostora nad istim poljem.

---

### Ustno vprašanje

**Vprašanje:** Zakaj je $\mathbb R^3$ izomorfen $\mathbb R_2[x]$?

**Kratek odgovor:** Oba sta trirazsežna vektorska prostora nad $\mathbb R$:

$$
\dim\mathbb R^3=3,
$$

$$
\dim\mathbb R_2[x]=3.
$$

Na primer izomorfizem je

$$
A(a,b,c)=a+bx+cx^2.
$$

---

# 12. Tip naloge: preverjanje linearnosti

## Kako jo prepoznam

Podana je preslikava s formulo in vprašanje:

- ali je linearna,
- katere izmed preslikav so linearne,
- kateri predpis ni linearen.

---

## Postopek

1. Najprej preveri $A(0)$.
2. Če $A(0)\neq0$, takoj zaključi, da ni linearna.
3. Če ničelni test ne odloči, preveri
   $$
   A(\alpha u+\beta v)
   =
   \alpha A(u)+\beta A(v).
   $$
4. Pri očitno nelinearnih členih lahko uporabiš konkreten protiprimer.

---

## Pomembne formule

$$
A(u+v)=A(u)+A(v)
$$

$$
A(\lambda u)=\lambda A(u)
$$

---

## Primer 1

Naj bo

$$
A:\mathbb R^2\to\mathbb R^2,
\qquad
A(x,y)=(x,0).
$$

Ali je $A$ linearna?

## Rešitev

Naj bosta

$$
u=(x_1,y_1),\qquad v=(x_2,y_2),
$$

in $\alpha,\beta\in\mathbb R$.

Potem

$$
A(\alpha u+\beta v)
=
A(\alpha x_1+\beta x_2,\alpha y_1+\beta y_2)
$$

$$
=
(\alpha x_1+\beta x_2,0).
$$

Po drugi strani

$$
\alpha A(u)+\beta A(v)
=
\alpha(x_1,0)+\beta(x_2,0)
$$

$$
=
(\alpha x_1+\beta x_2,0).
$$

Zato je

$$
\boxed{A\text{ linearna}.}
$$

---

## Primer 2

Naj bo

$$
C(x,y)=(x+1,y).
$$

## Rešitev

$$
C(0,0)=(1,0)\neq(0,0).
$$

Ker mora za vsako linearno preslikavo veljati $C(0)=0$, preslikava ni linearna.

$$
\boxed{C\text{ ni linearna}.}
$$

---

## Primer 3

Naj bo

$$
E(x,y)=(|x|,y).
$$

## Rešitev

Vzamemo

$$
v=(1,0).
$$

Potem

$$
E(-v)=E(-1,0)=(1,0),
$$

medtem ko

$$
-E(v)=-(1,0)=(-1,0).
$$

Ker

$$
E(-v)\neq-E(v),
$$

preslikava ni linearna.

$$
\boxed{E\text{ ni linearna}.}
$$

---

## Pogoste napake

- Samo napišeš: "zaradi absolutne vrednosti ni linearna."
- Preveriš samo $A(0)=0$ in zaključiš, da je linearna.
- Pri dodani konstanti delaš dolg splošni izračun namesto hitrega testa $A(0)$.

---

# 13. Tip naloge: izračun slike z uporabo podanih slik vektorjev

## Kako jo prepoznam

Podane so vrednosti

$$
A(v_1),\dots,A(v_k)
$$

in iskati moraš

$$
A(v).
$$

Ključ je izraziti $v$ kot linearno kombinacijo podanih vektorjev.

---

## Postopek

1. Reši
   $$
   v=\alpha_1v_1+\cdots+\alpha_kv_k.
   $$
2. Uporabi linearnost:
   $$
   A(v)=\alpha_1A(v_1)+\cdots+\alpha_kA(v_k).
   $$
3. Izračunaj rezultat.

---

## Primer

Naj bo linearna preslikava

$$
A:\mathbb R_2[x]\to\mathbb R^2
$$

podana z

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

---

## Rešitev

Iščemo $\alpha,\beta,\gamma$, da

$$
1+x+x^2
=
\alpha(1+x)+
\beta(x+x^2)+
\gamma(1+x^2).
$$

Primerjava koeficientov da

$$
\alpha+\gamma=1,
$$

$$
\alpha+\beta=1,
$$

$$
\beta+\gamma=1.
$$

Od tod

$$
\alpha=\beta=\gamma=\frac12.
$$

Zato

$$
A(1+x+x^2)
=
\frac12A(1+x)
+
\frac12A(x+x^2)
+
\frac12A(1+x^2)
$$

$$
=
\frac12(1,0)
+
\frac12(0,-1)
+
\frac12(1,5)
$$

$$
=
(1,2).
$$

Torej

$$
\boxed{A(1+x+x^2)=(1,2).}
$$

---

## Pogoste napake

- Koeficiente pri polinomih primerjaš napačno.
- Pozabiš uporabiti iste koeficiente pri slikah.
- Predpostaviš, da so podani vektorji avtomatično baza, ne da bi to potreboval.

---

# 14. Tip naloge: ali se predpis lahko razširi do linearne preslikave

## Kako jo prepoznam

Podane so slike več vektorjev, nato vprašanje:

- ali obstaja linearna preslikava s temi vrednostmi,
- ali lahko predpis razširimo,
- ali lahko razširitev dodatno postane injektivna ali surjektivna.

---

## Osnovna ideja

Linearna preslikava mora ohraniti vse linearne relacije.

Če velja

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0,
$$

mora nujno veljati

$$
\alpha_1A(v_1)+\cdots+\alpha_kA(v_k)=0.
$$

---

## Postopek

1. Preveri linearno neodvisnost podanih vhodnih vektorjev.
2. Če so odvisni, poišči relacijo med njimi.
3. Preveri isto relacijo med slikami.
4. Če relacija ni ohranjena, linearna preslikava ne obstaja.
5. Če obstaja, šele nato preverjaj dodatne zahteve, kot sta injektivnost ali surjektivnost.

---

## Primer

Podani so

$$
v_1=(4,0,2),
$$

$$
v_2=(1,-1,0),
$$

$$
v_3=(3,1,2),
$$

in želimo linearno preslikavo $A:\mathbb R^3\to\mathbb R^4$, za katero bi veljalo

$$
A(v_1)=(2,-1,3,1),
$$

$$
A(v_2)=(0,1,3,0),
$$

$$
A(v_3)=(1,0,1,0).
$$

Ali taka linearna preslikava obstaja?

---

## Rešitev

Med vhodnimi vektorji velja

$$
-v_1+v_2+v_3=0,
$$

saj

$$
-(4,0,2)+(1,-1,0)+(3,1,2)=(0,0,0).
$$

Če bi bil $A$ linearen, bi moralo veljati

$$
-A(v_1)+A(v_2)+A(v_3)=0.
$$

Izračunamo:

$$
-(2,-1,3,1)+(0,1,3,0)+(1,0,1,0)
$$

$$
=
(-1,2,1,-1)\neq0.
$$

Relacija se ne ohrani.

Zato

$$
\boxed{
\text{taka linearna preslikava ne obstaja}.
}
$$

Posledično je tudi ni mogoče razširiti do injektivne linearne preslikave.

---

## Pogoste napake

- Takoj preverjaš injektivnost, preden preveriš, ali preslikava sploh obstaja.
- Preveriš samo število podanih vektorjev, ne njihove linearne odvisnosti.
- Poiščeš relacijo vhodov, nato pa pri slikah spremeniš koeficiente.

---

# 15. Tip naloge: izračun ranga iz predpisa linearne preslikave

## Kako jo prepoznam

Podana je formula

$$
A:\mathbb R^n\to\mathbb R^m
$$

in vprašanje za rang.

---

## Postopek

1. Izračunaj slike standardnih baznih vektorjev.
2. Te slike postavi kot stolpce matrike.
3. Vrstično reduciraj matriko.
4. Število pivotov je rang.

---

## Primer

Naj bo

$$
A:\mathbb R^3\to\mathbb R^4
$$

podana z

$$
A(a,b,c)
=
(a+2b-c,\,-2a-c,\,-2a+4b-4c,\;a+6b-4c).
$$

---

## Rešitev

Matrika v standardnih bazah je

$$
M=
\begin{pmatrix}
1 & 2 & -1\\
-2 & 0 & -1\\
-2 & 4 & -4\\
1 & 6 & -4
\end{pmatrix}.
$$

Po Gaussovi eliminaciji dobimo dve pivotni vrstici, na primer reducirano obliko

$$
\begin{pmatrix}
1 & 0 & \frac12\\
0 & 1 & -\frac34\\
0 & 0 & 0\\
0 & 0 & 0
\end{pmatrix}.
$$

Zato je

$$
\boxed{\operatorname{rang}A=2.}
$$

---

## Pogoste napake

- Rang enačiš s številom stolpcev.
- Pozabiš, da je največji možni rang $\min\{n,m\}$.
- Pri sliki vzameš vse stolpce kot bazo, čeprav so lahko linearno odvisni.

---

# 16. Tip naloge: jedro in slika iz matrike

## Kako jo prepoznam

Podana je matrika linearne preslikave in iskati moraš:

- $\ker A$,
- $\operatorname{Im}A$,
- bazo jedra,
- bazo slike,
- rang.

---

## Postopek za jedro

1. Reši
   $$
   Mx=0.
   $$
2. Izrazi vodilne spremenljivke s prostimi.
3. Zapiši splošno rešitev kot linearno kombinacijo.
4. Koeficientni vektorji parametrov tvorijo bazo jedra.

---

## Postopek za sliko

1. Vrstično reduciraj $M$.
2. Poišči pivotne stolpce.
3. Vzemi ustrezne stolpce **originalne matrike**.
4. Ti stolpci tvorijo bazo slike.

---

## Primer

Naj bo matrika linearne preslikave

$$
M=
\begin{pmatrix}
1 & -1 & 2\\
1 & -1 & 4
\end{pmatrix}.
$$

### Jedro

Rešujemo

$$
\begin{pmatrix}
1 & -1 & 2\\
1 & -1 & 4
\end{pmatrix}
\begin{pmatrix}
x\\y\\z
\end{pmatrix}
=
\begin{pmatrix}
0\\0
\end{pmatrix}.
$$

Sistem:

$$
x-y+2z=0,
$$

$$
x-y+4z=0.
$$

Odštejemo enačbi:

$$
2z=0
\Longrightarrow
z=0.
$$

Nato

$$
x-y=0
\Longrightarrow
x=y.
$$

Naj bo $x=y=t$. Potem

$$
(x,y,z)=t(1,1,0).
$$

Zato

$$
\boxed{
\ker A=L\{(1,1,0)\}.
}
$$

### Slika

Stolpci matrike so

$$
c_1=
\begin{pmatrix}
1\\1
\end{pmatrix},
\qquad
c_2=
\begin{pmatrix}
-1\\-1
\end{pmatrix},
\qquad
c_3=
\begin{pmatrix}
2\\4
\end{pmatrix}.
$$

Ker je

$$
c_2=-c_1
$$

in sta $c_1,c_3$ linearno neodvisna,

$$
\operatorname{Im}A
=
L\left\{
\begin{pmatrix}
1\\1
\end{pmatrix},
\begin{pmatrix}
2\\4
\end{pmatrix}
\right\}
=
\mathbb R^2.
$$

Torej

$$
\boxed{
\operatorname{Im}A=\mathbb R^2,
\qquad
\operatorname{rang}A=2.
}
$$

Preverjanje:

$$
\dim\ker A+\operatorname{rang}A
=
1+2=3
=
\dim\mathbb R^3.
$$

---

## Pogoste napake

- Za $\ker A$ rešuješ $Mx=b$ namesto $Mx=0$.
- Za sliko vzameš vrstice namesto stolpcev.
- Za bazo slike vzameš stolpce reducirane matrike namesto ustreznih stolpcev originalne matrike.
- Ne preveriš rezultata z izrekom o rangu in ničelnosti.

---

# 17. Tip naloge: rang oziroma dimenzija jedra iz izreka o rangu in ničelnosti

## Kako jo prepoznam

Podani so:

- domena,
- razsežnost jedra ali slike,
- morda generatorji jedra,

in iščeš preostalo razsežnost.

---

## Postopek

1. Določi $\dim V$.
2. Če je jedro podano z generatorji, najprej določi njihovo dejansko linearno neodvisnost.
3. Uporabi
   $$
   \dim V
   =
   \dim\ker A+
   \dim\operatorname{Im}A.
   $$

---

## Primer 1

Naj bo

$$
A:\mathbb R_5[x]\to\mathbb R^5
$$

linearna preslikava z

$$
\dim\operatorname{Im}A=2.
$$

Kolikšna je dimenzija jedra?

### Rešitev

Velja

$$
\dim\mathbb R_5[x]=6.
$$

Po izreku o rangu in ničelnosti:

$$
6
=
\dim\ker A+2.
$$

Zato

$$
\boxed{\dim\ker A=4.}
$$

---

## Primer 2

Naj bo

$$
A:\mathbb R_3[x]\to\mathbb R^7
$$

in

$$
\ker A
=
L\{1+x-x^2,\;x-x^3,\;-1+x^2-x^3\}.
$$

Določi $\dim\operatorname{Im}A$.

### Rešitev

Označimo

$$
p_1=1+x-x^2,
$$

$$
p_2=x-x^3,
$$

$$
p_3=-1+x^2-x^3.
$$

Opazimo:

$$
p_3=-p_1+p_2.
$$

Zato so generatorji jedra linearno odvisni in

$$
\dim\ker A=2.
$$

Ker

$$
\dim\mathbb R_3[x]=4,
$$

dobimo

$$
4=2+\dim\operatorname{Im}A.
$$

Torej

$$
\boxed{\dim\operatorname{Im}A=2.}
$$

---

## Pogoste napake

- Tri generatorje avtomatično šteješ kot dimenzijo $3$.
- Pozabiš, da je $\dim\mathbb R_n[x]=n+1$.
- V formulo vstaviš dimenzijo kodomene namesto domene.

---

# 18. Tip naloge: injektivnost in surjektivnost

## Kako jo prepoznam

Vprašanje zahteva:

- ali je $A$ injektivna,
- ali je $A$ surjektivna,
- ali obstaja preslikava z določeno lastnostjo.

---

## Najhitrejši kriteriji

### Injektivnost

$$
A\text{ injektivna}
\iff
\ker A=\{0\}.
$$

V končnorazsežnem primeru:

$$
A\text{ injektivna}
\iff
\operatorname{rang}A=\dim V.
$$

### Surjektivnost

$$
A\text{ surjektivna}
\iff
\operatorname{Im}A=W.
$$

V končnorazsežnem primeru:

$$
A\text{ surjektivna}
\iff
\operatorname{rang}A=\dim W.
$$

---

## Dimenzijski nemogoči primeri

Če

$$
\dim V>\dim W,
$$

injektivnost ni možna.

Če

$$
\dim V<\dim W,
$$

surjektivnost ni možna.

---

## Primer

Ali lahko obstaja injektivna linearna preslikava

$$
A:\mathbb R^4\to\mathbb R^3?
$$

## Rešitev

Za injektivnost bi moralo veljati

$$
\dim\ker A=0.
$$

Tedaj bi po izreku o rangu in ničelnosti dobili

$$
\operatorname{rang}A=4.
$$

Toda

$$
\operatorname{rang}A\leq\dim\mathbb R^3=3.
$$

Protislovje.

Zato

$$
\boxed{
\text{injektivna linearna preslikava }
\mathbb R^4\to\mathbb R^3
\text{ ne obstaja}.
}
$$

---

# 19. Tip naloge: linearni funkcional z danim jedrom

## Kako jo prepoznam

Podano je

$$
\ker f
$$

in iščeš funkcional

$$
f:\mathbb R^n\to\mathbb R.
$$

---

## Postopek

Za

$$
f(x_1,\dots,x_n)
=
a_1x_1+\cdots+a_nx_n
$$

vstavi generatorje jedra in zahtevaj, da se preslikajo v $0$.

Reši sistem za koeficiente $a_i$.

---

## Primer

Poišči neničelni linearni funkcional

$$
f:\mathbb R^3\to\mathbb R
$$

z

$$
\ker f
=
L\{(1,-1,0),(0,1,-1)\}.
$$

---

## Rešitev

Naj bo

$$
f(x,y,z)=ax+by+cz.
$$

Ker sta generatorja v jedru:

$$
f(1,-1,0)=a-b=0,
$$

$$
f(0,1,-1)=b-c=0.
$$

Zato

$$
a=b=c.
$$

Izberemo $a=b=c=1$.

Dobimo

$$
\boxed{
f(x,y,z)=x+y+z.
}
$$

Ker množenje funkcionala z neničelnim skalarjem ne spremeni jedra, so vse rešitve oblike

$$
f(x,y,z)=\lambda(x+y+z),
\qquad
\lambda\neq0.
$$

---

## Pogoste napake

- Pozabiš, da je funkcional neničeln.
- Meniš, da je rešitev enolična; jedro določa funkcional le do neničelnega skalarnega faktorja.
- Vektorje jedra vstaviš kot koeficiente funkcionala namesto kot argumente.

---

# 20. Tip naloge: vsi funkcionali, ki izpolnjujejo podane pogoje

## Kako jo prepoznam

Podane so vrednosti funkcionala na nekaj polinomih ali vektorjih.

---

## Primer

Poišči vse linearne funkcionale

$$
f:\mathbb R_2[x]\to\mathbb R
$$

za katere velja

$$
f(x^2-x)=1,
$$

$$
f(x+1)=2.
$$

---

## Rešitev

Naj bo

$$
f(1)=a,\qquad
f(x)=b,\qquad
f(x^2)=c.
$$

Iz prvega pogoja:

$$
c-b=1.
$$

Iz drugega:

$$
b+a=2.
$$

Naj bo

$$
a=t.
$$

Potem

$$
b=2-t,
$$

$$
c=3-t.
$$

Za

$$
p(x)=\alpha+\beta x+\gamma x^2
$$

so vsi iskani funkcionali

$$
\boxed{
f_t(p)
=
t\alpha+(2-t)\beta+(3-t)\gamma,
\qquad
t\in\mathbb R.
}
$$

Obstaja torej neskončno mnogo takih funkcionalov.

---

# 21. Tip naloge: prepoznavanje izomorfnih prostorov

## Kako jo prepoznam

Vprašanje je oblike:

> Kateri izmed prostorov je izomorfen $\mathbb R^n$?

Če so prostori končnorazsežni nad istim poljem, primerjaš samo dimenzije.

---

## Postopek

1. Izračunaj dimenzijo vsakega prostora.
2. Primerjaj z zahtevano dimenzijo.
3. Prostor je izomorfen natanko tedaj, ko ima isto dimenzijo.

---

## Primer

Naj bo

$$
U
=
L\{x^2,\;x-1,\;x^4-x^3\}
\leq\mathbb R_5[x].
$$

Ali je $U\cong\mathbb R^3$?

## Rešitev

Polinomi

$$
x^2,\qquad x-1,\qquad x^4-x^3
$$

imajo neničelne člene različnih najvišjih stopenj in so linearno neodvisni.

Zato tvorijo bazo svojega linearnega ogrinjača in

$$
\dim U=3.
$$

Ker

$$
\dim\mathbb R^3=3,
$$

sledi

$$
\boxed{U\cong\mathbb R^3.}
$$

---

# 22. Tip naloge: preverjanje, ali je konkreten predpis izomorfizem

## Kako jo prepoznam

Podan je konkreten predpis

$$
A:\mathbb R^n\to\mathbb R_{n-1}[x]
$$

ali med drugima prostoroma enake dimenzije.

---

## Postopek

1. Preveri linearnost.
2. Zapiši matriko preslikave glede na naravni bazi.
3. Preveri, ali ima poln rang oziroma ali je determinant neničeln.
4. Če je, je preslikava izomorfizem.

---

## Primer

Naj bo

$$
A:\mathbb R^3\to\mathbb R_2[x],
$$

$$
A(a,b,c)
=
a-b+(b-c)x+(c-a)x^2.
$$

Ali je $A$ izomorfizem?

---

## Rešitev

Glede na standardni bazi ima preslikava matriko

$$
M=
\begin{pmatrix}
1 & -1 & 0\\
0 & 1 & -1\\
-1 & 0 & 1
\end{pmatrix}.
$$

Izračunamo

$$
\det M=0.
$$

Zato matrika ni obrnljiva.

Ker imata domena in kodomena obe dimenzijo $3$, preslikava ni bijektivna.

Torej

$$
\boxed{A\text{ ni izomorfizem}.}
$$

Opazimo lahko tudi neposredno, da je

$$
A(1,1,1)=0,
$$

čeprav je $(1,1,1)\neq0$, zato jedro ni trivialno.

---

# 23. Tip naloge: štetje injektivnih in surjektivnih preslikav nad $\mathbb F_2$

Ta tip se pojavi v vajah in je nekoliko bolj kombinatoričen.

Naj bo

$$
\mathbb F_2=\{0,1\}.
$$

Velja

$$
|\mathbb F_2^n|=2^n.
$$

---

## 23.1 Injektivna preslikava

Naj bo

$$
A:\mathbb F_2^2\to\mathbb F_2^3
$$

in naj bo

$$
A(e_1)=(1,1,1).
$$

Koliko injektivnih linearnih preslikav obstaja?

### Rešitev

Ker je $A$ določena s slikama baze $e_1,e_2$, izbrati moramo še $A(e_2)$.

Za injektivnost morata biti

$$
A(e_1),A(e_2)
$$

linearno neodvisna.

V prostoru $\mathbb F_2^3$ je $8$ vektorjev.

Linearni ogrinjač neničelnega vektorja $(1,1,1)$ je

$$
L\{(1,1,1)\}
=
\{(0,0,0),(1,1,1)\}.
$$

Zato $A(e_2)$ ne sme biti nobeden od teh dveh vektorjev.

Možnosti:

$$
8-2=6.
$$

Torej

$$
\boxed{6}
$$

injektivnih preslikav.

---

## 23.2 Surjektivna preslikava

Naj bo

$$
A:\mathbb F_2^3\to\mathbb F_2^2
$$

in

$$
A(e_1)=0.
$$

Koliko surjektivnih linearnih preslikav obstaja?

### Rešitev

Za surjektivnost morata $A(e_2)$ in $A(e_3)$ tvoriti bazo prostora $\mathbb F_2^2$.

Za $A(e_2)$ imamo $3$ neničelne možnosti.

Ko je $A(e_2)$ izbran, njegov ogrinjač vsebuje

$$
\{0,A(e_2)\}.
$$

Za $A(e_3)$ zato ostaneta

$$
4-2=2
$$

možnosti.

Skupaj:

$$
3\cdot2=6.
$$

Torej

$$
\boxed{6}
$$

surjektivnih preslikav.

---

# 24. Hitra tabela za izbiro metode

| Če naloga sprašuje ... | Najprej naredi ... |
|---|---|
| Ali je $A$ linearna? | Preveri $A(0)$, nato aditivnost/homogenost |
| Izračunaj $A(v)$ iz znanih slik | Izrazi $v$ kot linearno kombinacijo |
| Ali podane slike določajo linearno preslikavo? | Preveri linearne relacije vhodnih vektorjev |
| Poišči $\ker A$ | Reši $A(v)=0$ oziroma $Mx=0$ |
| Poišči $\operatorname{Im}A$ | Preslikaj bazo domene oziroma vzemi stolpčni prostor |
| Poišči rang | Določi dimenzijo slike oziroma število pivotov |
| Poznaš $\dim\ker A$ | Uporabi rang–ničelnost |
| Poznaš rang | Uporabi rang–ničelnost za jedro |
| Ali je $A$ injektivna? | Preveri $\ker A=\{0\}$ |
| Ali je $A$ surjektivna? | Preveri $\operatorname{Im}A=W$ oziroma poln vrstični rang |
| Ali je konkretna $A$ izomorfizem? | Linearnost + bijektivnost/poln rang |
| Ali sta prostora izomorfna? | Primerjaj dimenziji |
| Poišči funkcional z danim jedrom | Zapiši splošno linearno obliko in vstavi generatorje jedra |
| Štetje nad $\mathbb F_q$ | Slike baznih vektorjev izbiraj tako, da ohranijo zahtevano neodvisnost/spanning |

---

# 25. Najpomembnejše povezave za ustni izpit

## 25.1 Jedro in injektivnost

$$
\ker A=\{0\}
\iff
A\text{ injektivna}.
$$

To moraš znati tudi dokazati.

---

## 25.2 Slika in surjektivnost

$$
\operatorname{Im}A=W
\iff
A\text{ surjektivna}.
$$

---

## 25.3 Rang in dimenzija

$$
\operatorname{rang}A
=
\dim\operatorname{Im}A.
$$

---

## 25.4 Rang in jedro

$$
\dim V
=
\dim\ker A+\operatorname{rang}A.
$$

---

## 25.5 Izomorfizem in dimenzija

Za končnorazsežna prostora nad istim poljem:

$$
V\cong W
\iff
\dim V=\dim W.
$$

---

## 25.6 Baza in linearna preslikava

Če je

$$
\Sigma=\{v_1,\dots,v_n\}
$$

baza $V$, je linearna preslikava popolnoma določena z

$$
A(v_1),\dots,A(v_n).
$$

To je neposredna priprava na naslednjo fazo, kjer bomo linearne preslikave zapisovali z matrikami.

---

# 26. Dokazi, ki jih moraš znati

Za ustni izpit pripravi najmanj naslednje dokaze.

## 26.1 $A(0)=0$

$$
A(0)=A(0+0)=A(0)+A(0)
$$

in zato

$$
A(0)=0.
$$

---

## 26.2 Jedro je podprostor

Pokaži:

1. $0\in\ker A$;
2. če $u,v\in\ker A$, potem
   $$
   A(\alpha u+\beta v)=0.
   $$

---

## 26.3 Slika je podprostor

Če sta

$$
y_1=A(v_1),\qquad y_2=A(v_2),
$$

potem

$$
\alpha y_1+\beta y_2
=
A(\alpha v_1+\beta v_2)
\in\operatorname{Im}A.
$$

---

## 26.4 Injektivnost in trivialno jedro

Znati oba koraka:

$$
A\text{ injektivna}
\Rightarrow
\ker A=\{0\},
$$

$$
\ker A=\{0\}
\Rightarrow
A\text{ injektivna}.
$$

---

## 26.5 Izrek o rangu in ničelnosti

Znati idejo:

1. izberi bazo jedra;
2. dopolni jo do baze domene;
3. pokaži, da slike dodanih vektorjev tvorijo bazo slike;
4. preštej elemente.

---

## 26.6 Linearna preslikava je določena s slikami baze

Če

$$
v=\sum_i\alpha_iv_i,
$$

potem mora biti

$$
A(v)=\sum_i\alpha_iA(v_i).
$$

Ker je razvoj po bazi enoličen, je tudi $A(v)$ enolično določen.

---

# 27. Dodatna ustna vprašanja

### Ustno vprašanje

**Vprašanje:** Kaj je jedro linearne preslikave?

**Kratek odgovor:**

$$
\ker A=\{v\in V;A(v)=0\}.
$$

Je podprostor domene $V$.

**Profesor lahko dodatno vpraša:** Kaj nam jedro pove?

**Odgovor:** Meri, koliko informacij preslikava "izgubi". Preslikava je injektivna natanko tedaj, ko je jedro trivialno.

---

### Ustno vprašanje

**Vprašanje:** Kaj je slika linearne preslikave?

**Kratek odgovor:**

$$
\operatorname{Im}A=\{A(v);v\in V\}.
$$

Je podprostor kodomene $W$.

**Profesor lahko dodatno vpraša:** Kako jo določiš iz baze domene?

**Odgovor:** Če je $\{v_1,\dots,v_n\}$ baza domene, potem

$$
\operatorname{Im}A=L\{A(v_1),\dots,A(v_n)\}.
$$

---

### Ustno vprašanje

**Vprašanje:** Kaj je rang linearne preslikave?

**Kratek odgovor:**

$$
\operatorname{rang}A=\dim\operatorname{Im}A.
$$

**Profesor lahko dodatno vpraša:** Kakšna je največja možna vrednost ranga preslikave $A:V\to W$?

**Odgovor:**

$$
\operatorname{rang}A
\leq
\min\{\dim V,\dim W\}.
$$

---

### Ustno vprašanje

**Vprašanje:** Naj bo $A:V\to W$ linearna in $\dim V=\dim W<\infty$. Zakaj je injektivnost ekvivalentna surjektivnosti?

**Kratek odgovor:** Če je $A$ injektivna, je $\dim\ker A=0$, zato po izreku o rangu in ničelnosti

$$
\operatorname{rang}A=\dim V=\dim W,
$$

zato je $A$ surjektivna. Obratno, če je surjektivna, je

$$
\operatorname{rang}A=\dim W=\dim V,
$$

zato je $\dim\ker A=0$ in je $A$ injektivna.

---

### Ustno vprašanje

**Vprašanje:** Ali lahko obstaja injektivna linearna preslikava iz večrazsežnega v manjrazsežni prostor?

**Kratek odgovor:** Ne, če sta prostora končnorazsežna in je

$$
\dim V>\dim W.
$$

Takrat je

$$
\operatorname{rang}A\leq\dim W<\dim V,
$$

zato je po izreku o rangu in ničelnosti jedro netrivialno.

---

### Ustno vprašanje

**Vprašanje:** Ali lahko obstaja surjektivna linearna preslikava iz manjrazsežnega v večrazsežni prostor?

**Kratek odgovor:** Ne. Če je

$$
\dim V<\dim W,
$$

je

$$
\operatorname{rang}A\leq\dim V<\dim W,
$$

zato slika ne more biti cel $W$.

---

### Ustno vprašanje

**Vprašanje:** Kaj je linearni funkcional?

**Kratek odgovor:** Linearni funkcional je linearna preslikava

$$
f:V\to F,
$$

kjer je $F$ osnovno polje prostora $V$.

**Profesor lahko dodatno vpraša:** Kakšna je razsežnost jedra neničelnega funkcionala na $n$-razsežnem prostoru?

**Odgovor:**

$$
\dim\ker f=n-1.
$$

---

# 28. Najpogostejše napake v celotni fazi

- $\dim\mathbb R_n[x]$ napišeš kot $n$ namesto $n+1$.
- Število generatorjev jedra zamenjaš z dimenzijo jedra.
- Pri rangu upoštevaš kodomeno namesto dejanske slike.
- Misliš, da je vsaka preslikava med prostoroma iste dimenzije izomorfizem.
- Pri injektivnosti preverjaš samo, ali so slike nekaterih vektorjev različne.
- Pri surjektivnosti preveriš samo, ali preslikava doseže nekaj neničelnih vektorjev.
- Pozabiš, da je jedro vedno v domeni, slika pa v kodomeni.
- Pri jedru matrike iščeš stolpčni prostor namesto rešitev homogenega sistema.
- Pri sliki matrike vzameš vrstice namesto stolpcev.
- Pri bazi slike uporabiš pivotne stolpce reducirane matrike namesto originalne matrike.
- Izrek o rangu in ničelnosti uporabiš z $\dim W$ namesto z $\dim V$.
- Pri delno podani preslikavi ne preveriš linearnih relacij med vhodnimi vektorji.
- Pri funkcionalu z danim jedrom pozabiš, da množenje z neničelnim skalarjem da isto jedro.
- Pri izomorfizmu primerjaš samo dimenzije, čeprav je vprašanje o **konkretnem predpisu**; dimenzije povedo le, da izomorfizem lahko obstaja.

---

# 29. Minimalni izpitni algoritem

Če dobiš neznano nalogo iz te faze, si postavi vprašanja v tem vrstnem redu:

1. **Ali je preslikava sploh linearna?**
2. **Kako je podana?**
   - formula,
   - slike vektorjev,
   - matrika,
   - jedro/slika.
3. **Ali poznam bazo domene?**
4. **Ali moram računati jedro?**
   $$
   A(v)=0.
   $$
5. **Ali moram računati sliko?**
   Preslikam bazo domene.
6. **Ali lahko uporabim rang–ničelnost?**
7. **Ali vprašanje o injektivnosti rešim prek jedra?**
8. **Ali vprašanje o surjektivnosti rešim prek ranga/slike?**
9. **Ali sta dimenziji domene in kodomene enaki?**
   Če da, postanejo injektivnost, surjektivnost in bijektivnost ekvivalentne.
10. **Če gre za izomorfnost prostorov, ali zadostuje primerjava dimenzij?**

---

# 30. Srednje težke naloge

## Naloga 1.

Preveri, ali je preslikava

$$
A:\mathbb R^3\to\mathbb R^2,
$$

$$
A(x,y,z)=(x-2y+z,\;3x+y)
$$

linearna.

Če je, določi

$$
A(1,-1,2).
$$

---

## Naloga 2.

Preveri linearnost preslikave

$$
B:\mathbb R^2\to\mathbb R^2,
$$

$$
B(x,y)=(x+y+2,\;x-y).
$$

---

## Naloga 3.

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2
$$

linearna preslikava in

$$
A(1,0,0)=(1,2),
$$

$$
A(0,1,0)=(-1,1),
$$

$$
A(0,0,1)=(2,0).
$$

Izračunaj

$$
A(2,-1,3).
$$

---

## Naloga 4.

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2
$$

podana z

$$
A(x,y,z)=(x+y+z,\;x-y).
$$

Poišči:

1. bazo $\ker A$,
2. bazo $\operatorname{Im}A$,
3. $\operatorname{rang}A$,
4. $\dim\ker A$.

---

## Naloga 5.

Naj bo

$$
A:\mathbb R_4[x]\to\mathbb R^3
$$

linearna preslikava in naj velja

$$
\dim\ker A=2.
$$

Določi

$$
\operatorname{rang}A.
$$

Ali je lahko $A$ surjektivna?

---

## Naloga 6.

Poišči vse linearne funkcionale

$$
f:\mathbb R^2\to\mathbb R
$$

za katere velja

$$
f(1,1)=3,
$$

$$
f(1,-1)=1.
$$

---

## Naloga 7.

Naj bo

$$
U=
\{(x,y,z,w)\in\mathbb R^4;\;x+y=0,\;z=0\}.
$$

Ali je $U$ izomorfen $\mathbb R^2$?

---

## Naloga 8.

Naj bo

$$
M=
\begin{pmatrix}
1 & 2 & -1\\
2 & 4 & -2\\
0 & 1 & 1
\end{pmatrix}
$$

matrika linearne preslikave

$$
A:\mathbb R^3\to\mathbb R^3.
$$

Določi:

1. rang,
2. dimenzijo jedra,
3. ali je $A$ injektivna,
4. ali je $A$ surjektivna.

---

# 31. Težke / izpitne naloge

## Naloga 9.

Podani so vektorji

$$
v_1=(1,1,0),
$$

$$
v_2=(0,1,1),
$$

$$
v_3=(1,2,1),
$$

in njihove želene slike

$$
w_1=(1,0),
$$

$$
w_2=(0,1),
$$

$$
w_3=(2,2).
$$

Ali obstaja linearna preslikava

$$
A:\mathbb R^3\to\mathbb R^2
$$

za katero velja

$$
A(v_i)=w_i
$$

za $i=1,2,3$?

Utemelji z linearno relacijo.

---

## Naloga 10.

Naj bo

$$
A:\mathbb R^4\to\mathbb R^3
$$

podana z

$$
A(x,y,z,w)
=
(x+y+z,\;y+z+w,\;x+2y+2z+w).
$$

Poišči:

1. bazo jedra,
2. bazo slike,
3. rang,
4. ničelnost,
5. ali je $A$ injektivna,
6. ali je $A$ surjektivna.

---

## Naloga 11.

Naj bo

$$
f:\mathbb R^4\to\mathbb R
$$

neničelni linearni funkcional in

$$
(1,-1,0,0),
\quad
(0,1,-1,0),
\quad
(0,0,1,-1)
$$

pripadajo $\ker f$.

Določi splošno obliko vseh takih funkcionalov in razsežnost njihovega jedra.

---

## Naloga 12.

Naj bo

$$
A:\mathbb R_2[x]\to\mathbb R^3
$$

linearna preslikava, za katero velja

$$
A(1)=(1,0,1),
$$

$$
A(x)=(0,1,1),
$$

$$
A(x^2)=(1,1,2).
$$

1. Določi $\ker A$.
2. Določi $\operatorname{Im}A$.
3. Določi rang.
4. Ali je $A$ izomorfizem?

---

## Naloga 13.

Naj bo

$$
A:\mathbb F_2^3\to\mathbb F_2^3
$$

linearna preslikava in naj velja

$$
A(e_1)=(1,0,0).
$$

Koliko različnih injektivnih linearnih preslikav $A$ obstaja?

---

## Naloga 14.

Za parameter $t\in\mathbb R$ je podana linearna preslikava

$$
A_t:\mathbb R^3\to\mathbb R^3
$$

z matriko

$$
M_t=
\begin{pmatrix}
1 & 1 & 0\\
0 & 1 & 1\\
1 & t & 1
\end{pmatrix}.
$$

Določi vse $t$, za katere je $A_t$ izomorfizem.

Za preostale vrednosti $t$ določi dimenzijo jedra.

---

## Naloga 15.

Naj bo

$$
V=
\{p\in\mathbb R_4[x];p(1)=0,\;p(-1)=0\}.
$$

1. Določi $\dim V$.
2. Ali je $V\cong\mathbb R^3$?
3. Poišči eno možno bazo prostora $V$.

---

# 32. Odgovori

**1.** Preslikava je linearna in

$$
A(1,-1,2)=(5,2).
$$

**2.**

$$
B(0,0)=(2,0)\neq0,
$$

zato $B$ ni linearna.

**3.**

$$
A(2,-1,3)
=
2(1,2)-(-1,1)+3(2,0)
=
(9,3).
$$

**4.**

$$
\ker A=L\{(1,1,-2)\},
$$

$$
\operatorname{Im}A=\mathbb R^2,
$$

$$
\operatorname{rang}A=2,
$$

$$
\dim\ker A=1.
$$

**5.**

$$
\dim\mathbb R_4[x]=5,
$$

zato

$$
\operatorname{rang}A=5-2=3.
$$

Da, $A$ je lahko in v tem primeru mora biti surjektivna, ker je kodomena $\mathbb R^3$.

**6.**

$$
f(x,y)=2x+y.
$$

**7.**

$$
\dim U=2,
$$

zato

$$
U\cong\mathbb R^2.
$$

**8.**

$$
\operatorname{rang}A=2,
$$

$$
\dim\ker A=1.
$$

$A$ ni injektivna in ni surjektivna.

**9.** Ne obstaja. Velja

$$
v_3=v_1+v_2,
$$

vendar

$$
w_3\neq w_1+w_2.
$$

**10.**

$$
\ker A
=
L\{(0,-1,1,0),\,(1,-1,0,1)\}.
$$

Ena baza slike je

$$
\{(1,0,1),(1,1,2)\}.
$$

$$
\operatorname{rang}A=2,
\qquad
\dim\ker A=2.
$$

$A$ ni injektivna in ni surjektivna.

**11.**

$$
f(x_1,x_2,x_3,x_4)
=
\lambda(x_1+x_2+x_3+x_4),
\qquad
\lambda\neq0.
$$

$$
\dim\ker f=3.
$$

**12.**

Ker

$$
A(x^2)=A(1)+A(x),
$$

velja

$$
x^2-x-1\in\ker A.
$$

Pravzaprav

$$
\ker A=L\{x^2-x-1\}.
$$

$$
\operatorname{Im}A
=
L\{(1,0,1),(0,1,1)\},
$$

$$
\operatorname{rang}A=2.
$$

$A$ ni izomorfizem.

**13.**

Za $A(e_2)$ je $6$ dovoljenih izbir, za $A(e_3)$ pa po izbiri prvih dveh slik $4$.

$$
\boxed{24}
$$

**14.**

$$
\det M_t=2-t.
$$

Zato je $A_t$ izomorfizem natanko za

$$
\boxed{t\neq2}.
$$

Za

$$
t=2
$$

je rang $2$ in

$$
\boxed{\dim\ker A_2=1}.
$$

**15.**

Ker mora biti polinom deljiv z

$$
(x-1)(x+1)=x^2-1,
$$

velja

$$
V=(x^2-1)\mathbb R_2[x].
$$

Zato

$$
\dim V=3,
$$

$$
V\cong\mathbb R^3.
$$

Ena baza je

$$
\boxed{
\{x^2-1,\;x^3-x,\;x^4-x^2\}.
}
$$

---

# 33. Faza je zaključena, ko znam ...

- [ ] natančno definirati linearno preslikavo;
- [ ] preveriti linearnost s pogojem $A(\alpha u+\beta v)=\alpha A(u)+\beta A(v)$;
- [ ] uporabiti $A(0)\neq0$ kot hiter dokaz nelinearnosti;
- [ ] poiskati konkreten protiprimer za nelinearnost;
- [ ] razložiti razliko med linearno preslikavo in endomorfizmom;
- [ ] dokazati $A(0)=0$;
- [ ] dokazati $A(-v)=-A(v)$;
- [ ] uporabiti linearnost na poljubni linearni kombinaciji;
- [ ] razložiti, zakaj slike baznih vektorjev enolično določajo linearno preslikavo;
- [ ] preveriti, ali podane slike linearno odvisnih vektorjev spoštujejo iste linearne relacije;
- [ ] odločiti, ali se delni predpis lahko razširi do linearne preslikave;
- [ ] natančno definirati $\ker A$;
- [ ] dokazati, da je $\ker A$ podprostor domene;
- [ ] iz formule preslikave rešiti enačbo $A(v)=0$ in določiti bazo jedra;
- [ ] iz matrike rešiti $Mx=0$ in določiti bazo jedra;
- [ ] natančno definirati $\operatorname{Im}A$;
- [ ] dokazati, da je $\operatorname{Im}A$ podprostor kodomene;
- [ ] poiskati sliko iz slik baznih vektorjev;
- [ ] poiskati bazo slike iz pivotnih stolpcev originalne matrike;
- [ ] definirati rang kot $\dim\operatorname{Im}A$;
- [ ] izračunati rang s Gaussovo eliminacijo;
- [ ] povedati omejitev $\operatorname{rang}A\leq\min\{\dim V,\dim W\}$;
- [ ] natančno povedati izrek o rangu in ničelnosti;
- [ ] vedeti, da v formuli nastopa dimenzija domene;
- [ ] uporabiti izrek za računanje dimenzije jedra ali slike;
- [ ] pojasniti idejo dokaza izreka o rangu in ničelnosti;
- [ ] definirati injektivnost;
- [ ] dokazati $A$ injektivna $\iff\ker A=\{0\}$;
- [ ] definirati surjektivnost;
- [ ] uporabiti $A$ surjektivna $\iff\operatorname{Im}A=W$;
- [ ] iz dimenzij hitro prepoznati, kdaj injektivnost ali surjektivnost ni mogoča;
- [ ] razložiti, zakaj sta pri enakih končnih dimenzijah injektivnost in surjektivnost ekvivalentni;
- [ ] definirati bijektivnost;
- [ ] definirati linearni funkcional;
- [ ] določiti funkcional iz njegovih vrednosti na bazi ali iz drugih linearnih pogojev;
- [ ] določiti funkcional iz podanega jedra;
- [ ] razložiti, zakaj ima neničelni funkcional na $n$-razsežnem prostoru jedro razsežnosti $n-1$;
- [ ] definirati izomorfizem;
- [ ] povedati in uporabiti izrek $V\cong W\iff\dim V=\dim W$ za končnorazsežna prostora nad istim poljem;
- [ ] razlikovati med vprašanjem "ali sta prostora izomorfna" in "ali je konkretna preslikava izomorfizem";
- [ ] preveriti konkreten izomorfizem z jedrom, rangom ali determinanto;
- [ ] reševati naloge nad $\mathbb F_2$, kjer štejemo injektivne ali surjektivne linearne preslikave;
- [ ] povezati jedro, sliko, rang, injektivnost, surjektivnost in izomorfizem brez gledanja v zapiske;
- [ ] na ustnem izpitu kratko in matematično natančno odgovoriti na vsa vprašanja iz tega poglavja;
- [ ] brez pomoči rešiti večino srednje težkih nalog in vsaj dve težki nalogi zapored pravilno.
