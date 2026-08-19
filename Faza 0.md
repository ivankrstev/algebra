# FAZA 0 — Algebraične osnove: operacije, grupe in kolobarji

## Namen faze

Ta faza pokriva algebraične osnove, ki se v priloženem gradivu pojavijo v **1., 2. in 3. vajah**:

- dvomestne notranje operacije,
- komutativnost in asociativnost,
- levi in desni nevtralni elementi,
- levi in desni obrati,
- grupe in komutativne grupe,
- pravilo krajšanja in osnovne posledice grupnih aksiomov,
- polgrupe z identiteto,
- red elementa,
- obrnljivost elementov,
- kolobarji,
- levi in desni delitelji niča.

V priloženih datotekah ni ločenih preteklih izpitov ali kolokvijev. Zato so prioritete v tej fazi določene po **Vajah 1–3** in po tipih nalog, ki se tam sistematično ponavljajo. Težje naloge na koncu so sestavljene v istem slogu in iz iste teorije, niso pa predstavljene kot dejanske pretekle izpitne naloge.

## Podlaga v priloženem gradivu

- **1. vaje, naloge 1–4:** notranje operacije, komutativnost, asociativnost.
- **2. vaje, naloge 5–7:** obrati in preverjanje, ali je dana struktura grupa.
- **3. vaje, naloge 8–10:** posledice grupnih aksiomov, red elementa in obrnljivost.
- **3. vaje, naloge 11–13:** kolobarji in levi/desni delitelji niča.

## Prioriteta za izpit

1. **Preverjanje, ali je dana struktura grupa.**
2. **Iskanje identitete in obratov pri nestandardni operaciji.**
3. **Preverjanje notranjosti, asociativnosti in komutativnosti.**
4. **Red elementa in obrnljivost v $\mathbb Z_n$.**
5. **Preverjanje aksiomov kolobarja.**
6. **Levi in desni delitelji niča v nekomutativnih primerih.**
7. **Teoretične posledice aksiomov grupe:** enoličnost identitete, enoličnost obrata, pravilo krajšanja.

---

## 1. Predpogoji in oznake

Pred začetkom te faze moraš obvladati:

- množice $\mathbb N$, $\mathbb Z$, $\mathbb Q$, $\mathbb R$,
- računanje po modulu $n$ v $\mathbb Z_n$,
- osnovno računanje z matrikami,
- pojem preslikave,
- razliko med trditvijo, ki jo moraš **dokazati za vse elemente**, in protiprimerom, ki zadošča za **ovržbo** trditve.

Uporabljali bomo:

- $e$ za nevtralni element pri splošni grupni operaciji,
- $0$ za nevtralni element pri seštevanju,
- $1$ za nevtralni element pri množenju,
- $a^{-1}$ za obrat elementa $a$ v grupi,
- $a^n$ za $n$-kratni produkt elementa $a$ pri multiplikativnem zapisu,
- $na$ za $n$-kratno vsoto elementa $a$ pri aditivnem zapisu.

---

## 2. Dvomestna notranja operacija

### 2.1 Definicija

Naj bo $S$ neprazna množica. **Dvomestna notranja operacija** na $S$ je preslikava

$$
\circ:S\times S\to S.
$$

To pomeni:

$$
\forall a,b\in S:\quad a\circ b\in S.
$$

Beseda **notranja** pomeni, da rezultat operacije ne zapusti množice $S$.

### 2.2 Kaj moraš pri nalogi preveriti

Če naloga sprašuje:

> Ali predpis definira dvomestno notranjo operacijo na $S$?

preveri dve stvari:

1. ali je izraz definiran za **vsak** par $(a,b)\in S\times S$;
2. ali rezultat vedno pripada $S$.

Za zavrnitev zadošča **en sam protiprimer**.

### 2.3 Tipični razlogi, da predpis ni notranja operacija

- deljenje z nič:
  $$
  a\circ b=\frac ab;
  $$
- koren negativnega števila, če delamo v $\mathbb R$;
- logaritem z nedovoljeno osnovo ali argumentom;
- rezultat zapusti množico, npr. iz $\mathbb N$ pridemo v negativna cela števila;
- pri matrikah rezultat ne ohrani zahtevane oblike.

### Tip naloge: preverjanje notranjosti operacije

**Kako jo prepoznam**

Naloga poda množico $S$ in predpis $a\circ b$ ter vpraša, ali gre za dvomestno notranjo operacijo.

**Postopek**

1. Vzemi poljubna $a,b\in S$.
2. Preveri, ali je $a\circ b$ vedno definiran.
3. Preveri, ali $a\circ b\in S$.
4. Če ne, napiši konkreten protiprimer.

**Pomembna formula**

$$
\circ:S\times S\to S.
$$

**Primer**

Na $S=\mathbb R$ definiramo

$$
a\circ b=\frac ab.
$$

Ali je $\circ$ dvomestna notranja operacija na $\mathbb R$?

**Rešitev**

Za notranjo operacijo mora biti $a\circ b$ definiran za vsak $a,b\in\mathbb R$.

Izberemo $a=1$ in $b=0$. Tedaj

$$
1\circ 0=\frac10
$$

ni definirano.

Zato predpis **ne definira** dvomestne notranje operacije na $\mathbb R$.

**Pogoste napake**

- Preveriš le, da je rezultat realen, pozabiš pa na nedovoljene vrednosti.
- Preveriš nekaj primerov in iz tega sklepaš, da operacija vedno deluje.
- Za dokaz notranjosti uporabiš en primer; en primer zadošča samo za **ovržbo**, ne za dokaz.

### Ustno vprašanje

**Vprašanje:** Kaj je dvomestna notranja operacija na množici $S$?

**Kratek odgovor:** Dvomestna notranja operacija je preslikava $\circ:S\times S\to S$, torej za vsaka $a,b\in S$ velja $a\circ b\in S$.

**Profesor lahko dodatno vpraša:** Kako najhitreje pokažeš, da predpis ni notranja operacija?

**Odgovor:** Poiščem en par $a,b\in S$, za katerega izraz ni definiran ali rezultat ne pripada $S$.

---

## 3. Komutativnost in asociativnost

### 3.1 Komutativnost

Operacija $\circ$ je **komutativna**, če

$$
\forall a,b\in S:\quad a\circ b=b\circ a.
$$

Pri komutativnosti zamenjamo **vrstni red operandov**.

### 3.2 Asociativnost

Operacija $\circ$ je **asociativna**, če

$$
\forall a,b,c\in S:\quad
(a\circ b)\circ c=a\circ(b\circ c).
$$

Pri asociativnosti ne menjamo vrstnega reda elementov, temveč samo **oklepaje**.

### 3.3 Kako dokazujemo in kako zavračamo

Za dokaz komutativnosti:

$$
a\circ b
\overset{?}=b\circ a
$$

za splošna $a,b$.

Za dokaz asociativnosti izračunaj obe strani:

$$
(a\circ b)\circ c
$$

in

$$
a\circ(b\circ c).
$$

Za zavrnitev komutativnosti ali asociativnosti zadošča en protiprimer.

### Tip naloge: komutativna, vendar ne asociativna operacija

**Kako jo prepoznam**

Naloga zahteva, da med podanimi predpisi poiščeš operacijo, ki ima eno lastnost, druge pa ne.

**Postopek**

1. Najprej preveri notranjost.
2. Za komutativnost primerjaj $a\circ b$ in $b\circ a$.
3. Za asociativnost izračunaj obe razporeditvi oklepajev.
4. Če sumiš, da asociativnost ne velja, poišči majhne konkretne vrednosti.

**Primer**

Na $\mathbb R$ definiramo

$$
a\diamond b=a^2+b^2.
$$

Preveri komutativnost in asociativnost.

**Rešitev**

Komutativnost:

$$
a\diamond b=a^2+b^2=b^2+a^2=b\diamond a.
$$

Operacija je komutativna.

Za asociativnost vzamemo $a=1$, $b=1$, $c=2$.

$$
(1\diamond 1)\diamond 2
=
2\diamond 2
=
2^2+2^2
=
8.
$$

Po drugi strani:

$$
1\diamond(1\diamond 2)
=
1\diamond 5
=
1^2+5^2
=
26.
$$

Ker je

$$
8\neq 26,
$$

operacija ni asociativna.

**Sklep:** $\diamond$ je **komutativna, ni pa asociativna**.

**Pogoste napake**

- Komutativnost in asociativnost zamenjaš.
- Za asociativnost preveriš samo $a\circ b=b\circ a$.
- Iz nekaj uspešnih številskih primerov sklepaš, da je operacija asociativna.
- Pri gnezdenih nestandardnih operacijah ne vstaviš pravilno celotnega rezultata prve operacije.

### Pomembna povezava

Običajno seštevanje realnih števil je komutativno in asociativno, običajno množenje matrik pa je asociativno, vendar na splošno **ni komutativno**.

Če je množica matrik zaprta za običajno množenje, lahko asociativnost pogosto podedujemo iz asociativnosti matričnega množenja.

### Ustno vprašanje

**Vprašanje:** Kakšna je razlika med komutativnostjo in asociativnostjo?

**Kratek odgovor:** Komutativnost dovoljuje zamenjavo vrstnega reda dveh elementov,

$$
a\circ b=b\circ a,
$$

asociativnost pa dovoljuje spreminjanje oklepajev brez spreminjanja vrstnega reda,

$$
(a\circ b)\circ c=a\circ(b\circ c).
$$

**Profesor lahko dodatno vpraša:** Ali je vsaka asociativna operacija komutativna?

**Odgovor:** Ne. Običajno množenje matrik je asociativno, vendar v splošnem ni komutativno.

---

## 4. Nevtralni element

### 4.1 Levi in desni nevtralni element

Element $e_L\in S$ je **levi nevtralni element**, če

$$
e_L\circ a=a
$$

za vsak $a\in S$.

Element $e_D\in S$ je **desni nevtralni element**, če

$$
a\circ e_D=a
$$

za vsak $a\in S$.

Če je isti element nevtralen z obeh strani, ga imenujemo **nevtralni element** oziroma **identiteta**:

$$
e\circ a=a\circ e=a.
$$

### 4.2 Kako iščemo identiteto

Postavi neznani element $e$ in rešuj

$$
a\circ e=a
$$

ter

$$
e\circ a=a
$$

za **splošen** $a$.

Rezultat $e$ ne sme biti odvisen od $a$.

### 4.3 Enoličnost identitete

Če identiteta obstaja, je enolična.

#### Dokaz

Naj bosta $e$ in $f$ identiteti. Ker je $e$ levi nevtralni element in $f$ desni nevtralni element,

$$
e=e\circ f=f.
$$

Torej je identiteta enolična.

Točno ta argument se pojavi kot ena izmed teoretičnih trditev v 3. vajah.

### Ustno vprašanje

**Vprašanje:** Ali je nevtralni element v grupi enoličen?

**Kratek odgovor:** Da.

**Profesor lahko dodatno vpraša:** Dokaži.

**Odgovor:** Če je $e$ levi nevtralni element in $f$ desni nevtralni element, potem

$$
e=e\circ f=f.
$$

Zato sta enaka.

---

## 5. Obrat elementa

### 5.1 Levi in desni obrat

Naj bo $e$ nevtralni element.

Element $b$ je **levi obrat** elementa $a$, če

$$
b\circ a=e.
$$

Element $b$ je **desni obrat** elementa $a$, če

$$
a\circ b=e.
$$

V grupi levi in desni obrat sovpadata. Pišemo

$$
b=a^{-1}.
$$

### 5.2 Enoličnost obrata v grupi

Če je $b$ levi obrat elementa $a$ in $c$ njegov desni obrat, potem

$$
b=b\circ e
=b\circ(a\circ c)
=(b\circ a)\circ c
=e\circ c
=c.
$$

Zato je obrat enoličen.

### Tip naloge: poišči identiteto in obrat

**Kako jo prepoznam**

Podana je nestandardna operacija in vprašanje o identiteti oziroma obratih posameznih elementov.

**Postopek**

1. Najprej poišči identiteto $e$.
2. Za obrat elementa $a$ rešuj
   $$
   a\circ b=e
   $$
   in po potrebi še
   $$
   b\circ a=e.
   $$
3. Preveri, ali rešitev pripada osnovni množici.
4. Preveri posebne vrednosti parametra, pri katerih deljenje ni dovoljeno.

**Primer**

Na $\mathbb Q$ je definirano

$$
a\triangle b=a-2ab+b.
$$

Poišči identiteto in obrat elementa $a$.

**Rešitev**

Za identiteto $e$ zahtevamo

$$
a\triangle e=a.
$$

Torej

$$
a-2ae+e=a,
$$

zato

$$
e(1-2a)=0
$$

za vsak $a\in\mathbb Q$. Sledi

$$
e=0.
$$

Zaradi komutativnosti predpisa je $0$ identiteta z obeh strani.

Za obrat $b$ elementa $a$ rešujemo

$$
a\triangle b=0.
$$

Dobimo

$$
a+b-2ab=0,
$$

zato

$$
b(1-2a)=-a.
$$

Če $a\neq \frac12$, je

$$
b=\frac{-a}{1-2a}
=
\frac{a}{2a-1}.
$$

Torej

$$
a^{-1}
=
\frac{a}{2a-1},
\qquad
a\neq \frac12.
$$

Za $a=\frac12$ velja

$$
\frac12\triangle b=\frac12
$$

za vsak $b$, zato $\frac12$ nima obrata.

Posebej:

$$
2^{-1}=\frac23,
\qquad
3^{-1}=\frac35.
$$

**Pogoste napake**

- Obrat zamenjaš z običajnim recipročnim številom $1/a$.
- Obrat iščeš, preden sploh določiš identiteto.
- Spregledaš posebno vrednost, pri kateri imenovalec postane $0$.
- Preveriš samo eno stran pri operaciji, za katero še ne veš, da je komutativna ali da tvori grupo.

### Ustno vprašanje

**Vprašanje:** Kaj pomeni, da je $b$ obrat elementa $a$?

**Kratek odgovor:** Če je $e$ identiteta, mora veljati

$$
a\circ b=b\circ a=e.
$$

**Profesor lahko dodatno vpraša:** Zakaj je obrat v grupi enoličen?

**Odgovor:** Če je $b$ levi in $c$ desni obrat elementa $a$, potem

$$
b=b\circ e=b\circ(a\circ c)=(b\circ a)\circ c=e\circ c=c.
$$

---

## 6. Grupe

### 6.1 Definicija grupe

Par $(G,\circ)$ je **grupa**, če velja:

1. **notranjost**
   $$
   a,b\in G\Longrightarrow a\circ b\in G;
   $$

2. **asociativnost**
   $$
   (a\circ b)\circ c=a\circ(b\circ c);
   $$

3. **obstoj identitete**
   $$
   \exists e\in G\ \forall a\in G:
   \quad
   e\circ a=a\circ e=a;
   $$

4. **obstoj obratov**
   $$
   \forall a\in G\ \exists a^{-1}\in G:
   \quad
   a\circ a^{-1}=a^{-1}\circ a=e.
   $$

Če poleg tega velja

$$
a\circ b=b\circ a
$$

za vse $a,b\in G$, je grupa **komutativna** oziroma **Abelova**.

### 6.2 Priporočeni vrstni red preverjanja

Pri nalogi »Ali je $(G,\circ)$ grupa?« uporabljaj vedno isti vrstni red:

1. zaprtost,
2. asociativnost,
3. identiteta,
4. obrati,
5. šele nato po potrebi komutativnost.

Če že pri eni nujni lastnosti dobiš protiprimer, lahko zaključiš, da struktura ni grupa.

### 6.3 Zelo uporabna metoda: prepoznaj skrito znano operacijo

V vajah se večkrat pojavijo operacije oblike

$$
a\circ b=(a+c)(b+c)-c.
$$

Uvedemo preslikavo

$$
\varphi(a)=a+c.
$$

Tedaj pogosto velja

$$
\varphi(a\circ b)=\varphi(a)\varphi(b).
$$

Če je $\varphi$ bijekcija na znano grupo, lahko iz tega hitro razberemo:

- asociativnost,
- identiteto,
- obrate,
- komutativnost.

To ni nadomestilo za razumevanje aksiomov, je pa zelo učinkovita izpitna strategija.

### Tip naloge: preveri grupo pri nestandardni operaciji

**Kako jo prepoznam**

Množica je pogosto $\mathbb R$ z izločenim enim elementom, operacija pa ima obliko produkta premaknjenih izrazov.

**Primer**

Naj bo

$$
G=\mathbb R\setminus\{-3\}
$$

in

$$
a\circ b=(a+3)(b+3)-3.
$$

Preveri, ali je $(G,\circ)$ grupa.

**Rešitev**

**1. Zaprtost.**

Za $a,b\in G$ velja

$$
a+3\neq0,
\qquad
b+3\neq0.
$$

Če je

$$
c=a\circ b,
$$

potem

$$
c+3=(a+3)(b+3)\neq0.
$$

Zato $c\neq-3$ in $c\in G$.

**2. Asociativnost.**

$$
(a\circ b)\circ c
=
(a+3)(b+3)(c+3)-3.
$$

Prav tako

$$
a\circ(b\circ c)
=
(a+3)(b+3)(c+3)-3.
$$

Zato je operacija asociativna.

**3. Identiteta.**

Iščemo $e\in G$, da

$$
a\circ e=a.
$$

Torej

$$
(a+3)(e+3)-3=a,
$$

zato

$$
(a+3)(e+3)=a+3.
$$

Ker $a+3\neq0$,

$$
e+3=1,
$$

torej

$$
e=-2.
$$

**4. Obrat.**

Za $b=a^{-1}$ zahtevamo

$$
a\circ b=-2.
$$

Torej

$$
(a+3)(b+3)-3=-2,
$$

zato

$$
(a+3)(b+3)=1.
$$

Sledi

$$
b+3=\frac1{a+3},
$$

torej

$$
a^{-1}
=
\frac1{a+3}-3.
$$

Ta element pripada $G$, saj

$$
a^{-1}+3=\frac1{a+3}\neq0.
$$

Zato je $(G,\circ)$ grupa.

Ker je množenje realnih števil komutativno,

$$
a\circ b=b\circ a,
$$

zato je grupa celo Abelova.

**Pogoste napake**

- Ne preveriš, zakaj rezultat ne more biti izločeni element $-3$.
- Identiteto napačno vzameš kot $0$ ali $1$.
- Obrat zamenjaš z $1/a$.
- Asociativnost razglasiš brez argumenta.
- Pozabiš preveriti, da obrat pripada $G$.

### Tip naloge: matrična grupa

**Kako jo prepoznam**

Množica vsebuje matrike posebne oblike in operacija je običajno matrično množenje.

**Ključna ideja**

Asociativnost običajnega matričnega množenja je že znana. Preveriti moraš predvsem:

- zaprtost oblike,
- identično matriko,
- obliko inverza.

**Primer**

Naj bo

$$
G=
\left\{
\begin{pmatrix}
a & b\\
0 & 1
\end{pmatrix}
;
\ a,b\in\mathbb R,\ a\neq0
\right\}
$$

z običajnim množenjem matrik.

Preveri, ali je $G$ grupa.

**Rešitev**

Naj bosta

$$
A=
\begin{pmatrix}
a & b\\
0 & 1
\end{pmatrix},
\qquad
B=
\begin{pmatrix}
c & d\\
0 & 1
\end{pmatrix}.
$$

Tedaj

$$
AB=
\begin{pmatrix}
ac & ad+b\\
0 & 1
\end{pmatrix}.
$$

Ker $a\neq0$ in $c\neq0$, je $ac\neq0$, zato $AB\in G$.

Asociativnost sledi iz asociativnosti matričnega množenja.

Identiteta je

$$
I=
\begin{pmatrix}
1&0\\
0&1
\end{pmatrix}\in G.
$$

Za

$$
A=
\begin{pmatrix}
a & b\\
0 & 1
\end{pmatrix}
$$

je

$$
A^{-1}
=
\begin{pmatrix}
\frac1a & -\frac ba\\
0 & 1
\end{pmatrix}\in G.
$$

Zato je $G$ grupa.

Na splošno ni komutativna. Na primer za

$$
A=
\begin{pmatrix}
1&1\\
0&1
\end{pmatrix},
\qquad
B=
\begin{pmatrix}
2&0\\
0&1
\end{pmatrix}
$$

dobimo

$$
AB=
\begin{pmatrix}
2&1\\
0&1
\end{pmatrix},
\qquad
BA=
\begin{pmatrix}
2&2\\
0&1
\end{pmatrix}.
$$

Torej $AB\neq BA$.

### Ustno vprašanje

**Vprašanje:** Definiraj grupo.

**Kratek odgovor:** Grupa je množica $G$ z notranjo asociativno operacijo, ki ima nevtralni element in v kateri ima vsak element obrat.

**Profesor lahko dodatno vpraša:** Ali je komutativnost del definicije grupe?

**Odgovor:** Ne. Če je grupna operacija dodatno komutativna, govorimo o Abelovi oziroma komutativni grupi.

### Ustno vprašanje

**Vprašanje:** Katere štiri stvari preveriš, če želiš dokazati, da je neka struktura grupa?

**Kratek odgovor:** Zaprtost, asociativnost, obstoj identitete in obstoj obrata za vsak element.

**Profesor lahko dodatno vpraša:** Če najdeš element brez obrata, ali moraš še preverjati asociativnost?

**Odgovor:** Ne, če je cilj samo ugotoviti, ali gre za grupo. Že ena kršitev grupnega aksioma zadošča za negativen odgovor.

---

## 7. Osnovne posledice grupnih aksiomov

Te lastnosti so pomembne predvsem za ustni del in za teoretične naloge izbirnega tipa.

### 7.1 Pravilo krajšanja

V grupi velja:

$$
a\circ b=a\circ c
\Longrightarrow
b=c.
$$

Podobno:

$$
b\circ a=c\circ a
\Longrightarrow
b=c.
$$

#### Dokaz levega krajšanja

Če

$$
a\circ b=a\circ c,
$$

pomnožimo z leve z $a^{-1}$:

$$
a^{-1}\circ(a\circ b)
=
a^{-1}\circ(a\circ c).
$$

Po asociativnosti:

$$
(a^{-1}\circ a)\circ b
=
(a^{-1}\circ a)\circ c.
$$

Zato

$$
e\circ b=e\circ c,
$$

torej

$$
b=c.
$$

### 7.2 Reševanje enačb v grupi

Enačba

$$
a\circ x=b
$$

ima enolično rešitev

$$
x=a^{-1}\circ b.
$$

Enačba

$$
x\circ a=b
$$

ima enolično rešitev

$$
x=b\circ a^{-1}.
$$

V nekomutativni grupi vrstnega reda faktorjev ne smeš zamenjati.

### 7.3 Inverz produkta

V grupi velja

$$
(a\circ b)^{-1}=b^{-1}\circ a^{-1}.
$$

#### Dokaz

$$
(a\circ b)\circ(b^{-1}\circ a^{-1})
=
a\circ(b\circ b^{-1})\circ a^{-1}
=
a\circ e\circ a^{-1}
=
e.
$$

Podobno tudi v drugi smeri.

### Tip naloge: teoretična trditev o grupi

**Kako jo prepoznam**

Naloga poda več splošnih trditev o poljubni grupi in zahteva pravilno oziroma nepravilno trditev.

**Primer**

Naj bo $(G,\circ)$ grupa z vsaj dvema elementoma. Presodi trditev:

> Za vsak $a\in G$ obstaja $b\in G$, da je $b\circ a=b$.

**Rešitev**

Iz

$$
b\circ a=b
$$

in

$$
b=b\circ e
$$

dobimo

$$
b\circ a=b\circ e.
$$

Po levem pravilu krajšanja sledi

$$
a=e.
$$

Trditev bi torej lahko veljala samo za $a=e$, ne pa za vsak $a\in G$, ker ima grupa vsaj dva elementa.

Trditev je **napačna**.

**Pogoste napake**

- Pri krajšanju pozabiš, da moraš biti v grupi oziroma v strukturi, kjer je krajšanje dovoljeno.
- V nekomutativni grupi »deliš« na napačni strani.
- Inverz produkta zapišeš kot $a^{-1}b^{-1}$ namesto v obratnem vrstnem redu.

### Ustno vprašanje

**Vprašanje:** Formuliraj pravilo krajšanja v grupi.

**Kratek odgovor:** Če je $a\circ b=a\circ c$, potem je $b=c$; analogno velja krajšanje z desne.

**Profesor lahko dodatno vpraša:** Zakaj?

**Odgovor:** Na obe strani z leve uporabimo $a^{-1}$ in nato asociativnost ter $a^{-1}\circ a=e$.

---

## 8. Polgrupa z identiteto in red elementa

### 8.1 Polgrupa

**Polgrupa** je množica z asociativno notranjo operacijo.

### 8.2 Polgrupa z identiteto

Polgrupa z identiteto ima še nevtralni element $e$.

Pogosto se uporablja tudi izraz **monoid**.

Vsaka grupa je polgrupa z identiteto, obratno pa ne velja.

### 8.3 Red elementa

Naj bo $a$ element polgrupe z identiteto.

Če obstaja najmanjši $n\ge1$, za katerega velja

$$
a^n=e,
$$

je $n$ **red elementa $a$**:

$$
\operatorname{ord}(a)=n.
$$

V aditivnem zapisu iščemo najmanjši $n\ge1$, da

$$
na=0.
$$

Če takega $n$ ni, rečemo, da ima element neskončen red.

### 8.4 Pomembna posledica

Če za neki $n\ge1$ velja

$$
a^n=e,
$$

je $a$ avtomatično obrnljiv in

$$
a^{-1}=a^{n-1}.
$$

Zato neobrnljiv element ne more imeti končnega reda v smislu $a^n=e$.

### 8.5 Standardna formula v aditivni grupi $\mathbb Z_n$

Za $\overline a\in(\mathbb Z_n,+)$ velja

$$
\operatorname{ord}(\overline a)
=
\frac{n}{\gcd(n,a)}.
$$

To formulo lahko uporabiš samo pri **aditivni** grupi $\mathbb Z_n$.

### 8.6 Obrnljivost pri množenju v $\mathbb Z_n$

Element $\overline a$ je obrnljiv glede na množenje modulo $n$ natanko tedaj, ko

$$
\gcd(a,n)=1.
$$

Pri množenju je identiteta

$$
\overline1.
$$

Pri seštevanju pa

$$
\overline0.
$$

### Tip naloge: določi red elementa

**Kako jo prepoznam**

Podana je struktura, na primer $(\mathbb Z_n,+)$ ali $(\mathbb Z_n,\cdot)$, in element, za katerega moraš določiti red.

**Postopek**

- Pri seštevanju računaj
  $$
  a,\ 2a,\ 3a,\ldots
  $$
  do $0$.
- Pri množenju računaj
  $$
  a,\ a^2,\ a^3,\ldots
  $$
  do $1$.
- Pri $(\mathbb Z_n,+)$ uporabi formulo
  $$
  \operatorname{ord}(\overline a)=\frac n{\gcd(n,a)}.
  $$

**Primer**

V kateri izmed naslednjih struktur ima element $\overline5$ red $2$?

- $(\mathbb Z_7,+)$,
- $(\mathbb Z_{10},\cdot)$,
- $(\mathbb Z_6,+)$,
- $(\mathbb Z_6,\cdot)$,
- $(\mathbb Z_8,+)$.

**Rešitev**

V $(\mathbb Z_7,+)$:

$$
\operatorname{ord}(\overline5)
=
\frac7{\gcd(7,5)}
=
7.
$$

V $(\mathbb Z_{10},\cdot)$:

$$
\overline5^2=\overline{25}=\overline5,
$$

zato ne dobimo $\overline1$.

V $(\mathbb Z_6,+)$:

$$
\operatorname{ord}(\overline5)
=
\frac6{\gcd(6,5)}
=
6.
$$

V $(\mathbb Z_6,\cdot)$:

$$
\overline5^2
=
\overline{25}
=
\overline1.
$$

Ker $\overline5\neq\overline1$,

$$
\operatorname{ord}(\overline5)=2.
$$

V $(\mathbb Z_8,+)$:

$$
\operatorname{ord}(\overline5)
=
\frac8{\gcd(8,5)}
=
8.
$$

**Odgovor:** element $\overline5$ ima red $2$ v

$$
(\mathbb Z_6,\cdot).
$$

### Tip naloge: obrnljivost in končen red

**Primer**

Presodi naslednje elemente:

1. $-1$ v $(\mathbb Z,\cdot)$,
2. $-1$ v $(\mathbb Z,+)$,
3. $\overline4$ v $(\mathbb Z_6,\cdot)$,
4. $\overline4$ v $(\mathbb Z_6,+)$,
5. $\overline0$ v $(\mathbb Z_7,\cdot)$.

**Rešitev**

1. V $(\mathbb Z,\cdot)$ je $-1$ obrnljiv in
   $$
   (-1)^2=1,
   $$
   zato ima red $2$.

2. V $(\mathbb Z,+)$ so vsi elementi obrnljivi glede na seštevanje, toda
   $$
   n(-1)=-n\neq0
   $$
   za vsak $n\ge1$, zato ima $-1$ neskončen red.

3. V $(\mathbb Z_6,\cdot)$ velja
   $$
   \gcd(4,6)=2\neq1,
   $$
   zato $\overline4$ ni obrnljiv.

4. V $(\mathbb Z_6,+)$ je vsak element obrnljiv, in
   $$
   \operatorname{ord}(\overline4)
   =
   \frac6{\gcd(6,4)}
   =
   3.
   $$

5. V $(\mathbb Z_7,\cdot)$ element $\overline0$ ni obrnljiv.

Torej sta obrnljiva in končnega reda primera **1 in 4**.

**Pogoste napake**

- Pri seštevanju uporabljaš identiteto $1$ namesto $0$.
- Pri množenju uporabljaš identiteto $0$ namesto $1$.
- Red v $(\mathbb Z_n,+)$ zamenjaš z multiplikativnim redom.
- Ne preveriš obrnljivosti pred iskanjem multiplikativnega reda.

### Ustno vprašanje

**Vprašanje:** Kaj je red elementa $a$?

**Kratek odgovor:** Najmanjši pozitivni $n$, za katerega je $a^n=e$. V aditivnem zapisu je to najmanjši $n$, za katerega je $na=0$.

**Profesor lahko dodatno vpraša:** Če velja $a^n=e$, zakaj je $a$ obrnljiv?

**Odgovor:** Ker je

$$
a\cdot a^{n-1}=a^n=e
$$

in

$$
a^{n-1}\cdot a=a^n=e,
$$

zato je $a^{-1}=a^{n-1}$.

---

## 9. Kolobarji

### 9.1 Pomembna opomba o konvenciji

Priložene vaje ne vsebujejo eksplicitne definicije kolobarja, zato iz samih datotek ni mogoče stoodstotno potrditi, ali profesor v definiciji zahteva multiplikativno identiteto.

V tem poglavju uporabljamo običajno algebraično konvencijo:

- **kolobarju ni nujno zahtevana multiplikativna identiteta**;
- če jo ima, govorimo o **kolobarju z enoto**.

Ta konvencija je skladna z načinom, kako je zastavljena naloga o ničelni multiplikaciji v 3. vajah. Pred ustnim izpitom vseeno uskladi formulacijo z definicijo iz profesorjevih predavanj.

### 9.2 Definicija kolobarja

Struktura $(R,+,\cdot)$ je **kolobar**, če:

1. $(R,+)$ je Abelova grupa;
2. množenje je notranje in asociativno;
3. velja leva distributivnost:
   $$
   a(b+c)=ab+ac;
   $$
4. velja desna distributivnost:
   $$
   (a+b)c=ac+bc.
   $$

Če je množenje komutativno, je kolobar **komutativen**.

Če obstaja $1\in R$, da

$$
1a=a1=a,
$$

je kolobar **z enoto**.

### 9.3 Kaj moraš pri nenavadnih operacijah posebej paziti

Če sta seštevanje in množenje definirana nestandardno, potem:

- aditivna identiteta ni nujno običajna $0$;
- aditivni obrat ni nujno $-a$;
- multiplikativna identiteta ni nujno običajna $1$.

Vse moraš določiti glede na **podani operaciji**.

### 9.4 Ničelna multiplikacija

Naj bo $(G,+)$ Abelova grupa in definirajmo

$$
a\circ b=0
$$

za vsa $a,b\in G$.

Potem je množenje:

- notranje,
- asociativno,
- distributivno glede na $+$.

Na primer:

$$
a\circ(b+c)=0
$$

in

$$
a\circ b+a\circ c=0+0=0.
$$

Po konvenciji brez obvezne multiplikativne identitete dobimo kolobar.

Če $G$ vsebuje več kot en element, ta kolobar praviloma nima multiplikativne identitete.

### Tip naloge: preveri kolobar z nestandardnima operacijama

**Kako jo prepoznam**

Podani sta dve operaciji, na primer $\oplus$ in $\star$, in vprašanje, ali $(R,\oplus,\star)$ tvori kolobar.

**Postopek**

1. Preveri, ali je $(R,\oplus)$ Abelova grupa.
2. Preveri asociativnost $\star$.
3. Preveri obe distributivnosti.
4. Če naloga zahteva kolobar z enoto, poišči še multiplikativno identiteto.
5. Preveri komutativnost množenja samo, če je to zahtevano.

**Primer**

Na $\mathbb R$ definiramo

$$
a\oplus b=a+b+1
$$

in

$$
a\star b=ab+a+b.
$$

Preveri, ali je $(\mathbb R,\oplus,\star)$ kolobar.

**Rešitev**

Najprej seštevanje $\oplus$.

Asociativnost:

$$
(a\oplus b)\oplus c
=
a+b+c+2
=
a\oplus(b\oplus c).
$$

Komutativnost je očitna.

Aditivna identiteta $e_\oplus$ zadosti

$$
a\oplus e_\oplus=a,
$$

torej

$$
a+e_\oplus+1=a,
$$

zato

$$
e_\oplus=-1.
$$

Aditivni obrat elementa $a$ zadosti

$$
a\oplus b=-1.
$$

Torej

$$
a+b+1=-1,
$$

zato

$$
b=-a-2.
$$

Tako je $(\mathbb R,\oplus)$ Abelova grupa.

Za $\star$:

$$
(a\star b)\star c
=
abc+ab+ac+bc+a+b+c,
$$

in

$$
a\star(b\star c)
=
abc+ab+ac+bc+a+b+c.
$$

Zato je $\star$ asociativna.

Preverimo levo distributivnost:

$$
a\star(b\oplus c)
=
a\star(b+c+1)
$$

$$
=
a(b+c+1)+a+(b+c+1)
$$

$$
=
ab+ac+2a+b+c+1.
$$

Po drugi strani:

$$
(a\star b)\oplus(a\star c)
$$

$$
=
(ab+a+b)+(ac+a+c)+1
$$

$$
=
ab+ac+2a+b+c+1.
$$

Zato velja leva distributivnost. Ker je $\star$ komutativna, sledi tudi desna distributivnost.

Torej je

$$
(\mathbb R,\oplus,\star)
$$

komutativen kolobar.

Multiplikativna identiteta glede na $\star$ je $0$, saj

$$
a\star0=a.
$$

Torej je to celo kolobar z enoto.

**Hitrejša povezava**

Definiraj

$$
\varphi(a)=a+1.
$$

Tedaj

$$
\varphi(a\oplus b)
=
\varphi(a)+\varphi(b)
$$

in

$$
\varphi(a\star b)
=
\varphi(a)\varphi(b).
$$

Struktura je zato samo »premaknjena« kopija običajnega kolobarja $\mathbb R$.

**Pogoste napake**

- Za aditivno identiteto avtomatično napišeš $0$.
- Aditivni obrat avtomatično napišeš $-a$.
- Preveriš distributivnost glede na običajno seštevanje namesto glede na $\oplus$.
- Preveriš samo eno stran distributivnosti, če množenje ni komutativno.
- Zamešaš identiteto za seštevanje z identiteto za množenje.

### Ustno vprašanje

**Vprašanje:** Definiraj kolobar.

**Kratek odgovor:** Kolobar je množica $R$ z operacijama $+$ in $\cdot$, kjer je $(R,+)$ Abelova grupa, množenje je asociativna notranja operacija in velja distributivnost množenja glede na seštevanje z obeh strani.

**Profesor lahko dodatno vpraša:** Ali mora biti množenje komutativno?

**Odgovor:** Ne. Če je komutativno, govorimo o komutativnem kolobarju.

### Ustno vprašanje

**Vprašanje:** Zakaj ničelna multiplikacija $ab=0$ vedno zadosti distributivnosti?

**Kratek odgovor:** Ker sta obe strani vsake distributivne enačbe enaki aditivni ničli. Na primer

$$
a(b+c)=0=0+0=ab+ac.
$$

---

## 10. Obrnljivi elementi in delitelji niča

### 10.1 Obrnljiv element v kolobarju z enoto

Naj bo $R$ kolobar z enoto $1$.

Element $a\in R$ je **obrnljiv**, če obstaja $b\in R$, da

$$
ab=ba=1.
$$

Tedaj pišemo

$$
b=a^{-1}.
$$

Množica vseh obrnljivih elementov kolobarja z enoto tvori grupo glede na množenje.

### 10.2 Levi delitelj niča

Neničelni element $a\in R$ je **levi delitelj niča**, če obstaja neničelni $b\in R$, da

$$
ab=0.
$$

Element $a$ stoji **na levi**.

### 10.3 Desni delitelj niča

Neničelni element $a\in R$ je **desni delitelj niča**, če obstaja neničelni $b\in R$, da

$$
ba=0.
$$

Element $a$ stoji **na desni**.

V komutativnem kolobarju razlike med levim in desnim deliteljem niča ni.

V nekomutativnem kolobarju je ta razlika bistvena.

### 10.4 Obrnljiv element ne more biti delitelj niča

V kolobarju z enoto naj bo $a$ obrnljiv in naj velja

$$
ab=0.
$$

Pomnožimo z leve z $a^{-1}$:

$$
a^{-1}ab=a^{-1}0.
$$

Dobimo

$$
b=0.
$$

Zato obrnljiv element ne more biti levi delitelj niča. Analogno ne more biti desni delitelj niča.

### Tip naloge: levi ali desni delitelj niča

**Kako jo prepoznam**

Podan je nekomutativen matrični kolobar in konkreten element $X$. Naloga zahteva, da ugotoviš, ali obstaja neničelni element, ki ga $X$ anihilira z leve ali desne.

**Postopek**

1. Zapiši splošen element $Y$ kolobarja.
2. Izračunaj $XY$.
3. Reši $XY=0$ in preveri, ali obstaja $Y\neq0$.
4. Izračunaj $YX$.
5. Reši $YX=0$ in preveri, ali obstaja $Y\neq0$.
6. Jasno zapiši, na kateri strani je $X$.

**Primer**

V množici

$$
R=
\left\{
\begin{pmatrix}
0&0\\
a&b
\end{pmatrix}
;
\ a,b\in\mathbb R
\right\}
$$

obravnavamo

$$
X=
\begin{pmatrix}
0&0\\
1&1
\end{pmatrix}.
$$

Določi, ali je $X$ levi ali desni delitelj niča.

**Rešitev**

Naj bo

$$
Y=
\begin{pmatrix}
0&0\\
a&b
\end{pmatrix}.
$$

Najprej:

$$
XY
=
\begin{pmatrix}
0&0\\
1&1
\end{pmatrix}
\begin{pmatrix}
0&0\\
a&b
\end{pmatrix}
=
\begin{pmatrix}
0&0\\
a&b
\end{pmatrix}
=
Y.
$$

Če je $Y\neq0$, potem je $XY\neq0$. Zato $X$ ni levi delitelj niča.

Po drugi strani:

$$
YX
=
\begin{pmatrix}
0&0\\
a&b
\end{pmatrix}
\begin{pmatrix}
0&0\\
1&1
\end{pmatrix}
=
\begin{pmatrix}
0&0\\
b&b
\end{pmatrix}.
$$

Izberemo na primer

$$
Y=
\begin{pmatrix}
0&0\\
1&0
\end{pmatrix}\neq0.
$$

Tedaj

$$
YX=0.
$$

Zato je $X$ **desni delitelj niča**, ni pa levi delitelj niča.

**Pogoste napake**

- Zamenjaš pomen »levi« in »desni«.
- Za anihilator uporabiš ničelni element; zahtevamo $Y\neq0$.
- Iz $XY\neq0$ za en sam $Y$ sklepaš, da ni levega delitelja niča; pokazati moraš, da za noben neničelni $Y$ ne dobimo $XY=0$.
- Pri matričnem množenju zamenjaš $XY$ in $YX$.

### Ustno vprašanje

**Vprašanje:** Kaj je levi delitelj niča?

**Kratek odgovor:** Neničelni element $a$ je levi delitelj niča, če obstaja neničelni $b$, za katerega je $ab=0$.

**Profesor lahko dodatno vpraša:** Zakaj v nekomutativnem kolobarju ločimo leve in desne delitelje niča?

**Odgovor:** Ker iz $ab=0$ v splošnem ne sledi $ba=0$.

---

## 11. Dokazi, ki jih moraš znati reproducirati

### 11.1 Enoličnost nevtralnega elementa

Če sta $e$ levi in $f$ desni nevtralni element, potem

$$
e=e\circ f=f.
$$

### 11.2 Enoličnost obrata v grupi

Če je $b$ levi in $c$ desni obrat elementa $a$, potem

$$
b
=
b\circ e
=
b\circ(a\circ c)
=
(b\circ a)\circ c
=
e\circ c
=
c.
$$

### 11.3 Pravilo krajšanja

Iz

$$
a\circ b=a\circ c
$$

sledi

$$
a^{-1}\circ(a\circ b)
=
a^{-1}\circ(a\circ c),
$$

zato

$$
b=c.
$$

### 11.4 Inverz produkta

$$
(a\circ b)^{-1}=b^{-1}\circ a^{-1}.
$$

Ključ je obratni vrstni red.

### 11.5 Element končnega reda je obrnljiv

Če

$$
a^n=e,
$$

potem

$$
a^{n-1}
$$

deluje kot obrat elementa $a$.

### 11.6 Obrnljiv element ni delitelj niča

Če je $a$ obrnljiv in

$$
ab=0,
$$

potem

$$
b=a^{-1}ab=0.
$$

---

## 12. Kako prepoznam pravo metodo

| Oblika vprašanja | Kaj naredim |
|---|---|
| »Ali predpis določa notranjo operacijo?« | Preveri definiranost in zaprtost. Za negativen odgovor poišči protiprimer. |
| »Ali je operacija komutativna?« | Primerjaj $a\circ b$ in $b\circ a$. |
| »Ali je operacija asociativna?« | Primerjaj $(a\circ b)\circ c$ in $a\circ(b\circ c)$. |
| »Poišči identiteto.« | Reši $a\circ e=a$ in $e\circ a=a$ za splošni $a$. |
| »Poišči obrat elementa.« | Najprej določi $e$, nato reši $a\circ b=e$ in $b\circ a=e$. |
| »Ali je to grupa?« | Zaprtost $\to$ asociativnost $\to$ identiteta $\to$ obrati. |
| »Kakšen je red elementa?« | Ponavljaj operacijo do identitete; v $(\mathbb Z_n,+)$ uporabi $\frac n{\gcd(n,a)}$. |
| »Ali je element obrnljiv modulo $n$?« | Pri množenju preveri $\gcd(a,n)=1$. |
| »Ali je to kolobar?« | Aditivna Abelova grupa + asociativno množenje + obe distributivnosti. |
| »Levi/desni delitelj niča?« | Izračunaj posebej $ab$ in $ba$ s splošnim neničelnim elementom. |

---

## 13. Najpomembnejše povezave med pojmi

### 13.1 Od operacije do grupe

$$
\text{notranja operacija}
+
\text{asociativnost}
+
\text{identiteta}
+
\text{obrati}
=
\text{grupa}.
$$

Komutativnost je dodatna lastnost:

$$
\text{grupa}
+
\text{komutativnost}
=
\text{Abelova grupa}.
$$

### 13.2 Od grupe do kolobarja

Pri kolobarju mora biti aditivna struktura Abelova grupa:

$$
(R,+)
\quad\text{je Abelova grupa}.
$$

Množenje mora biti asociativno in distributivno glede na seštevanje.

Zato je razumevanje grupnih aksiomov neposreden predpogoj za kolobarje.

### 13.3 Red in obrnljivost

Če ima element končen red, potem je obrnljiv:

$$
a^n=e
\Longrightarrow
a^{-1}=a^{n-1}.
$$

Obratno ne velja nujno: obrnljiv element ima lahko neskončen red.

Primer je $-1$ v aditivni grupi $(\mathbb Z,+)$: vsak element je aditivno obrnljiv, $-1$ pa ima neskončen red.

### 13.4 Delitelji niča in obrnljivost

V kolobarju z enoto:

$$
\text{obrnljiv}
\Longrightarrow
\text{ni delitelj niča}.
$$

Zato je iskanje deliteljev niča pogosto tudi hiter način za dokaz neobrnljivosti.

### 13.5 »Premaknjene« operacije

Operacije

$$
a\circ b=(a+c)(b+c)-c
$$

ali podobne konstrukcije so pogosto samo običajna operacija po spremembi koordinat

$$
\varphi(a)=a+c.
$$

Na izpitu vedno preveri, ali lahko izraz preoblikuješ v produkt ali vsoto znanih struktur.

---

## 14. Pogoste napake v celotni fazi

- **Notranjost ni isto kot asociativnost.**
- Za dokaz splošne lastnosti uporabiš samo nekaj številskih primerov.
- Pozabiš, da identiteta mora biti **en sam element**, ki deluje za vse $a$.
- Pri nestandardni operaciji avtomatično vzameš identiteto $0$ ali $1$.
- Obrat pri nestandardni operaciji zamenjaš z običajnim $-a$ ali $1/a$.
- Pri preverjanju grupe pozabiš na zaprtost.
- Pri matrični grupi ne preveriš, da inverz ohrani zahtevano obliko.
- V $\mathbb Z_n$ zamenjaš aditivni in multiplikativni red.
- Pri množenju modulo $n$ ne preveriš $\gcd(a,n)=1$.
- Pri kolobarju preveriš distributivnost glede na napačno operacijo.
- V nekomutativnem primeru zamenjaš levi in desni delitelj niča.
- Pri delitelju niča dovoliš, da je drugi faktor $0$.
- Pri krajšanju implicitno uporabljaš komutativnost, čeprav ni potrebna in morda ne velja.

---

## 15. Ustni del — vprašanja za memoriranje

### Ustno vprašanje

**Vprašanje:** Kaj je notranja operacija?

**Kratek odgovor:** Preslikava $\circ:S\times S\to S$.

**Profesor lahko dodatno vpraša:** Kaj pomeni zaprtost?

**Odgovor:** Za vsaka $a,b\in S$ mora rezultat $a\circ b$ pripadati $S$.

### Ustno vprašanje

**Vprašanje:** Definiraj asociativnost.

**Kratek odgovor:**

$$
(a\circ b)\circ c=a\circ(b\circ c)
$$

za vse $a,b,c$.

**Profesor lahko dodatno vpraša:** Ali zadošča preverjanje nekaj primerov?

**Odgovor:** Ne za dokaz. Nekaj primerov lahko odkrije protiprimer, ne more pa dokazati splošne asociativnosti.

### Ustno vprašanje

**Vprašanje:** Definiraj komutativnost.

**Kratek odgovor:**

$$
a\circ b=b\circ a
$$

za vse $a,b$.

**Profesor lahko dodatno vpraša:** Navedi asociativno, a nekomutativno operacijo.

**Odgovor:** Običajno množenje kvadratnih matrik.

### Ustno vprašanje

**Vprašanje:** Kaj je identiteta?

**Kratek odgovor:** Element $e$, za katerega velja

$$
e\circ a=a\circ e=a
$$

za vsak $a$.

**Profesor lahko dodatno vpraša:** Ali je enolična?

**Odgovor:** Da. Če sta $e$ in $f$ identiteti, potem $e=e\circ f=f$.

### Ustno vprašanje

**Vprašanje:** Kaj je obrat elementa?

**Kratek odgovor:** Element $a^{-1}$, za katerega velja

$$
aa^{-1}=a^{-1}a=e.
$$

**Profesor lahko dodatno vpraša:** Ali je v grupi enoličen?

**Odgovor:** Da.

### Ustno vprašanje

**Vprašanje:** Definiraj grupo.

**Kratek odgovor:** Množica z asociativno notranjo operacijo, identiteto in obratom vsakega elementa.

**Profesor lahko dodatno vpraša:** Kaj je Abelova grupa?

**Odgovor:** Grupa, katere operacija je komutativna.

### Ustno vprašanje

**Vprašanje:** Formuliraj pravilo krajšanja.

**Kratek odgovor:**

$$
ab=ac\Longrightarrow b=c,
$$

in

$$
ba=ca\Longrightarrow b=c.
$$

**Profesor lahko dodatno vpraša:** Kaj uporabiš v dokazu?

**Odgovor:** Obrat elementa $a$ in asociativnost.

### Ustno vprašanje

**Vprašanje:** Kaj je polgrupa z identiteto?

**Kratek odgovor:** Množica z asociativno notranjo operacijo in nevtralnim elementom.

**Profesor lahko dodatno vpraša:** Kaj ji manjka, da bi bila grupa?

**Odgovor:** Ni nujno, da ima vsak element obrat.

### Ustno vprašanje

**Vprašanje:** Kaj je red elementa?

**Kratek odgovor:** Najmanjši $n\ge1$, za katerega je $a^n=e$; v aditivnem zapisu najmanjši $n$, za katerega je $na=0$.

**Profesor lahko dodatno vpraša:** Kolikšen je red identitete?

**Odgovor:** $1$.

### Ustno vprašanje

**Vprašanje:** Definiraj kolobar.

**Kratek odgovor:** $(R,+)$ je Abelova grupa, množenje je asociativno in distributivno glede na seštevanje z obeh strani.

**Profesor lahko dodatno vpraša:** Ali je množenje v kolobarju nujno komutativno?

**Odgovor:** Ne.

### Ustno vprašanje

**Vprašanje:** Kaj je obrnljiv element kolobarja z enoto?

**Kratek odgovor:** Element $a$, za katerega obstaja $a^{-1}$ z

$$
aa^{-1}=a^{-1}a=1.
$$

**Profesor lahko dodatno vpraša:** Ali je lahko obrnljiv element delitelj niča?

**Odgovor:** Ne.

### Ustno vprašanje

**Vprašanje:** Definiraj levi in desni delitelj niča.

**Kratek odgovor:** Neničelni $a$ je levi delitelj niča, če obstaja $b\neq0$ z $ab=0$, in desni delitelj niča, če obstaja $b\neq0$ z $ba=0$.

**Profesor lahko dodatno vpraša:** Kdaj se pojma avtomatično ujemata?

**Odgovor:** V komutativnem kolobarju.

---

## 16. Priporočen vrstni red učenja

1. Nauči se na pamet definicijo notranje operacije, asociativnosti in komutativnosti.
2. Reši več kratkih nalog samo na zaprtost.
3. Nauči se sistematično iskati identiteto.
4. Nato vadi obrate pri nestandardnih operacijah.
5. Šele nato rešuj celotne naloge »Ali je to grupa?«.
6. Nauči se dokaze:
   - enoličnost identitete,
   - enoličnost obrata,
   - pravilo krajšanja.
7. Ponovi $\mathbb Z_n$ in red elementa.
8. Nato preidi na kolobarje.
9. Zaključi z levimi/desnimi delitelji niča.
10. Na koncu odgovori na vsa ustna vprašanja brez zapiskov.

---

## 17. Naloge za samostojno reševanje

## Srednje težke naloge

**Naloga 1.**

Na $\mathbb Z$ definiramo

$$
a\circ b=a+b+2.
$$

Preveri, ali je $(\mathbb Z,\circ)$ Abelova grupa. Če je, določi identiteto in obrat elementa $a$.

**Naloga 2.**

Na $\mathbb R$ definiramo

$$
a\diamond b=a^2+b^2+1.
$$

Preveri, ali je operacija notranja, komutativna in asociativna.

**Naloga 3.**

Naj bo

$$
G=\mathbb R\setminus\{-1\}
$$

in

$$
a\circ b=a+b+ab.
$$

Preveri, ali je $(G,\circ)$ grupa. Določi identiteto in obrat elementa $a$.

**Naloga 4.**

Določi red elementa $\overline8$ v aditivni grupi

$$
(\mathbb Z_{12},+).
$$

**Naloga 5.**

Določi vse obrnljive elemente kolobarja $\mathbb Z_{12}$ glede na množenje.

**Naloga 6.**

V $(\mathbb Z_{10},\cdot)$ določi, kateri izmed elementov

$$
\overline1,\overline3,\overline4,\overline7,\overline9
$$

so obrnljivi. Za obrnljive elemente določi njihov multiplikativni red.

**Naloga 7.**

Naj bo $(G,+)$ Abelova grupa in definiraj

$$
a\star b=0
$$

za vse $a,b\in G$.

Preveri asociativnost in distributivnost $\star$ glede na $+$.

**Naloga 8.**

V kolobarju matrik $M_2(\mathbb R)$ določi, ali je

$$
A=
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix}
$$

delitelj niča.

## Težke / izpitne naloge

**Naloga 9.**

Naj bo $c\in\mathbb R$, $c\neq0$, in

$$
G_c=\mathbb R\setminus\left\{-\frac1c\right\}.
$$

Na $G_c$ definiramo

$$
a\circ b=a+b+cab.
$$

Dokaži, da je $(G_c,\circ)$ Abelova grupa. Določi identiteto in obrat splošnega elementa $a$.

**Naloga 10.**

Naj bo

$$
G=
\left\{
\begin{pmatrix}
a&b\\
0&1
\end{pmatrix}
;
\ a,b\in\mathbb R,\ a\neq0
\right\}.
$$

Za

$$
A=
\begin{pmatrix}
2&-3\\
0&1
\end{pmatrix}
$$

poišči $A^{-1}$ in preveri rezultat z množenjem v obeh vrstnih redih.

**Naloga 11.**

Na $\mathbb R$ definiramo

$$
a\oplus b=a+b-2
$$

in

$$
a\star b=ab-2a-2b+6.
$$

Pokaži, da je $(\mathbb R,\oplus,\star)$ komutativen kolobar z enoto. Določi aditivno identiteto, aditivni obrat elementa $a$ in multiplikativno identiteto.

**Naloga 12.**

V množici

$$
R=
\left\{
\begin{pmatrix}
0&a\\
0&b
\end{pmatrix}
;
\ a,b\in\mathbb R
\right\}
$$

z običajnim seštevanjem in množenjem obravnavaj element

$$
X=
\begin{pmatrix}
0&1\\
0&0
\end{pmatrix}.
$$

Določi, ali je $X$ levi delitelj niča, desni delitelj niča ali oboje.

**Naloga 13.**

Naj bo $(G,\circ)$ grupa. Dokaži, da enačba

$$
a\circ x\circ b=c
$$

ima natanko eno rešitev in jo izrazi z $a^{-1}$, $b^{-1}$ in $c$.

**Naloga 14.**

Naj bo $a$ element grupe in naj velja

$$
a^{12}=e.
$$

Poleg tega naj bo

$$
a^8\neq e
$$

in

$$
a^6\neq e.
$$

Katere vrednosti so še možne za $\operatorname{ord}(a)$?

---

## Odgovori

**1.** Da, Abelova grupa.

$$
e=-2,
\qquad
a^{-1}=-a-4.
$$

**2.** Notranja in komutativna, ni asociativna. Na primer z $a=b=0$, $c=1$ dobiš različni vrednosti obeh razporeditev oklepajev.

**3.** Da, Abelova grupa.

$$
e=0,
\qquad
a^{-1}=-\frac{a}{a+1}.
$$

**4.**

$$
\operatorname{ord}(\overline8)
=
\frac{12}{\gcd(12,8)}
=
3.
$$

**5.**

$$
\overline1,\ \overline5,\ \overline7,\ \overline{11}.
$$

**6.**

Obrnljivi so

$$
\overline1,\overline3,\overline7,\overline9.
$$

Njihovi redi:

$$
\operatorname{ord}(\overline1)=1,
$$

$$
\operatorname{ord}(\overline3)=4,
$$

$$
\operatorname{ord}(\overline7)=4,
$$

$$
\operatorname{ord}(\overline9)=2.
$$

Element $\overline4$ ni obrnljiv.

**7.** $\star$ je asociativna in distributivna z leve in desne; vsi produkti so enaki $0$.

**8.** Da. Na primer

$$
A
\begin{pmatrix}
0&0\\
0&1
\end{pmatrix}
=
0.
$$

Matrika $A$ je neničelni delitelj niča.

**9.**

$$
e=0,
\qquad
a^{-1}
=
-\frac{a}{1+ca}.
$$

Uporabna preslikava:

$$
\varphi(a)=1+ca,
$$

za katero velja

$$
\varphi(a\circ b)=\varphi(a)\varphi(b).
$$

**10.**

$$
A^{-1}
=
\begin{pmatrix}
\frac12&\frac32\\
0&1
\end{pmatrix}.
$$

Velja

$$
AA^{-1}=A^{-1}A=I.
$$

**11.**

Aditivna identiteta:

$$
e_\oplus=2.
$$

Aditivni obrat:

$$
a^{(-\oplus)}=4-a.
$$

Multiplikativna identiteta:

$$
e_\star=3.
$$

Uporabna preslikava je

$$
\varphi(a)=a-2.
$$

**12.** $X$ je **levi delitelj niča**, ni pa desni delitelj niča.

**13.**

$$
x=a^{-1}\circ c\circ b^{-1}.
$$

Rešitev je enolična.

**14.**

Red mora deliti $12$. Zaradi

$$
a^6\neq e
$$

red ne deli $6$, zaradi

$$
a^8\neq e
$$

red ne deli $8$.

Možni delitelji $12$ so

$$
1,2,3,4,6,12.
$$

Edina možnost je

$$
\operatorname{ord}(a)=12.
$$

---

## Faza je zaključena, ko znam ...

- [ ] natančno definirati dvomestno notranjo operacijo;
- [ ] pri danem predpisu preveriti, ali je operacija dobro definirana in zaprta;
- [ ] s splošnim računom dokazati komutativnost;
- [ ] s splošnim računom dokazati asociativnost;
- [ ] z enim protiprimerom pravilno ovreči komutativnost ali asociativnost;
- [ ] razlikovati med asociativnostjo in komutativnostjo;
- [ ] natančno definirati levi, desni in dvostranski nevtralni element;
- [ ] iz enačb $a\circ e=a$ in $e\circ a=a$ izračunati identiteto;
- [ ] dokazati enoličnost identitete;
- [ ] natančno definirati levi, desni in dvostranski obrat;
- [ ] pri nestandardni operaciji izračunati obrat splošnega elementa;
- [ ] prepoznati posebne elemente, ki nimajo obrata;
- [ ] dokazati enoličnost obrata v grupi;
- [ ] natančno navesti vse aksiome grupe;
- [ ] razložiti razliko med grupo in Abelovo grupo;
- [ ] sistematično preveriti, ali je podana struktura grupa;
- [ ] pri matrični grupi preveriti zaprtost, identiteto in obliko inverza;
- [ ] prepoznati »premaknjeno« operacijo in jo povezati z običajnim seštevanjem ali množenjem;
- [ ] formulirati in dokazati levo in desno pravilo krajšanja;
- [ ] rešiti enačbe $a\circ x=b$, $x\circ a=b$ in $a\circ x\circ b=c$ v grupi;
- [ ] dokazati formulo $(a\circ b)^{-1}=b^{-1}\circ a^{-1}$;
- [ ] definirati polgrupo in polgrupo z identiteto;
- [ ] natančno definirati red elementa;
- [ ] izračunati red elementa v $(\mathbb Z_n,+)$;
- [ ] uporabiti formulo $\operatorname{ord}(\overline a)=\frac n{\gcd(n,a)}$ v aditivni grupi $\mathbb Z_n$;
- [ ] pri množenju modulo $n$ preveriti obrnljivost z $\gcd(a,n)=1$;
- [ ] razlikovati aditivni red od multiplikativnega reda;
- [ ] dokazati, da element končnega reda mora biti obrnljiv;
- [ ] natančno navesti aksiome kolobarja;
- [ ] pojasniti, da množenje v kolobarju ni nujno komutativno;
- [ ] pri nestandardnih operacijah pravilno poiskati aditivno identiteto in aditivne obrate;
- [ ] preveriti obe distributivnosti;
- [ ] razložiti ničelno multiplikacijo in zakaj je distributivna;
- [ ] definirati obrnljiv element kolobarja z enoto;
- [ ] definirati levi in desni delitelj niča;
- [ ] pri matričnem primeru ločeno izračunati $XY$ in $YX$;
- [ ] dokazati, da obrnljiv element v kolobarju z enoto ni delitelj niča;
- [ ] brez zapiskov odgovoriti na vsa ustna vprašanja iz tega poglavja;
- [ ] brez zapiskov reproducirati dokaze enoličnosti identitete, enoličnosti obrata in pravila krajšanja;
- [ ] samostojno rešiti vsaj 80–90 % nalog tega tipa brez gledanja postopka;
- [ ] jasno zapisati rešitev v kratkem, formalnem slogu, primernem za pisni izpit.
