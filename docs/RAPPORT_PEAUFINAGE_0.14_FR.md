# Hina Land — bêta 0.14.0

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. GeckoLib 4.4.9 et TerraBlender 3.0.1.7 sont nécessaires au JAR seul et inclus dans le modpack. Le projet est compilé avec Gradle 8.8 et le JAR est réobfusqué pour une installation dans `mods`.

## Trois minerais supplémentaires par univers

Les 14 ressources précédentes restent disponibles. Cette version ajoute **21 minerais et ressources, 21 blocs de stockage, 21 pioches, 21 épées, 21 haches et 21 ensembles d’armure complets (84 pièces)**. Chaque matériau possède ses recettes de fabrication, réparation, compression/décompression et cuisson. Il y a **231 nouvelles recettes minérales**, plus deux recettes Mario.

| Univers de l’Overworld | Niveau 1 | Niveau 2 | Niveau 3 |
|---|---|---|---|
| Mario | Bronze Super Clochette | Ambre Fleur de Feu | Grande étoilite |
| Sonic | Or des anneaux | Émeraude Sol | Cristal Anneau Rouge |
| OMORI | Quartz du pique-nique | Jade pastèque | Opale de Headspace |
| DELTARUNE | Éclat lumineux | Mithril des Ténèbres | Lazuli Pipis |
| Genshin | Fer blanc | Argent étoilé | Cristal de condensence |
| Overwatch | Acier omniaque | Cobalt Helix | Alliage Graviton |
| Lethal | Acier de récupération | Quartz de Vow | Alliage de Titan |

Ces noms forment une progression Hina Land inspirée des univers : ils ne prétendent pas tous désigner des minerais canoniques des jeux d’origine. Les familles concernées sont les **sept univers actuellement générés**, pas les univers supplémentaires encore dans la feuille de route.

| Statistique | Niveau 1 | Niveau 2 | Niveau 3 |
|---|---:|---:|---:|
| Durabilité des outils | 480 | 1 100 | 1 900 |
| Vitesse de minage | 6 | 8 | 9 |
| Dégâts totaux de l’épée, attribut de base du joueur compris | 6 | 7 | 8 |
| Protection totale de l’armure | 15 | 20 | 20 |
| Robustesse par pièce | 0 | 1 | 2 |
| Résistance au recul par pièce | 0 | 0 | 0,05 |
| Multiplicateur de durabilité de l’armure | 18 | 27 | 35 |
| Hauteurs d’apparition des veines | -32 à 80 | -48 à 32 | -60 à 0 |
| Tentatives de veines / chunk | 6 | 4 | 2 |

Le premier niveau ne récolte pas l’obsidienne, les deux suivants le permettent. Les minerais exigent au minimum une pioche en fer et fonctionnent avec Toucher de soie et les tables de butin minérales. Les tiers vanilla fer/diamant restent valides. Chaque équipement se répare avec son propre matériau.

Les textures sont copiées depuis les packs fournis, avec des textures Minecraft explicites lorsque le pack n’a pas la ressource. Les armures Mario, OMORI et DELTARUNE utilisent des textures fournies ; les chemins d’armure du pack DELTARUNE récent sont convertis vers ceux de 1.20.1. D’autres tenues reprennent des textures vanilla. Ce sont des réutilisations, pas 21 nouveaux dessins originaux d’armure. **42 couches d’armure** ont été contrôlées et **neuf animations de sprites** conservent leurs métadonnées.

## Blocs Mario et constructions

Le **bloc « ? »** se déclenche au clic droit, à la frappe, ou en sautant pour le toucher avec la tête. Le serveur remplace le bloc avant de produire une seule récompense : pièces Mario, Super Champignon ou bronze Super Clochette. Un bloc épuisé ne se recharge pas en le cassant/replaçant. Les récompenses tombent sous le bloc pour être récupérables depuis le sol.

- Fabrication : huit lingots d’or autour d’un coffre.
- Quatre pièces Mario s’échangent contre un lingot d’or.
- Le Super Champignon rend six points de nourriture et donne deux cœurs d’absorption pendant 600 ticks, soit 30 secondes à 20 ticks/s. Il peut être mangé avec la barre de faim pleine. Il ne change pas la taille physique du joueur.
- Le symbole « ? » est construit en relief sur quatre faces, avec la texture Mario fournie ; une illustration générée pendant la recherche n’est pas requise par le mod.

**Onze constructions nouvelles** rejoignent les dix constructions naturelles précédentes : un jardin bonus Mario avec trois blocs interactifs, un sanctuaire d’anneau Sonic, un pique-nique OMORI, une cour échiquier DELTARUNE, et un portail du Nether thématique pour chacun des sept univers. Les fleurs du pique-nique reposent sur du véritable sol plantable.

Les constructions partagent sept grilles par famille : espacement 48 chunks, séparation 24, fréquence 0,65, même sel de placement. Elles utilisent le contrôle de terrain sec, pente maximale de quatre blocs et fondations de la version précédente. Les constructions n’apparaissent que dans les plaines/forêts de leur famille. Les blocs « ? » suspendus au-dessus du jardin sont intentionnels.

Les sept nouveaux portails sont **complets et déjà allumés**, avec un cadre vanilla d’obsidienne 4×5 et six blocs de portail. Les 28 biomes Hina ne sont pas éligibles aux structures vanilla de portail en ruine. **Les ruines déjà enregistrées dans d’anciens chunks ne sont pas reconstruites automatiquement.** Les portails complets et les nouveaux minerais apparaissent dans les nouvelles zones générées.

## Modèles et références

Les 18 créatures existantes ont été auditées et affichées dans le client. Les adaptations restent volontairement cubiques ; elles ne constituent pas des copies exactes des modèles officiels.

| Créature | Peaufinage / contrôle |
|---|---|
| Goomba | Large tête, petit corps et deux pieds ; correction du visage transparent et UV du visage fourni. |
| Koopa Troopa | Posture bipède, bras, ventre et carapace distincts ; pose de carapace compacte reposant au sol. |
| Dry Bones / Skelerex | Proportions de Koopa squelettique, museau et carapace ; effondrement posé au sol. |
| Pokey | Segments de cactus et pointes, suppression des quatre pattes de Creeper. Variante verte du pack conservée. |
| Sprout Mole | Corps compact, deux pieds, tige et feuilles vertes, visage lisible aux yeux bruns. |
| Forest Bunny | Oreilles plus longues et animation alternée des pattes. Texture brune du pack conservée. |
| Moto Bug | Ancien modèle rouge sommaire remplacé par carapace, visage métallique, antennes et roue unique animée. |
| Buzz Bomber | Ancien modèle bleu sommaire remplacé par abdomen rayé, yeux, antennes, ailes battantes et canon. |
| Rudinn | Sprite conservé, proportion largeur/hauteur corrigée. |
| Hathy | Sprite conservé, proportion largeur/hauteur corrigée. |
| Omochao | Géométrie native déjà convertie du pack, hélice et clé conservées, affichage contrôlé. |
| Bracken | Échelle 0,88 pour rapprocher la géométrie de sa hauteur de collision ; animations conservées. |
| Coil-Head | Échelle 0,78, tête et ressort contrôlés ; gel sous le regard conservé. |
| Hoarding Bug | Échelle 0,40 pour corriger l’ancien modèle disproportionné ; antennes et animations conservées. |
| Barber | Échelle 0,74, ciseaux et silhouette contrôlés ; visibilité limitée à proximité conservée. |
| Bunker Spider | Échelle 0,63, corps et pattes contrôlés ; toiles et attaques conservées. |
| Ghost Girl | Échelle 0,76 ; robe rouge à pois contrôlée avec le joueur désigné comme victime. |
| Nutcracker | Échelle 0,65 ; tenue, fusil et animations conservés. |

Références effectivement consultées : rendus de jeux Mario hébergés sur [Mario Wiki](https://www.mariowiki.com/Goomba), [Koopa Troopa](https://www.mariowiki.com/Koopa_Troopa), [Dry Bones](https://www.mariowiki.com/Dry_Bones), [Pokey](https://www.mariowiki.com/Pokey) ; [Omochao sur le site officiel SEGA](https://sonic.sega.jp/SonicChannel/character/omochao.html) ; [Sprout Mole dans la boutique officielle OMOCAT](https://www.omocat-shop.com/products/sprout-mole-plush) ; [Forest Bunny](https://omori.wiki/Forest_Bunny), sprites [Rudinn](https://deltarune.wiki/w/Rudinn) / [Hathy](https://deltarune.wiki/w/Hathy) et rendus des sept espèces sur le wiki Lethal Company. Les wikis sont des hébergeurs communautaires, pas des sites officiels des éditeurs. La référence Sprout Mole est une peluche officielle, pas une capture de combat.

Des pages éditeurs OMORI, DELTARUNE et Lethal/Steam et des captures Sonic officielles ont également été récupérées. **La comparaison visuelle directe de Moto Bug et Buzz Bomber à une image officielle identifiée reste incomplète** : les pages de référence dédiées ont refusé l’accès. Les captures Steam récupérées n’ont pas été utilisées pour identifier arbitrairement un autre ennemi comme l’un de ces deux robots. Leur nouveau rendu Minecraft a bien été contrôlé ; leur fidélité précise reste à confirmer. Les 16 autres références permettent une comparaison de silhouette/couleurs, sans garantir une reproduction exacte. Forest Bunny garde notamment la variante de couleur du pack fourni.

## Vérifications réalisées

- **40 GameTests Forge réellement exécutés et réussis**, compilation Gradle terminée avec succès et JAR réobfusqué. Les vérifications de la version précédente restent dans cette suite.
- Les 231 recettes minérales ont été vérifiées avec de vraies grilles ou recettes de cuisson : résultats, compression/décompression, armures et outils. Réparation, protection, robustesse, récolte et préservation des tiers vanilla contrôlées.
- Les 21 minerais ont été trouvés dans **63 chunks FULL générés naturellement**, sur sept sites de la graine 20261014. Les chunks proches d’une limite de biome peuvent contenir plusieurs familles ; les placements sont contrôlés par biome.
- Les 28 formes/orientations des sept portails ont été reconnues complètes par le code vanilla de portail dans les GameTests.
- Client et serveur Forge de production avec **22 JAR** : modèles des 18 créatures, ensembles d’armure, nouvelles textures, états effondré/carapace et nouvelles petites constructions affichés. Le pique-nique OMORI a été replacé pour vérifier que ses quatre fleurs restent présentes sur le sol corrigé.
- Jardin Mario **naturel** : graine 20261014, origine `-7640 59 920`, terrain/fondations visibles, clic droit d’un bloc et saut sous un autre donnant chacun une récompense, avec remplacement par un bloc épuisé. Un Super Champignon a aussi été mangé dans le client : effet d’absorption observé dans les données serveur.
- Portail Mario **naturel** : origine `-9896 82 1032`. Passage réel par le portail en mode Survie vers `minecraft:the_nether`, puis retour par le portail de destination vers le portail initial. Arrivée Nether contrôlée sur terrain sec. Les trois autres nouveaux petits modèles Sonic/OMORI/DELTARUNE ont été placés manuellement pour le contrôle visuel ; leur génération naturelle sur plusieurs sites n’a pas été parcourue.
- Copie du monde de test **0.13** : ouverture avec 0.14, porte Lethal existante conservée, 28 biomes Hina toujours échantillonnés, puis apparition des trois nouveaux minerais OMORI dans **neuf chunks nouveaux** à proximité de `10000 10000`. Le monde 0.13 original n’a pas été modifié.
- **2 893 JSON**, 18 modèles et leurs hiérarchies d’animation, 42 textures d’armure et neuf animations de sprites contrôlés. Les deux dernières poses Mario ont été vérifiées avec des surcharges temporaires de ressources exactement identiques aux fichiers du JAR final ; ce pack de contrôle n’est pas distribué. Code serveur et données du JAR final identiques à ceux du dernier contrôle de production.

Les preuves, journaux et empreintes de ressources sont dans `audit` du modpack et les manifestes des sources. Les anciennes vérifications Nether/ciel OMORI/musiques/structures Lethal restent documentées dans les rapports précédents ; cette session ne répète pas tous leurs parcours.

## Installation et limites

Remplacer l’ancien JAR Hina Land dans `mods` ; ne pas installer deux versions simultanément. Copier les dépendances, ou utiliser le modpack de test 8 dans une instance Forge dédiée. Activer son petit pack d’intégration.

Une **copie de sauvegarde Normal 0.13** a été testée : les nouveaux minerais et constructions nécessitent de découvrir de nouveaux chunks. Conserver une sauvegarde avant toute mise à jour. Pour les mondes antérieurs à 0.13, le passage au générateur exclusivement Hina n’est pas validé : un nouveau monde Normal reste la solution contrôlée. Les types Plat/Grands biomes ne sont pas validés.

L’équilibrage sur une longue partie, plusieurs graines et des joueurs simultanés n’a pas été validé. Les ennemis thématiques restent hostiles en journée ; un joueur de test non protégé a été tué par un Koopa pendant le contrôle du jardin. Les essais de rendu et certains parcours utilisent des commandes, le mode Créatif/Spectateur ou une résistance pour isoler l’interaction testée. Ce ne sont pas des preuves d’équilibrage de survie.

L’audio utilise un périphérique OpenAL nul dans cet environnement : l’écoute des musiques ne peut pas être validée ici. La fidélité visuelle directe des deux robots Sonic reste partielle. Certaines textures d’équipement restent vanilla ; les anciens modèles de structures désactivés pour la génération naturelle n’ont pas tous été redessinés.

Le transport de coffres pleins par le Hoarding Bug, l’End entièrement custom, les quotas/navette/missions Lethal et le reste de la campagne ne sont toujours pas implémentés. Les sept monstres Hina Lethal gardent leur restriction aux intérieurs ; cette assertion ne concerne pas automatiquement tous les mobs de mods externes.

Lunaria Media manque dans le pack actuel : trois succès du compagnon de quêtes référencent des objets indisponibles. Le compagnon fourni continue de dupliquer des chapitres lors de ses redémarrages. Les configurations propres sont livrées, pas les configurations multipliées par les nombreux redémarrages de test.
