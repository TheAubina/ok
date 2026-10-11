# Hina Land 0.12.0 — nouveaux minerais

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. GeckoLib 4.4.9 et TerraBlender 3.0.1.7 requis.

## Contenu ajouté

14 véritables blocs de minerai enregistrés, 14 nouvelles ressources, 14 blocs de stockage, 7 pioches et 7 épées. Les minerais thématiques donnant les ressources Minecraft habituelles restent disponibles : les nouveaux matériaux s’ajoutent à cette progression.

| Famille de biomes | Ressource principale, plus rare | Ressource secondaire |
|---|---|---|
| Mario | Fragment d’étoile | Éclat de lune |
| Sonic | Émeraude du Chaos | Rubis Fantôme |
| OMORI | Verre de rêve | Pierre du cœur |
| DELTARUNE | Cristal des Ténèbres | Éclat de Lumière |
| Genshin | Morceau de cristal | Morceau d’améthyste |
| Overwatch | Cristal de lumière solide | Alliage de la Griffe |
| Lethal Company | Noyau d’appareil | Alliage de la Compagnie |

Les Émeraudes du Chaos, le Rubis Fantôme et les ressources de Genshin reprennent des noms de leurs univers. Les autres désignations sont des adaptations Hina Land. **Tous ces filons et leurs crafts constituent une adaptation Minecraft : ils ne reproduisent pas un système minier officiel de ces jeux.** Le noyau d’appareil et les alliages ne remplacent pas les objets de récupération MirRP déjà présents.

Chaque paire est générée dans les quatre variantes de sa propre famille, soit 28 biomes couverts. Les nouveaux minerais ne sont pas ajoutés aux biomes vanilla du Nether mélangé, ni à l’End vanilla. Les filons ciblent la roche thématique correspondante, ainsi que la pierre/deepslate vanilla dans leurs biomes. Ils ne remplacent ni la roche d’une autre famille ni le bedrock.

La ressource principale utilise des filons de taille 5, trois tentatives par chunk entre Y −60 et 16. La secondaire utilise des filons de taille 7, cinq tentatives entre Y −48 et 64. Il s’agit des hauteurs de placement des centres des filons ; leurs blocs peuvent déborder légèrement. Des tentatives peuvent échouer suivant la roche, les grottes et les frontières de biomes.

## Textures

Les minerais réutilisent les textures de minerai déjà intégrées depuis les packs, avec des identifiants, ressources et recettes propres. Ce ne sont pas de nouvelles illustrations : certains minerais ont donc le même aspect que leurs variantes thématiques antérieures. Les blocs de stockage réutilisent l’obsidienne ou les briques de leur famille.

Six icônes de ressources et six icônes d’outils Mario/OMORI/DELTARUNE reprennent directement les PNG des packs fournis. Les autres icônes utilisent les ressources graphiques déjà présentes dans Hina Land. Il n’y a pas encore une illustration unique pour chaque nouveau matériau ou outil. Aucun remplacement global des textures Minecraft n’est imposé.

## Récolte, crafts et outils

Une pioche en fer ou supérieure permet de récolter les nouveaux minerais. Sans Toucher de soie, chaque bloc donne une unité de sa nouvelle ressource ; Fortune augmente cette quantité, jusqu’à quatre avec Fortune III. Toucher de soie récupère le minerai intact. Les blocs de minerai attribuent également de l’expérience selon le mécanisme Minecraft des minerais.

77 nouvelles recettes, avec déverrouillage dans le livre de recettes :

- 14 compressions de neuf ressources vers un bloc ; 14 décompressions vers neuf ressources ;
- 14 recettes de fonte et 14 de haut-fourneau pour les minerais récoltés avec Toucher de soie ;
- 7 pioches : trois ressources principales en haut, une secondaire au centre et un bâton en bas ;
- 7 épées : deux ressources secondaires au-dessus d’une principale, dans une colonne ;
- 7 recettes d’essence : une ressource principale et une secondaire donnent deux essences de leur univers, utilisables dans les recettes existantes.

Les nouvelles pioches ont un niveau de récolte permettant l’obsidienne. Leur vitesse et durabilité varient : Mario 8,5/1600 ; Sonic 10/1400 ; OMORI 8/1800 ; DELTARUNE 9/1550 ; Genshin 8,5/1700 ; Overwatch 9,5/1450 ; Lethal 8/1900. Les épées infligent 7 points de dégâts de base. L’enchantabilité est 18. Les outils se réparent avec la ressource principale de leur famille, pas avec un diamant vanilla.

Aucun pouvoir magique propre aux outils, ensemble d’armure ou nouveau monstre n’est ajouté par cette version.

## Validation

- Build Gradle réussi ; JAR de production reobfusqué Forge 1.20.1, sans les classes de GameTest.
- **28 GameTests Forge obligatoires réussis**, dont trois nouveaux tests couvrant les 77 recettes avec de vraies grilles/conteneurs, les sorties de fonte, la réparation, les niveaux de récolte, les tables de butin normales/Toucher de soie/Fortune et l’isolation des features entre familles. Une première exécution a révélé un conflit de tags de niveau de pioche ; il a été corrigé et le test vérifie aussi que les niveaux vanilla diamant/fer restent corrects.
- **1832 JSON analysés**, références de textures vérifiées et 18 modèles/hiérarchies d’animations contrôlés. Aucun nouveau modèle de créature n’est ajouté.
- Serveur de production démarré avec les **22 mods** du pack, monde neuf de graine 20261012. Génération de neuf chunks autour de chacun des sept sites, puis sauvegarde. Lecture et décodage des blocs réels de **63 chunks FULL** : les **14 nouveaux minerais sont présents naturellement**, avant toute mise en scène de minerais.
- Client de production connecté à ce serveur ; les 14 blocs ont été affichés sur une plateforme de présentation et les ressources/outils dans l’inventaire. Les blocs de cette capture sont placés manuellement : la preuve de génération naturelle est le décodage de la sauvegarde, pas la capture. Aucun avertissement de texture/modèle manquant Hina Land n’a été relevé. Les autres avertissements vanilla/Forge et les trois succès Lunaria déjà bloqués ne sont pas présentés comme corrigés.

| Site naturel, neuf chunks chacun | Principale observée | Secondaire observée |
|---|---:|---:|
| Mario | 66 | 170 |
| Sonic | 69 | 162 |
| OMORI | 19 | 63 |
| DELTARUNE | 6 | 13 |
| Genshin | 45 | 142 |
| Overwatch | 62 | 141 |
| Lethal | 86 | 219 |

Ces nombres sont un échantillon, pas une garantie par chunk. Certains sites contiennent aussi des minerais d’une famille voisine aux frontières des biomes. Le JSON d’audit fournit les positions de plusieurs blocs et leurs hauteurs. La fonte et les crafts sont vérifiés par GameTests ; une campagne Survie complète et la difficulté de cette progression sur plusieurs heures ne sont pas testées. L’expérience attribuée par minage n’a pas fait l’objet d’un comptage séparé. Les 77 définitions de déverrouillage du livre de recettes sont incluses, sans validation manuelle exhaustive de chaque notification.

Le premier démarrage du serveur de test a pris environ 119 secondes en parallèle des autres contrôles. Les sept opérations de génération distante ont été réalisées en environ une minute ; ce n’est pas un benchmark d’exploration fluide. Les réglages Peaceful, graine, serveur hors ligne et plateforme de présentation sont locaux au test et ne sont pas imposés par le pack livré.

Preuves dans le modpack : `audit/minerals-0.12/`, contenant logs, manifeste de ressources, sites, comptages et captures.

## Installation et limites

Remplacer l’ancien JAR Hina Land par le 0.12.0, sans conserver deux versions. Les dépendances sont inchangées et incluses dans le modpack de test.

**Les nouveaux minerais apparaissent dans les chunks nouvellement générés.** Aucune insertion rétroactive dans les anciens chunks n’est effectuée. Sauvegarder son monde avant mise à jour. La migration d’un ancien Nether vers le Nether mélangé reste non validée ; créer un monde neuf pour reproduire cette génération.

Les limites générales de la 0.11 restent présentes : End custom à réaliser, pas de monstres Genshin/Overwatch, système Lethal incomplet, textures et plantes restant à intégrer. Le mod de quêtes fourni peut dupliquer ses chapitres au redémarrage ; Lunaria Media manque toujours et bloque trois succès. Les performances d’une longue exploration et une campagne multijoueur complète ne sont pas validées.
