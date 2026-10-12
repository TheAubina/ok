# Hina Land — bêta 0.15.0

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17

**[Télécharger le JAR compilé](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/hinaland-0.15.0.jar)** · **[Modpack de test 9 — 22 mods](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.15.0-modpack-test-9.zip)** · [Sources compilables](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.15.0-sources.zip)

**70 nouvelles constructions : dix pour chacun des sept univers de l’Overworld**, en plus des 21 précédentes. Mario, Sonic, OMORI, DELTARUNE, Genshin, Overwatch et Lethal reçoivent maisons, ateliers, monuments et installations inspirés de lieux ou d’éléments identifiés des jeux. Ce sont des réinterprétations compactes pour Minecraft, pas des cartes officielles reproduites à l’identique.

**Douze petits donjons de surface**, deux par univers hors Lethal, possèdent un générateur d’ennemis limité et du butin. Les dix ajouts Lethal sont des extérieurs sans nouveau donjon ; ses portes March/Offense et son intérieur dédié restent présents. Chacun des 70 ajouts dispose d’un coffre thématique ; les dix ajouts Mario comprennent aussi des blocs « ? » fonctionnels.

Les 91 choix naturels utilisent la même grille espacée et le contrôle du terrain sec et des fondations. Il n’y a pas 70 grilles de placement supplémentaires. Les lanternes intérieures se fixent au plafond et les canaux disposent de bordures testées contre les écoulements.

[Catalogue des 70 constructions et de leurs inspirations](docs/CATALOGUE_STRUCTURES_0.15_FR.md) · [Rapport de vérification](docs/RAPPORT_STRUCTURES_0.15_FR.md) · [Empreintes des téléchargements](docs/SHA256SUMS-0.15.0.txt)

## Installation

Remplacer l’ancien JAR Hina Land dans `mods`. Le JAR seul nécessite **GeckoLib 4.4.9 et TerraBlender 3.0.1.7** ; le modpack les inclut. Copier ses `mods`, `config` et `resourcepacks` dans une instance dédiée et activer le pack d’intégration.

**Explorer de nouveaux chunks pour les nouvelles constructions.** Les bâtiments et ruines déjà enregistrés ne sont pas reconstruits. Conserver une sauvegarde avant mise à jour. La migration d’une copie Normal 0.13 vers 0.14 avait été contrôlée ; cette version teste ses ajouts dans un nouveau monde Normal. Les autres presets et migrations antérieures ne sont pas validés.

## Vérifications et limites

**49 GameTests Forge réussis**, compilation Gradle et JAR réobfusqué. Les 70 nouveaux modèles sont placés dans leurs quatre rotations, soit 280 placements : tenue des décors, chemin vers le coffre, ouverture possible et résolution du butin. Les douze générateurs produisent réellement leurs espèces configurées. Les mises à jour de fluides restent dans les fontaines/canaux testés.

Client et serveur avec les 22 mods : **huit nouvelles structures générées naturellement**, couvrant les sept univers et une pyramide Mario, vérifiées dans les chunks et affichées. 872 colonnes de fondation sont soutenues. Dans le donjon Mario naturel, les Goombas apparaissent et poursuivent le joueur ; son coffre s’ouvre dans le client avec les ressources prévues. Le joueur a bénéficié de protections temporaires pour ce contrôle, qui ne valide pas l’équilibrage du combat. 3 053 JSON, 18 modèles/animations, 42 couches d’armure et neuf animations de sprites ont été contrôlés.

Les 70 modèles n’ont pas tous été parcourus naturellement sur plusieurs graines. Les longs donjons souterrains, boss, vendeurs et missions scénarisées ne font pas partie de ces ajouts. Les ennemis des donjons Genshin/Overwatch sont des zombies/squelettes Minecraft ; aucun nouveau Hilichurl ou robot omniaque n’est annoncé.

Les fonctionnalités 0.14 restent présentes : 21 minerais supplémentaires et leurs équipements, blocs « ? » avec récompense unique, sept portails Nether complets, modèles et poses améliorés. L’Overworld Normal conserve ses 28 biomes Hina sans biome vanilla ; le Nether conserve ses 63 biomes vanilla en petites parcelles, son niveau d’eau à Y=0 et ses lits utilisables. Le ciel violet étoilé OMORI, les musiques, fleurs et créatures restent inclus.

Les performances prolongées et le multijoueur simultané restent à vérifier. L’écoute audio n’est pas validée avec le périphérique nul de l’environnement. La comparaison officielle de deux robots Sonic reste partielle. Le transport des coffres pleins, l’End custom et les missions Lethal restent à développer. Lunaria Media manque et le compagnon de quêtes fourni peut dupliquer ses chapitres au redémarrage ; le pack reprend des configurations propres.

[Rapport précédent 0.14](docs/RAPPORT_PEAUFINAGE_0.14_FR.md) · [Rapport précédent 0.13](docs/RAPPORT_GENERATION_LETHAL_0.13_FR.md)
