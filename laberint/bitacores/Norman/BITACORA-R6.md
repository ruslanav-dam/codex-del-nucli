# BITACORA-R6 — El Fragment Perdut

## 1. Què he vist
Després d'executar `git reset --hard HEAD~3` els 3 commits del diari havien desaparegut
## 2. Què crec que estava passant
El `reset --hard` mou el punter de la branca enrere i descarta els commits. Sembla que s'han perdut però Git els guarda al reflog durant 30 dies.

## 3. Què he provat i què ha funcionat
1. Vaig executar `git reflog` per veure l'historial ocult
2. Vaig identificar el commit `e2c7f38` — l'última entrada del diari
3. Vaig crear una nova branca apuntant a aquell commit:
   `git checkout -b laberint/r6-recuperat/Norman e2c7f38`
4. Vaig verificar amb `git log --oneline -5` que els 3 commits eren allà
5. Vaig fer push: `git push -u origin laberint/r6-recuperat/Norman`

## 4. Sortida literal de git reflog (abans de la recuperació)
4680328 HEAD@{0}: reset: moving to HEAD~3
e2c7f38 HEAD@{1}: commit: entrada 3 del diari
c7e569c HEAD@{2}: commit: entrada 2 del diari
2a352c9 HEAD@{3}: commit: feat(r6): entrada 1 del diari

## 5. Conclusió
El `git reflog` és com una dimensió oculta on Git guarda tots els moviments del HEAD. Sense ell, un `reset --hard` seria irreversible. Aquesta tècnica NO funcionaria si haguéssim clonat el repo de nou perquè el reflog és local — no es puja al remot.
