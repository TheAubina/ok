# Hina Land — bêta 0.14.0

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17

**[Télécharger le JAR compilé](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/hinaland-0.14.0.jar)** · **[Modpack de test 8 — 22 JAR](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.14.0-modpack-test-8.zip)** · [Sources compilables](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.14.0-sources.zip)

Cette version ajoute **trois minerais supplémentaires par chacun des sept univers**, leurs blocs de stockage et trois niveaux d’équipement : 21 pioches, 21 épées, 21 haches et 84 pièces d’armure. Les 14 minerais précédents restent présents. 231 nouvelles recettes minérales accompagnent cette progression. Les textures fournies sont réutilisées, notamment les tenues Mario, OMORI et DELTARUNE ; certaines autres tenues utilisent des textures Minecraft.

Les **blocs « ? » Mario fonctionnent** au clic, à la frappe ou lors d’un saut sous le bloc. Ils donnent une récompense unique et deviennent épuisés. Les pièces peuvent s’échanger ; le Super Champignon nourrit et donne une absorption temporaire. Le jardin bonus Mario, le sanctuaire d’anneau Sonic, le pique-nique OMORI et la cour échiquier DELTARUNE rejoignent les constructions existantes. Sept nouveaux portails du Nether thématiques possèdent un cadre d’obsidienne **complet et déjà allumé**. Les anciennes ruines enregistrées dans un monde ne sont pas réparées automatiquement.

Les modèles et proportions des 18 créatures ont été repris ou contrôlés, avec des silhouettes Mario plus reconnaissables, de nouveaux modèles pour les deux robots Sonic, une géométrie compacte pour le Sprout Mole, des sprites DELTARUNE correctement proportionnés et des échelles Lethal ajustées. Les animations et comportements existants restent présents. La comparaison directe à des images officielles identifiées reste incomplète pour Moto Bug et Buzz Bomber ; les adaptations cubiques ne sont pas des reproductions exactes.

## Installation

Remplacer l’ancien JAR Hina Land dans `mods`. Le JAR seul nécessite **GeckoLib 4.4.9 et TerraBlender 3.0.1.7** ; le modpack les inclut. Copier ses `mods`, `config` et `resourcepacks` dans une instance dédiée et activer le pack d’intégration.

Une **copie de sauvegarde Normal 0.13** a été testée avec la mise à jour. Conserver une sauvegarde et explorer de **nouveaux chunks** pour les nouveaux minerais et constructions. Pour les versions antérieures, le nouveau monde Normal reste la solution contrôlée ; les anciens générateurs ne sont pas migrés automatiquement.

## Vérification

**40 GameTests Forge réussis**, compilation Gradle et JAR réobfusqué. Les recettes, réparations, protections, tiers de minage, récompenses uniques et cadres de portail dans leurs quatre orientations sont contrôlés. Les 21 minerais supplémentaires sont présents dans **63 chunks réellement générés** sur sept sites. 2 893 JSON, 18 modèles/animations, 42 couches d’armure et neuf animations de sprites ont été vérifiés.

Client et serveur avec les 22 mods : créatures et équipements affichés, clic et saut sous les blocs du jardin Mario naturel, consommation du Super Champignon, puis **aller-retour réel par un portail naturel** entre Overworld et Nether. Une copie du monde 0.13 conserve sa porte Lethal et génère les trois nouveaux minerais OMORI dans neuf nouveaux chunks.

L’Overworld Normal conserve ses 28 biomes Hina sans identifiant de biome vanilla ; le Nether conserve ses 63 biomes vanilla mélangés en petites parcelles et son niveau d’eau à Y=0. L’intérieur Lethal, les entrées March/Offense, les fleurs, musiques et ciel OMORI restent présents. Les rapports précédents précisent leurs vérifications.

L’équilibrage prolongé, plusieurs graines et le multijoueur simultané ne sont pas validés. L’écoute audio n’est pas vérifiable avec le périphérique nul de l’environnement. Le transport de coffres pleins, l’End custom et les missions complètes Lethal restent à développer. Lunaria Media manque et le compagnon de quêtes fourni peut dupliquer ses chapitres au redémarrage.

[Rapport détaillé](docs/RAPPORT_PEAUFINAGE_0.14_FR.md) · [Empreintes des fichiers](docs/SHA256SUMS-0.14.0.txt) · [Rapport précédent 0.13](docs/RAPPORT_GENERATION_LETHAL_0.13_FR.md)
