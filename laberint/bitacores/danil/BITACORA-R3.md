
1. **Què he vist** — el missatge d'error o símptoma exacte (copia-paste del terminal)


2. **Què crec que estava passant** — la teva interpretació (encara que t'equivoquis, val)


3. **Què he provat i què ha funcionat** — comandes copiades del teu terminal, en ordre

```bash
PS C:\Users\Daniel\OneDrive - La Salle Catalunya\LA_SALLE_MATERIAS\0487_EntornsDeDesenvolupament\Github\codex-del-nucli> git branch r3-dani
fatal: a branch named 'r3-dani' already exists
PS C:\Users\Daniel\OneDrive - La Salle Catalunya\LA_SALLE_MATERIAS\0487_EntornsDeDesenvolupament\Github\codex-del-nucli> git branch dani-r3
fatal: a branch named 'dani-r3' already exists
PS C:\Users\Daniel\OneDrive - La Salle Catalunya\LA_SALLE_MATERIAS\0487_EntornsDeDesenvolupament\Github\codex-del-nucli> git reset --hard HEAD~1
HEAD is now at e03e28b Merge pull request #9 from ruslanav-dam/gitignore-elim
PS C:\Users\Daniel\OneDrive - La Salle Catalunya\LA_SALLE_MATERIAS\0487_EntornsDeDesenvolupament\Github\codex-del-nucli> git checkout r3-dani
Deletion of directory 'laberint/bitacores/Norman' failed. Should I try again? (y/n) n
Deletion of directory 'laberint/bitacores/adria' failed. Should I try again? (y/n) n
Updating files: 100% (7/7), done.
Switched to branch 'r3-dani'
Your branch is based on 'origin/r3-dani', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)
```

4. **Conclusió** — una frase: què he après que no sabia abans

No entés molt el exercici, però ara r3-dani té el md en r3