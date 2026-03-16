# OSINT_GIT

Collection d'outils OSINT prêts à l'emploi. Tous les launchers sont dans `bin/` et ajoutés au PATH automatiquement.

---

## Installation

```zsh
echo 'export PATH="$PATH:/Users/mounir/ProjetsCoding/OSINT_GIT/bin"' >> ~/.zshrc
source ~/.zshrc
```

Le venv de chaque outil est créé automatiquement au premier lancement.

---

## Outils

### maigret — Username OSINT
Recherche un username sur 3000+ sites et génère un rapport complet.
```zsh
maigret <username>
maigret <username> --html          # rapport HTML
maigret <username> --pdf           # rapport PDF
```

---

### sherlock — Username hunting
Recherche un username sur 300+ réseaux sociaux.
```zsh
sherlock <username>
sherlock <username> --output results.txt
sherlock user1 user2 user3         # plusieurs usernames
```

---

### holehe — Email → comptes associés
Vérifie sur quels services un email est enregistré.
```zsh
holehe <email>
holehe <email> --only-used         # affiche seulement les comptes trouvés
holehe <email> -C                  # export CSV
```

---

### ghunt — OSINT Google account
Récupère les infos liées à un compte Google (nom, photo, Maps, YouTube...).
```zsh
# Première utilisation — authentification obligatoire :
ghunt login

# Ensuite :
ghunt email <email@gmail.com>
```

---

### h8mail — Email breach lookup
Vérifie si un email apparaît dans des fuites de données.
```zsh
h8mail -t <email>
h8mail -t <email> -bc config.ini   # avec clés API (dehashed, leakcheck...)
h8mail -t emails.txt               # liste d'emails depuis un fichier
```

---

### theHarvester — Domain recon
Collecte emails, subdomains, IPs et noms associés à un domaine.
```zsh
theharvester -d <domaine> -b google
theharvester -d <domaine> -b all           # toutes les sources
theharvester -d <domaine> -b google,bing -l 200
```

---

### spiderfoot — Framework OSINT automatisé
Lance une interface web pour automatiser une investigation complète.
```zsh
spiderfoot -l 127.0.0.1:5001       # démarre l'interface web
# Ouvre ensuite http://127.0.0.1:5001 dans ton navigateur
```

---

### recon-ng — Framework modulaire
Framework interactif avec des modules pour chaque type de recherche.
```zsh
recon-ng                           # lance le shell interactif
# Dans le shell :
# marketplace search <terme>       → cherche un module
# marketplace install <module>     → installe un module
# modules load <module>            → charge un module
# run                              → lance la recherche
```

---

### osintgram — OSINT Instagram
Collecte des informations sur un compte Instagram public.
```zsh
osintgram <username>
# Commandes dans le shell interactif :
# info          → infos du profil
# followers     → liste des followers
# followings    → liste des abonnements
# hashtags      → hashtags utilisés
# captions      → légendes des posts
# likes         → nombre de likes
```
> Nécessite des credentials Instagram dans `Osintgram/config/credentials.ini`

---

### subfinder — Enumération de subdomains
Trouve les sous-domaines d'un domaine cible.
```zsh
subfinder -d <domaine>
subfinder -d <domaine> -o output.txt
subfinder -d <domaine> -silent     # sortie propre sans logs
```

---

## Workflow typique

**À partir d'un email :**
```zsh
holehe target@gmail.com
ghunt email target@gmail.com
h8mail -t target@gmail.com
```

**À partir d'un username :**
```zsh
maigret username
sherlock username
```

**À partir d'un domaine :**
```zsh
theharvester -d exemple.com -b google
subfinder -d exemple.com
```
