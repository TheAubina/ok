# Hina Land 0.13.0 — génération et complexe Lethal

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. Le JAR livré est compilé et réobfusqué par ForgeGradle ; il ne contient pas les classes GameTest.

## Installation

Remplacer l’ancien JAR Hina Land dans `mods`, sans conserver deux versions. Le JAR seul requiert GeckoLib 4.4.9 et TerraBlender 3.0.1.7. Le modpack de test 7 inclut 22 JAR, ces dépendances et les autres mods fournis compatibles.

**Créer un monde neuf, de type Normal.** Le générateur et les sources de biomes sont enregistrés dans les sauvegardes. Les changements ne réparent pas automatiquement un ancien monde, ses maisons flottantes ou son Nether déjà rempli d’eau. La migration d’une sauvegarde existante et les presets Plat/Grandes biomes ne sont pas validés.

## Changements

- Overworld : source explicite limitée aux 28 biomes Hina Land (sept univers, quatre variantes), sur toute la hauteur. Aucune possibilité de biome vanilla dans cette source. Les régions restent grandes et les variantes stables en profondeur. Des mers et reliefs peuvent toujours exister, avec des identifiants et matériaux Hina.
- Créatures : sols thématiques admis pour les animaux ; animaux dans les variantes non désertiques des sept univers. Les dix ennemis thématiques ont une apparition de surface et deux contrôles compatibles avec la lumière du jour. Le contrôle de luminosité hérité de `PathfinderMob` était un deuxième blocage distinct de la règle de placement. Genshin/Overwatch disposent d’ennemis vanilla nocturnes, sans nouveaux modèles exclusifs.
- Structures : dix constructions sélectionnées dans six ensembles partageant une grille espacée de 48 chunks, séparation 24 et probabilité 0,65. Contrôle de chaque colonne de l’emprise : terrain sec, bon biome et dénivelé maximal de quatre blocs ; fondations comblant jusqu’à huit blocs sous les appuis. Les collines fortes et l’eau sont refusées. Les cellules vides des modèles préservent le terrain, pour éviter de creuser des fossés autour des façades. Les arbres évitent les chunks des constructions retenues. Les boîtes industrielles répétitives et les 24 autres placements automatiques sont retirés ; les anciens modèles restent accessibles pour placement manuel.
- Nether : mélange des 63 biomes vanilla conservé, climats échantillonnés six fois plus vite pour des parcelles plus petites. Niveau d’eau abaissé à Y=0, aquifères désactivés. De l’eau peut rester sous cette hauteur et des liquides locaux peuvent provenir des features vanilla. Les lits du Nether conservent leur comportement de la version 0.11.

## March, Offense et intérieur fourni

Les **façades d’entrée** March et Offense sont extraites de leurs sauvegardes Java 1.20.1 : 25 × 18 × 21 et 29 × 20 × 24 blocs. Le terrain découpé autour est retiré ; il ne s’agit pas d’une reproduction de toute la topographie des lunes. Elles se génèrent rarement dans les plaines/forêts Lethal. Les portes principales sont remplacées par des portes Hina utilisables au clic droit.

Elles mènent toutes deux à `hinaland:lethal_interior`, un complexe commun, fini et persistant. Le retour mémorise la dimension, la position et l’orientation de chaque joueur. Une sortie obstruée est refusée ; aucun bloc du joueur n’est cassé pour forcer un retour. Une porte peut aussi être fabriquée avec quatre lingots de fer et deux alliages de la Compagnie.

La zone industrielle de la carte Bedrock fournie est convertie : **133 × 26 × 116 blocs, 28 933 blocs conservés, 18 fragments NBT, 42 modèles industriels OBJ** avec textures, rotations et collisions. Les murs, tuyaux, passerelles, étagères et petits accessoires utilisent les ressources du pack. Une coque fermée protège la limite de cette zone finie. La texture `mesamadera` du bloc `ff:lamina` manque dans l’archive : une texture métallique fournie est utilisée à sa place.

Les commandes, scripts et comportements de l’add-on Bedrock ne sont pas exécutés ni transférés tels quels. La logique des portes et des monstres est une implémentation Java. Les mines/accessoires Bedrock sont décoratifs ; leur logique propre n’est pas reproduite.

Les sept espèces implémentées restent Bracken, Coil-Head, Hoarding Bug, Barber, Bunker Spider, Ghost Girl et Nutcracker. Elles ne peuvent apparaître et rester que dans un intérieur répondant aux contrôles de toit/murs. Le biome du complexe contient leurs sept entrées d’apparition, avec un coût de population partagé pour réduire la surpopulation de cette carte finie. Les behaviours et animations de la version précédente sont conservés ; les ennemis ne traversent pas les portes interdimensionnelles.

## Vérification

- Gradle : compilation, JAR réobfusqué et **32 GameTests requis réussis**. Les tests incluent les sources réellement utilisées, les animaux, les deux contrôles de luminosité, la restriction à la surface, l’intérieur converti, les sept prédicats Lethal, les portes des deux façades, la grille des structures et les fondations. Ils conservent les contrôles précédents des comportements, minerais et crafts.
- Client/serveur de production, 22 mods : aller-retour par March et Offense au clic droit. Retours confirmés à `[-8220.5, 74, -9587.5]` et `[-18203.5, 65, 2381.5]`, selon la porte empruntée. Le retour March a aussi été vérifié après redémarrage. Les déplacements dans la carte durant l’inspection utilisent des téléportations opérateur ; une traversée complète à pied n’est pas validée.
- Lethal : apparitions naturelles des sept espèces observées avant limitation de densité ; après réglage, deux audits de 11 puis 13 monstres, tous couverts, retrouvent ensemble les sept espèces. Les sept sont aussi vérifiées par les contrôles automatisés. Ce réglage n’est pas un plafond strict de 11 ou 13.
- Ressources : **1 990 JSON**, 18 modèles/hiérarchies d’animation GeckoLib contrôlés ; 42 modèles OBJ industriels chargés par le vrai client Forge.
- Monde neuf Normal, graine `20261013` : 16 641 échantillons de chaque dimension. Overworld : les 28 biomes Hina observés, zéro identifiant vanilla. Nether : 60 des 63 biomes possibles observés sur cet échantillon.
- Neuf sites Nether générés et enregistrés : blocs d’hôte et bedrock vérifiés ; zéro bloc d’eau au-dessus de Y=0 et zéro colonne avec une surface en eau sur les 2 304 colonnes examinées. Ce contrôle ne prouve pas l’absence de tout liquide dans toute la dimension.
- Apparitions réellement naturelles en journée dans Mario : 12 Dry Bones, 20 Goombas, 33 Koopas, 4 Pokeys ; animaux créés à la génération. Sur cet audit de 81 créatures, 70 avaient accès au ciel. Aucun de ces monstres n’a été invoqué pour produire cette preuve.

Les interactions en jeu portent sur les portes fermées utilisées au clic droit. Le dernier ajustement concerne uniquement leurs modèles d’états ouverts : le mapping est comparé au modèle officiel Minecraft. L’ouverture sous redstone n’a pas été testée en jeu. Toutes les classes et données serveur du JAR livré sont identiques à celles du JAR testé, ce qui est contrôlé dans `final-resource-comparison.json`.

Les preuves et journaux sont dans `audit`. Les contrôles visuels utilisent un client de test local et un rendu logiciel. Ils valident le chargement et des interactions représentatives ; ils ne remplacent pas une longue partie de survie ni des mesures sur ton PC.

## Reste à terminer

Équilibrage prolongé, exploration sur plusieurs graines, connexion simultanée de plusieurs joueurs et migration des anciennes sauvegardes. Toutes les anciennes structures n’ont pas été revues individuellement. Les apparitions des dix ennemis ont des contrôles automatisés, mais l’observation naturelle en journée documentée ici porte sur Mario.

Le complexe est commun à toutes les entrées ; pas encore d’instances de mission par groupe, de topographie complète March/Offense, de navette jouable, de quotas, d’économie Lethal complète ou de reproduction exacte de tous les comportements Bedrock. Le Hoarding Bug transporte les objets au sol, pas les coffres pleins. L’End personnalisé reste à réaliser.

Lunaria Media 2.0.2 reste absent et trois succès associés sont bloqués. Le mod de quêtes fourni peut dupliquer ses chapitres à chaque démarrage : les configurations du pack livré restent celles du paquet de base, pas celles du serveur de test redémarré plusieurs fois. Les grandes recherches `/locate` peuvent bloquer plusieurs secondes ; l’exploration prolongée reste à mesurer.

## Reproduire les contrôles

```sh
cd /workspace/hinaland
source tools/cloud-env.sh
./gradlew runGameTestServer build --max-workers=2 --console=plain
python tools/check_assets.py
```

Vérifier explicitement `All 32 required tests passed`, pas uniquement `BUILD SUCCESSFUL` : une erreur de datapack peut arrêter la préparation sans lancer les tests.

Les scripts d’import lisent les archives fournies et ne lancent pas leurs commandes. En cas de régénération des données : exécuter `revise_generation.py` après les anciens générateurs, puis `import_lethal_maps.py`. Le second requiert les blocs extraits par `read_bedrock.py` et les extractions Java originales ; les archives brutes ne sont pas republiées dans le ZIP de sources. Les ressources converties et compilables y sont présentes.
