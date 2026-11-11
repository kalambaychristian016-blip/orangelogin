

## 26 septembre 2026 — Paiement de quota Orange Money

Le parcours Orange Money affiche désormais **Paiement de quota** au lieu de l’abonnement. Les plans proposés sont 10 quotas à 25 000 FC et 20 quotas à 45 000 FC, payés manuellement au numéro de réception existant. L’agent saisit le numéro payeur et envoie une demande ; la gestion voit le plan, le montant et le numéro payeur, puis valide ou refuse.

Le quota est sans date d’expiration. Le portail agent affiche le total, le nombre de dossiers validés et le restant. Seuls les dossiers Orange Money validés par la gestion consomment un quota ; les dossiers rejetés n’en consomment pas. À zéro, l’accès est bloqué et le paiement de quota réapparaît. Le serveur bloque également la création d’un dossier lorsque le quota est épuisé.

Validation technique : **36 tests Vitest réussis** et **build de production réussi**. La migration SQL des colonnes de quota est non destructive.


## 28 septembre 2026 — Quotas premium par rubrique

Les rubriques **Zebra, CICO 145, Élargissement et Modification** proposent désormais un accès premium séparé. Un paiement manuel de **9 000 FC** vers le numéro Orange Money existant débloque **10 quotas** pour la seule rubrique choisie, sans expiration temporelle. L’agent saisit le numéro payeur et ne peut soumettre qu’une demande en attente par rubrique. Le portail admin reçoit chaque demande avec l’agent, la rubrique, le numéro payeur et le montant, puis peut valider ou refuser. Les quotas sont consommés uniquement par les dossiers validés ; lorsque le solde atteint zéro, la rubrique revient au paiement. Migration SQL 0017 appliquée avec succès, build validé et 36 tests Vitest passants.


## 29 septembre 2026 — Pass premium commun aux quatre rubriques

Le paiement premium de **9 000 FC** n’est plus rattaché à une seule rubrique. Une demande effectuée depuis Zebra, CICO 145, Élargissement ou Modification crée un paiement unique par agent ; après validation admin, **10 quotas sont ajoutés dans chacune des quatre rubriques**. Une nouvelle demande reste bloquée tant que le paiement global précédent est en attente. Si une seule rubrique épuise ses quotas, un nouveau paiement réactive et crédite simultanément les quatre rubriques. Tests et build à nouveau validés après modification.


## 1 octobre 2026 — Lots de quotas indépendants

Le calcul des quotas a été corrigé pour ne plus compter les dossiers validés avant le paiement. Chaque validation admin d’un paiement crée un nouveau lot complet : le compteur démarre à zéro au moment de l’achat, le quota total est celui du plan acheté, et les anciennes validations restent exclues du nouveau lot. Le comportement s’applique à Orange Money ainsi qu’aux quatre rubriques premium. Migration non destructive `0018_typical_galactus.sql` appliquée. 39 tests Vitest et le build de production sont validés.
