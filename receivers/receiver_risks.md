# Analyse des risques – Broadcast Receivers

## Composant analysé
- Nom : androidx.profileinstaller.ProfileInstallReceiver
- Exporté : Oui
- Protection : android.permission.DUMP

## Description
Le receiver est exporté mais protégé par une permission système.

## Risques identifiés
- Risque limité d’exploitation via intents malveillants

## Scénario d’attaque
Un attaquant pourrait tenter d’envoyer des intents malveillants si la permission est contournée ou mal implémentée.

## Impact
Faible dans un environnement standard.

## Niveau de risque
Faible

## Recommandations
- Limiter l’export si non nécessaire
- Vérifier les permissions associées