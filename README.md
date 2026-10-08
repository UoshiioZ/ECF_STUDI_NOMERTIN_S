# ECF_STUDI_NOMERTIN_S
 ECF Studi Sujet Garage


## Serveur Minecraft

Serveur Minecraft Java Edition via Docker (image `itzg/minecraft-server`).

### Démarrage

```bash
cp .env.example .env
# éditer .env : EULA=TRUE (après avoir lu https://aka.ms/MinecraftEULA), MC_OPS=<ton pseudo>
docker compose up -d
docker compose logs -f minecraft   # attendre "Done"
```

Connexion dans le jeu : `IP_DU_SERVEUR:25565`.

### Commandes utiles

```bash
docker compose exec minecraft rcon-cli      # console du serveur (ex. : op pseudo)
docker compose restart minecraft
docker compose down                         # arrêt (le monde reste dans ./data)
```

### Hébergement

- **VPS / machine dédiée** : ouvrir le port TCP 25565 dans le pare-feu. 2 Go de RAM minimum pour ~10 joueurs.
- **Maison** : rediriger le port 25565 sur la box vers la machine.
- Sauvegarde : copier régulièrement le dossier `data/`.
