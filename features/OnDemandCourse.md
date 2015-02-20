Les cours à la demande

#Liste des cours vide
Etant donné que je suis sur la page d'accueil
Et que je vois le lien "Liste des cours"
Et qu'aucun cours à la demande n'est disponible
Lorsque je suis le lien "Liste des cours"
Alors je peux voir "Aucun cours disponible pour le moment."

#Liste des cours sans authentification
Etant donné que je suis sur la page d'accueil
Et que je vois le lien "Liste des cours"
Et que les cours à la demande suivant sont disponibles :
  | Titre                                 |
  | AngularJS : Génération d'application  |
  | AngularJS : Les Directives            |
  | MongoDB : Requêtes et Projections     |
  | MongoDB : Framework d'agrégation      |
Lorsque je suis le lien "Liste des cours"
Alors je peux voir le lien "AngularJS : Génération d'application"

#Liste des cours avec authentification
Etant donné que je suis sur la page d'accueil
Et que je vois le lien "Liste des cours"
Et que les cours à la demande suivant sont disponibles :
  | Titre                                 |
  | AngularJS : Génération d'application  |
  | AngularJS : Les Directives            |
  | MongoDB : Requêtes et Projections     |
  | MongoDB : Framework d'agrégation      |
Et que j'ai déjà validé les cours suivants :
  | Titre                                 |
  | AngularJS : Génération d'application  |  
Lorsque je suis le lien "Liste des cours"
Et que je clique sur "A acquérir"
Alors je ne peux pas voir le lien "AngularJS : Génération d'application"
Et je peux voir le lien "AngularJS : Les Directives"

#Détails de cours
Etant donné que le cours suivant existe :
  | Titre       | Question universelle                                                    |
  | Description | Ce cours porte sur la recherche de la réponse à la question universelle |
Et que je suis sur la page "Liste des cours"
Lorsque je clique sur "Question universelle"
Alors je peux voir "Ce cours porte sur la recherche de la réponse à la question universelle"
Et je peux voir le bouton "Suivre maintenant"

#Cours avec exposé texte
Etant donné que le cours "Question universelle" avec une présentation texte :
    """
    La grande question sur la vie, l'univers et le reste
    (en anglais : The Ultimate Question of Life, the Universe and Everything)
    est – dans l'œuvre de science-fiction de Douglas Adams Le Guide du voyageur
    galactique – la question ultime sur le sens de la vie. Une réponse est
    proposée : le nombre 42, mais le problème est que personne n'a jamais su la
    question précise. Dans l'histoire, la réponse est cherchée par le
    super-ordinateur Pensées Profondes (Deep Thought en version originale1
    et Grand Compute Un dans les anciennes éditions). Cependant, celui-ci
    n'était pas assez puissant pour fournir la question ultime après avoir
    trouvé la réponse (à la suite de 7,5 millions d'années de calculs).
    La réponse de Pensées Profondes embarque les protagonistes dans une
    quête pour découvrir la question qui y correspond.
    """
Et que je suis sur la page "Liste des cours"
Lorsque je clique sur "Question universelle"
Et que je clique sur "Suivre maintenant"
Alors je dois voir *Le texte plus haut*

#Cours avec questions
Etant donné que le cours "Question universelle" avec une présentation texte :
  """
  LOREM IPSUM
  """
  Et que le cours "Question universelle" possède les questions suivantes :
  | Question                          | Réponses possibles    | Réponse correcte            |
  | Quelle est la réponse ?           | 32;34;40;42;54        | 42                          |
  | QUel est le nom de l'ordinateur ? | (libre)               | (Deep Thought;Compute One)  |
  Et que je suis sur la page "Liste des cours"
  Lorsque je clique sur "Question universelle"
  Et que je clique sur "Suivre maintenant"
  Et je clique sur "Valider ce cours"
  Alors je devrais voir les questions suivantes :
    | Question                          | Choix           |
    | Quelle est la réponse ?           | 32;34;40;42;54  |
    | QUel est le nom de l'ordinateur ? | (libre)         |

#Cours avec questions
Etant donné que le cours "Question universelle" avec une présentation texte :
  """
  LOREM IPSUM
  """
Et que le cours "Question universelle" possède les questions suivantes :
  | Question                          | Réponses possibles    | Réponse correcte            |
  | Quelle est la réponse ?           | 32;34;40;42;54        | 42                          |
  | QUel est le nom de l'ordinateur ? | (libre)               | (Deep Thought;Compute One)  |
Et que je suis sur la page "Liste des cours"
Lorsque je clique sur "Question universelle"
Et que je clique sur "Suivre maintenant"
Et je clique sur "Valider ce cours"
Et je donne les réponses suivantes :
  | Question                          | Réponse         |
  | Quelle est la réponse ?           | <answer1>       |
  | QUel est le nom de l'ordinateur ? | <answer2>       |
Et je clique sur "Terminer"
Alors je devrais voir "<result>/2"
Exemples :
  | answer1 | answer2       | result  |
  | 32      | Alfonzo       | 0       |
  | 34      | Compute One   | 1       |
  | 42      | Compute One   | 2       |
  | 42      | Deep Thought  | 2       |

#Validation d'un cours
Etant donné que je viens de terminer de répondre aux questions d'un cours "Cours Test"
Et que j'ai obtenu le résultat maximum
Lorsque je consulte les détails du cours "Cours Test"
Alors je peux voir "Cours validé"
