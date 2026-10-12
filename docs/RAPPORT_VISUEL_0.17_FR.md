# Hina Land — bêta 0.17.0 : textures, ciels et accès Lethal

Minecraft Java 1.20.1, Forge 47.3.0, Java 17. Ce rapport distingue les contrôles automatisés, les interactions réelles et les limites artistiques.

## Ce qui change

- 21 créatures voxel reçoivent un atlas de matériaux plus propre : tissus lisses, métal, fourrure et cristaux. Leur géométrie et leurs animations restent des adaptations simples. Les sept modèles Lethal et les sprites originaux OMORI/DELTARUNE sont préservés.
- 35 modèles de blocs utilisent de nouvelles textures : 28 minerais/blocs de stockage antérieurs, autel, deux blocs bonus Mario et quatre blocs du hall. 24 icônes de matériaux sont remplacées par des images transparentes. Les ressources authentiques d’armures et de sprites sont conservées ; 122 fichiers originaux ont été comparés octet par octet.
- Les 28 biomes Hina de l’Overworld sélectionnent 25 profils de ciel. Mario distingue World 1, World 5, World 6 et World 2 ; Sonic Green Hill, Angel Island, Ice Cap et Sandopolis. Les autres familles possèdent leurs variantes. Les quatre biomes OMORI gardent le même ciel violet étoilé original. Voir CATALOGUE_CIELS_0.17_FR.md pour chaque référence.
- Les nouveaux panoramas sont des illustrations originales inspirées des jeux. Le rendu cylindrique répète alternativement les motifs en miroir ; il ne reproduit pas des skyboxes officielles complètes à 360°. Transition d’environ deux secondes, atténuation nocturne, soleil, phases lunaires, étoiles et teinte de brouillard. Le Nether et les dimensions séparées gardent leur ciel précédent.
- Les portes March et Offense arrivent dans un hall éclairé, avec une sortie visible et une jonction vers les vrais couloirs de la carte Lethal fournie. La sortie conserve la position extérieure de chaque joueur.

## Vérifications réalisées

- Compilation Gradle de production réussie ; JAR Forge reobfusqué, classes Java 17 et ressources incluses. Les classes de test sont exclues du JAR distribué.
- 62 GameTests Forge réussis. Les trois nouveaux vérifient les profils des 28 biomes, les collisions et le chemin hall/couloir/sortie, et la migration unique d’un ancien intérieur avec préservation d’un coffre extérieur.
- Contrôle de 3 202 JSON et des hiérarchies de 50 modèles/animations ; UV des quatre atlas, transparence des icônes et conservation des 122 fichiers originaux vérifiés.
- Client et serveur réels avec les 23 mods, sur une copie d’une sauvegarde contenant l’intérieur Lethal ancien. Entrée par March et par Offense, retour à leurs positions extérieures respectives, déplacement à pied en mode Aventure jusqu’au couloir situé au-delà de la zone modifiée : vérifiés. Les captures et les journaux sont inclus dans audit/0.17 du modpack.
- Migration : les 400 316 états de blocs situés hors du petit hall et des deux cellules de l’ancienne porte sont identiques avant/après (SHA-256 1dc6c8978c6aef975e234f3f6dab415e6d077a1eda69ed8038d60aa5ff67637f). Le reste de la carte n’a pas été reconstruit.
- Captures du JAR final pour les 28 biomes sur une plateforme de contrôle, dont les quatre variantes OMORI, et un ciel Mario de nuit. Il s’agit de changements de biomes commandés pour tester le rendu, pas d’une exploration naturelle de tous les biomes.
- Les GameTests ont été exécutés avant les derniers réglages exclusivement graphiques du panorama ; la compilation et les contrôles client portent sur le JAR final.

## Mise à jour et limites

Remplacer l’ancien hinaland-*.jar et conserver une seule version. Le JAR seul nécessite GeckoLib 4.4.9 et TerraBlender 3.0.1.7 ; le modpack inclut ces dépendances et Lunaria Media 2.1.0 inchangé. Sauvegarder les mondes avant mise à jour.

L’ancien intérieur reçoit une seule fois une modification bornée : x64..78, y68..73, z35..43, plus l’ancienne porte. Une construction personnelle située dans cette zone peut être remplacée lors de cette première migration. Les modifications suivantes du hall ne sont pas écrasées automatiquement.

La comparaison visuelle officielle reste partielle, notamment Black Forest et certaines références Sonic. Les textures améliorées ne rendent pas les modèles voxel identiques aux modèles des jeux. Toutes les espèces n’ont pas été réinspectées individuellement sous tous les éclairages de cette livraison. L’équilibrage prolongé, le jeu multijoueur simultané et les transitions sur toutes les configurations graphiques restent à tester. Le logiciel graphique de test utilise un rendu logiciel et un périphérique audio muet : aucune validation audible des musiques ou de Lunaria.

Le compagnon de quêtes peut encore dupliquer les chapitres au redémarrage. Les configurations distribuées sont propres. L’End complet, le portage de coffres remplis et la boucle complète Lethal restent à développer. Les fonctionnalités des versions précédentes sont conservées ; cette livraison ne prétend pas les compléter toutes.
