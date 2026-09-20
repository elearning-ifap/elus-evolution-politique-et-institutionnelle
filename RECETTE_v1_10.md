# Recette fonctionnelle et technique — EPI v1.10

Date : 20 septembre 2026  
Noyau : v1.8.1  
Statut : **candidat à recette LIANE**

## 1. Non-régression statique

- Identifiants dupliqués : **0** []
- Cibles `data-go` manquantes : **0** []
- Médias locaux manquants : **0** []
- Syntaxe JavaScript : **OK**
- Cœur `GABARIT` identique au fichier de référence v1.8.1 : **OUI**
- Ressources iconographiques référencées : **20**

## 2. Reprise SCORM simulée

Test réalisé avec une API SCORM 1.2 factice :

- écran initial : `g-contrat` ;
- positionnement d’entrée : 6/6 réponses sauvegardées ;
- fermeture simulée au milieu de l’activité 1 : reprise sur `epi-p1-activite` ;
- réponses formatives après relance : **réinitialisées volontairement** ;
- aucune réponse formative présente dans `suspend_data` ;
- frise : filtre `accord` et repère `Nainville-les-Roches` restaurés ;
- largeur 1024 px : pas de débordement horizontal global ;
- largeur 800 px : pas de débordement horizontal global ;
- `suspend_data` du scénario de reprise testé : **233 caractères**.

## 3. Complétion SCORM simulée

- statut final : `completed` ;
- drapeau interne de complétion : `True` ;
- positionnement de sortie : 6/6 ;
- positionnement rétrospectif : 6/6 ;
- badge final : `Module complété ✓` ;
- `suspend_data` de fin de parcours : **712 caractères** ;
- erreurs JavaScript : **0**.

## 4. Correction de conformité apportée en v1.10

La v1.9 persistait dans `suspend_data` les réponses intermédiaires des activités formatives afin de les restaurer au caractère près. Cette pratique entrait en tension avec R14-R16 et A12 : les réponses formatives ne doivent pas créer une collecte pédagogique nominative implicite.

La v1.10 applique donc la règle suivante :

- l’écran courant est restauré ;
- les séquences terminées sont restaurées ;
- les auto-positionnements sont restaurés conformément au mode ipsatif ;
- la frise (filtre, repère ouvert, position) est restaurée ;
- **les réponses aux activités formatives restent en mémoire seulement pendant la session et ne sont jamais écrites dans SCORM**.

L’apprenant qui ferme au milieu d’une activité revient donc exactement sur le bon écran, mais recommence les choix de l’activité. C’est le compromis cohérent avec la politique de confidentialité du dispositif.

## 5. Reste à tester dans LIANE

- fermeture réelle de l’activité SCORM depuis Moodle puis réouverture ;
- comportement du lecteur YouTube dans l’iframe Moodle ;
- tablette réelle en portrait et paysage ;
- plein écran dans le navigateur cible ;
- statut de complétion visible dans les rapports Moodle ;
- retour d’un utilisateur après plusieurs jours.
