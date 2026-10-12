# Hina Land — bêta 0.16.1

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17

**[Télécharger le JAR compilé](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/hinaland-0.16.1.jar)** · **[Modpack de test 10 — 23 mods, Lunaria inclus](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.16.1-modpack-test-10.zip)** · [Sources compilables](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.16.1-sources.zip)

**32 nouvelles créatures, 50 Hina au total.** Mario reçoit Bob-omb, Boo, Maskass, Kamek, Frère Marto, Plante Piranha, Topi Taupe et Hériss ; Sonic quatre robots ; OMORI et DELTARUNE six ennemis chacun ; Genshin et Overwatch quatre chacun. Les sept Lethal précédents et Omochao sont conservés. [Catalogue des créatures et capacités](docs/CATALOGUE_CREATURES_0.16_FR.md).

**Les monstres vanilla sont bloqués dans l’Overworld**, y compris les entités enregistrées, commandes et anciens générateurs. Les animaux passifs/neutres restent autorisés ; le Nether conserve ses monstres. Les générateurs hostiles vanilla de l’Overworld sont convertis au chargement vers un ennemi du biome local. Les pièces Mario bleues sont renommées **costume Pingouin**, les vertes **costume Grenouille**, avec identifiants et recettes préservés.

**Lunaria Media 2.1.0** est inclus, inchangé. Son chargement client/serveur, sa télévision et son menu sont vérifiés ; la lecture audio/vidéo reste à tester. Les trois avancées qui référençaient ses objets sont désormais enregistrées.

**59 tests Forge réussis**, migration d’une copie de sauvegarde 0.15, connexion du client avec 23 mods, rendu des 32 nouvelles créatures. L’audit a confirmé 13 Pyroblobs, 13 Cryoblobs et 7 Brutocollinus avec provenance NATURAL, et des animaux vanilla passifs. Les capacités sont des adaptations Minecraft : 21 nouveaux modèles voxel simples, 11 créatures sur plans 2D. La fidélité artistique et l’équilibrage demandent encore du travail. [Rapport détaillé, preuves et limites](docs/RAPPORT_CREATURES_0.16_FR.md) · [Empreintes SHA-256](docs/SHA256SUMS-0.16.1.txt).

## Installation

Remplacer l’ancien JAR Hina Land dans `mods`. Le JAR seul nécessite **GeckoLib 4.4.9 et TerraBlender 3.0.1.7** ; le modpack les inclut. Copier ses `mods`, `config` et `resourcepacks` dans une instance dédiée, conserver une seule version de Hina Land/Lunaria et activer le pack d’intégration.

Conserver une sauvegarde avant mise à jour. Les nouvelles apparitions et les libellés concernent les biomes existants ; explorer de nouveaux chunks pour les nouveaux bâtiments. La copie Normal 0.15 testée s’ouvre en 0.16, sans validation exhaustive de toutes les sauvegardes antérieures. Le compagnon de quêtes peut encore dupliquer des chapitres au redémarrage ; le pack distribue une configuration propre.

## Contenu conservé

28 biomes Hina dans l’Overworld normal, géologie et fleurs thématiques ; Nether fracturé mélangeant 63 biomes vanilla, avec lits utilisables. Minerais, équipements, blocs « ? » Mario fonctionnels, cinq musiques et ciel OMORI ; portes March/Offense vers l’intérieur Lethal partagé. **70 constructions introduites en 0.15**, dix par chacun des sept univers, plus 21 précédentes : 91 choix naturels et douze petits donjons hors Lethal. [Catalogue des constructions](docs/CATALOGUE_STRUCTURES_0.15_FR.md) · [Vérification de la 0.15](docs/RAPPORT_STRUCTURES_0.15_FR.md).

L’End complet, le portage de coffres remplis par le Hoarding Bug, la boucle Lethal complète, la progression générale et les tests prolongés à plusieurs joueurs restent à terminer. Les détails historiques et limites propres à chaque livraison sont dans `docs`.
