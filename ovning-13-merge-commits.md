## Övning 13: Visa endast merge-commits med `git log --merges`

**Fokus:** GIT   
**Svårighetsgrad:** Medel   
**Betygsgrundande:** Nej   

### Mål

Lära sig hur man **filtrerar `git log`** för att visa enbart **merge-commits**.

### Instruktioner

1.  **Skapa ett repository** (om du inte redan har ett).
2.  Skapa flera branches och slå ihop dem med huvudbranchen.
    ```bash
    git branch feature-branch-a
    git branch feature-branch-b
    ```
3.  Gå till **`feature-branch-a`**:
    ```bash
    git checkout feature-branch-a
    # Lägg till en ny fil (t.ex. feature-a.txt) och gör en commit.
    ```
4.  Gå till **`feature-branch-b`**:
    ```bash
    git checkout feature-branch-b
    # Lägg till en ny fil (t.ex. feature-b.txt) och gör en commit.
    ```
5.  Byt tillbaka till huvudbranchen (`main` eller `master`):
    ```bash
    git checkout main
    ```
6.  Slå ihop (`merge`) `feature-branch-a` och `feature-branch-b` med huvudbranchen:
    ```bash
    git merge feature-branch-a
    git merge feature-branch-b
    ```
7.  Använd **`git log`** för att visa **enbart merge-commits**:
    ```bash
    git log --merges
    ```
8.  Använd följande kommando för att visa en **grafisk representation**:
    ```bash
    git log --graph --oneline --all
    ```

### Tips

Testa att köra **`gitk`** i terminalen, du borde nu se ett GUI.
