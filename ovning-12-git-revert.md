## Övning 12: Ångra en commit med `git revert`

**Fokus:** GIT   
**Svårighetsgrad:** Medel   
**Betygsgrundande:** Nej

### Mål

Lära sig att **återställa en commit** genom att använda **`git revert`**.

### Instruktioner

1.  Skapa ett **Git-repository** i din projektmapp och gör några commits genom att lägga till filer och göra ändringar.
2.  Kör kommandot:
    ```bash
    git log
    ```
3.  Använd **`git log`** för att hitta **hash-värdet** på en specifik commit som du vill ångra.
4.  Ångra commiten med följande kommando:
    ```bash
    git revert <commit-hash>
    ```
5. Se hur Git skapar en **ny commit** som återställer den tidigare commiten.

### Tips

Förstår du skillnaden på **`git reset`** och **`git revert`**? Annars läs denna: `https://www.atlassian.com/git/tutorials/undoing-changes/git-revert`.
