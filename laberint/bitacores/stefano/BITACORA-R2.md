# Bitácora Reto 2 - Stefano

1. **Què he vist** Un fitxer `credencials-fake.txt` estava sent rastrejat per Git, posant en perill la seguretat si fossin claus reals.
2. **Què crec que estava passant** Algú va fer un `git add .` sense tenir el fitxer ben configurat al `.gitignore`.
3. **Què he provat i què ha funcionat** - `git rm --cached laberint/r2/credencials-fake.txt` per treure'l de Git sense esborrar-lo del meu disc.
   - He afegit `credencials-fake.txt` i `.env` al fitxer `.gitignore`.
   - He comprovat el bloqueig amb `git check-ignore laberint/r2/credencials-fake.txt`.
4. **Conclusió** He après que `git rm --cached` és la solució ideal per esmenar l'error de pujar fitxers privats sense destruir la meva configuració local.