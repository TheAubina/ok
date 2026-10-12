# Hina Land — bêta 0.15.0 / 70 nouvelles constructions

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. Le JAR est compilé et réobfusqué avec Gradle 8.8. GeckoLib 4.4.9 et TerraBlender 3.0.1.7 sont requis pour le JAR seul et inclus dans le modpack de test 9.

## Contenu ajouté

**Dix constructions nouvelles par chacun des sept univers de l’Overworld : 70 ajouts, en plus des 21 modèles naturels de la version 0.14, soit 91 constructions sélectionnables naturellement.** Les anciennes constructions, les sept portails complets et les deux entrées Lethal ne sont pas comptés dans ce minimum de dix.

| Univers | Nouveautés | Dont petits donjons | Exemples d’inspiration |
|---|---:|---:|---|
| Mario | 10 | 2 | Maison de Toad, jardin royal, Royaume Végésia, place Delfino, pyramide des sables |
| Sonic | 10 | 2 | Green Hill, atelier de Tails, Chemical Plant, Hydrocity, Death Egg |
| OMORI | 10 | 2 | Basil, Neighbor’s Room, Otherworld, château de Sweetheart, Deeper Well |
| DELTARUNE | 10 | 2 | Castle Town, Card Castle, Spamton, Cyber City, manoir de Queen |
| Genshin | 10 | 2 | Mondstadt, Domaine de l’Aurore, Wangshu, Inazuma, Fontaine |
| Overwatch | 10 | 2 | Gibraltar, Hanamura, King’s Row, Route 66, Ilios, Volskaya |
| Lethal | 10 | **0** | Navette, Assurance, Vow, Experimentation, Rend, Titan, quai de la Compagnie |

Le [catalogue complet](CATALOGUE_STRUCTURES_0.15_FR.md) donne les 70 noms et leurs inspirations. Ce sont des réinterprétations compactes, pas des conversions exactes des cartes officielles. Le catalogue utilise 52 programmes architecturaux nommés ; certains principes sont réutilisés entre univers, avec leurs palettes, mobilier et détails. Les bâtiments utilisent les blocs thématiques existants et des blocs Minecraft lorsque le type nécessaire n’existe pas dans le mod.

Chaque ajout possède un coffre avec des ressources de son univers, du ravitaillement ou des torches. Les donjons ont un second tirage de récompense, avec des ressources de niveau supérieur plus rares. Les dix constructions Mario contiennent chacune deux vrais blocs « ? », utilisant le fonctionnement testé de 0.14.

Les **douze donjons** sont de petits bâtiments de surface avec des espaces reliés et un générateur d’ennemis. Leur générateur produit un ennemi par tentative, avec une limite locale de trois entités proches et un délai de 12 à 24 secondes après apparition. Cette limite n’est pas un plafond global : les ennemis peuvent quitter sa zone. Les Mario/Sonic/OMORI/DELTARUNE emploient les créatures Hina existantes ; Genshin et Overwatch utilisent respectivement zombies et squelettes Minecraft. Aucun nouveau Hilichurl ou robot omniaque n’est annoncé.

Les dix ajouts Lethal sont des installations extérieures sans donjon ni générateur de monstre extérieur. L’intérieur spécial et les portes March/Offense existants sont conservés. Les navettes, boutiques et monuments restent des décors explorables avec butin : pas encore de pilotage, de vendeurs, de gravité spéciale pour les boucles Sonic, de boss ou de mission scénarisée.

## Placement et corrections

Les sept familles conservent une grille commune : **espacement 48 chunks, séparation 24, fréquence 0,65, sel partagé**. Ajouter 70 choix ne crée pas 70 grilles indépendantes et n’augmente pas la densité totale configurée. Les donjons ont un poids inférieur à celui des nouveaux monuments. Les nouvelles empreintes sont limitées à 11 × 11 blocs, avec des bases aux coins coupés plutôt que de grandes plateformes carrées.

Le générateur vérifie chaque colonne du terrain, l’absence de liquide, l’éligibilité du biome, une différence maximale de quatre blocs et le soutien des fondations. Les ajouts se placent dans les variantes plaines/forêts de leur famille. Certaines fondations restent visibles sur une pente ; la vérification porte sur leur soutien, pas sur leur disparition esthétique complète.

Le contrôle en production a permis de corriger des lanternes intérieures sans fixation : elles sont maintenant suspendues au plafond. Les fleurs ont leur sol plantable, les échelles leur mur, et les rails leur appui. Les canaux de Hydrocity et Vow disposent de bordures complètes ; leur eau a été soumise aux mises à jour réelles du moteur de fluides.

## Vérifications effectuées

- **49 GameTests Forge exécutés et réussis**, avec le message explicite `All 49 required tests passed`, puis `BUILD SUCCESSFUL`. Le JAR de production exclut les classes de test et leur modèle vide.
- Les **70 nouveaux modèles ont été placés dans les quatre rotations**, soit 280 placements : enregistrement réel, codecs de terrain, tenue des blocs décoratifs, coffre ouvrable sans plafond bloquant, chemin praticable jusqu’à sa proximité et résolution du butin par le serveur.
- Les **douze générateurs de donjon ont réellement créé leur espèce configurée** dans les tests, auprès d’un joueur de test Forge. Leurs règles explicites permettent ces rencontres intérieures sans appliquer le filtre réservé aux apparitions naturelles en surface. Les ajouts Lethal sont vérifiés sans générateur.
- Fontaine et deux canaux : des mises à jour réelles des fluides confirment l’absence d’écoulement hors de leur enceinte. Les 40 tests précédents restent dans la suite : biomes, minerais/équipement, blocs Mario, portails et comportements Lethal.
- **3 053 JSON** et 18 modèles/hiérarchies d’animation contrôlés ; les 42 couches d’armure et neuf animations de sprites restent valides.
- Serveur et client de production démarrés avec **22 mods**, JAR final identique à celui livré. Nouveau monde Normal, difficulté Normal, graine **20261015**.
- **Huit constructions nouvelles générées naturellement**, couvrant les sept univers : porte royale Mario, refuge Sonic, camp OMORI, carrefour DELTARUNE, camp Genshin, clocher Overwatch, quai Lethal et pyramide Mario. Les chunks FULL enregistrés contiennent les blocs visibles attendus et **872 colonnes de fondation soutenues**. Les deux couches rocheuses enterrées peuvent recevoir les minerais/graviers de l’étape de décoration suivante ; ces substitutions solides sont consignées dans le contrôle.
- Les huit exemples naturels ont été affichés et examinés dans le client. Le ciel violet étoilé OMORI est également visible sur la capture du camp.
- Pyramide naturelle Mario : origine **`-7432 62 5544`**, générateur **`-7435 65 5537`**. Aucun Goomba proche avant l’arrivée en Survie ; ils apparaissent ensuite, poursuivent et poussent le joueur. **Coffre ouvert au clic dans le client** en `-7439 65 5537`, avec ambre Fleur de Feu, bronze Super Clochette et torches enregistrés dans ses données. Des protections temporaires ont été utilisées pour l’observation, puis retirées : ce contrôle ne valide pas l’équilibrage d’un combat normal.
- Échantillon du générateur réel : **16 641 points**, les 28 biomes Hina et aucun identifiant de biome vanilla dans l’Overworld Normal de test.

Le modpack contient les journaux, manifeste des 70 ajouts, vérification des chunks, captures et compte rendu des interactions dans `audit/0.15`. Les sources comprennent les générateurs et les données déjà produites ; compiler le mod ne nécessite pas de réimporter les grosses archives d’origine.

## Installation et limites

Remplacer le précédent JAR Hina Land dans `mods`, avec ses dépendances, ou installer le modpack de test 9 dans une instance Forge dédiée. Ne pas conserver deux versions de Hina Land. Activer le pack d’intégration fourni si utilisé.

**Les nouvelles constructions apparaissent dans de nouveaux chunks.** Les anciens bâtiments, lanternes et ruines enregistrés ne sont pas reconstruits automatiquement. Conserver une sauvegarde avant la mise à jour. La copie Normal 0.13 ouverte avec 0.14 était contrôlée dans la session précédente ; cette session utilise un nouveau monde Normal pour 0.15, sans revendiquer une nouvelle validation exhaustive des migrations.

Pour une recherche en tant qu’opérateur : `/locate structure #hinaland:mario_new_landmarks`, avec `sonic`, `omori`, `deltarune`, `genshin`, `overwatch` ou `lethal`. Les tags ne contiennent que les dix nouveaux modèles de la famille. Une recherche peut bloquer le tick serveur pendant plusieurs secondes ; ce coût concerne la commande de recherche, pas un test de performance de l’exploration normale.

Les 70 modèles sont testés par placement, **huit seulement ont été parcourus en génération naturelle sur cette graine**. L’ensemble des 70 n’a pas été parcouru naturellement sur plusieurs graines ; l’équilibrage prolongé, les performances d’un grand serveur et le multijoueur simultané restent à vérifier. Ces ajouts couvrent les sept univers de l’Overworld, pas dix nouvelles structures pour le Nether ou un End custom encore non implémenté.

Les limitations précédentes restent indiquées dans [le rapport 0.14](RAPPORT_PEAUFINAGE_0.14_FR.md) : fidélité officielle de deux robots Sonic encore partielle, audio non écoutable avec le périphérique nul, transport des coffres pleins et missions Lethal à terminer. Lunaria Media manque au pack fourni et son compagnon de quêtes peut dupliquer ses chapitres au redémarrage. Le pack distribué reprend des configurations propres, pas celles du serveur de tests redémarré plusieurs fois.
