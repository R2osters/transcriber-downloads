# Transcriber — site et téléchargements

Ce dépôt contient deux choses, et rien d'autre :

- **le site de présentation**, à la racine, servi par GitHub Pages ;
- **les installeurs**, publiés dans les [Releases](../../releases).

Le code source vit ailleurs : [AI-Video-Transcriber](https://github.com/R2osters/AI-Video-Transcriber).

## Pourquoi séparer

Un installeur pèse 218 Mo. Versionné dans git, il alourdirait chaque clone du
dépôt de code pour toujours — un fichier binaire ne se compresse pas d'une
version à l'autre. Les Releases GitHub le servent sans qu'il entre dans
l'historique.

## Le site

Sept pages HTML statiques, sans dépendance ni étape de construction. Pour le
consulter en local 

## Les installeurs

L'installeur Windows n'est signé par aucun certificat commercial. Windows
affichera un avertissement SmartScreen au premier lancement : « Informations
complémentaires » puis « Exécuter quand même ». Qui préfère ne rien exécuter
d'opaque trouvera dans le dépôt de code de quoi construire l'installeur
lui-même.

Le paquet macOS est fabriqué par la CI du dépôt de code, sur un runner Apple,
puis recopié ici : un workflow GitHub Actions ne peut publier que dans son
propre dépôt sans jeton personnel. Lui non plus n'est pas signé — Gatekeeper
refusera le double-clic, le contournement est le clic droit puis « Ouvrir ».

Il n'a jamais tourné sur un Mac réel. ffmpeg et ffprobe embarqués sont en
x86_64 et passent par Rosetta 2 ; l'application est native arm64.
