En una branca nova, he creat l'arxiu ``funcio-dani.md``, i he posat dins un text per demostrar que era l'arxiu bó, i després l'he guardat, commiteat i mergeat a main.
Un cop mergeat, he fet una nova branca per "trencar" l'arxiu, que era básicament canviar el text de bo a mal. Després de canviar el text, he fet ``add``, ``commit`` i ``push``. Un cop el PR s'ha mergeat a main, ho he tingut que "arreglar", per arreglar, he fet servir el ``git revert``. Abans de fer el revert, he fet una nova branca ``fix``. Abans de fer el revert, s'ha de saber el hash/codi del commit dolent, el qual es fa amb ``git log --oneline``. Un cop tenim el hash del commit mal, fem ``git revert <hash>`` i ``push``, finalitzant l'activitat amb el PR.

Es pot verificar el resultat fent ``checkout`` a main, fent ``pull`` del main i fent ``git log --oneline -5``.

*Perquè he fet el ``git log --oneline`` he perdut l'output previ, a més, m'he olvidat guardar el missatge del git revert per tal no tinc cap output.