# Recette EPI v1.14 — chronoscope

## Contrôles statiques réalisés
- 39 écrans fonctionnels conservés ;
- aucun identifiant HTML dupliqué ;
- aucune cible `data-go` manquante ;
- aucun média local manquant ;
- syntaxe JavaScript validée avec `node --check` ;
- 31 repères chronologiques déclarés ;
- 2 modes de lecture du chronoscope présents ;
- continuité de la sauvegarde de la frise : filtre, défilement, repère sélectionné et mode de lecture.

## Comportements à tester dans LIANE
1. Desktop : cliquer un repère -> fiche latérale immédiate, sans scroll vertical.
2. Tablette : cliquer un repère -> tiroir latéral ; fermeture par ×, arrière-plan ou Échap.
3. Petit écran : vérifier la feuille remontante depuis le bas.
4. Mode « Comprendre les bascules » : seuls les jalons structurants restent visibles.
5. Relations : les jalons directement liés au repère actif s’éclairent, les autres s’atténuent.
6. Navigation précédent / suivant : changement de fiche sans sortir du chronoscope.
7. Plein écran : entrée / sortie, conservation du repère et de la position horizontale.
8. Reprise : fermer puis rouvrir le SCORM et contrôler la restauration de la frise.
9. Accessibilité : tester Échap, focus des boutons, `prefers-reduced-motion`.
