\# Bitacora R6 — El Fragment Perdut



\## Que he vist



Despres de fer git reset --hard HEAD\~3, els 3 commits del diari han desaparegut de la branca.

HEAD is now at 0448757 Merge pull request #12



\## Que crec que estava passant



El reset --hard mou el HEAD i la branca 3 commits enrere, eliminant els canvis del working directory. Pero els commits no s'esborren realment, Git els guarda al reflog durant 30 dies.



\## Que he provat i que ha funcionat



1\. git reflog per localitzar el hash de l'ultim commit perdut (705f0fd)

2\. git checkout -b laberint/r6-recuperat/stefano 705f0fd per crear una branca nova apuntant al commit recuperat

3\. git push -u origin laberint/r6-recuperat/stefano per pujar-la al remot



Sortida del reflog abans de la recuperacio:



0448757 HEAD@{0}: reset: moving to HEAD\~3

705f0fd HEAD@{1}: commit: R6: entrada 3 del diari de Stefano

2c91d67 HEAD@{2}: commit: R6: entrada 2 del diari de Stefano

f49d14e HEAD@{3}: commit: R6: entrada 1 del diari de Stefano



\## Conclusio



El reflog es una eina de recuperacio local. Si hagues clonat el repo de nou, el reflog estaria buit i els commits perduts serien irrecuperables perque el clone nomes descarrega les referencies actives del remot, no l'historial intern de moviments locals.

