# Hina Land 0.8.0 — génération des biomes

## Changements

Douze biomes se génèrent dans l’Overworld : plaines, forêts, hauts plateaux et dunes/rivages pour Mario, Sonic et OMORI. Les anciens identifiants `hinaland:mario`, `sonic` et `omori` sont conservés pour les plaines. Les variantes ajoutent `_forest`, `_highlands` et `_dunes`. Il s’agit de variantes des trois univers déjà présents, pas de neuf univers supplémentaires.

Les régions thématiques ont chacune un poids TerraBlender de 12, contre 2 auparavant. Le modpack règle `overworld_region_size = 5` au lieu de 3 et `vanilla_overworld_region_weight = 6` au lieu de 10. Les océans, rivières et biomes de grottes restent vanilla ; une région vanilla conserve aussi une part des terres. La configuration du Nether n’est pas modifiée. Les variantes regroupent davantage de climats terrestres, au lieu de ne remplacer que quelques plaines et forêts.

La génération utilise désormais la roche thématique au-dessus de Y=0, les sols, terre, sable, grès, gravier, rochers en pierre/cobblestone, arbres thématiques et les cinq minerais thématiques (charbon, fer, or, redstone, diamant). Les hauts plateaux peuvent recevoir la neige thématique au-dessus de Y=120. La deepslate et le socle de bedrock restent vanilla. Cuivre, lapis et émeraude vanilla restent disponibles. Les briques, planches, obsidienne et netherrack décoratives ne sont pas dispersées arbitrairement dans le terrain : les structures thématiques restent à développer.

Les troncs et feuilles sont maintenant de vrais blocs de tronc/feuilles, avec axe et distance de feuillage. Le sable et le gravier ont la gravité. Les propriétés de dureté et les niveaux d’outils suivent les blocs vanilla correspondants. Les minerais disposent de drops adaptés (ressources vanilla, Silk Touch/Fortune), de recettes de fonte pour fer/or, et le bois thématique permet de fabriquer des planches utilisables dans les recettes vanilla. Ces ressources ne constituent pas une validation exhaustive de chaque recette en Survie.

Le ciel OMORI et les invasions reconnaissent également les variantes de leur famille. Les six créatures gardent leurs listes de spawns propres à chaque univers.

## Vérifications exécutées

- Compilation Java 17, réobfuscation et création du JAR : réussies.
- **Onze GameTests Forge : tous réussis.** Les neuf contrôles précédents sont conservés ; l’isolation des spawns couvre les douze biomes. Deux contrôles supplémentaires vérifient les matériaux/recettes et l’absence de cycle dans l’ordre de génération des features.
- Analyse de **590 JSON**, références de textures et 13 modèles/animations : réussie.
- Serveur Forge 47.3.0 utilisant le JAR 0.8.0 et les mêmes mods du pack : création d’un monde neuf, génération, sauvegarde et connexion du client de production réussies.
- **Douze sites naturels sauvegardés** contrôlés par décodage NBT : identifiant du biome confirmé à Y=80 et blocs réellement présents comptés. Roche thématique dans les douze chunks ; troncs/feuilles dans les trois forêts ; sable/grès dans les trois dunes. Les comptages sont dans `audit/worldgen-block-report.json`. Les captures forestières proviennent de téléportations vers des zones naturelles ; aucune commande de remplacement de biome n’a été employée pour ces vérifications.
- Affichage en client des forêts Mario et OMORI ; ciel violet observé dans la variante OMORI Forest. Le correctif d’atlas du pack reste activé ; aucun avertissement de texture manquante dans cette session.

Un premier essai a détecté un cycle d’ordre des minerais partagés avec Deep Dark. Les placed features de cuivre/lapis/émeraude ont été rendues propres à chaque région ; le test d’ordre et le monde neuf ont ensuite réussi. Un autre essai avait détecté une propriété `lit` manquante lors de la copie du minerai de redstone : celui-ci utilise maintenant la classe RedStoneOreBlock adaptée. Les résultats ci-dessus correspondent aux fichiers corrigés.

## Comparaison sur la même graine

Graine **20261011**, grille de **16 641 points**, pas de 128 blocs, X et Z entre −8192 et 8192, Y=80. La grille interroge la source de biomes du générateur ; elle ne génère pas chacun de ces chunks. Le témoin 0.7.0 utilise sa génération d’origine, avec uniquement la commande d’audit ajoutée au JAR de test. Ce JAR instrumenté n’est pas distribué.

| Mesure sur cet échantillon | 0.7.0 | 0.8.0 + configuration du pack |
|---|---:|---:|
| Points Hina Land, tous milieux compris | 9,6 % | 47,9 % |
| Points Hina Land hors océans, rivières et grottes | 16,5 % | 82,1 % |
| Traversée médiane d’un biome Hina Land sur les lignes de la grille | 128 blocs | 256 blocs |
| Traversée moyenne sur ces lignes | 240 blocs | 295 blocs |

Ces valeurs décrivent cette graine, à cette altitude et à cette résolution. Elles ne sont pas une proportion garantie pour tous les mondes, ni le diamètre exact des biomes. Des petites poches restent possibles aux transitions climatiques et aux reliefs. Les CSV des deux exécutions et les métriques sont fournis dans le paquet.

## Installation et limites

Remplacer l’ancien JAR Hina Land par `hinaland-0.8.0.jar` ; ne jamais garder les deux versions dans `mods/`. Pour obtenir les régions agrandies et la pondération vanilla mesurée, copier également le `config/terrablender.toml` du nouveau paquet. Les changements se voient dans les nouveaux chunks ; pour comparer proprement et éviter les raccords avec l’ancienne génération, créer un **nouveau monde**.

Lunaria Media reste absent ; ses trois succès de quête restent bloqués. Les boss, structures, autres univers et comportements complets Lethal restent à terminer conformément aux rapports précédents. Les recettes et drops ont été raccordés et chargés, mais aucune partie complète de Survie, progression de toutes les quêtes, compatibilité shaders ou campagne multijoueur n’est revendiquée.

Le test a employé un affichage virtuel, OpenGL logiciel et une sortie audio muette. La génération forcée en bloc de douze zones éloignées a provoqué une pause serveur d’environ 50 secondes dans le cloud ; ce scénario n’est pas un benchmark de déplacement normal et les performances n’ont pas été profilées. Le serveur de test utilisait un délai de surveillance augmenté ; ce réglage de test n’est pas distribué. La stabilité et l’équilibrage sur une longue session restent à vérifier.
