# Exercices

## Exercice 1 : Vérifier la validité d'une expression mathématique

Écrivez une fonction qui prend une chaîne de caractères représentant
une expression mathématique simple (ex : "2+3", "4*5", "6-1") et retourne
un booléen indiquant si l'expression est valide ou non.

Une expression est considérée valide si :
- Elle contient exactement deux nombres 
- Elle contient exactement un opérateur (+, -, *, /)
- Les nombres et l'opérateur sont séparés par des espaces (ex : "2 + 3"
est valide mais pas "2+3")

Utilisez le pattern matching pour analyser la chaîne et vérifier
ces conditions.

