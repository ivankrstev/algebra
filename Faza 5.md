# FAZA 5 — Koordinate, urejene baze, prehodne matrike in matrike linearnih preslikav

## Namen faze

V tej fazi moram obvladati prehod med tremi različnimi pogledi na isti objekt:

1. **vektor kot element vektorskega prostora**,
2. **koordinatni stolpec vektorja glede na izbrano urejeno bazo**,
3. **matrika linearne preslikave glede na izbrani bazi domene in kodomene**.

Glavna ideja celotne faze je:

$$
\boxed{
\text{abstraktni vektor}
\longleftrightarrow
\text{koordinatni stolpec}
}
$$

in

$$
\boxed{
\text{linearna preslikava}
\longleftrightarrow
\text{matrika preslikave}
}
$$

Ko zamenjamo bazo, se **vektor ne spremeni** in linearna preslikava se **ne spremeni**. Spremenijo se samo njune koordinate oziroma matrika.

Ta faza temelji predvsem na:

- **Vajah 8**, naloge 45–48: urejene baze in koordinatni stolpci,
- **Vajah 9**, naloge 49–54: prehodne matrike, kompozitum in računanje z več bazami,
- **Vajah 10**, naloge 55–58: matrike linearnih preslikav v različnih bazah ter povezava z jedrom, sliko in rangom.

V priloženih datotekah ni ločenih preteklih izpitov, zato je prioriteta tipov nalog določena po vajah.

---

## Kaj moram znati pred začetkom

Pred to fazo moram že znati:

- kaj je **vektorski prostor**,
- kaj je **baza**,
- kaj pomeni **linearna neodvisnost**,
- kaj je **dimenzija**,
- kaj je **linearna preslikava**,
- kaj sta $\ker A$ in $\operatorname{Im} A$,
- kaj je **rang** linearne preslikave,
- reševati sisteme linearnih enačb z Gaussovo eliminacijo.

Če pri izražanju vektorja kot linearne kombinacije baznih vektorjev še nisem zanesljiv, moram najprej ponoviti Fazo 2.

---

# 1. Urejena baza in koordinatni stolpec

## 1.1 Urejena baza

Naj bo $V$ končnorazsežen vektorski prostor in

$$
\Sigma=(v_1,v_2,\dots,v_n)
$$

baza prostora $V$.

Ker je pomemben tudi vrstni red baznih vektorjev, govorimo o **urejeni bazi**.

Na primer:

$$
\Sigma=((1,0),(0,1))
$$

in

$$
\Omega=((0,1),(1,0))
$$

sta različni urejeni bazi prostora $\mathbb R^2$, čeprav vsebujeta ista dva vektorja.

---

## 1.2 Koordinate vektorja

Ker je $\Sigma=(v_1,\dots,v_n)$ baza, lahko vsak $v\in V$ **enolično** zapišemo kot

$$
v=\alpha_1v_1+\alpha_2v_2+\cdots+\alpha_nv_n.
$$

Koordinatni stolpec vektorja $v$ glede na bazo $\Sigma$ je

$$
X_\Sigma(v)
=
[v]_\Sigma
=
\begin{pmatrix}
\alpha_1\\
\alpha_2\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

V tej zapiski bom uporabljal obe oznaki:

$$
X_\Sigma(v)=[v]_\Sigma.
$$

### Pomembno

Koordinate niso vektor sam.

Na primer, če je

$$
\Omega=((1,1),(1,-1))
$$

in

$$
[v]_\Omega=
\begin{pmatrix}
2\\
3
\end{pmatrix},
$$

potem

$$
v=2(1,1)+3(1,-1)=(5,-1).
$$

Torej:

$$
v\neq [v]_\Omega.
$$

Izenačimo ju lahko samo v posebnem primeru, ko uporabljamo običajno standardno bazo.

---

## 1.3 Običajna baza prostora $\mathbb R^n$

Običajna urejena baza prostora $\mathbb R^n$ je

$$
E=(e_1,\dots,e_n).
$$

Za

$$
v=
\begin{pmatrix}
x_1\\
\vdots\\
x_n
\end{pmatrix}
$$

velja

$$
[v]_E=
\begin{pmatrix}
x_1\\
\vdots\\
x_n
\end{pmatrix}.
$$

Zato pri običajni bazi koordinatnega stolpca pogosto niti posebej ne označujemo.

---

## 1.4 Koordinate polinoma

Za prostor $\mathbb R_n[x]$ je običajna baza

$$
E=(1,x,x^2,\dots,x^n).
$$

Če je

$$
p(x)=a_0+a_1x+\cdots+a_nx^n,
$$

potem

$$
[p]_E=
\begin{pmatrix}
a_0\\
a_1\\
\vdots\\
a_n
\end{pmatrix}.
$$

Če pa je baza drugačna, moramo polinom najprej zapisati kot linearno kombinacijo njenih elementov.

---

## 1.5 Koordinatna preslikava

Za urejeno bazo $\Sigma$ prostora $V$, kjer je $\dim V=n$, definiramo

$$
X_\Sigma:V\to F^n,
$$

$$
X_\Sigma(v)=[v]_\Sigma.
$$

Ta preslikava je **linearen izomorfizem**.

To pomeni:

$$
X_\Sigma(\alpha u+\beta v)
=
\alpha X_\Sigma(u)+\beta X_\Sigma(v).
$$

Vsak abstraktni $n$-razsežni vektorski prostor je zato po izbiri baze koordinatno predstavljen kot $F^n$.

---

# 2. Kako izračunam koordinate vektorja

Naj bo

$$
\Sigma=(v_1,\dots,v_n).
$$

Za dani $v$ iščemo

$$
[v]_\Sigma=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

Postavimo:

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n.
$$

Če so vektorji zapisani v običajnih koordinatah, sestavimo matriko

$$
B_\Sigma=
\begin{pmatrix}
|&|&&|\\
v_1&v_2&\cdots&v_n\\
|&|&&|
\end{pmatrix}.
$$

Tedaj rešujemo:

$$
B_\Sigma[v]_\Sigma=v.
$$

Zato:

$$
\boxed{
[v]_\Sigma=B_\Sigma^{-1}v
}
$$

če so $v$ in bazni vektorji zapisani v običajnih koordinatah.

### Pogoj

Formula z $B_\Sigma^{-1}$ velja, ker mora biti $\Sigma$ baza, zato je $B_\Sigma$ obrnljiva.

---

# 3. Matrika baze

Za urejeno bazo

$$
\Sigma=(v_1,\dots,v_n)
$$

prostora $\mathbb R^n$ definiramo **matriko baze**

$$
B_\Sigma=
\begin{pmatrix}
|&|&&|\\
v_1&v_2&\cdots&v_n\\
|&|&&|
\end{pmatrix}.
$$

Tedaj velja:

$$
\boxed{
v=B_\Sigma[v]_\Sigma
}
$$

in

$$
\boxed{
[v]_\Sigma=B_\Sigma^{-1}v.
}
$$

To sta eni izmed najpomembnejših formul faze.

---

# 4. Prehodne matrike

## 4.1 Kaj je prehodna matrika

Naj bosta $\Sigma$ in $\Delta$ urejeni bazi istega $n$-razsežnega vektorskega prostora.

Prehodna matrika **iz baze $\Sigma$ v bazo $\Delta$** pretvori koordinate glede na $\Sigma$ v koordinate glede na $\Delta$:

$$
\boxed{
[v]_\Delta
=
P_{\Delta\leftarrow\Sigma}[v]_\Sigma
}
$$

V tej zapiski uporabljamo oznako

$$
P_{\Delta\leftarrow\Sigma}
$$

zato, da je smer prehoda vedno očitna.

Puščico beremo:

> iz koordinat glede na $\Sigma$ v koordinate glede na $\Delta$.

V gradivu je prehodna matrika zapisana kot matrika identične preslikave med dvema bazama. Gre za isto idejo.

---

## 4.2 Formula za prehodno matriko

Če imamo obe bazi zapisani v običajnih koordinatah, velja

$$
v=B_\Sigma[v]_\Sigma
$$

in

$$
[v]_\Delta=B_\Delta^{-1}v.
$$

Zato:

$$
[v]_\Delta
=
B_\Delta^{-1}B_\Sigma[v]_\Sigma.
$$

Torej:

$$
\boxed{
P_{\Delta\leftarrow\Sigma}
=
B_\Delta^{-1}B_\Sigma
}
$$

---

## 4.3 Poseben primer: prehod iz običajne baze

Če je $\Sigma=E$ običajna baza, je

$$
B_E=I.
$$

Zato:

$$
\boxed{
P_{\Delta\leftarrow E}
=
B_\Delta^{-1}
}
$$

in

$$
\boxed{
P_{E\leftarrow\Delta}
=
B_\Delta.
}
$$

To je zelo pogost izpitni primer.

---

## 4.4 Inverzna prehodna matrika

Prehod iz $\Sigma$ v $\Delta$ in nato nazaj mora dati prvotne koordinate:

$$
P_{\Sigma\leftarrow\Delta}
P_{\Delta\leftarrow\Sigma}
=
I.
$$

Zato:

$$
\boxed{
P_{\Sigma\leftarrow\Delta}
=
P_{\Delta\leftarrow\Sigma}^{-1}.
}
$$

---

## 4.5 Sestavljanje prehodov

Če imamo tri baze $\Sigma,\Delta,\Gamma$, potem

$$
[v]_\Gamma
=
P_{\Gamma\leftarrow\Delta}
P_{\Delta\leftarrow\Sigma}
[v]_\Sigma.
$$

Zato:

$$
\boxed{
P_{\Gamma\leftarrow\Sigma}
=
P_{\Gamma\leftarrow\Delta}
P_{\Delta\leftarrow\Sigma}.
}
$$

Matrike se množijo v istem vrstnem redu, kot delujejo na stolpec: **desna deluje prva**.

---

# 5. Matrika linearne preslikave

Naj bo

$$
A:V\to W
$$

linearna preslikava.

Naj bo

$$
\Sigma=(v_1,\dots,v_n)
$$

urejena baza domene $V$ in

$$
\Delta=(w_1,\dots,w_m)
$$

urejena baza kodomene $W$.

Matrika preslikave $A$ glede na bazi $\Sigma$ in $\Delta$ je matrika

$$
M_{\Delta\leftarrow\Sigma}(A)
$$

za katero velja

$$
\boxed{
[A(v)]_\Delta
=
M_{\Delta\leftarrow\Sigma}(A)[v]_\Sigma.
}
$$

---

## 5.1 Kako sestavimo matriko preslikave

Za vsak bazni vektor domene izračunamo njegovo sliko:

$$
A(v_1),\dots,A(v_n).
$$

Vsako sliko razvijemo po bazi $\Delta$:

$$
[A(v_i)]_\Delta.
$$

Ti koordinatni stolpci postanejo stolpci matrike:

$$
\boxed{
M_{\Delta\leftarrow\Sigma}(A)
=
\begin{pmatrix}
|&|&&|\\
[A(v_1)]_\Delta&
[A(v_2)]_\Delta&
\cdots&
[A(v_n)]_\Delta\\
|&|&&|
\end{pmatrix}.
}
$$

### Ključno pravilo

**Stolpci matrike linearne preslikave so slike baznih vektorjev domene, izražene v bazi kodomene.**

---

## 5.2 Velikost matrike

Če

$$
\dim V=n,
\qquad
\dim W=m,
$$

potem ima matrika

$$
M_{\Delta\leftarrow\Sigma}(A)
$$

velikost

$$
\boxed{m\times n}.
$$

Torej:

- število **stolpcev** = dimenzija domene,
- število **vrstic** = dimenzija kodomene.

### Zapomnitev

$$
A:F^n\to F^m
\quad\Longrightarrow\quad
M(A)\in F^{m\times n}.
$$

---

# 6. Matrika preslikave v običajnih bazah

Če

$$
A:\mathbb R^n\to\mathbb R^m
$$

deluje po predpisu

$$
A(x)=Cx,
$$

je $C$ ravno matrika preslikave glede na običajni bazi.

Enakovredno:

$$
C=
\begin{pmatrix}
|&|&&|\\
A(e_1)&A(e_2)&\cdots&A(e_n)\\
|&|&&|
\end{pmatrix}.
$$

### Primer

Če

$$
A(x,y,z)
=
(2x-y+3z,\ x+4y),
$$

potem

$$
A(1,0,0)=(2,1),
$$

$$
A(0,1,0)=(-1,4),
$$

$$
A(0,0,1)=(3,0).
$$

Zato

$$
M(A)=
\begin{pmatrix}
2&-1&3\\
1&4&0
\end{pmatrix}.
$$

---

# 7. Kako iz matrike dobim sliko vektorja

Če je znano

$$
M_{\Delta\leftarrow\Sigma}(A)
$$

in

$$
[v]_\Sigma,
$$

potem neposredno:

$$
\boxed{
[A(v)]_\Delta
=
M_{\Delta\leftarrow\Sigma}(A)[v]_\Sigma.
}
$$

Če želimo dejanski vektor $A(v)$ in je $\Delta$ podana v običajnih koordinatah:

$$
\boxed{
A(v)
=
B_\Delta
M_{\Delta\leftarrow\Sigma}(A)
[v]_\Sigma.
}
$$

---

# 8. Kompozitum linearnih preslikav

Naj bo

$$
A:U\to V,
\qquad
B:V\to W.
$$

Izberimo baze:

- $\Sigma$ v $U$,
- $\Delta$ v $V$,
- $\Gamma$ v $W$.

Tedaj:

$$
[A(u)]_\Delta
=
M_{\Delta\leftarrow\Sigma}(A)[u]_\Sigma
$$

in

$$
[B(A(u))]_\Gamma
=
M_{\Gamma\leftarrow\Delta}(B)[A(u)]_\Delta.
$$

Zato:

$$
\boxed{
M_{\Gamma\leftarrow\Sigma}(B\circ A)
=
M_{\Gamma\leftarrow\Delta}(B)
M_{\Delta\leftarrow\Sigma}(A).
}
$$

### Pomembno

V produktu je matrika preslikave, ki deluje **prva**, na desni.

---

# 9. Matrika identične preslikave

Identična preslikava

$$
\operatorname{id}:V\to V
$$

zadovoljuje

$$
\operatorname{id}(v)=v.
$$

Če uporabljamo isto bazo na obeh straneh:

$$
M_{\Sigma\leftarrow\Sigma}(\operatorname{id})=I.
$$

Če uporabljamo različni bazi:

$$
M_{\Delta\leftarrow\Sigma}(\operatorname{id})
=
P_{\Delta\leftarrow\Sigma}.
$$

Torej je **prehodna matrika samo matrika identične preslikave glede na dve različni bazi**.

To je pomembna teoretična povezava.

---

# 10. Matrika inverzne preslikave

Naj bo

$$
A:V\to W
$$

izomorfizem.

Potem obstaja

$$
A^{-1}:W\to V.
$$

Če je

$$
M_{\Delta\leftarrow\Sigma}(A)
$$

matrika preslikave, potem

$$
\boxed{
M_{\Sigma\leftarrow\Delta}(A^{-1})
=
M_{\Delta\leftarrow\Sigma}(A)^{-1}.
}
$$

Pogoj je, da je $A$ bijektivna oziroma da je njena matrika obrnljiva.

---

# 11. Sprememba baze pri matriki linearne preslikave

To je eden najpomembnejših rezultatov faze.

Naj bo

$$
A:V\to W.
$$

Stara baza domene naj bo $\Sigma$, nova baza domene $\Gamma$.

Stara baza kodomene naj bo $\Delta$, nova baza kodomene $\Lambda$.

Poznamo

$$
M_{\Delta\leftarrow\Sigma}(A).
$$

Želimo

$$
M_{\Lambda\leftarrow\Gamma}(A).
$$

Najprej pretvorimo vhodne koordinate:

$$
[v]_\Sigma
=
P_{\Sigma\leftarrow\Gamma}[v]_\Gamma.
$$

Nato uporabimo $A$:

$$
[A(v)]_\Delta
=
M_{\Delta\leftarrow\Sigma}(A)
P_{\Sigma\leftarrow\Gamma}[v]_\Gamma.
$$

Nato pretvorimo izhodne koordinate:

$$
[A(v)]_\Lambda
=
P_{\Lambda\leftarrow\Delta}
M_{\Delta\leftarrow\Sigma}(A)
P_{\Sigma\leftarrow\Gamma}
[v]_\Gamma.
$$

Zato:

$$
\boxed{
M_{\Lambda\leftarrow\Gamma}(A)
=
P_{\Lambda\leftarrow\Delta}
M_{\Delta\leftarrow\Sigma}(A)
P_{\Sigma\leftarrow\Gamma}.
}
$$

### Zapomnitev

$$
\boxed{
\text{nova matrika}
=
\text{izhodni prehod}
\cdot
\text{stara matrika}
\cdot
\text{vhodni prehod}
}
$$

---

# 12. Poseben primer: endomorfizem in podobnost

Naj bo

$$
A:V\to V
$$

endomorfizem.

Naj bo $\Sigma$ stara baza in $\Gamma$ nova baza.

Če je

$$
S=P_{\Sigma\leftarrow\Gamma},
$$

torej $S$ pretvarja nove koordinate v stare, potem:

$$
\boxed{
M_\Gamma(A)
=
S^{-1}M_\Sigma(A)S.
}
$$

Matriki

$$
M_\Sigma(A)
$$

in

$$
M_\Gamma(A)
$$

sta zato **podobni**.

### Definicija podobnosti

Kvadratni matriki $A$ in $B$ sta podobni, če obstaja obrnljiva matrika $S$, da velja

$$
\boxed{
B=S^{-1}AS.
}
$$

Podobni matriki predstavljata **isti endomorfizem glede na različni bazi**.

To bo zelo pomembno pri diagonalizaciji.

---

# 13. Kaj se pri spremembi baze ne spremeni

Sprememba baze spremeni zapis matrike, ne pa same linearne preslikave.

Zato ostanejo enaki:

- rang,
- dimenzija jedra,
- dimenzija slike,
- injektivnost,
- surjektivnost,
- bijektivnost.

Za endomorfizme bodo kasneje pomembni tudi:

- karakteristični polinom,
- lastne vrednosti,
- diagonalizabilnost.

### Posebej pomembno

Če je matrika linearne preslikave v eni bazi ranga $r$, ima **vsaka** matrika iste preslikave v katerikoli drugi izbiri baz prav tako rang $r$.

---

# 14. Hiter pregled najpomembnejših formul

## Koordinate

$$
v=B_\Sigma[v]_\Sigma
$$

$$
[v]_\Sigma=B_\Sigma^{-1}v
$$

## Prehod med bazama

$$
[v]_\Delta
=
P_{\Delta\leftarrow\Sigma}[v]_\Sigma
$$

$$
P_{\Delta\leftarrow\Sigma}
=
B_\Delta^{-1}B_\Sigma
$$

$$
P_{\Sigma\leftarrow\Delta}
=
P_{\Delta\leftarrow\Sigma}^{-1}
$$

## Matrika linearne preslikave

$$
[A(v)]_\Delta
=
M_{\Delta\leftarrow\Sigma}(A)[v]_\Sigma
$$

$$
M_{\Delta\leftarrow\Sigma}(A)
=
\begin{pmatrix}
[A(v_1)]_\Delta&
\cdots&
[A(v_n)]_\Delta
\end{pmatrix}
$$

## Kompozitum

$$
M(B\circ A)=M(B)M(A)
$$

ob kompatibilni izbiri baz.

## Sprememba baz

$$
M_{\Lambda\leftarrow\Gamma}(A)
=
P_{\Lambda\leftarrow\Delta}
M_{\Delta\leftarrow\Sigma}(A)
P_{\Sigma\leftarrow\Gamma}
$$

## Endomorfizem

$$
M_\Gamma(A)
=
S^{-1}M_\Sigma(A)S.
$$

---

# 15. Kako prepoznam, katero metodo uporabiti

| Besedilo naloge | Kaj naredim |
|---|---|
| »Poiščite stolpec vektorja v bazi $\Sigma$« | Rešim $B_\Sigma[v]_\Sigma=v$ |
| »Iz koordinatnega stolpca določite vektor« | Izračunam $v=B_\Sigma[v]_\Sigma$ |
| »Prehodna matrika iz $\Sigma$ v $\Delta$« | $P_{\Delta\leftarrow\Sigma}=B_\Delta^{-1}B_\Sigma$ |
| »Matrika preslikave glede na bazi $\Sigma,\Delta$« | Stolpci so $[A(v_i)]_\Delta$ |
| »Iz matrike določite $A(v)$« | Uporabim $[A(v)]_\Delta=M_{\Delta\leftarrow\Sigma}(A)[v]_\Sigma$ |
| »Matrika kompozituma $BA$« | $M(BA)=M(B)M(A)$ |
| »Isti endomorfizem v drugi bazi« | Uporabim $S^{-1}AS$ |
| »Katera matrika je lahko matrika iste preslikave v drugih bazah?« | Primerjam rang |
| »Koliko baz lahko da podano matriko?« | Razložim, kaj morajo biti bazni vektorji kodomene glede na stolpce |
| »Vektor je podan v eni bazi, matrika $A$ v drugi, rezultat želimo v tretji« | Sistematično pretvarjam koordinate med bazami |

---

# 16. Tip naloge: določanje koordinat vektorja

## Kako jo prepoznam

Naloga vsebuje:

- urejeno bazo $\Sigma$,
- vektor $v$,
- zahtevo po $X_\Sigma(v)$ oziroma $[v]_\Sigma$.

To je glavni tip Vaj 8.

## Postopek

1. Zapišem bazo $\Sigma=(v_1,\dots,v_n)$.
2. Postavim:

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n.
$$

3. Rešim sistem za $\alpha_i$.
4. Zapišem:

$$
[v]_\Sigma=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

## Pomembne formule

$$
B_\Sigma[v]_\Sigma=v
$$

$$
[v]_\Sigma=B_\Sigma^{-1}v.
$$

## Primer

Naj bo

$$
\Omega=((1,1,1,1),(0,1,1,1),(0,0,1,1),(0,0,0,1))
$$

in

$$
v=(2,1,-3,0).
$$

Določi $[v]_\Omega$.

## Rešitev

Zapišemo:

$$
(2,1,-3,0)
=
a(1,1,1,1)
+b(0,1,1,1)
+c(0,0,1,1)
+d(0,0,0,1).
$$

Po komponentah:

$$
a=2,
$$

$$
a+b=1
\Rightarrow
b=-1,
$$

$$
a+b+c=-3
\Rightarrow
c=-4,
$$

$$
a+b+c+d=0
\Rightarrow
d=3.
$$

Zato:

$$
\boxed{
[v]_\Omega=
\begin{pmatrix}
2\\
-1\\
-4\\
3
\end{pmatrix}.
}
$$

## Pogoste napake

- bazne vektorje dam v vrstice namesto v stolpce,
- zamenjam vrstni red baznih vektorjev,
- rezultat zapišem kot vrstični namesto stolpčni vektor,
- koordinate zamenjam za dejanski vektor.

---

# 17. Tip naloge: iz koordinat določiti dejanski vektor

## Kako jo prepoznam

Podan je stolpec

$$
[v]_\Sigma
$$

in baza $\Sigma$, naloga pa zahteva $v$.

## Postopek

Če je

$$
[v]_\Sigma=
\begin{pmatrix}
a_1\\
\vdots\\
a_n
\end{pmatrix},
$$

potem:

$$
v=a_1v_1+\cdots+a_nv_n.
$$

## Primer iz tipa Vaj 8

Naj bo

$$
\Omega=((1,2,3),(2,3,1),(3,1,2))
$$

in

$$
[v]_\Omega=
\begin{pmatrix}
1\\
2\\
3
\end{pmatrix}.
$$

Določi $v$.

## Rešitev

$$
v
=
(1,2,3)
+
2(2,3,1)
+
3(3,1,2).
$$

Torej:

$$
v
=
(1,2,3)+(4,6,2)+(9,3,6)
$$

$$
\boxed{
v=(14,11,11).
}
$$

## Pogoste napake

- koordinate obravnavam kot običajne komponente,
- pozabim, da so koeficienti vezani na točno določen vrstni red baze.

---

# 18. Tip naloge: koordinate polinoma v različnih bazah

## Kako jo prepoznam

Podane so:

- baza polinomskega prostora,
- koordinatni stolpec polinoma v eni bazi,
- druga baza,
- zahteva po koordinatah v drugi bazi.

Točno tak tip se pojavi v Vajah 8.

## Postopek

Najvarnejša metoda:

1. iz prvega koordinatnega stolpca rekonstruiram polinom,
2. polinom poenostavim v standardni obliki,
3. polinom razvijem po drugi bazi.

## Primer

V bazi

$$
\Sigma=(1,\ 1+x,\ 1+x+x^2,\ x+x^3)
$$

ima $f\in\mathbb R_3[x]$ koordinatni stolpec

$$
[f]_\Sigma=
\begin{pmatrix}
1\\
-1\\
0\\
1
\end{pmatrix}.
$$

Poišči njegove koordinate v bazi

$$
\Delta=(1,x,2x^2,3x^3).
$$

## Rešitev

Najprej rekonstruiramo $f$:

$$
f
=
1-(1+x)+(x+x^3).
$$

Poenostavimo:

$$
f=x^3.
$$

V bazi $\Delta$ velja:

$$
x^3
=
0\cdot1
+0\cdot x
+0\cdot2x^2
+\frac13\cdot3x^3.
$$

Zato:

$$
\boxed{
[f]_\Delta=
\begin{pmatrix}
0\\
0\\
0\\
\frac13
\end{pmatrix}.
}
$$

## Pogoste napake

- koeficiente polinoma neposredno prepišem kot koordinate, čeprav baza ni standardna,
- pozabim faktor $2$ ali $3$ v baznem polinomu,
- pred prehodom ne poenostavim polinoma.

---

# 19. Tip naloge: prehodna matrika med bazama

## Kako jo prepoznam

Naloga zahteva:

- »prehodno matriko iz baze $\Sigma$ v bazo $\Delta$«,
- pretvorbo koordinat med bazama,
- ali matriko identične preslikave glede na dve različni bazi.

## Postopek

Če sta bazi zapisani v običajnih koordinatah:

1. sestavim $B_\Sigma$,
2. sestavim $B_\Delta$,
3. izračunam

$$
P_{\Delta\leftarrow\Sigma}
=
B_\Delta^{-1}B_\Sigma.
$$

## Primer iz tipa Vaj 9

Naj bo običajna baza

$$
E=((1,0),(0,1))
$$

in

$$
\Delta=((1,-1),(2,-1)).
$$

Poišči prehodno matriko iz $E$ v $\Delta$.

## Rešitev

Matrika baze $\Delta$ je

$$
B_\Delta=
\begin{pmatrix}
1&2\\
-1&-1
\end{pmatrix}.
$$

Ker je začetna baza običajna:

$$
P_{\Delta\leftarrow E}
=
B_\Delta^{-1}.
$$

Ker je

$$
\det B_\Delta
=
-1+2=1,
$$

dobimo

$$
B_\Delta^{-1}
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}.
$$

Torej:

$$
\boxed{
P_{\Delta\leftarrow E}
=
\begin{pmatrix}
-1&-2\\
1&1
\end{pmatrix}.
}
$$

Koeficient v prvi vrstici in drugem stolpcu je zato $-2$.

## Preverjanje

Za $e_2=(0,1)$:

$$
[e_2]_\Delta
=
\begin{pmatrix}
-2\\
1
\end{pmatrix}.
$$

Res:

$$
-2(1,-1)+(2,-1)
=
(0,1).
$$

## Pogoste napake

- uporabim $B_\Delta$ namesto $B_\Delta^{-1}$,
- ne preverim smeri prehoda,
- zamenjam $P_{\Delta\leftarrow\Sigma}$ in $P_{\Sigma\leftarrow\Delta}$.

---

# 20. Tip naloge: iz prehodne matrike določiti linearno preslikavo

## Kako jo prepoznam

Naloga pove, da je matrika neke preslikave enaka prehodni matriki med dvema bazama.

Tak tip se pojavi na Vajah 9.

## Primer

Naj bo

$$
\Omega=((1,-1),(1,1))
$$

in $E$ običajna baza prostora $\mathbb R^2$.

Matrika endomorfizma $A$ v običajni bazi je enaka prehodni matriki iz $\Omega$ v $E$.

Določi $A(x,y)$.

## Rešitev

Ker prehajamo iz $\Omega$ v običajno bazo,

$$
P_{E\leftarrow\Omega}
=
B_\Omega.
$$

Torej:

$$
M_E(A)
=
\begin{pmatrix}
1&1\\
-1&1
\end{pmatrix}.
$$

Zato:

$$
A(x,y)
=
\begin{pmatrix}
1&1\\
-1&1
\end{pmatrix}
\begin{pmatrix}
x\\
y
\end{pmatrix}.
$$

Dobimo:

$$
\boxed{
A(x,y)=(x+y,-x+y).
}
$$

---

# 21. Tip naloge: določanje matrike linearne preslikave iz predpisa

## Kako jo prepoznam

Podan je predpis:

$$
A(x_1,\dots,x_n)=\dots
$$

in naloga zahteva matriko v običajnih ali drugih bazah.

## Postopek za običajni bazi

Izračunam:

$$
A(e_1),\dots,A(e_n).
$$

Te vektorje dam v stolpce.

## Primer

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
$$

$$
A(x,y,z)
=
(2x-4y+6z,-3x+6y-9z).
$$

V običajnih bazah dobimo:

$$
A(e_1)=(2,-3),
$$

$$
A(e_2)=(-4,6),
$$

$$
A(e_3)=(6,-9).
$$

Zato:

$$
\boxed{
M(A)
=
\begin{pmatrix}
2&-4&6\\
-3&6&-9
\end{pmatrix}.
}
$$

Opazimo:

$$
(-3,6,-9)
=
-\frac32(2,-4,6),
$$

zato je rang matrike $1$.

Ta podatek bo pomemben, če iščemo, katera matrika bi lahko predstavljala isto preslikavo v drugih bazah.

---

# 22. Tip naloge: katera matrika lahko predstavlja isto preslikavo v nekih bazah

## Kako jo prepoznam

Podan je predpis linearne preslikave in več kandidatov za matriko v **nekih** urejenih bazah.

To je tip naloge iz Vaj 10.

## Ključna ideja

Sprememba baz je množenje z obrnljivima matrikama:

$$
M_{\text{nova}}
=
P\,M_{\text{stara}}\,Q.
$$

Množenje z obrnljivimi matrikami ne spremeni ranga.

Torej:

$$
\boxed{
\rank M_{\text{nova}}
=
\rank M_{\text{stara}}.
}
$$

## Postopek

1. Izračunam rang preslikave.
2. Izračunam rang vsakega kandidata.
3. Izločim vse matrike z napačnim rangom.

## Primer

Za

$$
A(x,y,z)
=
(2x-4y+6z,-3x+6y-9z)
$$

smo dobili rang $1$.

Zato mora imeti tudi matrika $A$ v katerikoli drugi izbiri baz rang $1$.

Na primer matrika

$$
\begin{pmatrix}
0&0&0\\
0&0&1
\end{pmatrix}
$$

ima rang $1$, zato je takšna oblika možna.

Matrika

$$
\begin{pmatrix}
1&0&0\\
0&1&0
\end{pmatrix}
$$

ima rang $2$, zato ne more predstavljati iste preslikave.

## Pogoste napake

- mislim, da morajo biti vse matrike iste linearne preslikave enake,
- primerjam posamezne elemente namesto invarianta, kot je rang,
- pozabim, da lahko pri preslikavi $V\to W$ neodvisno spreminjamo bazo domene in kodomene.

---

# 23. Tip naloge: matrika kompozituma

## Kako jo prepoznam

Podani sta preslikavi

$$
A:U\to V,
\qquad
B:V\to W
$$

in sprašujejo po matriki $BA=B\circ A$ ali samo po njeni velikosti.

## Postopek

Če so baze kompatibilne:

$$
M(BA)=M(B)M(A).
$$

Pred množenjem preverim velikosti.

## Primer

Naj bo

$$
A:\mathbb R^3\to\mathbb R_3[x],
$$

$$
B:\mathbb R_3[x]\to\mathbb R^2.
$$

Ker je

$$
\dim\mathbb R^3=3
$$

in

$$
\dim\mathbb R^2=2,
$$

je

$$
BA:\mathbb R^3\to\mathbb R^2.
$$

Zato ima matrika $BA$ velikost:

$$
\boxed{2\times3}.
$$

### Pomembno

Dimenzija vmesnega prostora vpliva na velikosti faktorjev, ne pa na končno velikost matrike kompozituma.

---

# 24. Tip naloge: matrika preslikave v nestandardnih bazah

## Kako jo prepoznam

Podani so:

- predpis ali običajna matrika $A$,
- baza $\Sigma$ domene,
- baza $\Delta$ kodomene,
- zahteva po $M_{\Delta\leftarrow\Sigma}(A)$.

## Metoda 1: po stolpcih

Za vsak $v_i\in\Sigma$:

1. izračunam $A(v_i)$,
2. izrazim $A(v_i)$ po bazi $\Delta$,
3. dobljeni koordinatni stolpec dam v ustrezen stolpec matrike.

## Metoda 2: z matrično formulo

Če je $M_E(A)$ matrika v običajnih bazah:

$$
\boxed{
M_{\Delta\leftarrow\Sigma}(A)
=
B_\Delta^{-1}
M_E(A)
B_\Sigma.
}
$$

To je zelo pomembna praktična formula.

---

# 25. Rešen primer: matrika v novih bazah

Naj bo

$$
A:\mathbb R^2\to\mathbb R^2
$$

z matriko v običajni bazi

$$
M_E(A)=
\begin{pmatrix}
2&1\\
1&1
\end{pmatrix}.
$$

Naj bo baza domene

$$
\Gamma=((1,1),(1,0))
$$

in baza kodomene

$$
\Lambda=((1,0),(1,1)).
$$

Poišči $M_{\Lambda\leftarrow\Gamma}(A)$.

## Rešitev

Matriki baz sta:

$$
B_\Gamma=
\begin{pmatrix}
1&1\\
1&0
\end{pmatrix},
$$

$$
B_\Lambda=
\begin{pmatrix}
1&1\\
0&1
\end{pmatrix}.
$$

Uporabimo:

$$
M_{\Lambda\leftarrow\Gamma}(A)
=
B_\Lambda^{-1}
M_E(A)
B_\Gamma.
$$

Najprej:

$$
M_E(A)B_\Gamma
=
\begin{pmatrix}
2&1\\
1&1
\end{pmatrix}
\begin{pmatrix}
1&1\\
1&0
\end{pmatrix}
=
\begin{pmatrix}
3&2\\
2&1
\end{pmatrix}.
$$

Ker je

$$
B_\Lambda^{-1}
=
\begin{pmatrix}
1&-1\\
0&1
\end{pmatrix},
$$

dobimo:

$$
M_{\Lambda\leftarrow\Gamma}(A)
=
\begin{pmatrix}
1&-1\\
0&1
\end{pmatrix}
\begin{pmatrix}
3&2\\
2&1
\end{pmatrix}
=
\boxed{
\begin{pmatrix}
1&1\\
2&1
\end{pmatrix}.
}
$$

---

# 26. Tip naloge: vektor je podan v eni bazi, matrika $A$ v drugi, rezultat želimo v tretji

## Kako jo prepoznam

To je tipična težja naloga iz Vaj 9.

Na primer:

- $[x]_\Pi$ je podan,
- matrika $A$ je podana glede na bazo $\Lambda$,
- želimo $[A(x)]_\Omega$.

## Najvarnejši postopek

Vedno si napišem pot:

$$
[x]_\Pi
\rightarrow
x
\rightarrow
[x]_\Lambda
\rightarrow
[A(x)]_\Lambda
\rightarrow
A(x)
\rightarrow
[A(x)]_\Omega.
$$

Ali vse korake zapišem kot matrični produkt.

### Univerzalno pravilo

Nikoli ne množim matrik »na pamet«. Vedno preverim, **v kateri bazi je trenutni stolpec**.

---

# 27. Rešen zahtevnejši primer po vzoru Vaj 9

V prostoru $\mathbb R^3$ so dane baze:

$$
\Lambda=
((0,0,-1),(2,1,1),(1,1,0)),
$$

$$
\Omega=
((1,2,-1),(0,1,3),(1,2,0)),
$$

$$
\Pi=
((1,1,2),(2,3,2),(0,0,1)).
$$

Endomorfizem $A$ ima v bazi $\Lambda$ matriko

$$
M_\Lambda(A)
=
\begin{pmatrix}
0&-1&0\\
1&-1&1\\
0&0&0
\end{pmatrix}.
$$

Za $x$ velja

$$
[x]_\Pi=
\begin{pmatrix}
1\\
1\\
1
\end{pmatrix}.
$$

Poišči $[A(x)]_\Omega$.

## Rešitev

Najprej iz koordinat v bazi $\Pi$ dobimo dejanski vektor:

$$
x
=
(1,1,2)+(2,3,2)+(0,0,1)
=
(3,4,5).
$$

Sedaj izrazimo $x$ v bazi $\Lambda$:

$$
[x]_\Lambda=
\begin{pmatrix}
-6\\
-1\\
5
\end{pmatrix}.
$$

Uporabimo matriko endomorfizma:

$$
[A(x)]_\Lambda
=
\begin{pmatrix}
0&-1&0\\
1&-1&1\\
0&0&0
\end{pmatrix}
\begin{pmatrix}
-6\\
-1\\
5
\end{pmatrix}
=
\begin{pmatrix}
1\\
0\\
0
\end{pmatrix}.
$$

Torej:

$$
A(x)
=
1(0,0,-1)
=
(0,0,-1).
$$

Sedaj razvijemo $(0,0,-1)$ po bazi $\Omega$:

$$
(0,0,-1)
=
1(1,2,-1)
+0(0,1,3)
-1(1,2,0).
$$

Zato:

$$
\boxed{
[A(x)]_\Omega=
\begin{pmatrix}
1\\
0\\
-1
\end{pmatrix}.
}
$$

## Pogoste napake

- matriko $M_\Lambda(A)$ pomnožim neposredno z $[x]_\Pi$,
- pozabim najprej pretvoriti $[x]_\Pi$ v $[x]_\Lambda$,
- po uporabi matrike pozabim, da je rezultat še vedno v koordinatah baze $\Lambda$.

---

# 28. Tip naloge: določanje baze kodomene iz podane matrike preslikave

## Kako jo prepoznam

Podan je predpis $A$, baza domene in zahtevana oblika matrike glede na neznano bazo kodomene.

To je tip naloge iz Vaj 10.

## Glavna ideja

Stolpci matrike povedo koordinate slik baznih vektorjev domene.

Če mora biti na primer

$$
M_{\Delta\leftarrow E}(A)
=
\begin{pmatrix}
2&0&1\\
0&0&0
\end{pmatrix},
$$

potem mora veljati:

$$
[A(e_1)]_\Delta=
\begin{pmatrix}
2\\
0
\end{pmatrix},
$$

$$
[A(e_2)]_\Delta=
\begin{pmatrix}
0\\
0
\end{pmatrix},
$$

$$
[A(e_3)]_\Delta=
\begin{pmatrix}
1\\
0
\end{pmatrix}.
$$

To pomeni, da so vse neničelne slike večkratniki prvega baznega vektorja kodomene.

Drugi bazni vektor lahko pogosto izberemo na neskončno mnogo načinov, dokler s prvim tvori bazo.

---

# 29. Rešen primer: koliko baz ustreza zahtevani matriki

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
$$

$$
A(x,y,z)=(2x+z,4x+2z).
$$

Želimo bazo $\Delta=(d_1,d_2)$ prostora $\mathbb R^2$, da bo

$$
M_{\Delta\leftarrow E}(A)
=
\begin{pmatrix}
2&0&1\\
0&0&0
\end{pmatrix}.
$$

## Rešitev

Izračunamo:

$$
A(e_1)=(2,4),
$$

$$
A(e_2)=(0,0),
$$

$$
A(e_3)=(1,2).
$$

Iz prvega stolpca zahtevane matrike mora veljati:

$$
A(e_1)=2d_1.
$$

Zato:

$$
d_1=(1,2).
$$

Tretji stolpec nato pravilno daje:

$$
A(e_3)=d_1=(1,2).
$$

Drugi bazni vektor $d_2$ v matriki sploh ne nastopa, zato je lahko poljuben vektor, ki ni večkratnik $d_1$:

$$
d_2\notin L\{(1,2)\}.
$$

Takih vektorjev je neskončno mnogo.

Zato obstaja:

$$
\boxed{\text{neskončno mnogo takih urejenih baz } \Delta.}
$$

---

# 30. Tip naloge: jedro, slika in nato matrika v novih bazah

## Kako jo prepoznam

Naloga poda matriko $A$ v običajnih bazah in zahteva več korakov:

1. bazo $\ker A$,
2. bazo $\operatorname{Im} A$,
3. koordinate teh vektorjev v drugih bazah,
4. matriko $A$ v novih bazah.

To je eden najcelovitejših tipov Vaj 10.

## Postopek

### Jedro

Rešim:

$$
Ax=0.
$$

Baza množice rešitev je baza $\ker A$.

### Slika

Vzamem linearno neodvisne pivotne stolpce **iz originalne matrike**.

Ti tvorijo bazo $\operatorname{Im} A$.

### Matrika v novih bazah

Uporabim:

$$
M_{\Pi\leftarrow\Omega}(A)
=
B_\Pi^{-1}AB_\Omega.
$$

---

# 31. Rešen celovit primer po vzoru Vaj 10

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

Gre za preslikavo

$$
A:\mathbb R^3\to\mathbb R^4.
$$

Naj bo baza domene

$$
\Omega=
((0,1,0),(1,1,0),(1,1,1))
$$

in baza kodomene

$$
\Pi=
((1,0,0,0),(0,0,1,1),(0,1,0,0),(0,1,1,0)).
$$

## (a) Baza jedra

Rešujemo:

$$
A
\begin{pmatrix}
x\\
y\\
z
\end{pmatrix}
=
0.
$$

Sistem je:

$$
x+z=0,
$$

$$
-y+z=0,
$$

$$
2x+2y=0,
$$

$$
-2y+2z=0.
$$

Iz druge enačbe:

$$
z=y.
$$

Iz prve:

$$
x=-y.
$$

Zato:

$$
(x,y,z)=t(-1,1,1).
$$

Torej:

$$
\boxed{
\ker A=L\{(-1,1,1)\}.
}
$$

## (b) Baza slike

Stolpci matrike so:

$$
c_1=
\begin{pmatrix}
1\\
0\\
2\\
0
\end{pmatrix},
\qquad
c_2=
\begin{pmatrix}
0\\
-1\\
2\\
-2
\end{pmatrix},
\qquad
c_3=
\begin{pmatrix}
1\\
1\\
0\\
2
\end{pmatrix}.
$$

Velja:

$$
c_3=c_1-c_2.
$$

Zato sta $c_1,c_2$ linearno neodvisna in:

$$
\boxed{
\operatorname{Im}A
=
L\left\{
\begin{pmatrix}
1\\
0\\
2\\
0
\end{pmatrix},
\begin{pmatrix}
0\\
-1\\
2\\
-2
\end{pmatrix}
\right\}.
}
$$

Torej:

$$
\rank A=2.
$$

Preverjanje z izrekom o rangu in ničelnosti:

$$
\dim\ker A+\rank A
=
1+2=3
=
\dim\mathbb R^3.
$$

## (c) Koordinate baze jedra v bazi $\Omega$

Iščemo:

$$
[(-1,1,1)]_\Omega.
$$

Dobimo:

$$
(-1,1,1)
=
2(0,1,0)
-2(1,1,0)
+1(1,1,1).
$$

Zato:

$$
\boxed{
[(-1,1,1)]_\Omega
=
\begin{pmatrix}
2\\
-2\\
1
\end{pmatrix}.
}
$$

## (d) Koordinate baznih vektorjev slike v bazi $\Pi$

Za

$$
c_1=(1,0,2,0)
$$

dobimo:

$$
[c_1]_\Pi
=
\begin{pmatrix}
1\\
0\\
-2\\
2
\end{pmatrix}.
$$

Za

$$
c_2=(0,-1,2,-2)
$$

dobimo:

$$
[c_2]_\Pi
=
\begin{pmatrix}
0\\
-2\\
-5\\
4
\end{pmatrix}.
$$

## (e) Matrika $A$ glede na bazi $\Omega$ in $\Pi$

Uporabimo:

$$
M_{\Pi\leftarrow\Omega}(A)
=
B_\Pi^{-1}AB_\Omega.
$$

Rezultat je:

$$
\boxed{
M_{\Pi\leftarrow\Omega}(A)
=
\begin{pmatrix}
0&1&2\\
-2&-2&0\\
-5&-7&-4\\
4&6&4
\end{pmatrix}.
}
$$

### Preverjanje

Nova matrika mora imeti isti rang:

$$
\rank M_{\Pi\leftarrow\Omega}(A)=2.
$$

---

# 32. Tip naloge: jedro in slika neposredno iz matrike

## Kako jo prepoznam

Podana je matrika preslikave v običajnih bazah in sprašujejo po $\ker A$ ter $\operatorname{Im} A$.

Ta tip se na Vajah 10 pojavi skupaj z matrično predstavitvijo preslikav.

## Primer

Naj bo

$$
A=
\begin{pmatrix}
1&-1&2\\
1&-1&4
\end{pmatrix}.
$$

## Jedro

Rešujemo:

$$
\begin{pmatrix}
1&-1&2\\
1&-1&4
\end{pmatrix}
\begin{pmatrix}
x\\
y\\
z
\end{pmatrix}
=0.
$$

Odštejemo prvo enačbo od druge:

$$
2z=0
\Rightarrow
z=0.
$$

Nato:

$$
x-y=0
\Rightarrow
x=y.
$$

Zato:

$$
\boxed{
\ker A=L\{(1,1,0)\}.
}
$$

## Slika

Stolpci so:

$$
\begin{pmatrix}
1\\
1
\end{pmatrix},
\quad
\begin{pmatrix}
-1\\
-1
\end{pmatrix},
\quad
\begin{pmatrix}
2\\
4
\end{pmatrix}.
$$

Prvi in tretji sta linearno neodvisna, zato:

$$
\boxed{
\operatorname{Im}A=\mathbb R^2.
}
$$

---

# 33. Najpogostejše konceptualne napake

## Napaka 1: vektor in njegove koordinate sta ista stvar

Napačno:

$$
v=[v]_\Sigma
$$

v splošnem.

Pravilno:

$$
v=B_\Sigma[v]_\Sigma.
$$

---

## Napaka 2: napačna smer prehodne matrike

Če želimo iz $[v]_\Sigma$ dobiti $[v]_\Delta$, potrebujemo:

$$
P_{\Delta\leftarrow\Sigma}.
$$

Ne obratno.

---

## Napaka 3: bazni vektorji kot vrstice

Pri

$$
B_\Sigma
$$

so bazni vektorji **stolpci**.

---

## Napaka 4: neposredno množim matriko z vektorjem v napačni bazi

Če je

$$
M_\Lambda(A)
$$

matrika v bazi $\Lambda$, lahko z njo množim samo stolpec

$$
[v]_\Lambda.
$$

Ne smem je neposredno množiti z $[v]_\Pi$, če je $\Pi\neq\Lambda$.

---

## Napaka 5: vrstni red pri kompoziciji

Če je

$$
BA=B\circ A,
$$

potem najprej deluje $A$:

$$
M(BA)=M(B)M(A).
$$

---

## Napaka 6: napačna formula pri spremembi baze

Pri endomorfizmu:

$$
A_{\text{nova}}
=
S^{-1}A_{\text{stara}}S,
$$

ne:

$$
S A S^{-1}
$$

razen če je $S$ definirana v obratni smeri.

Zato moram vedno vedeti, kaj moja matrika $S$ pretvarja.

---

## Napaka 7: rang naj bi se spremenil z bazo

Ne.

Če spremenimo bazi:

$$
M_{\text{nova}}=PM_{\text{stara}}Q
$$

z obrnljivima $P,Q$, potem:

$$
\rank M_{\text{nova}}=\rank M_{\text{stara}}.
$$

---

# 34. Ustni / teoretični del

## Ustno vprašanje 1

**Vprašanje:** Kaj je urejena baza?

**Kratek odgovor:** Urejena baza prostora $V$ je baza, pri kateri je določen tudi vrstni red baznih vektorjev:

$$
\Sigma=(v_1,\dots,v_n).
$$

Vrstni red je pomemben, ker določa vrstni red koordinat v koordinatnem stolpcu.

**Profesor lahko dodatno vpraša:** Ali bazi $(v_1,v_2)$ in $(v_2,v_1)$ določata iste koordinate?

**Odgovor:** Ne. Gre za različni urejeni bazi in koordinati se praviloma zamenjata oziroma drugače spremenita.

---

## Ustno vprašanje 2

**Vprašanje:** Kaj je koordinatni stolpec vektorja?

**Kratek odgovor:** Če je $\Sigma=(v_1,\dots,v_n)$ baza in

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n,
$$

potem je

$$
[v]_\Sigma=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}.
$$

**Profesor lahko dodatno vpraša:** Zakaj so koordinate enolične?

**Odgovor:** Ker je baza linearno neodvisna. Če bi obstajala dva različna razvoja, bi z odštevanjem dobili netrivialno linearno kombinacijo baznih vektorjev, enako nič.

---

## Ustno vprašanje 3

**Vprašanje:** Dokaži enoličnost koordinat.

**Kratek odgovor:** Recimo, da velja

$$
v=\sum_{i=1}^n\alpha_iv_i
$$

in

$$
v=\sum_{i=1}^n\beta_iv_i.
$$

Odštejemo:

$$
0=\sum_{i=1}^n(\alpha_i-\beta_i)v_i.
$$

Ker so $v_i$ linearno neodvisni:

$$
\alpha_i-\beta_i=0
$$

za vsak $i$, torej:

$$
\alpha_i=\beta_i.
$$

---

## Ustno vprašanje 4

**Vprašanje:** Kaj je koordinatna preslikava?

**Kratek odgovor:** Za urejeno bazo $\Sigma$ prostora $V$, $\dim V=n$, je

$$
X_\Sigma:V\to F^n,
\qquad
v\mapsto[v]_\Sigma.
$$

To je linearen izomorfizem.

**Profesor lahko dodatno vpraša:** Zakaj je surjektivna?

**Odgovor:** Za vsak stolpec $(\alpha_1,\dots,\alpha_n)^T$ obstaja vektor

$$
v=\alpha_1v_1+\cdots+\alpha_nv_n,
$$

ki ima natanko te koordinate.

---

## Ustno vprašanje 5

**Vprašanje:** Kaj je prehodna matrika?

**Kratek odgovor:** Prehodna matrika iz baze $\Sigma$ v bazo $\Delta$ je matrika, ki pretvori koordinatni stolpec istega vektorja:

$$
[v]_\Delta
=
P_{\Delta\leftarrow\Sigma}[v]_\Sigma.
$$

**Profesor lahko dodatno vpraša:** Kako jo izračunamo?

**Odgovor:**

$$
P_{\Delta\leftarrow\Sigma}
=
B_\Delta^{-1}B_\Sigma.
$$

---

## Ustno vprašanje 6

**Vprašanje:** Zakaj je vsaka prehodna matrika obrnljiva?

**Kratek odgovor:** Ker predstavlja identično preslikavo med dvema koordinatnima predstavitvama istega prostora. Prehod lahko vedno obrnemo:

$$
P_{\Sigma\leftarrow\Delta}
=
P_{\Delta\leftarrow\Sigma}^{-1}.
$$

**Profesor lahko dodatno vpraša:** Kaj je inverz?

**Odgovor:** Prehodna matrika v nasprotni smeri.

---

## Ustno vprašanje 7

**Vprašanje:** Kako definiramo matriko linearne preslikave glede na izbrani bazi?

**Kratek odgovor:** Za

$$
A:V\to W,
$$

bazo $\Sigma=(v_1,\dots,v_n)$ prostora $V$ in bazo $\Delta$ prostora $W$ definiramo matriko z lastnostjo:

$$
[A(v)]_\Delta
=
M_{\Delta\leftarrow\Sigma}(A)[v]_\Sigma.
$$

Njeni stolpci so:

$$
[A(v_1)]_\Delta,\dots,[A(v_n)]_\Delta.
$$

---

## Ustno vprašanje 8

**Vprašanje:** Zakaj so stolpci matrike preslikave slike baznih vektorjev?

**Kratek odgovor:** Ker je

$$
[e_i]_E
$$

$i$-ti standardni stolpec. Za bazni vektor $v_i$ velja:

$$
[v_i]_\Sigma=e_i.
$$

Zato:

$$
M_{\Delta\leftarrow\Sigma}(A)e_i
=
[A(v_i)]_\Delta,
$$

kar je ravno $i$-ti stolpec matrike.

---

## Ustno vprašanje 9

**Vprašanje:** Kakšne velikosti je matrika linearne preslikave $A:V\to W$?

**Kratek odgovor:** Če

$$
\dim V=n,
\qquad
\dim W=m,
$$

je matrika velikosti:

$$
m\times n.
$$

**Profesor lahko dodatno vpraša:** Zakaj?

**Odgovor:** Ima $n$ stolpcev, enega za vsak bazni vektor domene, vsak stolpec pa ima $m$ koordinat glede na bazo kodomene.

---

## Ustno vprašanje 10

**Vprašanje:** Kakšna je matrika kompozituma?

**Kratek odgovor:** Če so vmesne baze kompatibilne:

$$
M(B\circ A)
=
M(B)M(A).
$$

**Profesor lahko dodatno vpraša:** Katera preslikava deluje prva?

**Odgovor:** $A$. Zato je njena matrika v produktu na desni.

---

## Ustno vprašanje 11

**Vprašanje:** Kakšna je matrika identične preslikave?

**Kratek odgovor:** Glede na isto bazo:

$$
M_{\Sigma\leftarrow\Sigma}(\operatorname{id})=I.
$$

Glede na dve različni bazi pa je matrika identitete prehodna matrika:

$$
M_{\Delta\leftarrow\Sigma}(\operatorname{id})
=
P_{\Delta\leftarrow\Sigma}.
$$

---

## Ustno vprašanje 12

**Vprašanje:** Kakšna je matrika inverzne linearne preslikave?

**Kratek odgovor:** Če je $A$ izomorfizem, potem:

$$
M(A^{-1})=M(A)^{-1}
$$

ob ustrezno zamenjanih bazah domene in kodomene.

**Profesor lahko dodatno vpraša:** Kdaj inverzna preslikava obstaja?

**Odgovor:** Natanko tedaj, ko je $A$ bijektivna.

---

## Ustno vprašanje 13

**Vprašanje:** Kako se spremeni matrika linearne preslikave pri spremembi baz?

**Kratek odgovor:**

$$
M_{\Lambda\leftarrow\Gamma}(A)
=
P_{\Lambda\leftarrow\Delta}
M_{\Delta\leftarrow\Sigma}(A)
P_{\Sigma\leftarrow\Gamma}.
$$

**Profesor lahko dodatno vpraša:** Kaj pomenita prehodni matriki?

**Odgovor:** Desna najprej pretvori nove koordinate domene v stare, leva pa stare koordinate slike v nove koordinate kodomene.

---

## Ustno vprašanje 14

**Vprašanje:** Kaj pomeni podobnost matrik?

**Kratek odgovor:** Kvadratni matriki $A$ in $B$ sta podobni, če obstaja obrnljiva $S$, da:

$$
B=S^{-1}AS.
$$

**Profesor lahko dodatno vpraša:** Kaj podobni matriki predstavljata?

**Odgovor:** Isti endomorfizem glede na dve različni urejeni bazi.

---

## Ustno vprašanje 15

**Vprašanje:** Dokaži formulo za spremembo baze pri endomorfizmu.

**Kratek odgovor:** Naj bo

$$
[v]_\Sigma=S[v]_\Gamma.
$$

Za staro matriko $A_\Sigma$ velja:

$$
[A(v)]_\Sigma=A_\Sigma[v]_\Sigma.
$$

Vstavimo:

$$
[A(v)]_\Sigma=A_\Sigma S[v]_\Gamma.
$$

Ker je

$$
[A(v)]_\Gamma=S^{-1}[A(v)]_\Sigma,
$$

dobimo:

$$
[A(v)]_\Gamma
=
S^{-1}A_\Sigma S[v]_\Gamma.
$$

Zato:

$$
\boxed{
A_\Gamma=S^{-1}A_\Sigma S.
}
$$

---

## Ustno vprašanje 16

**Vprašanje:** Zakaj rang matrike ni odvisen od izbire baz?

**Kratek odgovor:** Pri spremembi baz dobimo:

$$
M_{\text{nova}}=PM_{\text{stara}}Q,
$$

kjer sta $P,Q$ obrnljivi. Množenje z obrnljivo matriko ne spremeni dimenzije stolpčnega oziroma vrstičnega prostora, zato:

$$
\rank M_{\text{nova}}=\rank M_{\text{stara}}.
$$

**Profesor lahko dodatno vpraša:** Kaj to pomeni za linearno preslikavo?

**Odgovor:** Rang je lastnost same linearne preslikave, ne njene matrične predstavitve.

---

# 35. Dokazi in izpeljave, ki jih moram znati

## 35.1 Enoličnost koordinat

Moram znati dokaz z odštevanjem dveh razvojov in uporabo linearne neodvisnosti baze.

---

## 35.2 Linearnost koordinatne preslikave

Če

$$
u=\sum_i\alpha_iv_i
$$

in

$$
v=\sum_i\beta_iv_i,
$$

potem:

$$
au+bv
=
\sum_i(a\alpha_i+b\beta_i)v_i.
$$

Zato:

$$
[au+bv]_\Sigma
=
a[u]_\Sigma+b[v]_\Sigma.
$$

---

## 35.3 Formula za prehodno matriko

Iz:

$$
v=B_\Sigma[v]_\Sigma
$$

in

$$
[v]_\Delta=B_\Delta^{-1}v
$$

dobimo:

$$
[v]_\Delta
=
B_\Delta^{-1}B_\Sigma[v]_\Sigma.
$$

Torej:

$$
P_{\Delta\leftarrow\Sigma}
=
B_\Delta^{-1}B_\Sigma.
$$

---

## 35.4 Matrika kompozituma

$$
[(B\circ A)(v)]_\Gamma
=
M_{\Gamma\leftarrow\Delta}(B)
[A(v)]_\Delta
$$

$$
=
M_{\Gamma\leftarrow\Delta}(B)
M_{\Delta\leftarrow\Sigma}(A)
[v]_\Sigma.
$$

Zato:

$$
M(B\circ A)
=
M(B)M(A).
$$

---

## 35.5 Formula za spremembo baz

Moram znati verigo:

$$
[v]_\Gamma
\to
[v]_\Sigma
\to
[A(v)]_\Delta
\to
[A(v)]_\Lambda.
$$

Zato:

$$
M_{\Lambda\leftarrow\Gamma}(A)
=
P_{\Lambda\leftarrow\Delta}
M_{\Delta\leftarrow\Sigma}(A)
P_{\Sigma\leftarrow\Gamma}.
$$

---

# 36. Povezave z drugimi koncepti

## Baza in koordinatna preslikava

Izbira baze omogoči, da abstraktni prostor $V$ predstavimo kot $F^n$.

---

## Linearna preslikava in matrika

Ko izberemo baze domene in kodomene, vsaka linearna preslikava dobi natanko eno matriko.

---

## Jedro in matrika

Če je $M$ matrika $A$, potem:

$$
\ker A
\longleftrightarrow
\{x;Mx=0\}.
$$

---

## Slika in matrika

Slika $A$ je generirana s stolpci matrike $A$.

---

## Rang in matrika

$$
\rank A
=
\rank M(A).
$$

Rang je neodvisen od izbire baz.

---

## Podobnost in diagonalizacija

Kasneje bomo iskali bazo, v kateri bo matrika endomorfizma diagonalna.

To pomeni poiskati $S$, da:

$$
D=S^{-1}AS.
$$

Torej je diagonalizacija neposredno nadaljevanje te faze.

---

# 37. Strategija za izpit

## Če je naloga kratka

Najprej preverim:

1. katere baze so podane,
2. v kateri bazi je vhod,
3. glede na katere baze je podana matrika,
4. v kateri bazi mora biti rezultat.

Nato napišem eno pravilno matrično enačbo.

---

## Če je naloga dolga in uporablja več baz

Na rob si napišem:

$$
[x]_{\text{začetna baza}}
\rightarrow
[x]_{\text{baza matrike}}
\rightarrow
[A(x)]_{\text{baza matrike}}
\rightarrow
[A(x)]_{\text{zahtevana baza}}.
$$

Tako skoraj povsem preprečim zamenjavo baz.

---

## Če ne vem, ali potrebujem matriko ali njen inverz

Vprašam se:

> Kaj imam in kaj želim?

Če imam $[v]_\Sigma$ in želim $[v]_\Delta$, potrebujem:

$$
P_{\Delta\leftarrow\Sigma}.
$$

Puščica je najbolj varen način preverjanja.

---

# 38. Naloge za samostojno reševanje

## Srednje težke naloge

### Naloga 1

Naj bo

$$
\Sigma=((1,1,0),(0,1,1),(1,0,1))
$$

urejena baza prostora $\mathbb R^3$ in

$$
v=(3,2,1).
$$

Določi:

$$
[v]_\Sigma.
$$

---

### Naloga 2

V bazi

$$
\Sigma=(1,1+x,1+x+x^2)
$$

ima polinom $f\in\mathbb R_2[x]$ koordinate

$$
[f]_\Sigma=
\begin{pmatrix}
2\\
-1\\
3
\end{pmatrix}.
$$

1. Določi $f$ v standardni obliki.
2. Določi $[f]_\Delta$ za

$$
\Delta=(1,x,2x^2).
$$

---

### Naloga 3

Naj bo

$$
E=((1,0),(0,1))
$$

običajna baza in

$$
\Delta=((1,2),(2,3)).
$$

1. Poišči $P_{\Delta\leftarrow E}$.
2. Poišči $[(5,8)]_\Delta$.

---

### Naloga 4

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
$$

$$
A(x,y,z)=(x+2y-z,3x-y+2z).
$$

1. Poišči matriko $A$ v običajnih bazah.
2. Izračunaj $A(1,-1,2)$.

---

### Naloga 5

Naj bo

$$
A:\mathbb R_2[x]\to\mathbb R^2.
$$

Baza domene je

$$
\Sigma=(1,x,x^2),
$$

baza kodomene pa

$$
\Delta=((1,1),(1,-1)).
$$

Podana je matrika:

$$
M_{\Delta\leftarrow\Sigma}(A)
=
\begin{pmatrix}
1&0&2\\
-1&3&1
\end{pmatrix}.
$$

Določi:

1. $A(1)$,
2. $A(x)$,
3. $A(x^2)$,
4. $A(1+x)$

v običajnih koordinatah prostora $\mathbb R^2$.

---

### Naloga 6

Naj bosta

$$
A:\mathbb R^2\to\mathbb R^3,
\qquad
B:\mathbb R^3\to\mathbb R^2
$$

z matrikama v običajnih bazah:

$$
M(A)=
\begin{pmatrix}
1&0\\
2&1\\
0&1
\end{pmatrix},
$$

$$
M(B)=
\begin{pmatrix}
1&-1&0\\
0&2&1
\end{pmatrix}.
$$

Poišči matriko:

$$
M(B\circ A).
$$

---

### Naloga 7

Naj bo

$$
M_E(A)=
\begin{pmatrix}
2&1\\
1&1
\end{pmatrix}.
$$

Naj bo baza domene

$$
\Gamma=((1,1),(1,0))
$$

in baza kodomene

$$
\Lambda=((1,0),(1,1)).
$$

Izračunaj:

$$
M_{\Lambda\leftarrow\Gamma}(A).
$$

---

## Težke / izpitne naloge

### Naloga 8

V prostoru $\mathbb R^3$ so dane urejene baze:

$$
\Gamma=((1,0,0),(1,1,0),(1,1,1)),
$$

$$
\Lambda=((1,1,0),(0,1,1),(1,0,1)),
$$

$$
\Pi=((1,0,1),(0,1,0),(1,0,0)).
$$

Endomorfizem $A$ ima v bazi $\Gamma$ matriko

$$
M_\Gamma(A)=
\begin{pmatrix}
1&0&2\\
0&1&-1\\
1&1&0
\end{pmatrix}.
$$

Za $x$ velja:

$$
[x]_\Pi=
\begin{pmatrix}
1\\
-1\\
2
\end{pmatrix}.
$$

Določi:

$$
[A(x)]_\Lambda.
$$

---

### Naloga 9

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
$$

$$
A(x,y,z)=(x+2y,2x+4y).
$$

Katera izmed naslednjih matrik bi lahko bila matrika iste preslikave $A$ glede na neke urejene baze domene in kodomene?

$$
M_1=
\begin{pmatrix}
1&0&0\\
0&1&0
\end{pmatrix},
$$

$$
M_2=
\begin{pmatrix}
1&2&0\\
0&0&0
\end{pmatrix},
$$

$$
M_3=
\begin{pmatrix}
0&0&0\\
0&0&0
\end{pmatrix}.
$$

Utemelji z rangom.

---

### Naloga 10

Naj bo

$$
A:\mathbb R^3\to\mathbb R^2,
$$

$$
A(x,y,z)=(x+z,2x+2z).
$$

Poišči vse urejene baze

$$
\Delta=(d_1,d_2)
$$

prostora $\mathbb R^2$, za katere velja

$$
M_{\Delta\leftarrow E}(A)
=
\begin{pmatrix}
1&0&1\\
0&0&0
\end{pmatrix}.
$$

Koliko takih baz obstaja?

---

### Naloga 11

Endomorfizem $A:\mathbb R^2\to\mathbb R^2$ ima v običajni bazi matriko

$$
M_E(A)
=
\begin{pmatrix}
2&1\\
0&3
\end{pmatrix}.
$$

Naj bo

$$
\Gamma=((1,1),(1,0)).
$$

1. Poišči $M_\Gamma(A)$.
2. Preveri, da sta matriki podobni.
3. Zapiši ustrezno matriko $S$ v zvezi

$$
M_\Gamma(A)=S^{-1}M_E(A)S.
$$

---

### Naloga 12

Naj bo

$$
A:\mathbb R^3\to\mathbb R^3
$$

z matriko v običajni bazi

$$
M_E(A)=
\begin{pmatrix}
1&1&0\\
0&1&1\\
1&2&1
\end{pmatrix}.
$$

Naj bo

$$
\Omega=((1,0,0),(1,1,0),(1,1,1))
$$

baza domene in

$$
\Pi=((0,0,1),(1,0,0),(0,1,0))
$$

baza kodomene.

Določi:

1. bazo $\ker A$,
2. bazo $\operatorname{Im}A$,
3. rang $A$,
4. matriko

$$
M_{\Pi\leftarrow\Omega}(A).
$$

---

# 39. Odgovori

## Srednje težke naloge

**1.**

$$
\boxed{
[v]_\Sigma=
\begin{pmatrix}
2\\
0\\
1
\end{pmatrix}
}
$$

---

**2.**

$$
\boxed{
f(x)=4+2x+3x^2
}
$$

$$
\boxed{
[f]_\Delta=
\begin{pmatrix}
4\\
2\\
\frac32
\end{pmatrix}
}
$$

---

**3.**

$$
B_\Delta=
\begin{pmatrix}
1&2\\
2&3
\end{pmatrix}
$$

$$
\boxed{
P_{\Delta\leftarrow E}
=
\begin{pmatrix}
-3&2\\
2&-1
\end{pmatrix}
}
$$

$$
\boxed{
[(5,8)]_\Delta=
\begin{pmatrix}
1\\
2
\end{pmatrix}
}
$$

---

**4.**

$$
\boxed{
M(A)=
\begin{pmatrix}
1&2&-1\\
3&-1&2
\end{pmatrix}
}
$$

$$
\boxed{
A(1,-1,2)=(-3,8)
}
$$

---

**5.**

$$
\boxed{
A(1)=(0,2)
}
$$

$$
\boxed{
A(x)=(3,-3)
}
$$

$$
\boxed{
A(x^2)=(3,1)
}
$$

$$
\boxed{
A(1+x)=(3,-1)
}
$$

---

**6.**

$$
\boxed{
M(B\circ A)
=
\begin{pmatrix}
-1&-1\\
4&3
\end{pmatrix}
}
$$

---

**7.**

$$
\boxed{
M_{\Lambda\leftarrow\Gamma}(A)
=
\begin{pmatrix}
1&1\\
2&1
\end{pmatrix}
}
$$

---

## Težke / izpitne naloge

**8.**

$$
\boxed{
[A(x)]_\Lambda=
\begin{pmatrix}
1\\
-2\\
4
\end{pmatrix}
}
$$

---

**9.**

$$
\rank A=1.
$$

Zato je možna samo:

$$
\boxed{
M_2=
\begin{pmatrix}
1&2&0\\
0&0&0
\end{pmatrix}.
}
$$

---

**10.**

$$
\boxed{
d_1=(1,2)
}
$$

in

$$
\boxed{
d_2\in\mathbb R^2\setminus L\{(1,2)\}.
}
$$

Torej:

$$
\boxed{\text{neskončno mnogo baz}.}
$$

---

**11.**

$$
S=
\begin{pmatrix}
1&1\\
1&0
\end{pmatrix}
$$

$$
\boxed{
M_\Gamma(A)
=
\begin{pmatrix}
3&0\\
0&2
\end{pmatrix}
}
$$

in

$$
\boxed{
M_\Gamma(A)
=
S^{-1}M_E(A)S.
}
$$

---

**12.**

$$
\boxed{
\ker A=L\{(1,-1,1)\}
}
$$

$$
\boxed{
\operatorname{Im}A
=
L\{(1,0,1),(1,1,2)\}
}
$$

$$
\boxed{
\rank A=2
}
$$

$$
\boxed{
M_{\Pi\leftarrow\Omega}(A)
=
\begin{pmatrix}
1&3&4\\
1&2&2\\
0&1&2
\end{pmatrix}
}
$$

---

# 40. Faza je zaključena, ko znam ...

- [ ] natančno definirati **urejeno bazo**;
- [ ] natančno definirati **koordinatni stolpec** $[v]_\Sigma$;
- [ ] razložiti razliko med vektorjem $v$ in njegovimi koordinatami $[v]_\Sigma$;
- [ ] izračunati koordinate vektorja v poljubni podani bazi;
- [ ] iz koordinatnega stolpca rekonstruirati dejanski vektor;
- [ ] računati koordinate polinomov v nestandardnih bazah;
- [ ] sestaviti matriko baze $B_\Sigma$;
- [ ] uporabiti formuli $v=B_\Sigma[v]_\Sigma$ in $[v]_\Sigma=B_\Sigma^{-1}v$;
- [ ] natančno definirati **prehodno matriko**;
- [ ] izračunati $P_{\Delta\leftarrow\Sigma}=B_\Delta^{-1}B_\Sigma$;
- [ ] pravilno določiti smer prehodne matrike;
- [ ] uporabiti $P_{\Sigma\leftarrow\Delta}=P_{\Delta\leftarrow\Sigma}^{-1}$;
- [ ] sestavljati več zaporednih prehodov med bazami;
- [ ] natančno definirati matriko linearne preslikave glede na dve bazi;
- [ ] pojasniti, zakaj so stolpci matrike koordinatni stolpci slik baznih vektorjev domene;
- [ ] določiti velikost matrike preslikave $A:V\to W$;
- [ ] iz predpisa $A(x)$ sestaviti matriko v običajnih bazah;
- [ ] iz matrike in koordinat vhodnega vektorja izračunati koordinate slike;
- [ ] iz matrike preslikave rekonstruirati slike baznih vektorjev;
- [ ] uporabiti formulo $M(B\circ A)=M(B)M(A)$;
- [ ] pojasniti vrstni red množenja pri kompoziciji;
- [ ] razložiti, zakaj je prehodna matrika matrika identične preslikave glede na dve različni bazi;
- [ ] uporabiti zvezo med matriko preslikave in matriko njene inverzne preslikave;
- [ ] izračunati matriko preslikave glede na nestandardni bazi z metodo po stolpcih;
- [ ] uporabiti formulo $M_{\Delta\leftarrow\Sigma}(A)=B_\Delta^{-1}M_E(A)B_\Sigma$;
- [ ] pravilno reševati naloge, kjer je vektor podan v eni bazi, matrika $A$ v drugi, rezultat pa se zahteva v tretji;
- [ ] uporabiti splošno formulo za spremembo baz;
- [ ] natančno definirati **podobnost matrik**;
- [ ] uporabiti formulo $A_{\text{nova}}=S^{-1}A_{\text{stara}}S$;
- [ ] razložiti, zakaj podobni matriki predstavljata isti endomorfizem v različnih bazah;
- [ ] razložiti, zakaj se rang linearne preslikave pri spremembi baz ne spremeni;
- [ ] uporabiti rang za hitro izločanje nemogočih matričnih predstavitev iste preslikave;
- [ ] iz podane želene matrike preslikave sklepati na potrebno bazo kodomene;
- [ ] iz matrike izračunati $\ker A$ in $\operatorname{Im}A$;
- [ ] povezati rang matrike z rangom linearne preslikave;
- [ ] preveriti rezultat z izrekom $\dim\ker A+\rank A=\dim V$;
- [ ] dokazati enoličnost koordinat glede na bazo;
- [ ] dokazati linearnost koordinatne preslikave;
- [ ] izpeljati formulo za prehodno matriko;
- [ ] izpeljati formulo za matriko kompozituma;
- [ ] izpeljati formulo za spremembo baze pri endomorfizmu;
- [ ] na ustnem izpitu brez zapiskov odgovoriti na vprašanja o koordinatah, prehodnih matrikah, matrični predstavitvi linearne preslikave, kompoziciji, inverzu in podobnosti;
- [ ] pri večbazni nalogi vedno pravilno določiti, **v kateri bazi je vsak vmesni koordinatni stolpec**.
