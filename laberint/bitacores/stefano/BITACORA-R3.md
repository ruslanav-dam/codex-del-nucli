# Bitácora Reto 3 - Stefano

1. **Què he vist** Havia fet un commit directament a la branca `main` per accident. Si feia push, pujaria els canvis a la branca principal sense passar per PR.
2. **Què crec que estava passant** Vaig oblidar crear i canviar a una branca de funcionalitat abans de començar a treballar (`git checkout -b`).
3. **Què he provat i què ha funcionat** - He creat una branca nova per salvar el commit: `git checkout -b laberint/r3/stefano`.
   - He tornat a main: `git checkout main`.
   - He netejat main per deixar-la com al remot: `git reset --hard origin/main`.
   - He tornat a la meva branca i he fet push: `git push -u origin laberint/r3/stefano`.
4. **Conclusió** He après que mentre no faci `push`, qualsevol error d'estar a la branca equivocada es pot arreglar creant una branca nova i resetejant l'anterior.