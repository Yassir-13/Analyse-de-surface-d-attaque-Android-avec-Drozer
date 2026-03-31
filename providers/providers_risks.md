# Analyse des risques – Content Providers

## Observation
La commande Drozer suivante :
run app.provider.info -a com.vulnerablebankapp

indique :
"No matching providers"

Cela signifie qu’aucun content provider exporté n’est accessible.

## Analyse complémentaire
Un content provider interne est présent dans le manifest :

- Nom : androidx.startup.InitializationProvider
- Exporté : Non

## Risques identifiés
Aucun risque direct, car :
- Le provider n’est pas exposé
- Aucun accès externe possible

## Impact
Pas d’accès aux données via Content Provider

## Niveau de risque
Faible

## Conclusion
Les content providers ne constituent pas une surface d’attaque exploitable dans cette application.