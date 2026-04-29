# 🌀 EL LABERINT DEL NUCLI — Missió per a Branchwalkers

> *El Nucli ha activat sis trampes lògiques dins del Còdex. Cada Branchwalker haurà de creuar el laberint pel seu compte. Algunes trampes les podreu desactivar sols; altres requereixen treballar en parella. No totes són superables a la primera — i això forma part de l'aprenentatge.*

---

## 📜 De què va això

Sis **reptes** independents, cadascun simula una situació real que us trobareu treballant amb Git en un equip professional. No és un examen: és un entrenament. Si quedeu encallats, **consulteu el Receptari** de la web (secció *"Què faig si...?"*) — allà hi teniu la solució de cada tipus de situació.

**Treballareu tots al mateix repositori (el Còdex compartit)** dins de la carpeta `/laberint/`. Tot el que feu queda visible per al master i per als companys. Això és deliberat: en una empresa, la vostra feina amb Git també és pública per a l'equip.

---

## 🎯 Què cal entregar

Al final del laberint, cada un de vosaltres haurà creat la seva carpeta personal:

```
/laberint/bitacores/<el-teu-nom>/
   BITACORA-R1.md
   BITACORA-R2.md
   BITACORA-R3.md
   ...
```

**Cada BITACORA** ha de contenir, per al repte corresponent:

1. **Què he vist** — el missatge d'error o el símptoma exacte (copia-paste del terminal)
2. **Què crec que estava passant** — la teva interpretació (encara que t'equivoquis, val)
3. **Què he provat i què ha funcionat** — comandes copiades del teu terminal, en ordre
4. **Conclusió** — una frase: què he après que no sabia abans

> ⚠️ **La bítacora val tant com la solució en si.** Un repte resolt sense bítacora explicativa = mig punt. Un repte mig-resolt amb bítacora honesta i raonada = punt sencer.

---

## 📊 Nivells i puntuació

| Repte | Nivell | Punts | Requereix parella? |
|---|---|---|---|
| R1 — La Porta del Nucli | 🟢 Fàcil | 1 | Sí (2 persones) |
| R2 — El Polissó del Còdex | 🟢 Fàcil | 1 | No |
| R3 — Eco a `main` | 🟡 Mitjà | 1.5 | No |
| R4 — Dues Veritats | 🟡 Mitjà | 2 | Sí (2 persones) |
| R5 — L'Ombra del Bug | 🟠 Mitjà-Avançat | 2 | No |
| R6 — El Fragment Perdut | 🔴 Avançat | 2.5 | No |

**Total**: 10 punts. **Mínim per aprovar la missió: R1 + R2 + R3 (3.5 punts)**.

Els que aneu més ràpid, ataqueu R4-R6. Els que aneu més justos, **assegureu primer R1-R3 amb bítacora ben feta** abans de passar a la resta.

---

## ⚙️ Preparació (un cop, abans de començar)

```bash
# 1. Clona o actualitza el còdex
git clone <url-del-codex>
cd codex-del-nucli
# (o si ja el tens: git checkout main && git pull)

# 2. Crea la teva carpeta de bítacores en una branca personal
git checkout -b laberint/bitacores-<el-teu-nom>
mkdir -p laberint/bitacores/<el-teu-nom>
echo "# Bítacores de <el-teu-nom> al Laberint" > laberint/bitacores/<el-teu-nom>/README.md
git add .
git commit -m "chore(laberint): inicialitza bítacora de <el-teu-nom>"
git push -u origin laberint/bitacores-<el-teu-nom>
```

A partir d'aquí, cada repte us demanarà coses específiques. **Llegiu sencer cada repte abans de començar-lo.**

---

## 🟢 R1 — La Porta del Nucli

**Concepte**: dos col·laboradors a la mateixa branca, push rebutjat.

### Context narratiu
> *"Davant de la Porta del Nucli cal gravar dues runes seqüencialment. Si dos Branchwalkers proven d'inscriure-les a la vegada, el Nucli bloqueja la segona inscripció. Heu de coordinar-vos sense xafar la feina de l'altre."*

### Què heu de fer

El master us assignarà **per parelles**, i a cada parella una **branca compartida** del tipus `laberint/r1/equip-<X>` (ja existeix, amb un fitxer `runes.md` dins).

Cadascun de vosaltres dos ha d'**afegir la seva runa** a la llista del fitxer:

```markdown
# Runes de la Porta

1. (la teva runa: una paraula, ex. "FOC")
```

Format de la runa: una línia nova amb el seu número, el seu nom de Branchwalker i una paraula de poder. Ex:
```
1. [FORJADOR-Anna] FOC
2. [CRONOMANTE-Marc] TEMPS
```

### El que us passarà

- El primer dels dos farà commit i push **sense problemes**.
- El segon, en provar de fer push, **rebrà un rebuig** del tipus `! [rejected] non-fast-forward`.

### El que heu de demostrar

- El segon company resol el rebuig **sense perdre la runa del primer**, i acaba pushejant amb totes dues runes al fitxer.
- A la teva BITACORA-R1.md (encara que siguis el primer i no t'hagi rebutjat el push), explica què va passar al teu company i com es va resoldre.

### Pista
Mireu al receptari: *"El push em rebutja amb non-fast-forward"*.

### Avaluació
- ✅ La branca `laberint/r1/equip-<X>` té totes dues runes al fitxer
- ✅ Hi ha **dos commits** d'autors diferents
- ✅ Tots dos teniu BITACORA-R1.md ben explicada

---

## 🟢 R2 — El Polissó del Còdex

**Concepte**: un fitxer indesitjat (amb "credencials") s'ha colat al repo. Cal treure'l del seguiment de Git **sense esborrar-lo del disc** i evitar que torni a colar-se.

### Context narratiu
> *"Algú ha deixat un fitxer de claus dins del Còdex. El master diu que es tracta d'una credencial de proves, però en un escenari real seria una fuga greu. Heu d'expulsar el polissó del Còdex i posar guardes perquè no torni a entrar."*

### Què heu de fer

El master ja ha commitejat al `main` el fitxer `laberint/r2/credencials-fake.txt`. Aneu a mirar-lo: dins hi ha text com `API_KEY=fake-secret-12345`. (Tranquils, és fals.)

A la vostra branca personal `laberint/r2/<el-teu-nom>`:

1. **Modifiqueu (o creeu) el fitxer `.gitignore` del repo** perquè ignori `credencials-fake.txt` i tots els futurs `.env`.
2. **Traieu el fitxer del seguiment de Git** sense esborrar-lo del vostre disc.
3. Commit + push + obriu PR contra `main`.

### Pista (trampa pedagògica)
Si feu `rm credencials-fake.txt` esborrareu el fitxer del disc — i no és el que es demana en un escenari real (potser el necessites per fer-lo servir tu en local). Hi ha una manera de **dir a Git "ja no rastregis aquest fitxer" sense tocar el disc**. Mireu al receptari: *"He commitejat un fitxer que no havia"*.

### Avaluació
- ✅ El PR conté el `.gitignore` actualitzat amb les dues entrades
- ✅ El PR té un commit que treu `credencials-fake.txt` del seguiment **sense esborrar-lo de la teva carpeta local**
- ✅ Si fas `git status` després, `credencials-fake.txt` apareix com **"untracked" i ignorat** (no apareix a `git status` i `git check-ignore credencials-fake.txt` el confirma)
- ✅ BITACORA-R2.md

---

## 🟡 R3 — Eco a `main`

**Concepte**: has fet un commit a `main` per accident. L'has de "moure" a una branca nova i deixar `main` net.

### Context narratiu
> *"Un eco del Nucli us ha confós. Heu gravat la vostra runa directament al cor del Còdex (`main`) en comptes de la vostra rama personal. Si els altres Branchwalkers se sincronitzen amb `main` ara, hereten la vostra runa. Heu de **traslladar la runa a la vostra rama** i **netejar `main`** abans que els companys facin pull."*

### Què heu de fer

Aquest repte té **dues fases**:

**Fase 1 — Provoca tu mateix l'error.**
Estant a `main` i actualitzat (`git pull`), crea un fitxer nou a `laberint/r3/runa-<el-teu-nom>.md` (contingut lliure: una runa, una frase, el que vulguis) i fes-li commit **directament a `main` local** (sí, sense crear branca abans). Aquesta és la "cagada" que has de simular.

> ⚠️ **NO facis `git push` encara.** Si fas push, el teu commit "incorrecte" arriba al `main` remot i la història es complica. Mantén-lo nomès local.

**Fase 2 — Arregla-ho.**
El commit que acabes de fer ha d'acabar en una **branca nova** `laberint/r3/<el-teu-nom>`, i el teu `main` ha de tornar a estar **idèntic al `main` del remot** (com si l'error mai no hagués passat). Després, push de la branca i obre un PR contra `main`.

### Pista
És exactament l'escenari **"He fet commit a main sense voler"** del receptari de la web. Llegeix-lo amb atenció: l'ordre dels passos importa. Si reseteges `main` abans de "rescatar" el commit, el commit es perd.

### Avaluació
- ✅ A `main` (al remot) **NO hi ha** la teva runa de R3
- ✅ A la branca `laberint/r3/<el-teu-nom>` **sí** hi és, com a un únic commit
- ✅ Tens un PR obert (no cal mergejar-lo per puntuar; sí per nota completa)
- ✅ BITACORA-R3.md

### ⚠️ Si la cagues
Si fas push del `main` accidentalment **abans** de resoldre-ho, t'haurà de cridar el master i possiblement reconstruir-ho amb `revert`. No passa res — fica-ho a la BITACORA com a "primer intent fallit" i continua.

---

## 🟡 R4 — Dues Veritats *(en parella)*

**Concepte**: conflicte real entre dos companys que toquen el mateix fitxer **i un d'ells el reanomena**. És més subtil que un conflicte clàssic.

### Context narratiu
> *"Dues veritats no poden ocupar el mateix lloc. El primer Branchwalker reanomena el manual del gremi i hi escriu els seus compromisos. El segon, sense saber-ho, edita el manual original afegint-hi el calendari. Quan el segon prova de mergejar, el manual original ja no existeix — i la seva feina queda penjant. **Heu de fer que el manifest final contingui les dues veritats.**"*

### Què heu de fer

El master us emparellarà i us assignarà **rols A i B** dins de la parella. Hi ha un fitxer ja existent al `main`: `laberint/r4/manual-de-l-equip.md` amb un contingut base.

> ⚠️ **CRÍTIC**: tots dos heu de crear la vostra branca personal **abans** que cap dels dos mergegi a `main`. Si B parteix d'un main amb el rename ja fet, no provocareu el conflicte i el repte queda invalidat.

#### Alumne A — el que reanomena
- Treballa a la teva branca personal `laberint/r4/A-<el-teu-nom>`.
- **Reanomena** el fitxer `manual-de-l-equip.md` a `manifest-de-l-equip.md`. Hi ha una comanda Git que reanomena conservant l'historial; busca-la (és a `git --help` o al receptari de comandes de la web).
- Al fitxer reanomenat, afegeix una secció `## Compromisos` amb 3 compromisos concrets del gremi.
- Commit + push + obre PR + **mergeja a `main`**.
- Avisa l'alumne B que ja has mergejat.

#### Alumne B — el que edita en paral·lel
- Treballa a la teva branca personal `laberint/r4/B-<el-teu-nom>`.
- Edita el fitxer **amb el nom antic** (`manual-de-l-equip.md`) afegint una secció `## Calendari` amb 3 dates rellevants per al projecte.
- Commit + push + obre PR (encara **sense mergejar**).
- Quan A ja hagi mergejat, **intenta sincronitzar la teva branca amb el `main` actualitzat**. Apareixerà un conflicte estrany — un que no és simplement "dues edicions de la mateixa línia".

### El repte real

> **Nota important sobre l'ordre**: no importa qui dels dos mergeja primer. El primer en mergejar passarà net; el segon tindrà conflicte. **Els dos rols (A=reanomena, B=edita el nom antic) són diferents**, però l'ordre dels merges és lliure.
>
> - Si **A mergeja primer**: B veu el seu fitxer "esborrat" a `main` (en realitat reanomenat). B ha d'aplicar la seva edició al fitxer nou.
> - Si **B mergeja primer**: A veu que `main` ha modificat un fitxer que ell ha reanomenat. A ha d'incorporar l'edició de B al nom nou abans de mergejar.
>
> En tots dos casos, el segon ha de **descobrir què ha passat amb el fitxer**, **incorporar les dues edicions** al lloc correcte, i acabar amb un **únic fitxer** (no dos!) a `main` que contingui les contribucions dels dos.
>
> Pista: `git status` durant un merge amb conflicte és la teva millor amiga. Et dirà exactament quins fitxers han causat què (i si algun fitxer "ha estat esborrat" o "modificat" a un costat o l'altre).

### Avaluació
- ✅ A `main` només hi ha `manifest-de-l-equip.md` (no `manual-de-l-equip.md`)
- ✅ El fitxer conté **les dues seccions**: `## Compromisos` (d'A) **i** `## Calendari` (de B)
- ✅ A l'historial es veu el commit de merge de B (`git log --merges`)
- ✅ Tots dos teniu BITACORA-R4.md (cadascun explica el seu costat)

### Pista
Mira al receptari: *"Tinc conflictes en fer pull o merge"* + *"El meu PR té conflictes a GitHub"*.

---

## 🟠 R5 — L'Ombra del Bug

**Concepte**: has pushejat un commit que trenca alguna cosa, ja està a `main`, els companys ja l'han descarregat. **No pots reescriure història**: has de fer un *revert*.

### Context narratiu
> *"Has gravat al Còdex una runa corrompuda. Els altres Branchwalkers ja l'han copiat al seu propi gremi. Esborrar-la del Còdex no la treuria d'ells — i, a més, deixaria una cicatriu a l'historial. Has de gravar una **runa inversa** que cancel·li el dany sense alterar el passat."*

### Què heu de fer

A la branca personal `laberint/r5/<el-teu-nom>`:

**Fase 1 — Construir l'escenari** (DELIBERADAMENT introduir un bug):

1. Crea el fitxer `laberint/r5/funcio-<nom>.md` amb un contingut "correcte". Per exemple:
   ```markdown
   # Funció saludar()
   Retorna el missatge: "Hola, viatger del Còdex"
   ```
2. Commit (commit "bo"): `feat(r5): funció saludar()`
3. Push.
4. Obre PR i **mergeja a main**.
5. Ara torna a la branca i fes una segona edició que **trenca** la funció:
   ```markdown
   # Funció saludar()
   Retorna el missatge: undefined undefined
   if (true) return false;  // això no té cap sentit
   ```
6. Commit (commit "dolent"): `fix(r5): refactor saludar()`
7. Push i mergeja a main.

Ara `main` té el bug. Suposem que els companys ja han fet pull.

**Fase 2 — Arregla-ho.**

Has de fer que el contingut del fitxer a `main` torni a ser el "bo" original — però **sense reescriure història** (el commit dolent ha de seguir visible al `git log`, i un commit nou ha de neutralitzar-lo). Crea una nova branca `laberint/r5-fix/<el-teu-nom>` des de `main` actualitzat, fes-hi el que calgui, push + PR + mergeja.

> ⚠️ **PROHIBIT**: `git reset --hard` + `git push --force` a main. Si ho fas, repte a 0. La protecció de `main` t'hauria de bloquejar igualment.

### Pista
És exactament l'escenari **"Vull desfer un commit ja pushejat"** del receptari de la web.

### Avaluació
- ✅ L'historial de `main` mostra **4 commits** lligats al teu fitxer R5: el bo, el dolent, el revert, i el merge del PR de fix
- ✅ El contingut final del fitxer `laberint/r5/funcio-<nom>.md` és el "bo" (versió original)
- ✅ **NO** has fet `reset --hard` ni `push --force` a main (es comprovarà)
- ✅ BITACORA-R5.md amb el `git log --oneline -5` que ho demostri

---

## 🔴 R6 — El Fragment Perdut

**Concepte**: has fet `git reset --hard` i has "perdut" commits. En realitat, Git els guarda 30 dies al **reflog**. Has de recuperar-los.

### Context narratiu
> *"Has invocat el `reset --hard` sense saber-ne el preu: tres dels teus fragments han desaparegut del Còdex. Però no estan destruïts — estan a una dimensió oculta a la qual només es pot accedir amb el `reflog`. Recupera'ls i porta'ls a una nova rama segura abans que el Nucli els esborri per sempre (en 30 dies)."*

### Què heu de fer

A la branca personal `laberint/r6/<el-teu-nom>`:

**Fase 1 — Construir l'escenari de pèrdua:**

1. Crea el fitxer `laberint/r6/diari-<nom>.md` amb una primera entrada.
2. Commit `feat(r6): primera entrada del diari` + push.
3. Edita el fitxer (segona entrada). Commit `feat(r6): segona entrada` + push.
4. Edita el fitxer (tercera entrada). Commit `feat(r6): tercera entrada` + push.

Ara tens 3 commits visibles a `git log`.

5. **DESTRUEIX-LOS:**
   ```bash
   git reset --hard HEAD~3
   ```
6. `git log --oneline -5` — els 3 commits ja no hi són. El fitxer del diari, tampoc (o ha perdut entrades).

**Fase 2 — Recupera el que has destruït.**

Els 3 commits **no estan realment perduts**. Git té un mecanisme intern que recorda tots els moviments del HEAD durant 30 dies, encara que aparentment hagis esborrat coses. Cerca'l al receptari.

Quan l'hagis trobat i hagis identificat els 3 commits, has de **crear una nova branca** `laberint/r6-recuperat/<el-teu-nom>` que contingui els 3 commits originals (per tant, el fitxer `diari-<nom>.md` ha de tornar a tenir les 3 entrades). Push d'aquesta branca al remot.

### Avaluació
- ✅ La branca `laberint/r6-recuperat/<el-teu-nom>` existeix al remot amb els 3 commits originals
- ✅ El fitxer `diari-<nom>.md` té les 3 entrades
- ✅ La BITACORA-R6.md inclou la **sortida literal** del `git reflog` (copia-paste) **abans** de la recuperació
- ✅ La BITACORA explica per què el reflog no funcionaria si haguessis clonat el repo de nou

### Pista
És exactament l'escenari **"He perdut feina després d'un reset o checkout"** del receptari de la web.

---

## 🏁 Tancament

Quan hagis acabat (o quan se't acabi el temps), fes:

```bash
git checkout laberint/bitacores-<el-teu-nom>
# Assegura't que totes les bítacores estan commitejades
git add laberint/bitacores/<el-teu-nom>/
git commit -m "docs(bitacores): tancament del laberint"
git push
```

I obre **un PR final consolidat** d'aquesta branca contra `main` amb el títol:
```
Laberint: bítacores de <el-teu-nom>
```

Al cos del PR, llista quins reptes has completat (R1 ✅, R2 ✅, R3 ✅, R4 ❌, R5 ⚠️ a mig fer, etc.) amb una frase per cada un.

---

## 💡 Filosofia

- **No demaneu ajuda al master fins haver consultat el receptari.** Les solucions hi són; cal llegir.
- **Demaneu ajuda als companys que ja han passat el repte.** Explicar-ho a un company forma part de la formació del que ho explica.
- **Si un repte us bloqueja 30 minuts, salteu-lo i torneu-hi més tard.** No us encalleu.
- **Equivocar-se i documentar-ho val més que encertar-ho a la primera sense entendre-ho.** Les bítacores honestes sumen.

> *"Els Branchwalkers no tenen por dels conflictes. Saben que un conflict marker és informació, no un error. Saben que el reflog és un déu menor que els salvarà del seu propi `--hard`. Saben que cada `! [rejected]` és el Nucli recordant-los que treballen en equip."*

Bona sort. El Còdex us espera.
