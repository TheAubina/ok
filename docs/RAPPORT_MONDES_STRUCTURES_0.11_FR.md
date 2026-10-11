# Hina Land 0.11.0 — biomes supplémentaires, structures et Nether mixte

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. Dépendances : GeckoLib 4.4.9 et TerraBlender 3.0.1.7. Cette version suit la préférence exprimée : Genshin, Overwatch et Lethal sont des familles de biomes dans l’Overworld, sans dimensions séparées ni portails supplémentaires.

## Contenu intégré

Sept familles et quatre variantes chacune : plaine, forêt, hautes terres et dunes, soit 28 biomes Hina Land. Les trois nouveaux thèmes utilisent les textures fournies, des sols, roches jusqu’au sous-sol, minerais, arbres et fleurs. Douze nouvelles fleurs portent le total à 24. Les créatures Genshin et Overwatch ne sont pas ajoutées : les archives ne contiennent pas leurs modèles ni leurs IA. Les sept monstres Lethal conservent la restriction aux intérieurs de la version 0.10.

Les deux ZIP principaux contiennent cinq ZIP internes : trois resourcepacks et deux datapacks de structures. Conversion des chemins 1.21 `structure` et `loot_table` vers les chemins 1.20.1 `structures` et `loot_tables`, adaptation des références de biomes aux biomes Hina Land, et substitution des matériaux compatibles dans les palettes NBT. Les textures restent dans le namespace Hina Land ; elles ne remplacent pas globalement les blocs vanilla. Les PNG d’aperçu ne sont pas des tests de rendu en jeu.

Les 32 modèles sont intégrés dans des pools jigsaw et des ensembles de génération naturelle : 20 reliefs/décors et 12 constructions. Ils couvrent Mario, Sonic, OMORI, Genshin, Overwatch et Lethal. Les coffres ont des tables de butin ; les coffres Lethal utilisent les objets MirRP. Un vaisseau Lethal est une construction décorative, sans vol, quotas ou gestion de lunes. Les fichiers sources et empreintes sont répertoriés dans `imported-worlds-0.11.json`.

Les 215 textures de blocs/plantes fournies sont conservées dans les ressources du JAR. Les terrains usuels, minerais compatibles, arbres et quatre petites fleurs par nouveau thème ont des blocs utilisables. Toutes les plantes hautes et textures décoratives des packs ne sont pas encore des blocs indépendants générés naturellement.

## Nether mixte et sommeil

Le Nether utilise désormais un terrain ouvert de type Overworld, avec eau, ciel et cycle jour/nuit, et une source de biomes qui combine les 53 biomes Overworld, les cinq biomes Nether et les cinq biomes End de Minecraft 1.20.1. Le biome technique vide est exclu. La répartition utilise une grille climatique personnalisée ; elle ne reproduit pas à l’identique les répartitions de chaque dimension vanilla et ne garantit pas des proportions égales.

Les zones Nether ont netherrack, soul soil ou basalte, et les forêts cramoisies/biscornues ont le nylium nécessaire à leur végétation. Les zones End ont une roche hôte en end stone. Les lits ne doivent plus exploser, permettent le repos et le point de réapparition. Un gestionnaire Forge fait avancer l’horloge partagée avec l’Overworld jusqu’au matin après le sommeil dans le Nether. Le facteur des portails est configuré à 8:1 ; son rapport exact en jeu n’a pas été mesuré. Les ancres de réapparition restent utilisables.

L’End lui-même reste vanilla dans cette version. Sa transformation complète en monde custom reste à réaliser ; ajouter ses biomes au Nether ne remplace pas encore sa dimension.

## Installation et compatibilité

Remplacer l’ancien JAR Hina Land, sans garder plusieurs versions. Le modpack de test inclut les dépendances et les autres mods précédemment fournis. Java 17 et Forge 47.3.0 sont nécessaires.

**Créer un nouveau monde est recommandé et nécessaire pour reproduire le Nether testé ici.** Une sauvegarde existante peut conserver son ancien générateur/dimension Nether ; explorer de nouveaux chunks ne garantit pas l’adoption du nouveau Nether. La migration de ces sauvegardes n’a pas été validée. Ne pas supprimer les dimensions d’une sauvegarde pour appliquer cette bêta. Les constructions déjà générées restent inchangées.

Les valeurs TerraBlender du pack conservent de grandes régions et un poids vanilla réduit. Le mod de quêtes fourni peut dupliquer ses chapitres au redémarrage, et Lunaria Media manque toujours : trois succès restent bloqués. Ces limites du pack précédent ne sont pas corrigées ici.

## Vérifications

- Compilation Gradle et reobfuscation du JAR réussies.
- 25 GameTests Forge réussis : tests précédents, 28 biomes dans la source Overworld, 63 biomes dans la source Nether, chargement des 32 templates et butin non vide des tables de coffres, avance effective de l’horloge partagée après événement de sommeil Nether. Le test des fleurs couvre maintenant les six familles concernées.
- Un test Ghost Girl a d’abord échoué parce qu’il attendait aucune victime alors qu’un autre joueur de test intérieur pouvait être choisi. L’assertion vérifie désormais qu’aucune victime extérieure n’est conservée et qu’un éventuel remplacement est à l’intérieur ; le test a ensuite réussi.
- Contrôle statique : 1469 JSON et 18 modèles GeckoLib, références de textures contrôlées. Les premières ressources manquantes Overwatch et les chemins de butin 1.21 ont été corrigés.
- Audit du véritable générateur sur 16641 positions à Y=80 : les 28 biomes Hina Land sont observés dans l’Overworld ; 58 biomes vanilla distincts sont observés dans le Nether. Les cinq autres restent disponibles dans la source mais n’ont pas été retrouvés dans cet échantillon. Cette grille n’équivaut pas à générer tous les chunks.

- Inspection NBT des chunks FULL : les 12 sites naturels des nouveaux thèmes ont la roche thématique jusqu’en dessous de Y=0, le bedrock thématique, des arbres dans les forêts et sable/grès dans les dunes. Le point initial des dunes Lethal était recouvert par une construction ; un point voisin intact a été retenu avec les mêmes assertions.
- Les 12 nouvelles fleurs sont comptées effectivement dans les chunks, avec entre 1298 et 4967 blocs par type dans la zone inspectée.
- Neuf sites Nether FULL contrôlés : Nether wastes, soul sand valley, basalt deltas, crimson forest, warped forest, end highlands, the end, plains et forest. Le nylium cramoisi et biscornu est effectivement présent dans les deux forêts. Biomes attendus à Y=80, roches hôtes attendues et bedrock présents.
- 17 débuts de structures naturelles, de 12 types différents, ont été enregistrés dans les chunks inspectés. Les six recherches de structures ont abouti : pavillon et sakura Genshin, payload et cénote Overwatch, bâtiment et cratère Lethal. Des débuts et pièces de structures naturelles sont enregistrés dans `natural-structures-0.11.json`.
- Test du lit avec un joueur Survie connecté au serveur de production : entrée en sommeil sans explosion, `SleepTimer=19`, point de réapparition `minecraft:the_nether`, puis réveil avec `SleepTimer=0` et heure passée de 13601 à 94 (matin du jour suivant). Le lit et sa plateforme ont été placés manuellement pour isoler ce test. Après une mort provoquée, le bouton Réapparaître a replacé le joueur dans le Nether près du lit ; dimension, position et santé ont été contrôlées.

- Accès au Nether par un véritable portail vanilla activé au feu : joueur Survie passé de l’Overworld au Nether ; dimension et position confirmées par les données serveur. Le cadre a été construit manuellement dans le monde de test.

Les paysages et constructions naturelles ont été capturés en mode Spectateur pour stabiliser la caméra. Certaines constructions peuvent être recouvertes par la végétation ; aucun contrôle systématique de toutes leurs voies de passage n’a été réalisé.

Les rapports bruts, captures et fichiers de comptage sont fournis dans l’audit du modpack.

## Limites

Une partie longue en Survie, tous les emplacements de chaque structure, les rencontres multijoueurs et une campagne FTB complète ne sont pas encore validés. La génération de nouveaux chunks peut provoquer des pauses : le premier démarrage du monde de test a pris environ 91 secondes dans cet environnement, puis les redémarrages environ 24 secondes. Le chargement forcé de 19 sites éloignés à la suite a bloqué le serveur environ 142 secondes et nécessité une reconnexion du client ; cette méthode d’audit lourde ne valide pas les performances d’une exploration ordinaire. Les paramètres de serveur de test (mode hors ligne et watchdog étendu) ne sont pas inclus dans le modpack.

Les constructions et décors sont ceux fournis, adaptés techniquement ; pas une reproduction certifiée des jeux d’origine. Les IA de la version précédente restent des adaptations, Rudinn/Hathy sont des sprites et certains modèles CEM restent à convertir. Le ciel et les cinq musiques de la version 0.10 sont conservés ; aucune nouvelle écoute humaine n’a été réalisée.
