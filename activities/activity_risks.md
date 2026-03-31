# Analyse des risques – Activities

## Composant analysé
- Nom : com.vulnerablebankapp.MainActivity
- Exporté : Oui
- Protection : Aucune permission requise

## Description
L'activité principale est exportée et accessible sans restriction depuis des applications externes.

## Risques identifiés
- Accès non autorisé à l'application
- Possibilité de contournement de la logique interne (authentification)

## Scénario d’attaque
Un attaquant peut lancer l’activité via ADB :
adb shell am start -n com.vulnerablebankapp/.MainActivity

## Impact
- Accès direct à l'interface utilisateur
- Potentiel contournement de contrôles de sécurité

## Niveau de risque
Moyen

## Recommandations
- Restreindre l’export si non nécessaire
- Ajouter une vérification d’authentification côté application