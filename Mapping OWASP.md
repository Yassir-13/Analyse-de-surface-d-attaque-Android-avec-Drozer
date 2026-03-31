# Mapping OWASP MASVS / MASTG

| ID  | Vulnérabilité                          | Référence MASVS        | Description                                                                 |
|-----|----------------------------------------|------------------------|-----------------------------------------------------------------------------|
| V1  | Activity exportée sans protection      | MSTG-PLATFORM-1        | L'application expose un composant sans restriction, permettant un accès externe non contrôlé |
| V2  | Données sensibles dans le manifest     | MSTG-STORAGE-2         | Des informations sensibles sont stockées en clair sans protection adéquate  |
| V3  | Cleartext traffic autorisé             | MSTG-NETWORK-1         | Les communications ne sont pas chiffrées, exposant les données à interception |
| V4  | allowBackup activé                     | MSTG-STORAGE-1         | Les données de l'application peuvent être extraites via des mécanismes de sauvegarde |
| V5  | Broadcast Receiver exporté (protégé)   | MSTG-PLATFORM-3        | Les intents reçus doivent être validés pour éviter les abus                  |
| V6  | Absence de services exportés           | MSTG-PLATFORM-2        | Aucun service exposé, donc pas de surface d’attaque via services             |
| V7  | Absence de Content Providers exportés  | MSTG-STORAGE-2         | Aucun accès externe aux données via provider                                 |

---


## Analyse globale

L'application présente principalement :
- des **failles de configuration (manifest)**
- une **exposition de données sensibles**
- une **gestion insuffisante des communications réseau**

Les composants Android (Activities, Receivers) sont globalement maîtrisés, mais certaines expositions doivent être contrôlées.

---

## Priorité de correction

1. Données sensibles dans le manifest (Critique)  
2. Cleartext traffic (Moyen → Élevé selon contexte)  
3. allowBackup activé  
4. Activity exportée sans contrôle  

---

## Conclusion

L'application ne présente pas une surface d'attaque étendue au niveau des composants Android, mais souffre de **mauvaises pratiques de sécurité critiques**, notamment en matière de gestion des données sensibles.