# Hina Land 0.9.0 — musiques et géologie

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. JAR seul : GeckoLib 4.4.9 et TerraBlender 3.0.1.7 requis. Le pack fournit ces dépendances.

## Changements

- Mario : New Super Mario Bros Wii — Overworld 1.
- Sonic : Sonic The Hedgehog — Green Hill Zone.
- OMORI : Trees…, Sugar Star Planetarium et Snow Forest — A Single Flower Blooms.
- Les cinq MP3 fournis sont convertis en OGG Vorbis stéréo 44,1 kHz, déclarés en streaming. Playlist locale au client, trois morceaux OMORI aléatoires sans répétition immédiate, arrêt au changement d’univers, délai entre les morceaux et respect du réglage Musique. La musique vanilla est suspendue dans ces biomes.
- Faces d’herbe, dessus des troncs et dessus du grès raccordés aux textures présentes. Tronc orientable suivant son axe.
- Roche thématique à toutes les profondeurs, y compris sous Y=0 et sous les biomes de grottes qui traversent ces régions. Socle thématique avec la résistance du bedrock. Remplacement de la roche hôte uniquement : minerais, air, eau et blocs de grottes conservés.
- Les douze variantes de biomes et la configuration des régions agrandies de 0.8.0 sont conservées.

## Textures de fleurs

Aucune image de fleur n’a été retrouvée dans l’archive 0.6 ni dans les pièces jointes accessibles. Le titre musical « A Single Flower Blooms » ne contient pas une texture. L’intégration des fleurs avec vos images reste à faire lorsque ces fichiers seront accessibles. Aucun visuel inventé n’est présenté comme une texture fournie.

## Installation et limites

Remplacer l’ancien JAR Hina Land, sans conserver deux versions. Copier la configuration TerraBlender du pack. Créer un monde neuf ou explorer de nouveaux chunks pour la géologie : les chunks déjà générés ne sont pas convertis. Activer le resourcepack d’intégration fourni pour les particules des autres mods.

Le pack conserve les limites documentées en 0.8.0 : Lunaria Media absent, trois succès associés bloqués ; autres univers, structures, boss et comportements Lethal complets encore en développement. Le Hoarding Bug ne transporte pas encore de coffres.

Les tests audio du cloud valident le décodage et le moteur de lecture ; ils ne remplacent pas une écoute sur un ordinateur avec sortie audio. Une campagne complète de Survie et la compatibilité avec des mods supplémentaires ne sont pas validées.

## Validation de cette version

- Gradle : compilation, reobfuscation et build réussis. Douze GameTests Forge exécutés et réussis, dont sélection des trois morceaux OMORI, cinq événements enregistrés et absence de répétition immédiate.
- Assets : 597 JSON analysés, références et hiérarchies d’animations des treize créatures contrôlées ; toutes les textures référencées par les modèles de blocs existent.
- Audio : cinq fichiers Vorbis stéréo intégralement décodés sans erreur par FFmpeg ; aucun flux vidéo conservé. Le client de production confirme via SoundManager.isActive la lecture des cinq pistes : Mario, Sonic, OMORI Snow Forest, Trees… et Sugar Star Planetarium. Les deux changements OMORI ont été provoqués par /stopsound pour tester le passage au morceau suivant sans attendre toute leur durée. Sortie OpenAL nulle dans le cloud : aucune écoute humaine réalisée.
- Monde neuf, graine 20261011 : douze sites naturels sauvegardés vérifiés. Roche thématique et bedrock thématique présents sous Y=0 dans chacun ; aucune deepslate vanilla comme roche hôte dans la colonne centrale contrôlée. Troncs et feuilles dans les forêts, sable et grès dans les dunes. Ce sondage ne couvre pas tous les chunks possibles.
- Client Minecraft et serveur Forge de production chargés avec les 22 JAR ; capture du ciel violet étoilé dans la forêt OMORI et du terrain Mario, sans erreur de texture manquante Hina Land observée. Les erreurs des trois succès Lunaria et les requêtes d’authentification indisponibles dans le test hors ligne restent documentées.

Les détails bruts sont fournis dans audit/audio-0.9. Le premier JAR de serveur de contrôle précédait uniquement la suppression de la couverture vidéo Sonic ; le JAR client testé et livré contient la correction finale. La logique et les données de génération sont identiques.
