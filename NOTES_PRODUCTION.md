# EPI — version de production v1.4

## Objet de la passe

Sécurisation avant recette Moodle : feedbacks réellement visibles et rejouables, non-régression de la reprise SCORM, radar ipsatif à 6 dimensions sans score global, frise persistante, chargement vidéo allégé et crédits consolidés.

## Changements v1.4

- suppression visuelle de la barre de navigation basse générique : **un seul CTA contextuel** par écran, navigation macro à gauche ;
- activités des cinq périodes et défi final en **deux temps** : choix → vérification/feedback → continuation ;
- feedbacks immédiats avec **✓ / ✕**, 2–3 lignes explicatives et possibilité de **rejouer** ;
- ordonnancements P2 et P4 désormais réellement mélangés au chargement initial ;
- correction de l’activité P1 : suppression de l’item ambigu « participation immédiatement pleine et uniforme » ;
- état de validation des activités sauvegardé dans `suspend_data` ; feedback restauré à la reprise ;
- frise : filtre, repère sélectionné, consultation et position horizontale sauvegardés ; progression de la frise validable après consultation d’au moins un repère ;
- positionnement final : remplacement des barres et de la « progression moyenne » par le **radar ipsatif standard à 6 branches**, sans score global ;
- SCORM 1.2 : `cmi.core.exit = suspend` tant que le module n’est pas complété ; alerte de budget `suspend_data` à 3900 caractères / limite 4096 ;
- vidéos YouTube chargées seulement à l’ouverture de leur écran ; sous-titres demandés au lecteur (`cc_load_policy=1`) ; les lecteurs déjà chargés sont mis en pause au changement d’écran ;
- crédits : détail média par média pour les cinq photogrammes ; suppression du marqueur de fabrication visible ;
- sources : liens institutionnels cliquables et date de consultation ;
- plusieurs formulations historiques rendues plus factuelles dans les écrans et la frise.

## Points encore bloquants avant diffusion

1. **Sous-titres** : vérifier dans YouTube que chacune des cinq capsules dispose bien de sous-titres français exploitables.
2. **Transcriptions** : les règles médias du projet prévoient une transcription en ressource Moodle ; elle n’est pas incluse dans ce package.
3. **Crédits des archives présentes dans les vidéos** : confirmer que les génériques/dossiers de production des cinq capsules documentent les ayants droit et sources des archives.
4. **Recette Moodle réelle** : vérifier reprise après fermeture, statut `completed`, lecture de `suspend_data` et comportement de `cmi.core.exit`.
5. **Tablette réelle** : tester iPad + tablette Android, notamment la frise et le panneau « Parcours ».

## Non-régression à contrôler

- 32 panneaux présents ;
- 5 périodes, 5 vidéos, 5 activités + défi ;
- aucune activité obligatoire ne passe directement à l’écran suivant avant affichage du feedback ;
- crédits et sources restent hors progression ;
- aucune donnée de score global n’est écrite dans SCORM ;
- radar affiché uniquement après les trois passations ipsatives complètes ;
- frise toujours accessible depuis le menu et l’accès direct.
