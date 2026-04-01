## Question (Ex1) : Une méthode default dans une interface peut-elle accéder aux champs privés de la classe qui l'implémente ? Justifiez, en vous appuyant sur isDefective() dans Qualifiable et getQualityScore() dans Duck.

Non, une méthode default dans une interface ne peut absolument pas accéder au champs privés ou publics de la classe qui l'implémente, l'interface n'a aucune connaissance de l'etat interne des les classes.

la méthode isDefective de l'interface Qualifiable a besoin de connaître le score pour faire son test, et elle ne peut pas lire l'attribut privé qualityScore de la classe Duck, elle est obligée d'appeler la méthode publique getQualityScore définie dans son propre contrat. C'est ensuite l'instance de la classe Duck qui fourni la valeur reelle apres l'exécution.