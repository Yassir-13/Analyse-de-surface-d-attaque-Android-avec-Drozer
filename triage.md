# Tableau de priorisation des vulnérabilités

| ID  | Composant                     | Vulnérabilité                          | Confiance | Sévérité  | Impact                                      | Recommandation                                  | Statut        |
|-----|-------------------------------|----------------------------------------|-----------|-----------|---------------------------------------------|-------------------------------------------------|---------------|
| V1  | MainActivity                  | Activity exportée sans protection      | Élevée    | Moyenne   | Accès non autorisé / contournement logique   | Restreindre exported ou ajouter contrôle auth   | À corriger    |
| V2  | AndroidManifest (meta-data)   | Données sensibles exposées             | Élevée    | Critique  | Accès administrateur / compromission totale  | Supprimer les données sensibles du manifest     | À corriger    |
| V3  | Configuration réseau          | Cleartext traffic autorisé             | Élevée    | Moyenne   | Interception des communications (MITM)       | Forcer HTTPS (usesCleartextTraffic=false)       | À corriger    |
| V4  | Configuration application     | allowBackup activé                     | Élevée    | Moyenne   | Extraction de données via ADB                | Désactiver allowBackup en production            | À corriger    |
| V5  | Broadcast Receiver            | Receiver exporté (protégé système)     | Moyenne   | Faible    | Déclenchement d’actions limité               | Vérifier nécessité / restreindre si possible    | À surveiller  |
| V6  | Content Providers             | Aucun provider exporté                 | Élevée    | Faible    | Aucun impact exploitable                     | Aucun correctif nécessaire                      | Accepté       |
| V7  | Services                      | Aucun service exporté                  | Élevée    | Faible    | Aucun impact exploitable                     | Aucun correctif nécessaire                      | Accepté       |

---

