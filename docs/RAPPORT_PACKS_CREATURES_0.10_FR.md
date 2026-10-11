# Hina Land 0.10.0 — packs et créatures

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17. JAR installable reobfusqué ; dépendances GeckoLib 4.4.9 et TerraBlender 3.0.1.7. Pack de test avec les 22 JAR habituels.

## Archives et provenance

Les cinq fichiers reçus sont des packs de ressources, et non des mods fournissant une IA. Aucune instruction contenue dans ces fichiers n’a été exécutée. Les archives OMORI et DELTARUNE dépassaient la limite de transfert de 32 Mo ; elles ont été téléchargées depuis les liens fournis par l’utilisateur :

- OMORI : https://drive.google.com/file/d/1CvGzjqCZAbzYelDyJt9LwHHuNx2wB5iJ/view — 195 661 043 octets.
- DELTARUNE : https://www.curseforge.com/minecraft/texture-packs/deltarune/download/7484269 — 85 834 420 octets, téléchargement CDN Forge autorisé par cette page.
- Sonic : pack de NameleSss87, format 11. Mario : Super Mario Mash-up, incluant des ressources de versions récentes. OMORI : pack 1.20, format 15. DELTARUNE : format 34, adapté par extraction des ressources compatibles ; le pack complet récent n’est pas activé globalement en 1.20.1.
- MirRPLethalCompany : 27 modèles d’objets de récupération CIT. Aucun modèle de créature ni code d’IA trouvé dans cette archive. Les sept modèles et animations Lethal de la version précédente sont conservés.

Les textures sélectionnées sont copiées dans l’espace `hinaland`, sans remplacer les blocs et créatures vanilla de tous les biomes. `imported-assets-0.10.json` conserve les chemins et empreintes des textures principales. Les auteurs et crédits des modèles sont conservés. Les menus, skins, musiques supplémentaires et milliers de textures non raccordées à des objets Hina Land ne sont pas importés automatiquement.

## Biomes et fleurs

- Mario, Sonic et OMORI utilisent les ressources compatibles des nouveaux packs pour les blocs existants. Les modèles de sol Sonic conservent les variations pondérées du pack, avec une coloration issue du biome.
- Douze fleurs réelles sont ajoutées : pissenlit, coquelicot, orchidée bleue et marguerite pour Mario, OMORI et DELTARUNE. Génération naturelle dans les plaines, forêts et hauts plateaux ; support des sols thématiques, récolte et objets d’inventaire. Les fleurs Mario animées conservent leur fichier `.mcmeta`.
- DELTARUNE a quatre variantes dans l’Overworld : plaine, forêt, hauts plateaux et dunes. Blocs, roche jusqu’au bedrock, minerais, arbres, sable et grès utilisent les mêmes mécanismes fonctionnels que les autres univers, avec ses textures adaptées et ses couleurs propres.
- Les cinq musiques de 0.9.0 et le ciel étoilé OMORI sont conservés. Aucun morceau DELTARUNE n’a été ajouté sans fichier fourni.
- Les grandes régions restent configurées avec taille 5 et poids vanilla 6. Ajouter une quatrième famille change leur répartition ; les anciennes mesures de pourcentage de 0.8.0 ne décrivent pas cette version.

## Créatures et IA

Les noms ont été recoupés sur des encyclopédies de jeux accessibles. Ce sont des références communautaires, pas une certification officielle des modèles du pack.

| Créature | Visuel utilisé | Comportement ajouté ou conservé |
|---|---|---|
| Goomba | Texture de la poule Mario, identification confirmée par Mario Wiki ; maillage natif adapté | Marche, poursuite ; écrasement par un joueur descendant et rebond |
| Koopa Troopa | Texture du mouton Mario ; maillage natif adapté | Retrait en carapace après un coup, deuxième coup pour propulser la carapace, dommages par contact en mouvement, retour après délai ; état sauvegardé |
| Skelerex / Dry Bones | Texture de squelette Mario ; maillage natif adapté | Coup fatal par une créature : effondrement au lieu de mourir, invulnérabilité temporaire et reconstitution ; apparitions naturelles |
| Pokey | Texture de Creeper Mario identifiée comme Pokey, maillage adapté | Ennemi terrestre au contact, plus fréquent dans les dunes ; n’explose pas |
| Moto Bug | Visuel bêta précédent | Charge en ligne droite par intervalles |
| Buzz Bomber | Visuel bêta précédent | Vol vers la cible et tirs avec dégâts, sans récupération de flèches |
| Omochao | Modèle CEM mécanique et texture Allay du pack Sonic, convertis en GeckoLib natif ; hélice et clé animées | Créature amicale naturelle Sonic, vol, suivi à courte distance ; réparation avec pépite d’or et conseil. Adaptation Minecraft, pas simulation d’un jardin Chao |
| Sprout Mole | Texture de villageois OMORI, nom confirmé par le fichier de langue ; maillage adapté | Ennemi terrestre au contact |
| Forest Bunny | Texture de lapin OMORI, maillage adapté | Poursuite et bonds vers la cible |
| Rudinn | Sprite de référence DELTARUNE Wiki, converti en PNG sans modification des pixels | Ennemi naturel DELTARUNE, éventail de trois projectiles diamant ; interaction à main vide pour convaincre et arrêter temporairement le combat |
| Hathy | Sprite de référence DELTARUNE Wiki, converti en PNG sans modification des pixels | Ennemi naturel DELTARUNE, anneau de huit projectiles cœur ; interaction à main vide pour flatter et arrêter temporairement le combat |

Rudinn et Hathy ont un rendu de sprite dans le monde 3D, pas un modèle 3D détaillé provenant de l’archive. Les projectiles ont propriétaire, dégâts, collision avec les murs et durée de vie limitée. Le clic à main vide est une adaptation du système ACT/SPARE ; il n’y a pas d’interface de combat au tour par tour. Frapper à nouveau annule l’état apaisé.

Les autres modèles CEM Sonic et les nombreux reskins DELTARUNE ne sont pas tous convertis : plusieurs représentations n’ont pas pu être identifiées avec certitude. Aucun nom de monstre officiel n’est inventé pour ces fichiers. Les bosses, autres univers et comportements complets du cahier des charges restent en développement.

## Système Lethal Company

- Les sept créatures sont soumises à la même règle d’intérieur, **Ghost Girl comprise**, y compris lorsqu’on tente de les invoquer dehors.
- Un intérieur est une zone couverte par un bloc de collision plein à 2–16 blocs au-dessus, avec une paroi détectée dans au moins trois directions à 12 blocs maximum. Feuilles et eau ne comptent pas. Cette règle accepte les petites salles et les tunnels/cavernes étroits ; elle n’identifie pas exclusivement des bâtiments industriels.
- Apparitions naturelles rares dans les biomes Overworld, avec les conditions de monstre et d’intérieur. Une créature sortie d’une salle est ramenée à sa dernière position intérieure valide. Sans intérieur valide, elle est supprimée. Les cibles extérieures sont ignorées et Ghost Girl abandonne une victime sortie dehors.
- De petits postes de récupération couverts peuvent se générer dans les biomes Hina Land : coffre avec les objets MirRP et deux créatures Lethal. Ce sont des structures simples générées par une feature, pas des complexes industriels complets ni une reproduction des lunes.
- Bracken recule devant un regard bref ; un regard prolongé le rend agressif. Coil-Head se fige lorsqu’il est regardé avec visibilité. Hoarding Bug ramasse les objets au sol, garde son butin dans les sauvegardes et le rend à sa mort ; il s’énerve en cas d’attaque ou de proximité pendant qu’il transporte du butin. Bunker Spider pose des toiles si `mobGriefing` le permet. Nutcracker détecte les changements de position et tire cinq projectiles par salve avec deux coups avant recharge. Barber bondit et son rendu est masqué à grande distance. Ghost Girl conserve une victime synchronisée et n’est rendue que pour celle-ci.
- Les dégâts, temporisations et limites restent adaptés à Minecraft. Les IA ne sont pas des copies exactes du code du jeu. Ghost Girl peut normalement sortir dans Lethal Company ; sa restriction ici est volontaire et demandée par l’utilisateur.
- Pas encore de quota de vente, de vaisseau, de cycle de lunes, de transport de corps ni de transport de coffres par le Hoarding Bug.

## Références consultées

- https://www.mariowiki.com/Minecraft — correspondances des textures Goomba, Koopa Troopa, Dry Bones et Pokey.
- https://deltarune.wiki/w/Rudinn et https://deltarune.wiki/w/Hathy — noms, sprites et attaques en diamants/cœurs.
- https://deltarune.wiki/images/Rudinn_battle.gif et https://deltarune.wiki/images/Hathy_battle.gif — sprites utilisés.
- https://omori.wiki/Forest_Bunny — référence du lapin ennemi.
- https://en.wikipedia.org/wiki/Chao_(Sonic_the_Hedgehog) — redirection vers la liste des personnages Sonic, section Omochao.
- https://lethal.miraheze.org/wiki/Bracken
- https://lethal.miraheze.org/wiki/Coil-Head
- https://lethal.miraheze.org/wiki/Hoarding_Bug
- https://lethal.miraheze.org/wiki/Bunker_Spider
- https://lethal.miraheze.org/wiki/Ghost_Girl
- https://lethal.miraheze.org/wiki/Nutcracker
- https://lethal.miraheze.org/wiki/Barber

Les sites Fandom et certaines pages Sonic n’étaient pas accessibles dans l’environnement ; leurs contenus n’ont pas été présentés comme vérifiés.

## Installation

Remplacer le précédent JAR Hina Land, sans garder plusieurs versions. Java 17, Forge 1.20.1/47.3.0. JAR seul : ajouter GeckoLib 4.4.9 et TerraBlender 3.0.1.7. Pack : copier `mods`, `config` et `resourcepacks`, et activer le petit resourcepack d’intégration fourni pour les particules des autres mods. **Ne pas activer globalement les cinq gros packs à la fois** : les ressources choisies sont déjà incorporées dans le JAR.

Créer un monde neuf ou explorer de nouveaux chunks pour les fleurs, postes de récupération et DELTARUNE. Les chunks déjà générés ne sont pas convertis. Les œufs Lethal doivent être utilisés dans une salle couverte conforme à la règle ci-dessus.

## Limites conservées

Lunaria Media 2.0.2 manque toujours au pack ; trois succès de Hina Land Quest restent bloqués. Les chapitres FTB se chargent, mais une campagne complète n’est pas testée et le mod de quêtes fourni peut ajouter à nouveau ses chapitres au démarrage. Les mécanismes de tous les autres mods personnels ne sont pas certifiés par ces tests. Pas d’écoute audio humaine dans le cloud.

## Résultats des contrôles

- Build Gradle et reobfuscation réussis. **22 GameTests Forge exécutés et réussis**, y compris les contrôles historiques et les nouvelles règles d’intérieur, Ghost Girl, récupération de Skelerex, carapace Koopa, projectiles et apaisement DELTARUNE, fleurs et interaction Omochao.
- **856 JSON**, **18 modèles** et leurs références d’animations analysés ; références de textures et présence dans l’atlas vérifiées. Les métadonnées des deux fleurs Mario animées sont conservées.
- Monde de production, graine 20261011 : **16 sites naturels contrôlés**, tous avec roche et bedrock thématiques sous Y=0. Les quatre forêts de contrôle contiennent troncs et feuilles, les quatre dunes sable et grès. Le premier point de forêt DELTARUNE était sous l’eau ; le contrôle des arbres a utilisé la rive voisine, toujours dans le biome forêt, sans modifier la génération.
- **Les 12 fleurs sont toutes présentes réellement dans les chunks sauvegardés**, confirmées par décodage des palettes, pas seulement par l’existence de fichiers ou de noms dans les palettes.
- **9 coffres de postes Lethal générés naturellement** identifiés dans les chunks sauvegardés, avec la table de butin `hinaland:chests/lethal_facility`. La commande de butin a aussi été exécutée sur cette table en production.
- Client et serveur Minecraft Forge de production chargés avec les **22 JAR du pack**. Captures du paysage DELTARUNE, de ses fleurs, des sprites Rudinn/Hathy, du modèle Omochao, des objets MirRP, des états de carapace/effondrement et des monstres dans une salle générée. Les présentations de modèles utilisaient des entités avec `NoAI` pour isoler le rendu ; elles ne constituent pas une validation de tous les cycles d’IA. Les tests mécaniques sont les GameTests séparés.
- Les premières vérifications ont détecté puis corrigé une erreur de type Java, deux fixtures de test prétendument extérieures qui étaient encore sous le terrain, des textures situées hors de l’atlas par défaut et les métadonnées manquantes des fleurs animées. Ces contrôles ont été relancés après correction ; aucun de ces premiers échecs n’est présenté comme un test réussi.
- Le chargement forcé de seize sites éloignés a provoqué une pause de serveur d’environ 81 secondes et une tentative de connexion a expiré pendant ce chargement. La connexion a réussi une fois cette opération terminée. Cela ne valide pas les performances d’une longue exploration, ni un serveur multijoueur chargé.
- Les cinq musiques et le ciel OMORI restent ceux validés en 0.9.0 ; aucune nouvelle écoute humaine réalisée ici. Les requêtes Mojang indisponibles dans le test hors ligne et les trois succès Lunaria manquants restent visibles dans les logs.

Une campagne complète de Survie, tous les clips d’animation possibles, tous les comportements multijoueurs et la totalité des reskins contenus dans les packs restent à tester ou à développer. Les rapports bruts, fichiers de comptage et captures sont inclus dans `audit/packs-0.10`.
