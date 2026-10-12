# Hina Land — bêta 0.13.0

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17

**[Télécharger le JAR](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/hinaland-0.13.0.jar)** · **[Modpack de test 7 — 22 JAR](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.13.0-modpack-test-7.zip)** · [Sources compilables](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.13.0-sources.zip)

Les entrées March et Offense mènent, au clic droit, à une dimension Lethal contenant la zone industrielle convertie de la carte Bedrock fournie. Le retour mémorise l’entrée de chaque joueur. 42 modèles industriels avec leurs textures sont intégrés ; les sept monstres Lethal gardent leurs animations et comportements Java et leur restriction aux intérieurs. Une porte peut aussi être fabriquée avec quatre lingots de fer et deux alliages de la Compagnie. Le complexe est fini et commun à toutes les entrées.

L’Overworld Normal utilise exclusivement les 28 biomes Hina Land des sept univers. Les dix ennemis thématiques peuvent apparaître à la surface en journée, avec des animaux sur les sols moddés. Les constructions naturelles sont limitées à dix modèles sélectionnés, espacés et contrôlés sur terrain sec avec des fondations ; les anciens placements répétitifs sont désactivés. Les cellules vides préservent le terrain autour des façades.

Le Nether mélange toujours les 63 biomes vanilla, avec des parcelles plus petites et un niveau d’eau abaissé à Y=0. Le sommeil y est conservé. Les textures, fleurs, musiques, ciel OMORI, 14 ressources minérales et 77 crafts de la version précédente restent présents.

## Installation

Remplacer l’ancien JAR Hina Land dans `mods` et **créer un monde neuf de type Normal**. Les anciennes sauvegardes et leurs générateurs ne sont pas migrés automatiquement. Le JAR seul nécessite GeckoLib 4.4.9 et TerraBlender 3.0.1.7 ; ces dépendances sont incluses dans le modpack. Copier `mods`, `config` et `resourcepacks` dans une instance Forge dédiée, puis activer le petit pack d’intégration fourni.

## Vérification

**32 GameTests Forge réussis**, compilation Gradle et JAR réobfusqué. 1 990 JSON et 18 modèles/animations GeckoLib contrôlés. Client et serveur de production avec les 22 mods : affichage de la carte convertie, passages March/Offense et retours à la bonne entrée. Apparitions réellement naturelles en journée dans Mario, et des sept espèces dans les intérieurs Lethal. Population Lethal réduite après observation de la surpopulation initiale.

Audit de 16 641 positions par dimension : 28 biomes Hina et zéro identifiant vanilla dans l’Overworld ; 60 des 63 biomes possibles observés dans le Nether. Neuf sites Nether enregistrés : aucune eau au-dessus de Y=0 et aucune surface en eau sur les 2 304 colonnes examinées. De l’eau reste possible plus bas.

Les contrôles ne valident pas une longue partie sur plusieurs graines, le multijoueur simultané ou la migration d’un ancien monde. Les façades ne reproduisent pas toute la topographie March/Offense. L’End custom, les missions/quotas/navette Lethal et le transport de coffres pleins par le Hoarding Bug restent à développer. Lunaria Media manque toujours et le compagnon de quêtes fourni peut dupliquer ses chapitres au redémarrage.

[Rapport détaillé et limites](docs/RAPPORT_GENERATION_LETHAL_0.13_FR.md) · [Empreintes des téléchargements](docs/SHA256SUMS-0.13.0.txt) · [Version précédente 0.12](docs/RAPPORT_MINERAIS_0.12_FR.md)
