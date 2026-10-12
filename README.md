# Hina Land — bêta 0.17.0

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17

**[Télécharger le JAR compilé](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/hinaland-0.17.0.jar)** · **[Modpack test 11 — 23 mods](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.17.0-modpack-test-11.zip)** · [Sources](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.17.0-sources.zip)

**25 ambiances de ciel pour les 28 biomes**, avec variantes Mario World 1/forêt/montagne/désert et un ciel OMORI commun inchangé. Panoramas originaux inspirés des univers, avec transition et éclairage nocturne. [Catalogue et références](docs/CATALOGUE_CIELS_0.17_FR.md).

**Textures améliorées pour 21 créatures voxel, 35 blocs et 24 icônes.** Les modèles restent des adaptations simples ; les sprites, armures et sept modèles Lethal originaux sont préservés. 50 créatures Hina au total, blocage des monstres vanilla de l’Overworld conservé.

**March et Offense arrivent dans un hall Lethal éclairé**, avec sortie et accès aux couloirs d’origine. Les deux allers-retours et le déplacement à pied dans les couloirs ont été vérifiés. Sur une copie d’ancien monde, 400 316 états de blocs hors de la zone du hall restent identiques.

**62 GameTests Forge réussis**, compilation du JAR final et contrôles dans le client Minecraft. [Rapport précis et limites](docs/RAPPORT_VISUEL_0.17_FR.md) · [Empreintes SHA-256](docs/SHA256SUMS-0.17.0.txt).

## Installation

Remplacer l’ancien JAR Hina Land dans `mods`. Le JAR seul nécessite GeckoLib 4.4.9 et TerraBlender 3.0.1.7 ; le modpack les inclut, ainsi que Lunaria Media 2.1.0 inchangé. Copier `mods`, `config` et `resourcepacks` dans une instance dédiée ; activer HinaLand-integration-textures et conserver une seule version de chaque mod.

Sauvegarder les mondes : le hall est ajouté une seule fois à l’ancien intérieur, dans la zone x64..78, y68..73, z35..43, plus l’ancienne porte. Une construction personnelle dans cette petite zone peut être remplacée lors de la migration. Les autres zones sont préservées. Les tests prolongés à plusieurs joueurs, l’audio/vidéo Lunaria et la fidélité artistique exhaustive restent à vérifier. Le compagnon de quêtes peut dupliquer des chapitres au redémarrage ; les configurations distribuées sont propres.

## Contenu conservé

28 biomes Hina dans l’Overworld normal, géologie et fleurs thématiques ; Nether fracturé mélangeant 63 biomes vanilla, avec lits utilisables. Minerais, équipements, blocs « ? » Mario fonctionnels, cinq musiques et ciel OMORI ; portes March/Offense vers l’intérieur Lethal partagé. **70 constructions introduites en 0.15**, dix par chacun des sept univers, plus 21 précédentes : 91 choix naturels et douze petits donjons hors Lethal. [Catalogue des constructions](docs/CATALOGUE_STRUCTURES_0.15_FR.md) · [Vérification de la 0.15](docs/RAPPORT_STRUCTURES_0.15_FR.md).

L’End complet, le portage de coffres remplis par le Hoarding Bug, la boucle Lethal complète, la progression générale et les tests prolongés à plusieurs joueurs restent à terminer. Les détails historiques et limites propres à chaque livraison sont dans `docs`.
