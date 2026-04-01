## Question (Ex1) : Une méthode default dans une interface peut-elle accéder aux champs privés de la classe qui l'implémente ? Justifiez, en vous appuyant sur isDefective() dans Qualifiable et getQualityScore() dans Duck.

Non, une méthode default dans une interface ne peut absolument pas accéder au champs privés ou publics de la classe qui l'implémente, l'interface n'a aucune connaissance de l'etat interne des les classes.

la méthode isDefective de l'interface Qualifiable a besoin de connaître le score pour faire son test, et elle ne peut pas lire l'attribut privé qualityScore de la classe Duck, elle est obligée d'appeler la méthode publique getQualityScore définie dans son propre contrat. C'est ensuite l'instance de la classe Duck qui fourni la valeur reelle apres l'exécution.


## Question (Ex2) : Dans ce projet, Maintainable est une interface et Machine est une classe abstraite. Quelle règle Java vous aurait empêché de faire l'inverse ? Plus généralement, quand choisit-on une interface plutôt qu'une classe abstraite ?

La regle Java qui m'aurait empêché de faire l'inverse est l'héritage simple. En Java, une classe ne peut  hériter de une seule classe mère soit abstraite ou non.
 Si Maintainable était une classe abstraite, une machine ne pourrait hériter de rien d'autre.

 On choisi une Interface comme Maintainable pour définir un contrat de comportement un "sait-faire" comment cetait signaler dans les interrogations faites. Une classe peut implémenter plusieurs interfaces.

 ## Question (Ex4) : Expliquez pourquoi canBeFulfilled(Stock<Duck> stock) serait une signature plus restrictive que canBeFulfilled(Stock<? extends Duck> stock). Donnez un exemple.

les types génériques sont invariants, même si StandardDuck hérite de Duck, une liste Stock StandardDuck n'hérite pas de Stock Duck.
Si la signature était canBeFulfilled(Stock Duck stock), le compilateur exigerait exactement un Stock Duck. Le joker ? extends Duck la fameusse covariance que permet de re liverer  cette contrainte et d'accepter nimporte quel stock contenant un soustype de Duck.