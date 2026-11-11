# Cartographie de l’application existante

## Tableau de bord observé
Rubriques visibles : Kaabu, Zebra, Reset PIN Zebra, Reset PIN Kaabu, RLMS 395, CICO Lite, Modification, Élargissement, Envoyer les dossiers et Paramètres.

## Formulaire Kaabu observé
Le formulaire comporte les champs « Nom », « Prénom », « Postnom » et « Numéro », avec un bouton « Enregistrer » et un bouton « Retour au menu ».

## Objectif demandé
Chaque enregistrement métier doit être conservé dans l’application, apparaître dans « Envoyer les dossiers », être transmissible au Gmail du propriétaire via Resend, puis pouvoir être validé par le propriétaire. Les codes PIN, mots de passe et secrets ne doivent jamais être inclus.

## Point d’attention
Le tableau de bord actuellement ouvert est l’application déjà déployée. Le projet de développement actif doit être relié à cette version existante avant de remplacer son intérieur, afin de préserver ses rubriques et ses données.

## Rubrique « Envoyer les dossiers » observée
La rubrique existe déjà dans le tableau de bord, mais elle affiche actuellement « Aucun formulaire à envoyer ». Elle dispose d’un bouton « Retour au menu ». Le flux demandé doit donc relier les enregistrements des formulaires aux éléments listés ici, puis ajouter l’envoi, le statut et la validation.
