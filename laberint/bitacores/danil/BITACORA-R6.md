He començant fent un ``checkout -b`` a una nova branca ``laberint/r6/danil``. Després, en ``diari-danil.md`` he fet 3 canvis (missatges), un commit per cada canvi, i després un ``push origin``.

El segon pas era fer el reset ``git reset --hard HEAD~3``, fent aquest comando s'han eliminat els canvis i l'arxiu, 
**OUTPUT:**
```bash
HEAD is now at b6a76dc Merge pull request #25 from ruslanav-dam/laberint/r5-fix/dani** 
```

Fent ``git reflog`` podem veure els últims commits
**OUTPUT:** 
```bash
b6a76dc (HEAD -> laberint/r6/danil, origin/main, origin/HEAD, main) HEAD@{0}: reset: moving to HEAD~3
fc761e6 (origin/laberint/r6/danil) HEAD@{1}: commit: Missatge 3
f66addc HEAD@{2}: commit: Missatge 2
a5371c2 HEAD@{3}: commit: Missatge 1
```

Gràcies a aquesta informació, podem veure que el commit ``fc761e6`` és el commit abans del reset, per tal hem de revertir a aquest commit, el qual es pot fer amb revert o millor: ``git checkout -b laberint/r6-recuperat/danil fc761e6``, i després simplement fent ``push`` i PR.

S'ha d'anotar que el reflog nomès funciona en local; els canvis en la màquina local.