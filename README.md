# mrrobot55.fr

Site vitrine personnel — HTML statique servi par un conteneur nginx.

Historique extrait du monorepo `DOJ` le 2026-07-09 (via `git subtree split`), pour rendre ce
site totalement indépendant : dépôt Git séparé, déploiement séparé, aucune dépendance au
reste de l'infra.

## Déploiement

Le conteneur rejoint le réseau Docker `doj_doj_network`, déjà créé sur le VPS par ailleurs
(Nginx Proxy Manager y route `mrrobot55.fr` / `www.mrrobot55.fr` vers le conteneur
`doj_mrrobot55`). Si ce réseau n'existe pas sur une autre machine, crée-le avant de lancer
la stack, ou adapte la section `networks` du `docker-compose.yml` pour utiliser un réseau
dédié (et mets à jour ton reverse proxy en conséquence).

```bash
docker compose up -d
```

## Structure

- `index.html` — page unique du site.
