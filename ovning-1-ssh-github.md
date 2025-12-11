# 🐙 Labb: GitHub-Grunderna – Konto, SSH & Första Repo

## 🎯 Mål

I den här övningen kommer du att:
1.  Skapa ett **GitHub-konto**.
2.  Lägga till en befintlig **SSH Public Key** till kontot.
3.  Skapa ett nytt **Repository (Repo)**.
4.  Klona ner Repot till din lokala maskin (och/eller till din vm) via SSH.

---

## 1. Skapa och Säkra Ditt GitHub-Konto

### A. Registrering

1.  Gå till [https://github.com/join](https://github.com/join).
2.  Fyll i dina uppgifter och skapa kontot.

### B. Hämta Din Publika SSH-Nyckel

Du behöver den **publika** nyckeln du skapade i [https://github.com/learnwithlandell/vm-ovningar/blob/main/ovning-3-vbox-ssh-keypair.md](vm-ovningar/blob/main/ovning-3-vbox-ssh-keypair.md) (Steg 3A). 
eller så kan du skapa en ny 
```
ssh-keygen -t ed25519
```

Öppna din Windows Terminal/PowerShell.

```bash
# Byt ut sökvägen till din .ssh-mapp vid behov.
# Filen slutar på .pub
cat ~\.ssh\id_ed25519.pub
```
➡️ Kopiera **hela utdata** (den långa strängen som börjar med `ssh-ed25519...`).

### C. Lägg till Nyckeln på GitHub

1.  Gå till din GitHub-profil $\rightarrow$ **Settings**.
2.  Välj **SSH and GPG keys** i menyn till vänster.
3.  Klicka på **New SSH key**.
4.  **Title:** Ge nyckeln ett beskrivande namn, t.ex. `Min Windows-Laptop` eller `Calle-Kali-VM`.
5.  **Key:** Klistra in den kopierade publika nyckeln här.
6.  Klicka på **Add SSH key**.

---

## 2. Skapa och Testa Ditt Första Repository

### A. Skapa Repot

1.  På GitHub, klicka på `+` uppe till höger $\rightarrow$ **New repository**.
2.  **Repository name:** Välj ett namn, t.ex. `min-forsta-labb`.
3.  Välj **Private** (om du inte vill att det ska vara publikt).
4.  Markera rutan **Add a README file**.
5.  Klicka på **Create repository**.

### B. Verifiera SSH-anslutningen

Öppna Terminalen på din linux VM (eller Windows). Vi testar nu att SSH-anslutningen till GitHub fungerar med din nyckel.

```bash
ssh -T git@github.com
```

> **Resultat:** Om det fungerar ska du få ett meddelande som säger något i stil med: `Hi ditt-användarnamn! You've successfully authenticated...`
gott!

### C. Klona Repot till Din Lokala Maskin

Nu kopierar vi ner repot till din dator.

1.  På din GitHub-repo-sida, klicka på den gröna knappen **Code**.
2.  Välj fliken **SSH** och kopiera URL:en (den ska börja med `git@github.com:...`).
3.  Gå till din Kali-terminal, navigera till en mapp där du vill ha projektet (t.ex. `~/Documents/`).
4.  Klona repot:

```bash
# Klona repot (byt ut URL:en mot din egen)
git clone git@github.com:ditt-användarnamn/min-forsta-labb.git

# Gå in i den nya mappen
cd min-forsta-labb
```

---

## 3. Extra Utmaning: Gör en Ändring och Synka

1.  Öppna README-filen och lägg till en rad:

```bash
nano README.md
# Lägg till en rad som: "Jag klarade detta steg via SSH!"
```

2.  **Staging** (förbered ändringen):

```bash
git add .
```

3.  **Commit** (spara ändringen lokalt):

```bash
git commit -m "Adderade framgångsmeddelande till README"
```

4.  **Push** (skicka ändringen till GitHub):

```bash
git push
```

> **Verifikation:** Gå till GitHub i webbläsaren. Din ändring ska nu vara synlig i din `README.md`-fil.

---

**🎓 Klart!** Du har nu full kontroll över GitHub via SSH och kan hantera koden säkert!
