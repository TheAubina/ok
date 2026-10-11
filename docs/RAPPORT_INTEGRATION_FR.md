# Rapport d’intégration — 11 octobre 2026

## Résultat

Un paquet installable de 22 JAR a été assemblé : Hina Land 0.7.0, GeckoLib 4.4.9, TerraBlender 3.0.1.7 et 19 des 20 JAR transmis. Les 19 JAR utilisateur sont conservés à l’identique ; les empreintes SHA-256 sont fournies. Lunaria Media n’a pas pu être transféré à cause de la limite de 32 Mio de l’outil.

## Contrôles réellement exécutés

- Intégrité ZIP et lecture des métadonnées des JAR ; aucun identifiant de mod dupliqué. Les dépendances obligatoires déclarées sont disponibles. Leur résolution est confirmée par le chargement Forge.
- Arrêt normal du client par le bouton Quitter : code de sortie 0 ; arrêt du serveur avec sauvegarde des chunks confirmé.
- Serveur dédié Forge 47.3.0 / Java 17 lancé avec les 22 JAR de production : création d’un monde neuf, message de disponibilité, sauvegarde effectuée.
- Client Forge 47.3.0 de production lancé avec les mêmes JAR, connexion au serveur, affichage du monde et ouverture de l’inventaire réussis. Le JAR Hina Land distribué est effectivement utilisé dans ce test.
- Ciel OMORI observé sur le client de production avec tous les mods après application locale du biome par la commande de test. Ce contrôle ne remplace pas le test de génération naturelle réalisé pour la bêta.
- FTB Quests : chargement de **2 groupes, 14 chapitres et 148 quêtes**, synchronisation vers le client et ouverture du carnet. La tâche de bienvenue apparaît terminée et sa récompense XP a été récupérée. Cela ne valide pas les 147 autres quêtes ni toutes leurs chaînes de dépendances.
- Diagnostic des quinze avertissements de textures d’objets d’OverCraft, Flandre et Portal Rick : douze images distinctes existent mais ne sont pas incluses dans l’atlas. Un pack de ressources additionnel enregistre ces images dans l’atlas. Après activation et rechargement en jeu : **aucun avertissement « Missing textures in model »**. Les modèles et images des JAR ne sont pas remplacés. Les objets concernés n’ont pas tous été examinés individuellement en main.

## Problèmes connus et non testé

Trois succès de Hina Land Quest ne se chargent pas sans Lunaria Media : `hinalandquest:q050`, `q051` et `q143`. Ils référencent l’écran `lunariamedia:flat_screen_stand` et/ou l’enceinte `lunariamedia:speaker_tower`. Le serveur démarre malgré ces erreurs, mais ces objectifs et les progressions qui en dépendent restent bloqués. Aucun faux remplacement par un objet vanilla n’a été ajouté.

Le test local utilise un serveur hors ligne isolé. Une première connexion employait un UUID différent de celui attribué par le serveur : FTB Teams signalait alors une identité inconnue. Le client de test a été corrigé pour employer l’UUID hors ligne correspondant ; l’erreur n’apparaît plus dans l’exécution finale. Une erreur initiale de classpath du lanceur manuel a également été corrigée avant le test de connexion. Une fermeture forcée du premier client a produit une erreur native ; elle ne permet pas d’évaluer la stabilité d’une fermeture normale, vérifiée séparément en fin de test.

L’environnement utilise un affichage virtuel, OpenGL logiciel et une sortie audio muette. Les avertissements d’authentification et de recherche de mises à jour sont liés au contexte réseau de test. Deux avertissements de sons vanilla de corne de chèvre restent présents. Aucun résultat audible n’est revendiqué.

Les compagnons, combats, véhicules Brobot, portails, résurrection OverCraft, bottes Luigi, effets Poop Mod, équipements Curios, récupération Corpse/Corpse Curios Compat et progression complète des quêtes **ne sont pas validés fonctionnellement** par ce simple chargement. Compatibilité à long terme, multijoueur avec plusieurs personnes, sauvegardes existantes et shaders non testés.

Flandre enregistre également sa propre dimension `flandre:scarlet_world`, chargée par le serveur ; aucune migration de son contenu vers l’Overworld n’a été réalisée.

Les JAR sont assemblés en modpack ; leurs systèmes ne sont pas fusionnés dans Hina Land et aucune intégration de progression nouvelle n’a été codée. Les limites de la bêta Hina Land précédemment décrites restent applicables. Carry On et le transport de coffres par le Hoarding Bug ne font pas partie de ce paquet.

## Inventaire

| Fichier | Identifiant de mod | Version |
|---|---|---|
| TerraBlender-forge-1.20.1-3.0.1.7.jar | terrablender | 3.0.1.7 |
| architectury-9.2.14-forge.jar | architectury | 9.2.14 |
| aubrey-1.20.1-1.0.1.jar | aubrey | 1.0.1 |
| baguettelib-1.20.1-Forge-1.1.6.jar | baguettelib | 1.1.6 |
| brobot-1.0.1.jar | brobot | 1.0.1 |
| corpse-forge-1.20.1-1.0.23.jar | corpse | 1.20.1-1.0.23 |
| corpsecurioscompat-1.20.1-Forge-3.1.3.jar | corpsecurioscompat | 3.1.3 |
| curios-forge-5.14.1+1.20.1.jar | curios | 5.14.1+1.20.1 |
| flandre-1.2.4.jar | flandre | 1.2.4 |
| ftb-library-forge-2001.2.13.jar | ftblibrary | 2001.2.13 |
| ftb-quests-forge-2001.4.22.jar | ftbquests | 2001.4.22 |
| ftb-teams-forge-2001.3.2.jar | ftbteams | 2001.3.2 |
| geckolib-forge-1.20.1-4.4.9.jar | geckolib | 4.4.9 |
| hina-land-quest-1.20.1-1.0.1.jar | hinalandquest | 1.0.1 |
| hinaland-0.7.0.jar | hinaland | 0.7.0 |
| jester-1.20.1-1.0.2.jar | jester | 1.0.2 |
| jonathan-1.20.1-1.0.2.jar | gnome | 1.0.2 |
| luigi-boots-1.20.1-1.0.2.jar | luigiboots | 1.0.2 |
| overcraft-1.9.10-beta1.jar | juno | 1.9.10-beta1 |
| poopmod-1.20.1-1.0.2.jar | poopmod | 1.0.2 |
| portalrick-1.20.1-1.0.4.jar | portalrick | 1.0.4 |
| robe-1.20.1-1.0.2.jar | robe | 1.0.2 |

Les journaux et captures du contrôle sont dans `audit/`. Les seules modifications de ressources propres à ce paquet sont dans `resourcepacks/HinaLand-integration-textures.zip`.
