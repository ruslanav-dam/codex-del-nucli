El meu rol era de rol B, he esperat fins que el meu company A ha fet els canvis i el PR ha sigut acceptat, llavorç he posat els meus canvis de calendari. I he fet push (no he fet PR encara). Llavorç he fet el fetch dels canvis i ha aparegut el conficlte esperat. Per veure el conficte amb més informació he fet ``git status`` i els seguents comandes:

``git rm laberint/r4/manual-de-l-equip.md``
``git mv laberint/r4/manifest-de-l-equip.md laberint/r4/manifest-de-l-equip.md``

Amb això fet, he fet click a "Accept both changes" i els dos canvis s'han combinat, resolvent el conflicte.
Després de resoldre el conflicte, he fet el add, commit i PR, finalitzant l'activitat.

``git add laberint/r4/manifest-de-l-equip.md``
``git commit -m "combined"``