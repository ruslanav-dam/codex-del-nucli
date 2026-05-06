1. **Què he vist** — el missatge d'error o símptoma exacte (copia-paste del terminal)
no hem deixaba fer push

2. **Què crec que estava passant** — la teva interpretació (encara que t'equivoquis, val)
no habia creat el meu Branch

3. **Què he provat i què ha funcionat** — comandes copiades del teu terminal, en ordre
fer ho tot per terminal

PS C:\Users\User\Documents\GitHub\codex-del-nucli> git pull origin main
From https://github.com/ruslanav-dam/codex-del-nucli
 * branch            main       -> FETCH_HEAD
Already up to date.
PS C:\Users\User\Documents\GitHub\codex-del-nucli> git checkout -b laberint/bitacores-adria
Switched to a new branch 'laberint/bitacores-adria'
PS C:\Users\User\Documents\GitHub\codex-del-nucli> git add .                   
PS C:\Users\User\Documents\GitHub\codex-del-nucli> git commit -m "chore(laberint): inicialitza bítacora de Adrià"
[laberint/bitacores-adria 4316114] chore(laberint): inicialitza bítacora de Adrià
 1 file changed, 2 insertions(+), 1 deletion(-)
PS C:\Users\User\Documents\GitHub\codex-del-nucli> echo "# Bítacores de Adrià" > laberint/bitacores/adria/README.md              
PS C:\Users\User\Documents\GitHub\codex-del-nucli> git add .                                   
PS C:\Users\User\Documents\GitHub\codex-del-nucli> git commit -m "chore(laberint): inicialitza bítacora de Adrià 2"
[laberint/bitacores-adria 3bcbaf9] chore(laberint): inicialitza bítacora de Adrià 2
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 laberint/bitacores/adria/README.md

4. **Conclusió** — una frase: què he après que no sabia abans

Fer Commit y push desde terminal de VS
