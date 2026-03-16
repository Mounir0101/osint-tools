# OSINT_GIT

Dépôt central regroupant des outils OSINT clonés et des scripts personnalisés.

## Structure

```
OSINT_GIT/
├── bin/                  # Launchers exécutables (ajoutés au PATH)
├── Osintgram/            # OSINT Instagram
├── sherlock/             # Username hunting (300+ sites)
├── maigret/              # Username → profil complet
├── holehe/               # Email → comptes associés
├── GHunt/                # OSINT Google account
├── phoneinfoga/          # OSINT numéros de téléphone
├── theHarvester/         # Emails, subdomains, IPs
├── spiderfoot/           # Automatisation OSINT (framework web)
├── recon-ng/             # Framework OSINT modulaire
├── twint/                # Scraping Twitter/X
├── h8mail/               # Email breach lookup
├── Sublist3r/            # Énumération subdomains
├── subfinder/            # Énumération subdomains (projectdiscovery)
├── Photon/               # Web crawler OSINT
├── EmailFinder/          # Recherche emails
├── email2phonenumber/    # Email → numéro de téléphone
├── social_mapper/        # Mapping réseaux sociaux
├── datasploit/           # Framework OSINT automatisé
└── compreface/           # Reconnaissance faciale
```

## Launchers disponibles (tapez directement dans le terminal)

| Commande | Outil | Usage |
|---|---|---|
| `osintgram` | Osintgram | `osintgram <instagram_target>` |
| `sherlock` | Sherlock | `sherlock <username>` |
| `maigret` | Maigret | `maigret <username>` |
| `holehe` | Holehe | `holehe <email>` |
| `ghunt` | GHunt | `ghunt email <email>` |
| `h8mail` | H8mail | `h8mail -t <email>` |
| `theharvester` | theHarvester | `theharvester -d <domain> -b google` |
| `photon` | Photon | `photon -u <url>` |
| `sublist3r` | Sublist3r | `sublist3r -d <domain>` |
| `twint` | Twint | `twint -u <username>` |
| `spiderfoot` | Spiderfoot | `spiderfoot -l 127.0.0.1:5001` (UI web) |
| `recon-ng` | Recon-ng | `recon-ng` (framework interactif) |

## Ajouter un nouveau launcher

Créer un script dans `bin/` :
```zsh
#!/bin/zsh
OSINT_DIR="$(cd "$(dirname "$0")/.." && pwd)"
cd "$OSINT_DIR/NomDuRepo"
# ... activation venv + lancement
```
Puis `chmod +x bin/nom_du_script`.

## Notes

- Chaque outil a son propre venv créé automatiquement au premier lancement
- Les credentials Instagram pour Osintgram se configurent dans `Osintgram/config/credentials.ini`
