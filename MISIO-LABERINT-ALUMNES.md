# 🌀 EL LABERINT DEL NUCLI — Missió per a Branchwalkers

> *El Nucli ha activat sis trampes lògiques dins del Còdex. Algunes les desactivareu sols, altres en parella. No totes són superables a la primera — i això forma part de l'aprenentatge.*

---

## 📜 Resum

Sis **reptes** independents. Cadascun simula una situació real que us trobareu treballant amb Git en un equip professional.

- **Treballareu tots al mateix repositori** (el Còdex compartit) dins de `/laberint/`.
- Tot el que feu queda visible per al master i per als companys.
- Si quedeu encallats, **abans de demanar al master** consulteu el receptari: 👉 https://ruslanav-dam.github.io/repositorisLIVE → secció *"Què faig si...?"*

---

## 🎯 Què cal entregar

Cada Branchwalker crea la seva carpeta `/laberint/bitacores/<el-teu-nom>/` i hi escriu **una bítacora per repte** (`BITACORA-R1.md`, `BITACORA-R2.md`...).

Cada bítacora ha de contenir:
1. **Què he vist** (símptoma exacte, copia-paste del terminal)
2. **Què crec que estava passant** (la teva interpretació)
3. **Què he provat i què ha funcionat** (comandes en ordre)
4. **Conclusió** (una frase: què he après que no sabia)

> ⚠️ **La bítacora val tant com la solució.** Repte resolt sense bítacora = mig punt. Repte mig-resolt amb bítacora honesta = punt sencer.

---

## 📊 Reptes i puntuació

| Repte | Nivell | Punts | Format |
|---|---|---|---|
| R1 — La Porta del Nucli | 🟢 Fàcil | 1 | Tots simultàniament a la mateixa branca |
| R2 — El Polissó del Còdex | 🟢 Fàcil | 1 | Individual |
| R3 — Eco a `main` | 🟡 Mitjà | 1.5 | Individual |
| R4 — Dues Veritats | 🟡 Mitjà | 2 | En parella (la trieu vosaltres) |
| R5 — L'Ombra del Bug | 🟠 Mitjà-Avançat | 2 | Individual |
| R6 — El Fragment Perdut | 🔴 Avançat | 2.5 | Individual |

**Total**: 10 punts. **Mínim per aprovar la missió: R1 + R2 + R3 (3.5 punts).**

---

## ⚙️ Preparació inicial (un cop)

```bash
git clone https://github.com/ruslanav-dam/codex-del-nucli.git
cd codex-del-nucli

# Crea la teva branca personal per a les bítacores
git checkout -b laberint/bitacores-<el-teu-nom>
mkdir -p laberint/bitacores/<el-teu-nom>
echo "# Bítacores de <el-teu-nom>" > laberint/bitacores/<el-teu-nom>/README.md
git add .
git commit -m "chore(laberint): inicialitza bítacora de <el-teu-nom>"
git push -u origin laberint/bitacores-<el-teu-nom>
```

---

## ⚔️ Personatges del gremi

| Branchwalker | Classe |
|---|---|
| Daniil | 🌿 BRANCHWALKER |
| Norman | ⚔️ MERGEMANCER |
| Stefano | 🕰️ CRONOMANTE |
| Adrià | 🔨 FORJADOR |
| Hector | 📡 NETRUNNER |

---

## 🟢 R1 — La Porta del Nucli

> *La Porta del Nucli s'obre quan tots els Branchwalkers hi gravin la seva runa. Però la Porta només accepta una runa cada vegada — qui s'avanci, passa; els altres han de readaptar-se a la nova realitat.*

**Què has d'aconseguir**: a la branca compartida `laberint/r1/porta-del-nucli`, afegir la teva runa al fitxer `porta-del-nucli.md`.

Format de runa (una línia, ordre lliure):
```
[CLASSE-Nom] PARAULA_DE_PODER
```
Exemple: `[FORJADOR-Adrià] FOC`

**Setup**: a la senyal del master, els 5 Branchwalkers feu el commit i el push **a la vegada**. La Porta només accepta una runa de cop.

**Avaluació**:
- ✅ El fitxer final té les 5 runes (una per cada Branchwalker)
- ✅ Hi ha 5 commits, un per cada autor
- ✅ Tens BITACORA-R1.md (especialment si has hagut de resoldre alguna cosa)

**Pista** (si quedes encallat): receptari → *"El push em rebutja amb non-fast-forward"*.

---

## 🟢 R2 — El Polissó del Còdex

> *Algú ha colat un fitxer de credencials al Còdex. Encara que les claus són falses, el procediment de neteja ha de ser el mateix que en producció.*

**Què has d'aconseguir**: a la teva branca personal `laberint/r2/<el-teu-nom>`, fer que `laberint/r2/credencials-fake.txt` deixi d'estar rastrejat per Git **sense esborrar-lo del teu disc local**, i evitar que pugui tornar a colar-se. Push + PR contra `main`.

**Avaluació**:
- ✅ El PR conté un `.gitignore` actualitzat (mínim: `credencials-fake.txt`, `.env`)
- ✅ El PR té un commit que treu el fitxer del seguiment
- ✅ El fitxer encara existeix a la teva carpeta local
- ✅ `git check-ignore laberint/r2/credencials-fake.txt` confirma que està ignorat
- ✅ BITACORA-R2.md

**Pista**: receptari → *"He commitejat un fitxer que no havia"*. Atenció a la trampa: `rm` no és la resposta.

---

## 🟡 R3 — Eco a `main`

> *Has gravat la teva runa directament al cor del Còdex en lloc de la teva rama. Si els companys es sincronitzen ara, hereten el teu error.*

**Què has d'aconseguir** (dues fases):

1. **Provoca tu mateix l'error**: estant a `main` (NO a una branca), crea un fitxer `laberint/r3/runa-<el-teu-nom>.md` (contingut lliure: una runa, una frase, el que vulguis) i fes-li commit. **No facis push.**
2. **Arregla-ho**: el commit ha d'acabar a una branca nova `laberint/r3/<el-teu-nom>`, i el teu `main` local ha de tornar a estar idèntic al `main` remot. Push de la branca + PR contra `main`.

**Avaluació**:
- ✅ A `main` (remot) NO hi ha la teva runa de R3
- ✅ A la branca `laberint/r3/<el-teu-nom>` SÍ
- ✅ PR obert
- ✅ BITACORA-R3.md

**Pista**: receptari → *"He fet commit a main sense voler"*. L'ordre dels passos importa: si reseteges `main` abans de "rescatar" el commit, el commit es perd.

---

## 🟡 R4 — Dues Veritats *(en parella)*

> *Dues veritats no poden ocupar el mateix lloc. Si dos Branchwalkers editen alhora un manual i un d'ells decideix reanomenar-lo, què passa amb la feina de l'altre?*

**Què heu d'aconseguir** (en parella, **vosaltres trieu parella**; si quedeu imparells, un fa parella amb el master):

1. Decidiu rols: **A reanomena**, **B edita el nom antic**.
2. **Tots dos creeu la vostra branca personal abans que cap mergegi a `main`** (crític: si B parteix d'un main ja modificat, el repte queda invalidat).
3. **A** treballa a `laberint/r4/A-<el-teu-nom>`: reanomena `manual-de-l-equip.md` a `manifest-de-l-equip.md` (busca quina comanda Git ho fa de manera neta) i hi afegeix una secció `## Compromisos` amb 3 línies de compromisos del gremi. Push + PR + mergeja a `main`.
4. **B** treballa a `laberint/r4/B-<el-teu-nom>`: edita el fitxer `manual-de-l-equip.md` (amb el nom **antic**) afegint una secció `## Calendari` amb 3 dates rellevants. Push + PR (no mergeja encara).
5. Quan el primer dels dos hagi mergejat, el segon sincronitza la seva branca amb el `main` actualitzat. Apareixerà un conflicte estrany (no un conflicte clàssic de "dues edicions a la mateixa línia"). Resol-lo de manera que a `main` quedi **un únic fitxer** (amb el nom nou) amb totes dues seccions.

**Avaluació**:
- ✅ A `main` només hi ha `manifest-de-l-equip.md` (no `manual-de-l-equip.md`)
- ✅ El fitxer té `## Compromisos` I `## Calendari`
- ✅ Hi ha un commit de merge a l'historial
- ✅ Tots dos teniu BITACORA-R4.md (el rol que ha resolt el conflicte ho explica amb més detall)

**Pista**: receptari → *"Tinc conflictes en fer pull o merge"* + *"El meu PR té conflictes a GitHub"*. `git status` durant un merge és la teva millor amiga.

---

## 🟠 R5 — L'Ombra del Bug

> *Has gravat al Còdex una runa corrompuda. Els companys ja l'han copiat. No pots reescriure el passat — has de gravar una runa inversa que cancel·li el dany.*

**Què has d'aconseguir** (dues fases):

1. **Provoca l'escenari**: a la teva branca `laberint/r5/<el-teu-nom>`, fes un commit que afegeix un fitxer `funcio-<el-teu-nom>.md` amb un contingut "bo" (text que pretengui ser una funció correcta). Mergeja a `main` via PR. Després, a una nova branca, fes un commit que **trenca** aquell mateix fitxer (canvia el contingut perquè no tingui sentit). Mergeja també.
2. **Arregla-ho**: el contingut del fitxer a `main` ha de tornar a ser el "bo" original, però **sense reescriure història** (el commit dolent ha de seguir visible al `git log`). Crea una branca `laberint/r5-fix/<el-teu-nom>`, fes-hi el que calgui, push + PR + mergeja.

> ⚠️ **PROHIBIT**: `git reset --hard` + `git push --force` a main → repte a 0. La protecció de `main` t'hauria de bloquejar igualment.

**Avaluació**:
- ✅ El contingut final del fitxer és el "bo"
- ✅ L'historial té els 4 commits (bo, dolent, fix, merges)
- ✅ NO has fet force-push a main
- ✅ BITACORA-R5.md amb `git log --oneline -5` enganxat

**Pista**: receptari → *"Vull desfer un commit ja pushejat"*.

---

## 🔴 R6 — El Fragment Perdut

> *Has invocat el `reset --hard` sense saber-ne el preu: tres dels teus fragments han desaparegut. No estan destruïts — hi ha una dimensió oculta on Git els guarda 30 dies.*

**Què has d'aconseguir** (dues fases):

1. **Provoca l'escenari**: a la teva branca `laberint/r6/<el-teu-nom>`, fes 3 commits seguits (per exemple, 3 entrades successives a `diari-<el-teu-nom>.md`). Pusheja-ho. Després executa `git reset --hard HEAD~3`. Els 3 commits "han desaparegut".
2. **Recupera-ho**: crea una nova branca `laberint/r6-recuperat/<el-teu-nom>` que contingui els 3 commits originals (i, per tant, el fitxer amb les 3 entrades). Pusheja-la al remot.

**Avaluació**:
- ✅ La branca `laberint/r6-recuperat/<el-teu-nom>` existeix al remot amb els 3 commits originals
- ✅ El fitxer té les 3 entrades
- ✅ BITACORA-R6.md amb la sortida literal de `git reflog` (copia-paste) **abans** de la recuperació
- ✅ La BITACORA explica per què aquesta tècnica NO funcionaria si haguessis clonat el repo de nou

**Pista**: receptari → *"He perdut feina després d'un reset o checkout"*.

---

## 🏁 Tancament

Quan acabis (o quan se't acabi el temps), pusheja totes les bítacores i obre **un PR final consolidat** d'aquesta branca contra `main` amb el títol `Laberint: bítacores de <el-teu-nom>`.

Al cos del PR, llista quins reptes has completat (R1 ✅, R2 ✅, R3 ✅, R4 ❌, R5 ⚠️ a mig fer...) amb una frase per cada un.

---

## 💡 Filosofia

- **Receptari abans que master.** Les solucions hi són; cal llegir.
- **Companys abans que master.** Demanar a algú que ja ha passat el repte és vàlid (i ajuda al que ho explica a aprendre més).
- **Si t'encalles 30 minuts, salta el repte.** Torna-hi més tard. No us encalleu.
- **Una bítacora honesta i raonada val més que un repte resolt sense entendre.**

> *"Els Branchwalkers no tenen por dels conflictes. Saben que un conflict marker és informació, no un error. Saben que el reflog és un déu menor que els salvarà del seu propi `--hard`. Saben que cada `! [rejected]` és el Nucli recordant-los que treballen en equip."*

Bona sort. El Còdex us espera.
