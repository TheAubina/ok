# Hina Land — bêta 0.11.0

Minecraft Java 1.20.1 · Forge 47.3.0 · Java 17

**[JAR installable](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/hinaland-0.11.0.jar)** · **[Modpack de test 5 — 22 JAR](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.11.0-modpack-test-5.zip)** · [Sources compilables](https://github.com/TheAubina/ok/raw/refs/heads/main/livrables/HinaLand-0.11.0-sources.zip)

Genshin, Overwatch et Lethal rejoignent Mario, Sonic, OMORI et DELTARUNE **dans l’Overworld**, pour 28 biomes Hina Land. Les textures fournies sont intégrées aux blocs thématiques et au sous-sol. 24 fleurs et 32 constructions/décors sont disponibles, avec des coffres et une génération naturelle.

Le Nether mélange les 63 biomes vanilla jouables de l’Overworld, du Nether et de l’End sur un terrain ouvert avec eau, ciel et cycle jour/nuit. Les lits permettent de dormir et d’y réapparaître. Les sept monstres Lethal conservent leur restriction aux intérieurs, Ghost Girl comprise. Les créatures, musiques et ciel OMORI de la version 0.10 sont conservés.

## Installation

Remplacer l’ancien JAR Hina Land sans garder plusieurs versions. Le JAR seul nécessite GeckoLib 4.4.9 et TerraBlender 3.0.1.7, inclus dans le modpack. Copier mods, config et resourcepacks dans une instance Forge 47.3.0 ; activer le petit pack d’intégration fourni. Les textures thématiques sont déjà dans le JAR.

**Créer un monde neuf pour reproduire le Nether testé.** La migration du Nether d’une sauvegarde existante n’est pas validée. Les nouveaux biomes et structures Overworld nécessitent des chunks neufs. La configuration TerraBlender conserve de grandes régions et un poids vanilla réduit.

## Validation et limites

25 GameTests Forge réussis ; 1469 JSON et 18 modèles contrôlés. Audit de 16641 positions par dimension : les 28 biomes Hina Land sont observés dans l’Overworld et 58 des 63 biomes vanilla dans le Nether. Inspection de 12 sites naturels des nouveaux thèmes et 9 sites Nether, comptage des 12 nouvelles fleurs et enregistrement de 17 débuts de structures naturelles de 12 types.

Client et serveur de production testés avec 22 mods. Un joueur Survie a dormi dans le Nether, s’est réveillé au matin, est réapparu près de son lit après une mort provoquée et a rejoint le Nether par un portail vanilla. Les plateformes de test étaient placées manuellement.

L’End custom reste à réaliser. Pas encore de monstres Genshin/Overwatch, de système complet de lunes/quotas/vaisseau Lethal, ni de campagne complète validée. Certaines plantes hautes restent à intégrer. La génération massive de sites éloignés provoque des pauses ; les performances d’une longue exploration restent à vérifier. Lunaria Media manque toujours et trois succès sont bloqués ; le mod de quêtes fourni peut dupliquer ses chapitres au redémarrage.

[Rapport détaillé 0.11](docs/RAPPORT_MONDES_STRUCTURES_0.11_FR.md) · [Empreintes des téléchargements](docs/SHA256SUMS-0.11.0.txt) · [Rapport précédent 0.10](docs/RAPPORT_PACKS_CREATURES_0.10_FR.md)
