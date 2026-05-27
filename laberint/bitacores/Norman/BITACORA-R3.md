# BITACORA-R3 — Eco a `main`

## 1. Què he vist
Estava a la branca `main` i vaig crear i commitjar el fitxer `runa-Norman.md` directament sense estar a una branca pròpia.

## 2. Què crec que estava passant
El commit havia anat a `main` local, cosa que és perillosa perquè si fas push els companys hereten el teu canvi sense revisió ni PR.

## 3. Què he provat i què ha funcionat
1. Primer vaig crear la branca nova **abans** de tocar `main`: `git checkout -b laberint/r3/Norman`
   Això porta el commit "accidental" a la nova branca automàticament.
2. Vaig tornar a `main`: `git checkout main`
3. Vaig resetejar `main` al estat remot: `git reset --hard origin/main`
4. Vaig fer push de la branca: `git push -u origin laberint/r3/Norman`
5. Vaig obrir el PR contra `main`

## 4. Conclusió
L'ordre importa molt: si resetegem `main` abans de crear la branca nova, el commit es perd per sempre. Primer rescatar, després netejar.
