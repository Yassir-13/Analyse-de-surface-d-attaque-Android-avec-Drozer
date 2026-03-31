# Analyse du AndroidManifest

## Informations générales
- Package : com.vulnerablebankapp
- Version : 1.0

## Configuration de sécurité

### 1. allowBackup activé
- Risque : Extraction de données via ADB
- Impact : Fuite de données utilisateur

### 2. Cleartext traffic autorisé
- Paramètre : usesCleartextTraffic="true"
- Risque : Interception du trafic réseau (MITM)

---

## Données sensibles exposées

### Observation critique
Des informations sensibles sont présentes dans le manifest :

- Endpoint de debug
- Identifiants administrateur (non affichés ici pour sécurité)

## Risques identifiés
- Exposition de credentials
- Accès non autorisé aux fonctionnalités internes

## Impact
- Compromission complète de l’application
- Accès administrateur possible

## Niveau de risque
Critique

---

## Bonnes pratiques recommandées

- Ne jamais stocker de credentials dans le manifest
- Désactiver allowBackup en production
- Forcer HTTPS (désactiver cleartext traffic)
- Utiliser des mécanismes sécurisés de gestion des secrets

---

## Conclusion globale

L'application présente plusieurs faiblesses de configuration, dont une vulnérabilité critique liée à l’exposition de données sensibles.
