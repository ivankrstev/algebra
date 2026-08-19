# FAZA 9 — Ustni izpit: sistematična teorija

## Namen faze

Ta faza je namenjena **sistematični pripravi na ustni oziroma teoretični del izpita iz Algebre II – Linearne algebre**. Cilj ni samo znati računati, ampak znati:

- pravilno in natančno **definirati osnovne pojme**;
- pravilno **formulirati izreke skupaj s predpostavkami**;
- pojasniti **zakaj** določena metoda deluje;
- reproducirati najpomembnejše **dokaze in izpeljave**;
- povezovati sorodne pojme;
- na kratko in matematično natančno odgovoriti na tipična profesorjeva podvprašanja;
- pri računski nalogi prepoznati, katera teorija stoji za postopkom.

> **Opomba o virih.** V trenutno priloženem naboru so Vaje 1–12 za študijsko leto 2025/2026. Ločeni zapiski predavanj, kolokviji ali pretekli izpiti niso bili priloženi, zato je prioriteta določena predvsem po temah in tipih nalog, ki se pojavljajo v teh vajah. Standardna teorija, ki je nujna za razumevanje in ustni izpit, je dodana tam, kjer jo vaje uporabljajo posredno.

## Zemljevid snovi

1. **Dvomestne notranje operacije, grupe in kolobarji**
2. **Vektorski prostori in podprostori**
3. **Linearna kombinacija, linearna ogrinjača, linearna neodvisnost, ogrodje, baza in dimenzija**
4. **Vsota in presek podprostorov, direktna vsota**
5. **Linearne preslikave, jedro, slika, rang, injektivnost, surjektivnost, izomorfizmi**
6. **Linearni funkcionali**
7. **Urejene baze, koordinatni stolpci in prehodne matrike**
8. **Matrika linearne preslikave, kompozicija in sprememba baze**
9. **Invariantni podprostori**
10. **Projektorji in nilpotentni endomorfizmi**
11. **Karakteristični polinom**
12. **Lastne vrednosti, lastni vektorji in lastni podprostori**
13. **Diagonalizacija**

## Kako uporabljati to poglavje za ustni izpit

Za vsak pojem se nauči naslednji vrstni red:

1. **Definicija** — skoraj dobesedno.
2. **En značilen primer**.
3. **En protiprimer**, kadar je smiseln.
4. **Glavni izrek**, povezan s pojmom.
5. **Predpostavke izreka**.
6. **Ideja dokaza**.
7. **Povezava z računskimi nalogami**.
8. **Eno tipično profesorjevo podvprašanje**.

Pri ustnem odgovoru je praviloma bolje povedati kratek in popoln odgovor kot dolg odgovor z nejasnimi formulacijami.

---

## 1. Dvomestne notranje operacije, grupe in kolobarji

### 1.1 Dvomestna notranja operacija

Naj bo $S$ neprazna množica. **Dvomestna notranja operacija** na $S$ je preslikava

$$
\circ:S\times S\to S.
$$

Za vsak $a,b\in S$ mora biti rezultat $a\circ b$ ponovno element množice $S$.

#### Lastnosti operacije

Operacija $\circ$ je **asociativna**, če za vse $a,b,c\in S$ velja

$$
(a\circ b)\circ c=a\circ(b\circ c).
$$

Operacija je **komutativna**, če za vse $a,b\in S$ velja

$$
a\circ b=b\circ a.
$$

Element $e\in S$ je **nevtralni element**, če za vsak $a\in S$ velja

$$
e\circ a=a\circ e=a.
$$

Element $b\in S$ je **obrat elementa $a$**, če

$$
a\circ b=b\circ a=e.
$$

### 1.2 Grupa

**Grupa** je par $(G,\circ)$, kjer je $\circ$ dvomestna notranja operacija na $G$ in veljajo:

1. asociativnost;
2. obstoj nevtralnega elementa;
3. vsak element ima obrat.

Če je operacija še komutativna, je grupa **komutativna oziroma Abelova**.

#### Pomembne posledice

V grupi:

- je nevtralni element enoličen;
- je obrat vsakega elementa enoličen;
- veljata levi in desni zakon krajšanja;
- velja

$$
(a\circ b)^{-1}=b^{-1}\circ a^{-1}.
$$

#### Red elementa

Če obstaja najmanjši $n\in\mathbb N$ s

$$
a^n=e,
$$

je $n$ **red elementa $a$**. Če tak $n$ ne obstaja, ima element neskončen red.

Pri aditivnem zapisu namesto $a^n=e$ pišemo

$$
na=0.
$$

### 1.3 Kolobar

**Kolobar** $(R,+,\cdot)$ je množica z dvema operacijama, pri katerih:

- $(R,+)$ tvori Abelovo grupo;
- množenje je asociativno;
- veljata distributivnostni pravili

$$
a(b+c)=ab+ac,
$$

$$
(a+b)c=ac+bc.
$$

Če ima množenje nevtralni element $1$, govorimo o **kolobarju z enoto**.

Neničelni element $a$ je **levi delitelj niča**, če obstaja $b\neq 0$, da je

$$
ab=0.
$$

Analogno definiramo desni delitelj niča.

### Dokaz: enoličnost nevtralnega elementa

Predpostavimo, da je $e$ levi nevtralni element in $f$ desni nevtralni element. Potem

$$
e=e\circ f=f.
$$

Torej je nevtralni element enoličen.

### Dokaz: enoličnost obrata

Naj bosta $b$ in $c$ obrata elementa $a$. Tedaj

$$
b=b\circ e=b\circ(a\circ c)=(b\circ a)\circ c=e\circ c=c.
$$

Zato je obrat enoličen.

### Ustno vprašanje

**Vprašanje:** Kaj je grupa?

**Kratek odgovor:** Grupa je množica $G$ z asociativno notranjo operacijo, ki ima nevtralni element in v kateri ima vsak element obrat.

**Profesor lahko dodatno vpraša:** Ali mora biti operacija v grupi komutativna?

**Odgovor:** Ne. Če je dodatno komutativna, govorimo o Abelovi grupi.

### Ustno vprašanje

**Vprašanje:** Zakaj je nevtralni element enoličen?

**Kratek odgovor:** Če je $e$ levi in $f$ desni nevtralni element, potem $e=e\circ f=f$.

**Profesor lahko dodatno vpraša:** Ali je tudi obrat enoličen?

**Odgovor:** Da. Če sta $b$ in $c$ obrata elementa $a$, potem

$$
b=b\circ e=b\circ(a\circ c)=(b\circ a)\circ c=e\circ c=c.
$$

### Tip naloge: preverjanje, ali predpis definira grupo

**Kako jo prepoznam**

Dana je množica $G$ in nenavadno definirana operacija. Preveriti je treba grupne aksiome.

**Postopek**

1. Preveri zaprtost.
2. Preveri asociativnost.
3. Poišči nevtralni element.
4. Za poljuben element poišči obrat.
5. Če je potrebno, preveri komutativnost.

**Primer**

Na $G=\mathbb R\setminus\{-3\}$ definiramo

$$
a\circ b=(a+3)(b+3)-3.
$$

Ali je $(G,\circ)$ grupa?

**Rešitev**

Zaprtost: ker sta $a+3\neq 0$ in $b+3\neq 0$, je

$$
(a+3)(b+3)\neq 0,
$$

zato $a\circ b\neq -3$.

Asociativnost:

$$
(a\circ b)+3=(a+3)(b+3),
$$

zato

$$
((a\circ b)\circ c)+3=(a+3)(b+3)(c+3)
$$

in enako

$$
(a\circ(b\circ c))+3=(a+3)(b+3)(c+3).
$$

Nevtralni element $e$ zadošča

$$
(a+3)(e+3)-3=a,
$$

torej

$$
e+3=1,
$$

zato

$$
e=-2.
$$

Obrat $b$ elementa $a$ zadošča

$$
(a+3)(b+3)-3=-2,
$$

torej

$$
(a+3)(b+3)=1,
$$

zato

$$
b=\frac{1}{a+3}-3.
$$

Operacija je tudi komutativna. Torej je $(G,\circ)$ Abelova grupa.

**Pogoste napake**

- preverjanje samo identitete in obrata brez asociativnosti;
- pozabljena zaprtost;
- iskanje obrata glede na običajno seštevanje ali množenje namesto glede na dano operacijo.

### Tip naloge: kolobar in delitelji niča

**Kako jo prepoznam**

Podani sta dve operaciji ali matrični kolobar, vprašanje pa sprašuje po kolobarskih aksiomih, obrnljivosti ali deliteljih niča.

**Postopek**

1. Pri kolobarju najprej preveri Abelovo grupno strukturo za seštevanje.
2. Preveri asociativnost množenja.
3. Preveri distributivnost.
4. Pri delitelju niča išči neničelni $Y$, za katerega je $XY=0$ ali $YX=0$.

**Pomembna ideja**

V nekomutativnem kolobarju se lahko levi in desni delitelj niča razlikujeta.

---

## 2. Vektorski prostori in podprostori

### 2.1 Vektorski prostor

Naj bo $F$ polje. **Vektorski prostor nad $F$** je Abelova grupa $(V,+)$ skupaj z množenjem s skalarji

$$
F\times V\to V,\qquad (\lambda,v)\mapsto \lambda v,
$$

ki zadošča običajnim distributivnim in asociativnim aksiomom ter

$$
1v=v.
$$

Tipični primeri iz vaj:

- $\mathbb R^n$ nad $\mathbb R$;
- $\mathbb C^n$ nad $\mathbb C$;
- prostor polinomov $\mathbb R_n[x]$;
- prostor matrik $\mathbb R^{m\times n}$;
- različni podprostori teh prostorov.

### 2.2 Vektorski podprostor

Naj bo $V$ vektorski prostor nad $F$. Podmnožica $U\subseteq V$ je **vektorski podprostor**, če je sama vektorski prostor z operacijama, podedovanima iz $V$.

V praksi uporabljamo kriterij:

$$
U\leq V
$$

natanko tedaj, ko je $U\neq\varnothing$ in za vse $u,v\in U$ ter $\alpha,\beta\in F$ velja

$$
\alpha u+\beta v\in U.
$$

Ekvivalentno lahko preverimo:

- $0\in U$;
- $u,v\in U\Rightarrow u+v\in U$;
- $\lambda\in F,\ u\in U\Rightarrow \lambda u\in U$.

### Kako hitro prepoznati, da množica ni podprostor

Najprej preveri ničelni vektor. Če $0\notin U$, množica ni podprostor.

Pogosti razlogi za neuspeh:

- nehomogen pogoj, npr.

$$
x_1-x_n=1;
$$

- neenakost, npr.

$$
x_1\geq 0;
$$

- nelinearen pogoj, npr.

$$
x_1x_n=0;
$$

- pogoj obrnljivosti matrik;
- množica enotske krožnice.

### Pomembne lastnosti

Če sta $U,W\leq V$, je

$$
U\cap W\leq V.
$$

Unija $U\cup W$ pa je podprostor samo v posebnem primeru: kadar velja

$$
U\subseteq W
$$

ali

$$
W\subseteq U.
$$

### Ustno vprašanje

**Vprašanje:** Kaj je kriterij za podprostor?

**Kratek odgovor:** Neprazna podmnožica $U$ vektorskega prostora $V$ je podprostor natanko tedaj, ko je zaprta za vse linearne kombinacije dveh svojih elementov:

$$
u,v\in U,\ \alpha,\beta\in F
\Longrightarrow
\alpha u+\beta v\in U.
$$

**Profesor lahko dodatno vpraša:** Zakaj mora vsak podprostor vsebovati ničelni vektor?

**Odgovor:** Če je $u\in U$, potem zaradi zaprtosti za množenje s skalarjem velja

$$
0u=0\in U.
$$

### Ustno vprašanje

**Vprašanje:** Ali je množica rešitev sistema $Ax=b$ vedno podprostor?

**Kratek odgovor:** Ne. Množica rešitev homogenega sistema $Ax=0$ je podprostor, saj je enaka $\ker A$. Pri $b\neq 0$ množica rešitev praviloma ne vsebuje ničelnega vektorja in je afina množica, ne podprostor.

**Profesor lahko dodatno vpraša:** Kaj pa če sistem $Ax=b$ nima rešitev?

**Odgovor:** Prazna množica ni vektorski podprostor.

### Tip naloge: preverjanje podprostora in določitev baze

**Kako jo prepoznam**

Množica je podana s parametri ali z linearnimi enačbami.

**Postopek**

1. Preveri, ali je pogoj homogen in linearen.
2. Parametriziraj elemente.
3. Zapiši jih kot linearno kombinacijo generatorjev.
4. Iz generatorjev izberi linearno neodvisno množico.
5. Število baznih vektorjev je dimenzija.

**Primer**

Naj bo

$$
U=\{(2z,w,z);z,w\in\mathbb C\}\subseteq\mathbb C^3.
$$

Določi bazo in dimenzijo.

**Rešitev**

Vsak element je oblike

$$
(2z,w,z)=z(2,0,1)+w(0,1,0).
$$

Zato

$$
U=L\{(2,0,1),(0,1,0)\}.
$$

Vektorja sta linearno neodvisna, zato je

$$
\mathcal B=\{(2,0,1),(0,1,0)\}
$$

baza prostora $U$ in

$$
\dim U=2.
$$

**Pogoste napake**

- zamenjava števila parametrov z dimenzijo brez preverjanja neodvisnosti;
- pozabljeno preverjanje ničelnega vektorja;
- trditev, da je vsak sistem linearnih enačb podprostor, tudi če je nehomogen.

---

## 3. Linearna kombinacija, ogrinjača, linearna neodvisnost, baza in dimenzija

### 3.1 Linearna kombinacija

Vektor $v$ je **linearna kombinacija** vektorjev $v_1,\dots,v_k$, če obstajajo skalarji $\alpha_1,\dots,\alpha_k$ s

$$
v=\alpha_1v_1+\cdots+\alpha_kv_k.
$$

### 3.2 Linearna ogrinjača

**Linearna ogrinjača** množice $S=\{v_1,\dots,v_k\}$ je

$$
L(S)=
\left\{
\alpha_1v_1+\cdots+\alpha_kv_k;
\alpha_i\in F
\right\}.
$$

Je najmanjši podprostor, ki vsebuje vse elemente množice $S$.

Če je

$$
L(S)=V,
$$

je $S$ **ogrodje** prostora $V$.

### 3.3 Linearna neodvisnost

Vektorji $v_1,\dots,v_k$ so **linearno neodvisni**, če iz

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0
$$

sledi

$$
\alpha_1=\cdots=\alpha_k=0.
$$

Če obstaja netrivialna rešitev, so linearno odvisni.

#### Hitri kriteriji

- množica, ki vsebuje $0$, je linearno odvisna;
- v $n$-razsežnem prostoru je več kot $n$ vektorjev linearno odvisnih;
- manj kot $n$ vektorjev ne more generirati $n$-razsežnega prostora;
- $n$ linearno neodvisnih vektorjev v $n$-razsežnem prostoru že tvori bazo;
- $n$ generatorjev $n$-razsežnega prostora že tvori bazo.

### 3.4 Baza

**Baza** prostora $V$ je linearno neodvisno ogrodje prostora $V$.

Vsak $v\in V$ se glede na bazo

$$
\mathcal B=(v_1,\dots,v_n)
$$

enolično izrazi kot

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n.
$$

### 3.5 Dimenzija

Če je $V$ končnorazsežen in ima baza $n$ elementov, definiramo

$$
\dim V=n.
$$

Vse baze končnorazsežnega vektorskega prostora imajo enako število elementov.

Tipični primeri:

$$
\dim\mathbb R^n=n,
$$

$$
\dim\mathbb R_n[x]=n+1,
$$

$$
\dim\mathbb R^{m\times n}=mn.
$$

### Pomembni izreki

#### Izrek o dopolnitvi linearno neodvisne množice do baze

Če je $V$ končnorazsežen in je

$$
S=\{v_1,\dots,v_k\}
$$

linearno neodvisna množica, lahko $S$ dopolnimo do baze prostora $V$.

#### Izrek o krčenju ogrodja

Iz vsakega končnega ogrodja lahko odstranimo odvečne vektorje in dobimo bazo.

### Ustno vprašanje

**Vprašanje:** Kaj je baza?

**Kratek odgovor:** Baza je linearno neodvisno ogrodje vektorskega prostora.

**Profesor lahko dodatno vpraša:** Zakaj je razvoj vektorja po bazi enoličen?

**Odgovor:** Če bi veljalo

$$
v=\sum_i\alpha_iv_i=\sum_i\beta_iv_i,
$$

bi dobili

$$
\sum_i(\alpha_i-\beta_i)v_i=0.
$$

Ker so bazni vektorji linearno neodvisni, je

$$
\alpha_i=\beta_i
$$

za vsak $i$.

### Ustno vprašanje

**Vprašanje:** Naj bo $\dim V=n$. Kaj zadošča pokazati za množico $n$ vektorjev, da je baza?

**Kratek odgovor:** Zadošča pokazati bodisi linearno neodvisnost bodisi da množica generira $V$.

**Profesor lahko dodatno vpraša:** Zakaj?

**Odgovor:** V $n$-razsežnem prostoru ima vsaka linearno neodvisna množica največ $n$ elementov, vsako ogrodje pa najmanj $n$ elementov. Zato pri natanko $n$ vektorjih ena od obeh lastnosti implicira drugo.

### Tip naloge: linearna neodvisnost, ogrodje in baza

**Kako jo prepoznam**

Podana je množica vektorjev, polinomov ali matrik in vprašanje, ali je linearno neodvisna, ogrodje ali baza.

**Postopek**

1. Prevedi objekte v koordinatne stolpce glede na priročno standardno bazo.
2. Stolpce postavi v matriko.
3. Izračunaj rang oziroma uporabi Gaussovo eliminacijo.
4. Primerjaj rang s številom vektorjev in dimenzijo prostora.

**Pomembne formule**

Za matriko

$$
M=
\begin{pmatrix}
| & & |\\
v_1&\cdots&v_k\\
| & & |
\end{pmatrix}
$$

velja:

- stolpci so linearno neodvisni natanko tedaj, ko je

$$
\operatorname{rang}M=k;
$$

- generirajo $V$ dimenzije $n$ natanko tedaj, ko je

$$
\operatorname{rang}M=n.
$$

**Primer**

V prostoru $\mathbb R_5[x]$ obravnavamo

$$
N=
\{x-1,\ x^2-x,\ x^3-x^2,\ x^4-x^3,\ x^5-x^4\}.
$$

Ali je $N$ linearno neodvisna? Ali je ogrodje ali baza $\mathbb R_5[x]$?

**Rešitev**

Predpostavimo

$$
a_1(x-1)+a_2(x^2-x)+a_3(x^3-x^2)+a_4(x^4-x^3)+a_5(x^5-x^4)=0.
$$

Primerjava koeficienta pri $x^5$ da

$$
a_5=0.
$$

Nato pri $x^4$ dobimo $a_4=0$, pri $x^3$ dobimo $a_3=0$, pri $x^2$ dobimo $a_2=0$ in pri $x$ še $a_1=0$.

Množica je torej linearno neodvisna.

Ker je

$$
\dim\mathbb R_5[x]=6
$$

in ima $N$ samo $5$ elementov, ne more biti ogrodje celotnega prostora. Zato tudi ni baza.

**Pogoste napake**

- pozabljanje, da ima $\mathbb R_n[x]$ dimenzijo $n+1$;
- sklepanje, da je množica baza samo zato, ker je linearno neodvisna;
- zamenjava vrstičnega in stolpčnega ranga v interpretaciji generatorjev.

---

## 4. Vsota, presek in direktna vsota podprostorov

### 4.1 Vsota podprostorov

Za $U,W\leq V$ definiramo

$$
U+W=\{u+w;u\in U,\ w\in W\}.
$$

$U+W$ je najmanjši podprostor, ki vsebuje $U$ in $W$.

### 4.2 Presek podprostorov

$$
U\cap W=\{v\in V;v\in U\text{ in }v\in W\}.
$$

Presek podprostorov je vedno podprostor.

### 4.3 Formula za dimenzijo

Če sta $U$ in $W$ končnorazsežna, velja

$$
\dim(U+W)=\dim U+\dim W-\dim(U\cap W).
$$

Ekvivalentno:

$$
\dim(U\cap W)=\dim U+\dim W-\dim(U+W).
$$

#### Pomembne meje

Ker je $U+W\leq V$,

$$
\dim(U+W)\leq \dim V.
$$

Zato

$$
\dim(U\cap W)\geq \dim U+\dim W-\dim V.
$$

Vedno tudi

$$
\dim(U\cap W)\leq \min\{\dim U,\dim W\}.
$$

### 4.4 Direktna vsota

Pišemo

$$
V=U\oplus W
$$

če velja

$$
V=U+W
$$

in

$$
U\cap W=\{0\}.
$$

Ekvivalentno: vsak $v\in V$ se enolično zapiše kot

$$
v=u+w,
\qquad
u\in U,\ w\in W.
$$

### Dokaz dimenzijske formule

Naj bo

$$
\{z_1,\dots,z_r\}
$$

baza $U\cap W$.

Dopolnimo jo do baze $U$:

$$
\{z_1,\dots,z_r,u_1,\dots,u_p\},
$$

in do baze $W$:

$$
\{z_1,\dots,z_r,w_1,\dots,w_q\}.
$$

Potem je

$$
\{z_1,\dots,z_r,u_1,\dots,u_p,w_1,\dots,w_q\}
$$

baza $U+W$. Zato

$$
\dim(U+W)=r+p+q.
$$

Po drugi strani

$$
\dim U=r+p,
$$

$$
\dim W=r+q.
$$

Sledi

$$
\dim(U+W)=\dim U+\dim W-\dim(U\cap W).
$$

### Ustno vprašanje

**Vprašanje:** Kdaj je vsota $U+W$ direktna?

**Kratek odgovor:** Natanko tedaj, ko je

$$
U\cap W=\{0\}.
$$

**Profesor lahko dodatno vpraša:** Kaj to pomeni za zapis vektorja iz $U+W$?

**Odgovor:** Vsak vektor ima enoličen zapis $u+w$ z $u\in U$ in $w\in W$.

### Tip naloge: dimenzije vsote in preseka

**Kako jo prepoznam**

Podane so dimenzije $U$, $W$ in morda $U\cap W$ ali $U+W$.

**Postopek**

Uporabi

$$
\dim(U+W)=\dim U+\dim W-\dim(U\cap W).
$$

Vedno preveri še omejitev

$$
\dim(U+W)\leq \dim V.
$$

**Primer**

Naj bo

$$
\dim U=6,\qquad
\dim W=7,\qquad
\dim(U\cap W)=3.
$$

Potem

$$
\dim(U+W)=6+7-3=10.
$$

### Tip naloge: konkretni bazi $P$, $R$, $P\cap R$ in $P+R$

**Kako jo prepoznam**

Podprostora sta podana z generatorji, pogosto v prostoru polinomov ali v $\mathbb R^n$.

**Postopek**

1. Iz generatorjev $P$ izberi bazo.
2. Iz generatorjev $R$ izberi bazo.
3. Za presek rešuj enačbo

$$
P\alpha=R\beta.
$$

4. Dobljene vektorje po potrebi skrči na bazo.
5. Za vsoto združi generatorje obeh prostorov in izberi maksimalno linearno neodvisno podmnožico.

**Primer**

V $\mathbb R_3[x]$ naj bo

$$
P=L\{1+x^2+2x^3,\ 2-x+x^2+2x^3,\ 1+x+x^2+x^3\},
$$

$$
R=L\{1+x^3,\ 3+x^3,\ 1+x\}.
$$

**Rešitev**

V koordinatah glede na $(1,x,x^2,x^3)$ dobimo

$$
p_1=(1,0,1,2),
$$

$$
p_2=(2,-1,1,2),
$$

$$
p_3=(1,1,1,1),
$$

$$
r_1=(1,0,0,1),
$$

$$
r_2=(3,0,0,1),
$$

$$
r_3=(1,1,0,0).
$$

Oba trojčka sta linearno neodvisna, zato

$$
\dim P=\dim R=3.
$$

Iz enačbe

$$
a_1p_1+a_2p_2+a_3p_3
=
b_1r_1+b_2r_2+b_3r_3
$$

dobimo dve neodvisni rešitvi, ki dajeta

$$
1-x^3
$$

in

$$
x-x^3.
$$

Zato

$$
P\cap R=L\{1-x^3,\ x-x^3\}.
$$

Torej

$$
\dim(P\cap R)=2.
$$

Po dimenzijski formuli

$$
\dim(P+R)=3+3-2=4.
$$

Ker je

$$
\dim\mathbb R_3[x]=4,
$$

sledi

$$
P+R=\mathbb R_3[x].
$$

Ena možna baza vsote je

$$
\{p_1,p_2,p_3,r_1\}.
$$

**Pogoste napake**

- presek generatorjev ni isto kot presek prostorov;
- pri enačbi $P\alpha=R\beta$ se ne išče samo en skupni generator;
- po združitvi generatorjev vsote je treba odstraniti linearno odvisne.

---

## 5. Linearne preslikave, jedro, slika, rang in izomorfizmi

### 5.1 Linearna preslikava

Preslikava

$$
A:V\to W
$$

je **linearna**, če za vse $u,v\in V$ in $\alpha,\beta\in F$ velja

$$
A(\alpha u+\beta v)=\alpha A(u)+\beta A(v).
$$

Ekvivalentno lahko preverimo:

$$
A(u+v)=A(u)+A(v)
$$

in

$$
A(\lambda u)=\lambda A(u).
$$

Vsaka linearna preslikava zadošča

$$
A(0)=0.
$$

To je zelo uporaben hiter test: če $A(0)\neq 0$, preslikava ni linearna.

### 5.2 Jedro

**Jedro** linearne preslikave je

$$
\ker A=\{v\in V;A(v)=0\}.
$$

Velja

$$
\ker A\leq V.
$$

### 5.3 Slika

**Slika** oziroma **zaloga vrednosti** je

$$
\operatorname{Im}A=\{A(v);v\in V\}.
$$

Velja

$$
\operatorname{Im}A\leq W.
$$

### 5.4 Rang in ničelnost

**Rang** preslikave je

$$
\operatorname{rang}A=\dim(\operatorname{Im}A).
$$

**Ničelnost** je

$$
\operatorname{null}A=\dim(\ker A).
$$

### 5.5 Izrek o rangu in ničelnosti

Če je $V$ končnorazsežen in

$$
A:V\to W
$$

linearna, potem

$$
\boxed{
\dim V=\dim(\ker A)+\dim(\operatorname{Im}A)
}
$$

oziroma

$$
\dim V=\operatorname{null}A+\operatorname{rang}A.
$$

#### Pogoji

- $A$ mora biti linearna;
- domena $V$ mora biti končnorazsežna.

### Dokaz izreka o rangu in ničelnosti

Naj bo

$$
\{v_1,\dots,v_k\}
$$

baza $\ker A$.

Dopolnimo jo do baze prostora $V$:

$$
\{v_1,\dots,v_k,v_{k+1},\dots,v_n\}.
$$

Tedaj trdimo, da je

$$
\{A(v_{k+1}),\dots,A(v_n)\}
$$

baza $\operatorname{Im}A$.

Generatorstvo sledi iz razvoja poljubnega $v\in V$ po bazi. Linearna neodvisnost sledi tako: če

$$
\sum_{i=k+1}^n\alpha_iA(v_i)=0,
$$

potem

$$
A\left(\sum_{i=k+1}^n\alpha_iv_i\right)=0,
$$

zato je ta linearna kombinacija v $\ker A$. Ker pa je zapisana samo z vektorji $v_{k+1},\dots,v_n$, mora biti zaradi baze vsak $\alpha_i=0$.

Zato

$$
\dim(\operatorname{Im}A)=n-k,
$$

in

$$
n=k+(n-k).
$$

### 5.6 Injektivnost in surjektivnost

$A$ je **injektivna**, če

$$
A(u)=A(v)\Rightarrow u=v.
$$

Za linearno preslikavo velja ključni kriterij

$$
\boxed{
A\text{ je injektivna}
\iff
\ker A=\{0\}.
}
$$

$A$ je **surjektivna**, če

$$
\operatorname{Im}A=W.
$$

Če sta $V$ in $W$ končnorazsežna in

$$
\dim V=\dim W,
$$

potem za linearno preslikavo $A:V\to W$ velja

$$
A\text{ injektivna}
\iff
A\text{ surjektivna}
\iff
A\text{ bijektivna}.
$$

### 5.7 Izomorfizem

**Izomorfizem** je bijektivna linearna preslikava.

Končnorazsežna vektorska prostora nad istim poljem sta izomorfna natanko tedaj, ko imata enako dimenzijo.

### 5.8 Linearna preslikava je določena s slikami baze

Če je

$$
\mathcal B=(v_1,\dots,v_n)
$$

baza $V$ in poljubno izberemo $w_1,\dots,w_n\in W$, obstaja natanko ena linearna preslikava

$$
A:V\to W
$$

s

$$
A(v_i)=w_i.
$$

To je temelj za konstrukcijo matrike linearne preslikave.

### Ustno vprašanje

**Vprašanje:** Kako definiramo jedro in sliko linearne preslikave?

**Kratek odgovor:**

$$
\ker A=\{v\in V;A(v)=0\},
$$

$$
\operatorname{Im}A=\{A(v);v\in V\}.
$$

Jedro je podprostor domene, slika pa podprostor kodomene.

**Profesor lahko dodatno vpraša:** Kako iz jedra prepoznaš injektivnost?

**Odgovor:**

$$
A\text{ je injektivna}\iff\ker A=\{0\}.
$$

### Ustno vprašanje

**Vprašanje:** Formuliraj izrek o rangu in ničelnosti.

**Kratek odgovor:** Če je $A:V\to W$ linearna in je $V$ končnorazsežen, potem

$$
\dim V=\dim\ker A+\dim\operatorname{Im}A.
$$

**Profesor lahko dodatno vpraša:** Zakaj v izreku nastopa dimenzija domene in ne kodomene?

**Odgovor:** Ker dokaz začnemo z bazo jedra v domeni in jo dopolnimo do baze celotne domene. Slike dopolnilnih baznih vektorjev nato tvorijo bazo slike.

### Tip naloge: preverjanje linearnosti

**Kako jo prepoznam**

Podan je ekspliciten predpis $A(x)$.

**Postopek**

1. Najprej preveri $A(0)$.
2. Če je $A(0)\neq 0$, takoj sledi, da $A$ ni linearna.
3. Sicer preveri

$$
A(\alpha u+\beta v)=\alpha A(u)+\beta A(v).
$$

**Primer**

$$
C:\mathbb R^2\to\mathbb R^2,
\qquad
C(x,y)=(x+1,y).
$$

**Rešitev**

$$
C(0,0)=(1,0)\neq(0,0).
$$

Zato $C$ ni linearna.

### Tip naloge: določitev preslikave iz slik vektorjev

**Kako jo prepoznam**

Podane so slike več vektorjev in treba je izračunati sliko novega vektorja.

**Postopek**

1. Novi vektor izrazi kot linearno kombinacijo podanih vektorjev.
2. Uporabi linearnost.

**Primer**

Naj bo $A:\mathbb R_2[x]\to\mathbb R^2$ linearna in

$$
A(1+x)=(1,0),
$$

$$
A(x+x^2)=(0,-1),
$$

$$
A(1+x^2)=(1,5).
$$

Izračunaj $A(1+x+x^2)$.

**Rešitev**

Velja

$$
1+x+x^2=
\frac12(1+x)
+\frac12(x+x^2)
+\frac12(1+x^2).
$$

Zato

$$
A(1+x+x^2)
=
\frac12(1,0)
+\frac12(0,-1)
+\frac12(1,5)
$$

in

$$
A(1+x+x^2)=(1,2).
$$

### Tip naloge: jedro, slika in rang iz matrike

**Kako jo prepoznam**

Dana je matrika linearne preslikave.

**Postopek**

1. Jedro poišči iz

$$
Ax=0.
$$

2. Sliko določi kot stolpčni prostor matrike.
3. Bazo slike dobimo iz pivotnih stolpcev **originalne** matrike.
4. Rang je število pivotov.
5. Preveri izrek o rangu in ničelnosti.

**Primer**

Naj bo

$$
A=
\begin{pmatrix}
1&-1&2\\
1&-1&4
\end{pmatrix}.
$$

**Rešitev**

Za jedro rešimo

$$
\begin{pmatrix}
1&-1&2\\
1&-1&4
\end{pmatrix}
\begin{pmatrix}
x\\y\\z
\end{pmatrix}
=
\begin{pmatrix}
0\\0
\end{pmatrix}.
$$

Od druge enačbe odštejemo prvo:

$$
2z=0,
$$

zato $z=0$, nato

$$
x-y=0.
$$

Torej

$$
\ker A=L\{(1,1,0)\}.
$$

Stolpca

$$
\begin{pmatrix}1\\1\end{pmatrix},
\qquad
\begin{pmatrix}2\\4\end{pmatrix}
$$

sta linearno neodvisna, zato

$$
\operatorname{Im}A=\mathbb R^2
$$

in

$$
\operatorname{rang}A=2.
$$

Ker je domena tridimenzionalna,

$$
\dim\ker A+\operatorname{rang}A=1+2=3.
$$

Preslikava je surjektivna, ni pa injektivna.

**Pogoste napake**

- baza slike se vzame iz pivotnih stolpcev reducirane matrike namesto originalne;
- rang se zamenja z dimenzijo kodomene;
- iz $\dim V>\dim W$ se napačno sklepa, da preslikava ni surjektivna; pravilno je, da ne more biti injektivna.

### Tip naloge: uporaba izreka o rangu in ničelnosti

**Primer**

Naj bo $A:\mathbb R_3[x]\to\mathbb R^7$ linearna in

$$
\ker A=
L\{1+x-x^2,\ x-x^3,\ -1+x^2-x^3\}.
$$

Določi $\dim(\operatorname{Im}A)$.

**Rešitev**

Naj bodo

$$
v_1=1+x-x^2,
$$

$$
v_2=x-x^3,
$$

$$
v_3=-1+x^2-x^3.
$$

Opazimo

$$
v_1-v_2+v_3=0.
$$

Zato podani trije generatorji niso baza jedra. Prva dva sta linearno neodvisna, zato

$$
\dim\ker A=2.
$$

Ker

$$
\dim\mathbb R_3[x]=4,
$$

po izreku o rangu in ničelnosti

$$
4=2+\dim(\operatorname{Im}A).
$$

Torej

$$
\boxed{\dim(\operatorname{Im}A)=2}.
$$

**Pogosta napaka**

Iz števila zapisanih generatorjev jedra se ne sme avtomatsko sklepati na dimenzijo.

---

## 6. Linearni funkcionali

### Definicija

**Linearni funkcional** na $V$ je linearna preslikava

$$
f:V\to F.
$$

Če je $f\neq 0$ in je $V$ končnorazsežen, je

$$
\operatorname{Im}f=F,
$$

zato je

$$
\operatorname{rang}f=1.
$$

Po izreku o rangu in ničelnosti:

$$
\dim\ker f=\dim V-1.
$$

Jedro neničelnega linearnega funkcionala je torej hiperravnina.

### Ustno vprašanje

**Vprašanje:** Kaj je linearni funkcional?

**Kratek odgovor:** Linearni funkcional je linearna preslikava iz vektorskega prostora $V$ v njegovo osnovno polje $F$.

**Profesor lahko dodatno vpraša:** Kakšna je dimenzija jedra neničelnega funkcionala na $n$-razsežnem prostoru?

**Odgovor:** Ker ima neničelni funkcional rang $1$, po izreku o rangu in ničelnosti velja

$$
\dim\ker f=n-1.
$$

### Tip naloge: funkcional iz podanega jedra

**Primer**

Naj bo $f:\mathbb R^3\to\mathbb R$ neničelni linearni funkcional in

$$
\ker f=L\{(1,-1,0),(0,1,-1)\}.
$$

Poišči preprost predpis za $f$.

**Rešitev**

Zapišimo

$$
f(x,y,z)=ax+by+cz.
$$

Ker sta generatorja v jedru,

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

Ker je $f\neq 0$, izberemo $a=b=c=1$:

$$
\boxed{f(x,y,z)=x+y+z}.
$$

---

## 7. Urejene baze in koordinatni stolpci

### 7.1 Urejena baza

Pri matrikah je vrstni red baznih vektorjev pomemben. Zato uporabljamo **urejeno bazo**

$$
\mathcal B=(b_1,\dots,b_n).
$$

Če

$$
v=\alpha_1b_1+\cdots+\alpha_nb_n,
$$

je **koordinatni stolpec vektorja $v$ glede na bazo $\mathcal B$**

$$
[v]_{\mathcal B}
=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

### 7.2 Matrika baze

Če delamo v $\mathbb R^n$ in so bazni vektorji zapisani v standardnih koordinatah, definiramo

$$
P_{\mathcal B}
=
\begin{pmatrix}
|&&|\\
b_1&\cdots&b_n\\
|&&|
\end{pmatrix}.
$$

Tedaj

$$
v=P_{\mathcal B}[v]_{\mathcal B}.
$$

Zato

$$
[v]_{\mathcal B}=P_{\mathcal B}^{-1}v.
$$

### 7.3 Prehod med bazama

Za bazi $\mathcal B$ in $\mathcal C$ velja

$$
[v]_{\mathcal C}
=
P_{\mathcal C}^{-1}P_{\mathcal B}[v]_{\mathcal B}.
$$

Matrika

$$
P_{\mathcal C\leftarrow\mathcal B}
=
P_{\mathcal C}^{-1}P_{\mathcal B}
$$

preslika koordinate iz baze $\mathcal B$ v koordinate v bazi $\mathcal C$.

> **Pozor na notacijo.** V različnih gradivih se indeksi prehodnih matrik zapisujejo različno. Na izpitu najprej povej, kaj tvoja matrika preslika: iz katerih koordinat v katere. S tem odpraviš večino napak z inverzom.

### Ustno vprašanje

**Vprašanje:** Kaj je koordinatni stolpec vektorja glede na urejeno bazo?

**Kratek odgovor:** Če je $\mathcal B=(b_1,\dots,b_n)$ in

$$
v=\alpha_1b_1+\cdots+\alpha_nb_n,
$$

potem je

$$
[v]_{\mathcal B}=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

**Profesor lahko dodatno vpraša:** Zakaj je koordinatni stolpec enoličen?

**Odgovor:** Zaradi linearne neodvisnosti baznih vektorjev.

### Tip naloge: koordinatni stolpec in prehodna matrika

**Primer**

V $\mathbb R^2$ naj bo

$$
\Delta=((1,-1),(2,-1)).
$$

Poišči matriko, ki pretvarja koordinate v bazi $\Delta$ v standardne koordinate, in njen inverz.

**Rešitev**

Bazna matrika je

$$
P_\Delta=
\begin{pmatrix}
1&2\\
-1&-1
\end{pmatrix}.
$$

Zato

$$
v=P_\Delta[v]_\Delta.
$$

Ker

$$
\det P_\Delta=1,
$$

je

$$
P_\Delta^{-1}
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}.
$$

Torej:

- iz $\Delta$-koordinat v standardne:

$$
[v]_{\mathrm{std}}
=
\begin{pmatrix}
1&2\\
-1&-1
\end{pmatrix}
[v]_\Delta;
$$

- iz standardnih koordinat v $\Delta$-koordinate:

$$
[v]_\Delta
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}
[v]_{\mathrm{std}}.
$$

**Pogoste napake**

- zamenjava smeri prehoda;
- zapis baznih vektorjev po vrsticah namesto po stolpcih;
- pozabljanje, da je baza urejena.

---

## 8. Matrika linearne preslikave, kompozicija in sprememba baze

### 8.1 Matrika linearne preslikave

Naj bo

$$
A:V\to W,
$$

naj bo

$$
\mathcal B=(v_1,\dots,v_n)
$$

baza $V$ in

$$
\mathcal C=(w_1,\dots,w_m)
$$

baza $W$.

Matrika preslikave $A$ glede na ti bazi je matrika

$$
[A]_{\mathcal C\leftarrow\mathcal B}
$$

z lastnostjo

$$
[A(v)]_{\mathcal C}
=
[A]_{\mathcal C\leftarrow\mathcal B}
[v]_{\mathcal B}.
$$

Njeni stolpci so

$$
[A(v_1)]_{\mathcal C},
\dots,
[A(v_n)]_{\mathcal C}.
$$

Zato ima matrika velikost

$$
m\times n.
$$

### 8.2 Kompozicija

Naj bo

$$
A:U\to V,
\qquad
B:V\to W.
$$

Ob usklajenih bazah velja

$$
[BA]=[B][A].
$$

Vrstni red je pomemben: najprej deluje $A$, nato $B$.

### 8.3 Inverzna preslikava

Če je $A:V\to V$ izomorfizem, potem

$$
[A^{-1}]=[A]^{-1}
$$

ob isti izbiri baze.

### 8.4 Sprememba matrike endomorfizma

Naj bo $A:V\to V$ endomorfizem, $\mathcal B$ in $\mathcal C$ pa bazi prostora $V$.

Če je

$$
P=P_{\mathcal B\leftarrow\mathcal C},
$$

potem velja

$$
[A]_{\mathcal C}
=
P^{-1}[A]_{\mathcal B}P.
$$

Matriki sta zato **podobni**.

### 8.5 Podobnost matrik

Matriki $A$ in $B$ sta **podobni**, če obstaja obrnljiva matrika $P$, da

$$
B=P^{-1}AP.
$$

Podobni matriki predstavljata isti endomorfizem v različnih bazah.

Podobnost ohranja:

- karakteristični polinom;
- lastne vrednosti;
- determinant;
- sled;
- rang;
- diagonalizabilnost.

### Izpeljava formule za spremembo baze

Če

$$
[v]_{\mathcal B}=P[v]_{\mathcal C},
$$

potem

$$
[A(v)]_{\mathcal B}
=
[A]_{\mathcal B}[v]_{\mathcal B}
=
[A]_{\mathcal B}P[v]_{\mathcal C}.
$$

Po drugi strani

$$
[A(v)]_{\mathcal B}
=
P[A(v)]_{\mathcal C}
=
P[A]_{\mathcal C}[v]_{\mathcal C}.
$$

Zato

$$
P[A]_{\mathcal C}=[A]_{\mathcal B}P
$$

in

$$
[A]_{\mathcal C}=P^{-1}[A]_{\mathcal B}P.
$$

### Ustno vprašanje

**Vprašanje:** Kako sestavimo matriko linearne preslikave glede na izbrani bazi?

**Kratek odgovor:** Izračunamo slike baznih vektorjev domene in jih zapišemo v koordinatah baze kodomene. Ti koordinatni stolpci so stolpci matrike.

**Profesor lahko dodatno vpraša:** Kakšne velikosti je matrika preslikave $A:V\to W$, če je $\dim V=n$ in $\dim W=m$?

**Odgovor:** Velikosti $m\times n$.

### Ustno vprašanje

**Vprašanje:** Kaj pomeni, da sta matriki podobni?

**Kratek odgovor:** Matrika $B$ je podobna matriki $A$, če obstaja obrnljiva matrika $P$ s

$$
B=P^{-1}AP.
$$

**Profesor lahko dodatno vpraša:** Kakšen je geometrijski oziroma linearnoalgebrajski pomen?

**Odgovor:** Predstavljata isti endomorfizem glede na dve različni bazi.

### Tip naloge: matrika preslikave v novih bazah

**Kako jo prepoznam**

Podana je matrika $A$ v standardnih bazah ter druga baza domene in druga baza kodomene.

**Postopek**

Če je

$$
P_{\mathcal B}
$$

matrika baze domene v standardnih koordinatah in

$$
P_{\mathcal C}
$$

matrika baze kodomene, potem

$$
[A]_{\mathcal C\leftarrow\mathcal B}
=
P_{\mathcal C}^{-1}
[A]_{\mathrm{std}}
P_{\mathcal B}.
$$

**Primer**

Naj bo

$$
[A]_{\mathrm{std}}
=
\begin{pmatrix}
1&0&1\\
0&-1&1\\
2&2&0\\
0&-2&2
\end{pmatrix},
$$

$$
\Omega=((0,1,0),(1,1,0),(1,1,1))
$$

in

$$
\Pi=((1,0,0,0),(0,0,1,1),(0,1,0,0),(0,1,1,0)).
$$

**Rešitev**

Zapišemo

$$
P_\Omega=
\begin{pmatrix}
0&1&1\\
1&1&1\\
0&0&1
\end{pmatrix},
$$

$$
P_\Pi=
\begin{pmatrix}
1&0&0&0\\
0&0&1&1\\
0&1&0&1\\
0&1&0&0
\end{pmatrix}.
$$

Nato

$$
[A]_{\Pi\leftarrow\Omega}
=
P_\Pi^{-1}[A]_{\mathrm{std}}P_\Omega.
$$

Dobimo

$$
\boxed{
[A]_{\Pi\leftarrow\Omega}
=
\begin{pmatrix}
0&1&2\\
-2&-2&0\\
-5&-7&-4\\
4&6&4
\end{pmatrix}
}.
$$

**Pogoste napake**

- napačen vrstni red matrik;
- inverz napačne bazne matrike;
- uporaba iste baze za domeno in kodomeno, čeprav sta različni;
- pri endomorfizmu zamenjava formule za navadno spremembo koordinat s formulo podobnosti.

---

## 9. Invariantni podprostori

### Definicija

Naj bo $A:V\to V$ endomorfizem. Podprostor $U\leq V$ je **invarianten za $A$**, če

$$
A(U)\subseteq U.
$$

To pomeni: če je $u\in U$, potem je tudi $A(u)\in U$.

### Kako preverjamo invariantnost

Če je

$$
U=L\{u_1,\dots,u_k\},
$$

zadošča preveriti

$$
A(u_i)\in U
$$

za vse bazne vektorje $u_i$.

Za enorazsežen podprostor

$$
U=L\{u\}
$$

je invariantnost ekvivalentna obstoju $\lambda$, da

$$
A(u)=\lambda u.
$$

Zato so enorazsežni invariantni podprostori neposredno povezani z lastnimi vektorji.

### Omejitev endomorfizma

Če je $U$ invarianten za $A$, lahko definiramo

$$
A|_U:U\to U.
$$

To je omejitev endomorfizma na invariantni podprostor.

### Ustno vprašanje

**Vprašanje:** Kaj je invarianten podprostor?

**Kratek odgovor:** Podprostor $U\leq V$ je invarianten za endomorfizem $A$, če velja

$$
A(U)\subseteq U.
$$

**Profesor lahko dodatno vpraša:** Kako je enorazsežni invariantni podprostor povezan z lastnimi vektorji?

**Odgovor:** Če je $U=L\{u\}$ in $u\neq 0$, je $U$ invarianten natanko tedaj, ko

$$
A(u)=\lambda u
$$

za nek $\lambda$. Torej je $u$ lastni vektor.

### Tip naloge: preverjanje invariantnosti

**Primer**

Naj bo

$$
U=L\{(1,0,1)\}\leq\mathbb R^3
$$

in

$$
A(x,y,z)=(-z,y,-x).
$$

Ali je $U$ invarianten?

**Rešitev**

Za generator $u=(1,0,1)$ dobimo

$$
A(u)=(-1,0,-1)=-u.
$$

Zato

$$
A(U)\subseteq U
$$

in $U$ je invarianten.

**Pogoste napake**

- preverjanje samo enega naključnega elementa podprostora, ki ni baza;
- pri enorazsežnem podprostoru zahteva $A(u)=u$ namesto pravilne zahteve $A(u)=\lambda u$.

---

## 10. Projektorji in nilpotentni endomorfizmi

### 10.1 Projektor

Endomorfizem $P:V\to V$ je **projektor**, če

$$
P^2=P.
$$

#### Ključna struktura projektorja

Za vsak projektor velja

$$
V=\operatorname{Im}P\oplus\ker P.
$$

#### Dokaz

Za $v\in V$ zapišemo

$$
v=P(v)+(v-P(v)).
$$

Prvi člen je v $\operatorname{Im}P$. Za drugi člen velja

$$
P(v-P(v))
=
P(v)-P^2(v)
=
0,
$$

zato je v $\ker P$.

Če je $x\in\operatorname{Im}P\cap\ker P$, obstaja $y$ s $x=P(y)$, hkrati pa $P(x)=0$. Toda

$$
P(x)=P^2(y)=P(y)=x,
$$

zato $x=0$.

Torej je vsota direktna.

### 10.2 Nilpotentni endomorfizem

Endomorfizem $N:V\to V$ je **nilpotenten**, če obstaja $k\geq 1$, da

$$
N^k=0.
$$

Najmanjši tak $k$ imenujemo **indeks nilpotentnosti** oziroma v nekaterih gradivih red nilpotentnosti.

Če je $N$ nilpotenten in je $\lambda$ njegova lastna vrednost, potem mora biti

$$
\lambda=0.
$$

#### Dokaz

Če je

$$
Nv=\lambda v,
\qquad
v\neq 0,
$$

potem

$$
N^kv=\lambda^kv.
$$

Ker je $N^k=0$,

$$
0=\lambda^kv.
$$

Ker $v\neq 0$, sledi

$$
\lambda=0.
$$

### Ustno vprašanje

**Vprašanje:** Kaj je projektor?

**Kratek odgovor:** Endomorfizem $P$ je projektor, če

$$
P^2=P.
$$

**Profesor lahko dodatno vpraša:** Kako se prostor razcepi glede na projektor?

**Odgovor:**

$$
V=\operatorname{Im}P\oplus\ker P.
$$

### Ustno vprašanje

**Vprašanje:** Kaj je nilpotenten endomorfizem?

**Kratek odgovor:** Endomorfizem $N$ je nilpotenten, če obstaja $k\geq 1$ s

$$
N^k=0.
$$

**Profesor lahko dodatno vpraša:** Katere lastne vrednosti ima lahko nilpotenten endomorfizem?

**Odgovor:** Samo $0$.

### Tip naloge: prepoznavanje projektorja

**Primer**

Naj bo

$$
P(x,y)=(x-y,0).
$$

Preveri, ali je $P$ projektor.

**Rešitev**

$$
P^2(x,y)
=
P(x-y,0)
=
(x-y,0)
=
P(x,y).
$$

Torej

$$
P^2=P
$$

in $P$ je projektor.

### Tip naloge: indeks nilpotentnosti

**Primer**

Naj bo

$$
N:\mathbb C^3\to\mathbb C^3,
\qquad
N(x,y,z)=(0,x,y).
$$

**Rešitev**

$$
N^2(x,y,z)=(0,0,x),
$$

$$
N^3(x,y,z)=(0,0,0).
$$

Ker

$$
N^2\neq 0
$$

in

$$
N^3=0,
$$

je indeks nilpotentnosti enak

$$
\boxed{3}.
$$

---

## 11. Karakteristični polinom

### Definicija

Za endomorfizem oziroma kvadratno matriko $A\in F^{n\times n}$ definiramo karakteristični polinom z eno od dveh pogostih konvencij:

$$
p_A(\lambda)=\det(\lambda I-A)
$$

ali

$$
p_A(\lambda)=\det(A-\lambda I).
$$

Konvenciji se razlikujeta le za faktor $(-1)^n$, zato imata iste ničle.

V tem poglavju uporabljamo

$$
\boxed{
p_A(\lambda)=\det(\lambda I-A)
}.
$$

### Lastnosti

- $p_A$ ima stopnjo $n$;
- njegove ničle so lastne vrednosti matrike;
- podobni matriki imata isti karakteristični polinom.

### Dokaz invariantnosti pri podobnosti

Če je

$$
B=P^{-1}AP,
$$

potem

$$
\lambda I-B
=
P^{-1}(\lambda I-A)P.
$$

Zato

$$
\det(\lambda I-B)
=
\det(P^{-1})\det(\lambda I-A)\det(P)
$$

in

$$
p_B(\lambda)=p_A(\lambda).
$$

### Ustno vprašanje

**Vprašanje:** Kako definiramo karakteristični polinom matrike?

**Kratek odgovor:**

$$
p_A(\lambda)=\det(\lambda I-A).
$$

**Profesor lahko dodatno vpraša:** Zakaj karakteristični polinom ni odvisen od izbire baze endomorfizma?

**Odgovor:** Matrike istega endomorfizma v različnih bazah so podobne, podobni matriki pa imata isti karakteristični polinom.

### Tip naloge: karakteristični polinom operatorja na polinomih

**Primer**

Naj bo

$$
A:\mathbb R_2[x]\to\mathbb R_2[x],
\qquad
A(f)=f(0)+f.
$$

Poišči karakteristični polinom.

**Rešitev**

Za

$$
f=a+bx+cx^2
$$

je

$$
A(f)=2a+bx+cx^2.
$$

Glede na bazo

$$
(1,x,x^2)
$$

je

$$
[A]=
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
(\lambda-2)(\lambda-1)^2.
$$

---

## 12. Lastne vrednosti, lastni vektorji in lastni podprostori

### 12.1 Lastna vrednost in lastni vektor

Naj bo $A:V\to V$ endomorfizem.

Skalar $\lambda\in F$ je **lastna vrednost**, če obstaja $v\neq 0$ s

$$
A(v)=\lambda v.
$$

Tak $v$ je **lastni vektor** za $\lambda$.

Pomembno: ničelni vektor ni lastni vektor.

### 12.2 Lastni podprostor

Za lastno vrednost $\lambda$ definiramo

$$
E_\lambda
=
\ker(A-\lambda I).
$$

To je **lastni podprostor**.

Vsi neničelni elementi $E_\lambda$ so lastni vektorji za $\lambda$.

### 12.3 Karakteristična enačba

Enačba

$$
Av=\lambda v
$$

je ekvivalentna

$$
(A-\lambda I)v=0.
$$

Neničelna rešitev obstaja natanko tedaj, ko je $A-\lambda I$ singularna, torej

$$
\det(A-\lambda I)=0.
$$

Ekvivalentno:

$$
p_A(\lambda)=0.
$$

### 12.4 Algebraična in geometrijska večkratnost

**Algebraična večkratnost** $\lambda$ je njena večkratnost kot ničle karakterističnega polinoma.

**Geometrijska večkratnost** je

$$
\dim E_\lambda.
$$

Velja

$$
1\leq
\dim E_\lambda
\leq
m_a(\lambda),
$$

kjer je $m_a(\lambda)$ algebraična večkratnost.

### Izrek: lastni vektorji za različne lastne vrednosti so linearno neodvisni

Če so

$$
\lambda_1,\dots,\lambda_k
$$

paroma različne lastne vrednosti in so

$$
v_i\neq 0
$$

ustrezni lastni vektorji, potem so

$$
v_1,\dots,v_k
$$

linearno neodvisni.

#### Ideja dokaza

Predpostavimo minimalno netrivialno relacijo

$$
\alpha_1v_1+\cdots+\alpha_kv_k=0.
$$

Uporabimo $A$ in od dobljene enačbe odštejemo $\lambda_k$-krat prvotno enačbo:

$$
\alpha_1(\lambda_1-\lambda_k)v_1+\cdots+
\alpha_{k-1}(\lambda_{k-1}-\lambda_k)v_{k-1}=0.
$$

Zaradi minimalnosti in različnosti lastnih vrednosti morajo biti vsi koeficienti nič, kar da protislovje.

### Ustno vprašanje

**Vprašanje:** Kaj je lastna vrednost?

**Kratek odgovor:** $\lambda$ je lastna vrednost endomorfizma $A$, če obstaja neničelni vektor $v$ s

$$
A(v)=\lambda v.
$$

**Profesor lahko dodatno vpraša:** Zakaj zahtevamo $v\neq 0$?

**Odgovor:** Ker za ničelni vektor velja

$$
A(0)=\lambda 0
$$

za vsak $\lambda$, zato brez pogoja $v\neq 0$ definicija ne bi ločila lastnih vrednosti.

### Ustno vprašanje

**Vprašanje:** Zakaj so lastne vrednosti ničle karakterističnega polinoma?

**Kratek odgovor:** $\lambda$ je lastna vrednost natanko tedaj, ko ima sistem

$$
(A-\lambda I)v=0
$$

neničelno rešitev. To je natanko tedaj, ko je $A-\lambda I$ singularna, torej

$$
\det(A-\lambda I)=0.
$$

### Tip naloge: lastne vrednosti in lastni podprostori

**Kako jo prepoznam**

Dana je kvadratna matrika oziroma endomorfizem in zahtevane so lastne vrednosti ali lastni vektorji.

**Postopek**

1. Izračunaj

$$
p_A(\lambda)=\det(\lambda I-A).
$$

2. Reši

$$
p_A(\lambda)=0.
$$

3. Za vsako lastno vrednost reši

$$
(A-\lambda I)x=0.
$$

4. Zapiši bazo lastnega podprostora.
5. Določi algebraično in geometrijsko večkratnost.

**Primer**

Naj bo

$$
A=
\begin{pmatrix}
2&1&-1\\
-2&-1&-4\\
0&0&-5
\end{pmatrix}.
$$

**Rešitev**

Karakteristični polinom je

$$
p_A(\lambda)
=
\det(\lambda I-A)
=
\lambda(\lambda-1)(\lambda+5).
$$

Lastne vrednosti so

$$
\lambda_1=1,\qquad
\lambda_2=0,\qquad
\lambda_3=-5.
$$

Za $\lambda=1$:

$$
(A-I)x=0
$$

da

$$
E_1=L\{(-1,1,0)\}.
$$

Za $\lambda=0$:

$$
Ax=0
$$

da

$$
E_0=L\{(-1,2,0)\}.
$$

Za $\lambda=-5$:

$$
(A+5I)x=0
$$

da

$$
E_{-5}=L\{(0,1,1)\}.
$$

Ker so lastne vrednosti tri in med seboj različne, so ustrezni lastni vektorji linearno neodvisni.

**Pogoste napake**

- ničelni vektor se navede kot lastni vektor;
- rešuje se samo karakteristični polinom, ne pa tudi jedra $A-\lambda I$;
- napačen znak zaradi mešanja $\det(\lambda I-A)$ in $\det(A-\lambda I)$;
- pri večkratni lastni vrednosti se ne preveri dimenzije lastnega podprostora.

---

## 13. Diagonalizacija

### 13.1 Definicija

Endomorfizem $A:V\to V$ je **diagonalizabilen**, če obstaja baza $V$, glede na katero ima $A$ diagonalno matriko.

Matrika $A$ je diagonalizabilna, če obstajata obrnljiva matrika $P$ in diagonalna matrika $D$, da

$$
A=PDP^{-1}.
$$

Ekvivalentno:

$$
D=P^{-1}AP.
$$

### 13.2 Glavni kriterij

Endomorfizem je diagonalizabilen natanko tedaj, ko obstaja baza prostora, sestavljena iz lastnih vektorjev.

Če je

$$
\dim V=n,
$$

potrebujemo skupaj $n$ linearno neodvisnih lastnih vektorjev.

### 13.3 Zadostni kriterij

Če ima endomorfizem na $n$-razsežnem prostoru $n$ različnih lastnih vrednosti, je diagonalizabilen.

To je zadosten, ne pa potreben pogoj.

### 13.4 Kriterij z večkratnostmi

Če karakteristični polinom razpade na linearne faktorje, je $A$ diagonalizabilna natanko tedaj, ko za vsako lastno vrednost $\lambda$ velja

$$
\dim E_\lambda=m_a(\lambda).
$$

### Konstrukcija diagonalizacije

Če izberemo bazo lastnih vektorjev

$$
(v_1,\dots,v_n)
$$

z

$$
Av_i=\lambda_iv_i,
$$

postavimo

$$
P=
\begin{pmatrix}
|&&|\\
v_1&\cdots&v_n\\
|&&|
\end{pmatrix}
$$

in

$$
D=
\operatorname{diag}(\lambda_1,\dots,\lambda_n).
$$

Potem

$$
AP=PD,
$$

zato

$$
A=PDP^{-1}.
$$

### Dokaz kriterija diagonalizabilnosti

Če obstaja baza lastnih vektorjev, je vsak bazni vektor preslikan v skalarni večkratnik samega sebe, zato ima matrika preslikave v tej bazi samo diagonalne elemente.

Obratno, če je matrika endomorfizma v neki bazi diagonalna, potem za vsak bazni vektor velja

$$
A(v_i)=\lambda_iv_i.
$$

Bazni vektorji so torej lastni vektorji.

### Ustno vprašanje

**Vprašanje:** Kdaj je endomorfizem diagonalizabilen?

**Kratek odgovor:** Natanko tedaj, ko obstaja baza prostora, sestavljena iz lastnih vektorjev endomorfizma.

**Profesor lahko dodatno vpraša:** Ali različne lastne vrednosti vedno zagotavljajo diagonalizabilnost?

**Odgovor:** Če ima $n$-razsežen prostor $n$ različnih lastnih vrednosti, da. Če jih je manj, je treba preveriti dimenzije lastnih podprostorov.

### Ustno vprašanje

**Vprašanje:** Kako sestavimo matriki $P$ in $D$ pri diagonalizaciji?

**Kratek odgovor:** Stolpci $P$ so linearno neodvisni lastni vektorji. Na diagonalo $D$ damo pripadajoče lastne vrednosti v istem vrstnem redu.

**Profesor lahko dodatno vpraša:** Kaj se zgodi, če zamenjamo vrstni red stolpcev $P$?

**Odgovor:** V istem vrstnem redu moramo zamenjati diagonalne elemente $D$. Diagonalizacija ostane pravilna.

### Tip naloge: popolna diagonalizacija

**Primer**

Za

$$
A=
\begin{pmatrix}
2&1&-1\\
-2&-1&-4\\
0&0&-5
\end{pmatrix}
$$

smo dobili

$$
\lambda=1,\ 0,\ -5
$$

in lastne vektorje

$$
v_1=(-1,1,0),
$$

$$
v_2=(-1,2,0),
$$

$$
v_3=(0,1,1).
$$

Ker so lastne vrednosti različne, so vektorji linearno neodvisni. Postavimo

$$
P=
\begin{pmatrix}
-1&-1&0\\
1&2&1\\
0&0&1
\end{pmatrix}
$$

in

$$
D=
\begin{pmatrix}
1&0&0\\
0&0&0\\
0&0&-5
\end{pmatrix}.
$$

Potem

$$
\boxed{
A=PDP^{-1}
}.
$$

### Povezava z invariantnimi podprostori

Vsak lastni podprostor $E_\lambda$ je invarianten, saj za $v\in E_\lambda$ velja

$$
A(v)=\lambda v\in E_\lambda.
$$

Pri diagonalizabilnem endomorfizmu se prostor razcepi v direktno vsoto lastnih podprostorov:

$$
V=
\bigoplus_{\lambda}
E_\lambda.
$$

### Povezava s podobnostjo

Diagonalizacija je poseben primer podobnosti:

$$
D=P^{-1}AP.
$$

Zato imata $A$ in $D$ isti karakteristični polinom in iste lastne vrednosti.

### Povezava z računom potenc

Če

$$
A=PDP^{-1},
$$

potem

$$
A^k=PD^kP^{-1}.
$$

Ker je potenciranje diagonalne matrike preprosto,

$$
D^k=
\operatorname{diag}(\lambda_1^k,\dots,\lambda_n^k).
$$

To je eden glavnih praktičnih razlogov za diagonalizacijo.

---

## 14. Ključne povezave med pojmi

### Podprostor in jedro

Jedro linearne preslikave je vedno podprostor:

$$
\ker A\leq V.
$$

Homogeni sistem

$$
Ax=0
$$

je zato neposredno problem iskanja jedra.

### Slika in ogrodje stolpcev

Če je $A$ podana z matriko, je

$$
\operatorname{Im}A
$$

linearna ogrinjača stolpcev matrike.

### Rang in dimenzija

$$
\operatorname{rang}A=\dim(\operatorname{Im}A).
$$

Izrek o rangu in ničelnosti povezuje jedro in sliko:

$$
\dim V=
\dim\ker A+\operatorname{rang}A.
$$

### Baza in matrika preslikave

Linearna preslikava je abstrakten objekt. Matrika se pojavi šele po izbiri baz.

$$
\text{linearna preslikava}
+
\text{baza domene}
+
\text{baza kodomene}
\longrightarrow
\text{matrika}.
$$

### Sprememba baze in podobnost

Za endomorfizem različne baze dajo podobne matrike:

$$
B=P^{-1}AP.
$$

### Podobnost in karakteristični polinom

Podobne matrike imajo enak karakteristični polinom, zato tudi iste lastne vrednosti.

### Lastni vektor in invarianten podprostor

Če je

$$
Av=\lambda v,
$$

potem je

$$
L\{v\}
$$

invarianten podprostor.

### Lastni podprostori in diagonalizacija

Diagonalizacija obstaja natanko tedaj, ko je na voljo dovolj lastnih vektorjev za bazo celotnega prostora.

---

## 15. Najpomembnejši dokazi za ustni izpit

Naslednje dokaze je smiselno znati reproducirati brez zapiskov.

### Dokaz 1: enoličnost nevtralnega elementa

Če je $e$ levi in $f$ desni nevtralni element,

$$
e=e\circ f=f.
$$

### Dokaz 2: enoličnost razvoja po bazi

Če

$$
\sum_i\alpha_iv_i
=
\sum_i\beta_iv_i,
$$

potem

$$
\sum_i(\alpha_i-\beta_i)v_i=0.
$$

Linearna neodvisnost baze da

$$
\alpha_i=\beta_i.
$$

### Dokaz 3: presek podprostorov je podprostor

Če $u,v\in U\cap W$, sta oba v $U$ in $W$. Ker sta $U$ in $W$ podprostora,

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

### Dokaz 4: dimenzijska formula

Znati osnovno idejo z bazo $U\cap W$, ki jo dopolnimo do baz $U$ in $W$.

### Dokaz 5: jedro in slika sta podprostora

Za jedro:

$$
A(\alpha u+\beta v)
=
\alpha A(u)+\beta A(v)=0.
$$

Za sliko: če sta $A(u)$ in $A(v)$ v sliki,

$$
\alpha A(u)+\beta A(v)
=
A(\alpha u+\beta v)
$$

je ponovno v sliki.

### Dokaz 6: injektivnost in trivialno jedro

Če je $A$ injektivna in $A(v)=0=A(0)$, potem $v=0$.

Obratno, če je $\ker A=\{0\}$ in $A(u)=A(v)$, potem

$$
A(u-v)=0,
$$

zato $u-v=0$ in $u=v$.

### Dokaz 7: izrek o rangu in ničelnosti

Znati postopek:

1. baza jedra;
2. dopolnitev do baze domene;
3. slike dopolnilnih vektorjev tvorijo bazo slike.

### Dokaz 8: matrika kompozicije

Za koordinatni stolpec $x$:

$$
[BA(x)]
=
[B][A(x)]
=
[B][A][x].
$$

Zato

$$
[BA]=[B][A].
$$

### Dokaz 9: podobne matrike imajo isti karakteristični polinom

Če je

$$
B=P^{-1}AP,
$$

potem

$$
\det(\lambda I-B)
=
\det(P^{-1}(\lambda I-A)P)
=
\det(\lambda I-A).
$$

### Dokaz 10: različne lastne vrednosti dajo linearno neodvisne lastne vektorje

Znati dokaz z uporabo $A-\lambda_kI$ na linearni relaciji.

### Dokaz 11: kriterij diagonalizabilnosti

$$
A\text{ diagonalizabilen}
\iff
\text{obstaja baza lastnih vektorjev}.
$$

### Dokaz 12: razcep pri projektorju

$$
V=\operatorname{Im}P\oplus\ker P.
$$

---

## 16. Kako prepoznati pravo metodo

| Oblika naloge | Prva misel |
|---|---|
| Množica z enačbo ali parametri | Kriterij za podprostor, nato baza in dimenzija |
| Seznam vektorjev/polinomov | Linearna neodvisnost, rang, baza |
| Dva podprostora | $U\cap W$, $U+W$, dimenzijska formula |
| Predpis $A(x)$ | Preverjanje linearnosti |
| $A(x)=0$ | Jedro |
| Stolpci matrike $A$ | Slika in rang |
| Dimenzija jedra/slike | Izrek o rangu in ničelnosti |
| Slike baznih vektorjev | Matrika linearne preslikave |
| Koordinate v različnih bazah | Bazne in prehodne matrike |
| Isti endomorfizem v drugi bazi | Podobnost $P^{-1}AP$ |
| $A(U)\subseteq U$ | Invariantni podprostor |
| $A^2=A$ | Projektor |
| $A^k=0$ | Nilpotentnost |
| $\det(\lambda I-A)$ | Karakteristični polinom |
| $Av=\lambda v$ | Lastne vrednosti in lastni vektorji |
| $A=PDP^{-1}$ | Diagonalizacija |

---

## 17. Najpogostejše konceptualne napake

- **Podprostor ni samo podmnožica.** Mora biti zaprt za linearne kombinacije.
- **Afina množica ni podprostor**, če ne vsebuje ničle.
- **Generatorji niso nujno baza.** Najprej preveri linearno neodvisnost.
- **Število generatorjev ni nujno dimenzija.**
- **Baza je urejena**, kadar govorimo o koordinatah in matrikah.
- **Matrika linearne preslikave je odvisna od baz.**
- **Linearna preslikava sama ni matrika.**
- **Jedro je v domeni, slika je v kodomeni.**
- **Rang ni število stolpcev**, ampak dimenzija stolpčnega prostora.
- **Injektivnost** je povezana z jedrom.
- **Surjektivnost** je povezana s sliko.
- Pri prehodnih matrikah je treba vedno povedati **smer prehoda**.
- Pri kompoziciji je vrstni red

$$
[BA]=[B][A].
$$

- **Ničelni vektor ni lastni vektor.**
- Lastna vrednost je skalar, lastni vektor pa neničelni vektor.
- Večkratna lastna vrednost ne pomeni avtomatsko več linearno neodvisnih lastnih vektorjev.
- Diagonalizabilnost zahteva dovolj lastnih vektorjev, ne samo obstoj lastnih vrednosti.
- Pri $A=PDP^{-1}$ morajo biti lastne vrednosti na diagonali $D$ v istem vrstnem redu kot pripadajoči lastni vektorji v stolpcih $P$.

---

## 18. Mini ustni izpit — hitra vprašanja

### Ustno vprašanje

**Vprašanje:** Definiraj linearno ogrinjačo.

**Kratek odgovor:**

$$
L\{v_1,\dots,v_k\}
=
\left\{
\sum_{i=1}^k\alpha_iv_i;
\alpha_i\in F
\right\}.
$$

**Profesor lahko dodatno vpraša:** Kaj je geometrijsko pomembna lastnost ogrinjače?

**Odgovor:** Je najmanjši podprostor, ki vsebuje vse podane vektorje.

### Ustno vprašanje

**Vprašanje:** Kakšna je razlika med ogrodjem in bazo?

**Kratek odgovor:** Ogrodje generira celoten prostor, lahko pa vsebuje odvečne vektorje. Baza je ogrodje, ki je dodatno linearno neodvisno.

**Profesor lahko dodatno vpraša:** Kako iz ogrodja dobimo bazo?

**Odgovor:** Odstranjujemo linearno odvisne oziroma odvečne generatorje, dokler ostane linearno neodvisno ogrodje.

### Ustno vprašanje

**Vprašanje:** Kaj pomeni $\dim V=n$?

**Kratek odgovor:** Vsaka baza končnorazsežnega prostora $V$ ima natanko $n$ elementov.

**Profesor lahko dodatno vpraša:** Koliko elementov ima lahko linearno neodvisna množica v $V$?

**Odgovor:** Največ $n$.

### Ustno vprašanje

**Vprašanje:** Kaj je izomorfizem?

**Kratek odgovor:** Bijektivna linearna preslikava.

**Profesor lahko dodatno vpraša:** Kdaj sta dva končnorazsežna prostora nad istim poljem izomorfna?

**Odgovor:** Natanko tedaj, ko imata enako dimenzijo.

### Ustno vprašanje

**Vprašanje:** Kaj je podobnost matrik?

**Kratek odgovor:** $A$ in $B$ sta podobni, če obstaja obrnljiva $P$ s

$$
B=P^{-1}AP.
$$

**Profesor lahko dodatno vpraša:** Kaj podobnost pomeni za endomorfizem?

**Odgovor:** Matrika $A$ in matrika $B$ predstavljata isti endomorfizem glede na različni bazi.

### Ustno vprašanje

**Vprašanje:** Kaj je geometrijska večkratnost lastne vrednosti?

**Kratek odgovor:**

$$
m_g(\lambda)=\dim\ker(A-\lambda I).
$$

**Profesor lahko dodatno vpraša:** Kako je omejena z algebraično večkratnostjo?

**Odgovor:**

$$
1\leq m_g(\lambda)\leq m_a(\lambda).
$$

### Ustno vprašanje

**Vprašanje:** Kdaj je matrika z večkratno lastno vrednostjo diagonalizabilna?

**Kratek odgovor:** Če karakteristični polinom razpade in za vsako lastno vrednost geometrijska večkratnost doseže algebraično večkratnost.

**Profesor lahko dodatno vpraša:** Kako to preveriš računsko?

**Odgovor:** Za vsako $\lambda$ izračunam

$$
\dim\ker(A-\lambda I)
$$

in primerjam z večkratnostjo $\lambda$ v karakterističnem polinomu.

---

## Srednje težke naloge

**Naloga 1.**

Na množici

$$
G=\mathbb R\setminus\{-1\}
$$

definiramo

$$
a\circ b=a+b+ab.
$$

Preveri, ali je $(G,\circ)$ grupa. Določi nevtralni element in obrat poljubnega $a\in G$.

**Naloga 2.**

Naj bo

$$
U=\{(x,y,z)\in\mathbb R^3;x-2y+z=0\}.
$$

Pokaži, da je $U$ podprostor, poišči bazo in dimenzijo.

**Naloga 3.**

V prostoru $\mathbb R_2[x]$ obravnavaj množico

$$
S=\{1+x,\ x+x^2,\ 1+x^2\}.
$$

Ugotovi, ali je $S$ linearno neodvisna in ali je baza $\mathbb R_2[x]$.

**Naloga 4.**

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
\qquad
A(x,y,z)=(x+y,y+z).
$$

Določi:

- $\ker A$;
- $\operatorname{Im}A$;
- rang;
- ali je $A$ injektivna;
- ali je $A$ surjektivna.

**Naloga 5.**

V $\mathbb R^2$ naj bo

$$
\Delta=((1,1),(1,-1)).
$$

Določi koordinatni stolpec vektorja

$$
v=(4,2)
$$

glede na bazo $\Delta$.

Nato zapiši matriko prehoda iz $\Delta$-koordinat v standardne koordinate.

**Naloga 6.**

Naj bo

$$
P:\mathbb R^3\to\mathbb R^3,
\qquad
P(x,y,z)=(x,y,0).
$$

Preveri, ali je $P$ projektor. Določi $\ker P$, $\operatorname{Im}P$ in preveri razcep

$$
\mathbb R^3=\operatorname{Im}P\oplus\ker P.
$$

## Težke / izpitne naloge

**Naloga 7.**

V $\mathbb R_3[x]$ naj bo

$$
P=L\{1+x^2+2x^3,\ 2-x+x^2+2x^3,\ 1+x+x^2+x^3\},
$$

$$
R=L\{1+x^3,\ 3+x^3,\ 1+x\}.
$$

Poišči baze prostorov

$$
P,\qquad R,\qquad P\cap R,\qquad P+R.
$$

**Naloga 8.**

Naj bo

$$
A:\mathbb R^2\to\mathbb R^2,
\qquad
A(x,y)=(2x+y,x-y).
$$

Dani sta bazi

$$
\Omega=((1,1),(1,0))
$$

domene in

$$
\Delta=((1,0),(1,1))
$$

kodomene.

Poišči matriko

$$
[A]_{\Delta\leftarrow\Omega}.
$$

**Naloga 9.**

Naj bo $A:V\to W$ linearna preslikava, kjer

$$
\dim V=8,
\qquad
\dim W=5,
\qquad
\dim\ker A=3.
$$

Določi rang preslikave in odloči, ali je $A$ injektivna oziroma surjektivna.

**Naloga 10.**

Naj bo

$$
N:\mathbb R^4\to\mathbb R^4,
\qquad
N(x_1,x_2,x_3,x_4)=(0,x_1,x_2,x_3).
$$

Določi indeks nilpotentnosti. Poišči $\ker N$, $\ker N^2$, $\ker N^3$ in $\ker N^4$ ter njihove dimenzije.

**Naloga 11.**

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

Poišči:

1. karakteristični polinom;
2. vse lastne vrednosti;
3. baze vseh lastnih podprostorov;
4. odloči, ali je $A$ diagonalizabilna;
5. če je, poišči eno matriko $P$ in diagonalno matriko $D$, za kateri velja

$$
A=PDP^{-1}.
$$

**Naloga 12.**

Naj bo $A:V\to V$ endomorfizem štirirazsežnega realnega prostora. Njegov karakteristični polinom je

$$
p_A(\lambda)=(\lambda-2)^2(\lambda+1)^2.
$$

Predpostavimo

$$
\dim E_2=1
$$

in

$$
\dim E_{-1}=2.
$$

Ali je $A$ diagonalizabilen? Utemelji z dimenzijami lastnih podprostorov.

---

## Odgovori

**1.** Da, $(G,\circ)$ je Abelova grupa.

$$
e=0,
$$

$$
a^{-1}=-\frac{a}{1+a}.
$$

**2.**

$$
U=L\{(2,1,0),(-1,0,1)\},
$$

$$
\dim U=2.
$$

**3.** Množica $S$ je linearno neodvisna. Ker ima tri elemente in

$$
\dim\mathbb R_2[x]=3,
$$

je baza.

**4.**

$$
\ker A=L\{(-1,1,-1)\},
$$

$$
\operatorname{Im}A=\mathbb R^2,
$$

$$
\operatorname{rang}A=2.
$$

$A$ ni injektivna, je pa surjektivna.

**5.**

$$
[v]_\Delta=
\begin{pmatrix}
3\\
1
\end{pmatrix}.
$$

Prehod iz $\Delta$-koordinat v standardne:

$$
P_\Delta=
\begin{pmatrix}
1&1\\
1&-1
\end{pmatrix}.
$$

**6.** $P$ je projektor.

$$
\ker P=L\{(0,0,1)\},
$$

$$
\operatorname{Im}P=L\{(1,0,0),(0,1,0)\},
$$

$$
\mathbb R^3=\operatorname{Im}P\oplus\ker P.
$$

**7.**

$$
\dim P=3,
\qquad
\dim R=3.
$$

Ena možna izbira:

$$
\mathcal B_P=
\{1+x^2+2x^3,\ 2-x+x^2+2x^3,\ 1+x+x^2+x^3\},
$$

$$
\mathcal B_R=
\{1+x^3,\ 3+x^3,\ 1+x\}.
$$

$$
P\cap R=L\{1-x^3,\ x-x^3\}.
$$

$$
P+R=\mathbb R_3[x].
$$

Ena baza vsote je prva baza $P$ skupaj z $1+x^3$.

**8.**

$$
[A]_{\Delta\leftarrow\Omega}
=
\begin{pmatrix}
3&1\\
0&1
\end{pmatrix}.
$$

**9.**

$$
\operatorname{rang}A=8-3=5.
$$

Ker je

$$
\dim W=5,
$$

je $A$ surjektivna. Ker je $\ker A\neq\{0\}$, ni injektivna.

**10.**

$$
N^4=0,
\qquad
N^3\neq 0,
$$

zato je indeks nilpotentnosti $4$.

$$
\ker N=L\{e_4\},
\qquad
\dim\ker N=1,
$$

$$
\ker N^2=L\{e_3,e_4\},
\qquad
\dim\ker N^2=2,
$$

$$
\ker N^3=L\{e_2,e_3,e_4\},
\qquad
\dim\ker N^3=3,
$$

$$
\ker N^4=\mathbb R^4,
\qquad
\dim\ker N^4=4.
$$

**11.**

$$
p_A(\lambda)=\lambda^2(\lambda-2)(\lambda+1).
$$

Lastne vrednosti:

$$
\lambda=2,\qquad
\lambda=0,\qquad
\lambda=-1.
$$

Ena izbira baz:

$$
E_2=L\{(3,1,1,2)\},
$$

$$
E_0=L\{(1,-1,1,0),(-1,0,0,1)\},
$$

$$
E_{-1}=L\{(0,-1,2,1)\}.
$$

Skupna dimenzija lastnih podprostorov je

$$
1+2+1=4,
$$

zato je $A$ diagonalizabilna.

Ena možnost:

$$
P=
\begin{pmatrix}
3&1&-1&0\\
1&-1&0&-1\\
1&1&0&2\\
2&0&1&1
\end{pmatrix},
$$

$$
D=
\begin{pmatrix}
2&0&0&0\\
0&0&0&0\\
0&0&0&0\\
0&0&0&-1
\end{pmatrix}.
$$

**12.** Ne. Za diagonalizabilnost bi potrebovali

$$
\dim E_2=2
$$

in

$$
\dim E_{-1}=2.
$$

Tukaj je skupna dimenzija razpoložljivih lastnih podprostorov samo

$$
1+2=3<4.
$$

---

## Faza je zaključena, ko znam ...

- [ ] natančno definirati dvomestno notranjo operacijo, grupo, Abelovo grupo, nevtralni element in obrat;
- [ ] dokazati enoličnost nevtralnega elementa in obrata v grupi;
- [ ] preveriti, ali dan predpis definira notranjo operacijo oziroma grupo;
- [ ] definirati kolobar in delitelj niča;
- [ ] natančno definirati vektorski prostor in vektorski podprostor;
- [ ] uporabiti kriterij za podprostor;
- [ ] hitro prepoznati, zakaj nehomogeni ali nelinearni pogoji pogosto ne dajo podprostora;
- [ ] definirati linearno kombinacijo, linearno ogrinjačo in ogrodje;
- [ ] preveriti linearno neodvisnost vektorjev, polinomov in matrik;
- [ ] definirati bazo in dimenzijo;
- [ ] pojasniti, zakaj je razvoj po bazi enoličen;
- [ ] uporabiti dejstvo, da $n$ linearno neodvisnih vektorjev v $n$-razsežnem prostoru tvori bazo;
- [ ] določiti bazo in dimenzijo konkretno podanega podprostora;
- [ ] definirati $U+W$ in $U\cap W$;
- [ ] povedati in uporabiti formulo

$$
\dim(U+W)=\dim U+\dim W-\dim(U\cap W);
$$

- [ ] dokazati dimenzijsko formulo z dopolnjevanjem baze preseka;
- [ ] definirati direktno vsoto in pojasniti enoličnost razcepa;
- [ ] natančno definirati linearno preslikavo;
- [ ] prepoznati nelinearno preslikavo tudi s hitrim testom $A(0)\neq 0$;
- [ ] definirati jedro, sliko, rang in ničelnost;
- [ ] dokazati, da sta jedro in slika podprostora;
- [ ] povedati in dokazati kriterij

$$
A\text{ injektivna}\iff\ker A=\{0\};
$$

- [ ] povedati izrek o rangu in ničelnosti skupaj s predpostavkami;
- [ ] reproducirati dokaz izreka o rangu in ničelnosti;
- [ ] iz matrike izračunati $\ker A$, $\operatorname{Im}A$ in $\operatorname{rang}A$;
- [ ] odločiti, ali je linearna preslikava injektivna, surjektivna ali bijektivna;
- [ ] definirati izomorfizem in povedati kriterij izomorfnosti končnorazsežnih prostorov;
- [ ] pojasniti, zakaj linearna preslikava obstaja in je enolično določena s slikami baznih vektorjev;
- [ ] definirati linearni funkcional;
- [ ] pojasniti, zakaj ima neničelni funkcional na $n$-razsežnem prostoru jedro dimenzije $n-1$;
- [ ] definirati urejeno bazo in koordinatni stolpec;
- [ ] izračunati koordinate vektorja v poljubni bazi;
- [ ] sestaviti prehodno matriko in jasno povedati smer prehoda;
- [ ] natančno definirati matriko linearne preslikave glede na dve bazi;
- [ ] sestaviti matriko preslikave iz slik baznih vektorjev;
- [ ] povedati in uporabiti formulo za matriko kompozicije;
- [ ] izpeljati formulo spremembe baze;
- [ ] definirati podobnost matrik;
- [ ] pojasniti, zakaj podobni matriki predstavljata isti endomorfizem;
- [ ] dokazati, da imajo podobne matrike isti karakteristični polinom;
- [ ] definirati invarianten podprostor;
- [ ] preveriti invariantnost na bazi podprostora;
- [ ] povezati enorazsežne invariantne podprostore z lastnimi vektorji;
- [ ] definirati projektor in dokazati

$$
V=\operatorname{Im}P\oplus\ker P;
$$

- [ ] definirati nilpotenten endomorfizem in določiti njegov indeks nilpotentnosti;
- [ ] dokazati, da ima nilpotenten endomorfizem lahko le lastno vrednost $0$;
- [ ] definirati karakteristični polinom in poznati uporabljeno konvencijo;
- [ ] izračunati karakteristični polinom matrike ali operatorja;
- [ ] definirati lastno vrednost in lastni vektor;
- [ ] pojasniti, zakaj ničelni vektor ni lastni vektor;
- [ ] definirati lastni podprostor

$$
E_\lambda=\ker(A-\lambda I);
$$

- [ ] izpeljati karakteristično enačbo

$$
\det(A-\lambda I)=0;
$$

- [ ] definirati algebraično in geometrijsko večkratnost;
- [ ] povedati razmerje

$$
1\leq m_g(\lambda)\leq m_a(\lambda);
$$

- [ ] dokazati, da so lastni vektorji za različne lastne vrednosti linearno neodvisni;
- [ ] definirati diagonalizabilnost;
- [ ] povedati in dokazati kriterij: endomorfizem je diagonalizabilen natanko tedaj, ko obstaja baza lastnih vektorjev;
- [ ] preveriti diagonalizabilnost z dimenzijami lastnih podprostorov;
- [ ] pravilno sestaviti $P$ in $D$ v enačbi

$$
A=PDP^{-1};
$$

- [ ] pojasniti povezavo med podobnostjo, karakterističnim polinomom, lastnimi vrednostmi in diagonalizacijo;
- [ ] povezati jedro, sliko, rang, bazo, matriko, lastne podprostore in invariantne podprostore v enotno sliko;
- [ ] na ustnem izpitu na vsako glavno definicijo odgovoriti v največ nekaj stavkih, brez nejasnih formulacij;
- [ ] pri vsakem glavnem izreku povedati tudi njegove predpostavke;
- [ ] pri profesorjevem podvprašanju navesti kratek dokaz ali ključni argument brez računskega tavanja.
