---
sidebar_position: 1
---

# Architecture Decision Record (ADR)

## Qu’est-ce qu’un Architecture Decision Record ?

L’ADR est un journal de chaque décision et un outil de facilitation très puissant. Les utilisateurs de l’ADR sont les membres actuels et futurs de l’équipe et parfois des cellules d’architecture transverses.

Il prend la forme suivante :

- Qui décide ?
- Quel est le contexte ?
- Quelles sont les options que nous avons identifiées ?
- Quels sont les avantages et inconvénients pour chaque option ?
- Quelle décision est prise et selon quels critères ?
- Quels sont les conseils récoltés au fil de discussions ?
- Quelles sont les conséquences de cette décision ?

Le tableau suivant présente l’intérêt de chacun de ces éléments à la fois à court terme et à long terme :

| Information | Intérêt à court terme | Intérêt à long terme|
| --- | --- | --- |
| Contexte | S’assurer que nous comprenons tous le problème de la même façon | Se souvenir du cadre qui a amené une telle décision|
| Les options et leurs Avantages et inconvénients | Tracer toutes les idées, s’assurer qu’aucune n’est oubliée. Éviter les conversations qui se répètent.  Vous pourrez répondre à votre collègue qui se répète : “Oui, on a eu cette idée, elle est notée ici”. | Voir les pistes envisagées à l’époque.Éventuellement voir qu’une piste n’a pas été imaginée.|
| La décision & les critères | Se mettre d’accord sur les mots. S’assurer que tout le monde comprend la décision de la même façon. | Trace les choix d’archi.Permet de voir quel critère a été mis en avant.|
| Les conseils | Tracer les choses que l’on nous a dit qui n’influencent pas aujourd’hui la décision. Par exemple : Cette DB ne tiendra pas si vous passez les 10 millions de lignes, mais qu’aujourd’hui, seuls 1 million sont prévues. | Avoir des axes de compréhension des limitations de la solution choisie.|
| Les conséquences | Nourrir le backlog | |

Un exemple d'ADR est disponible [ici](1_exemple_simple.md) pour illustrer.

##  Utilisation dans un projet logiciel

- Pour chaque décision, ajouter un nouveau fichier dans le répertoire `..\architecture-decision-records` avec le nom au format `AAAAMMJJ_sujet.md` en utilisant le template fourni `template.md`
- La décision est initiée sur une feature et partagée avec les autres membres de l'équipe au travers d'une MR pour discussion
- La feature peut contenir des expérimentation (POC) permettant d'évaluer les différentes options
- Une fois validée, la décision est mergée sur la branche principale, le code impacté peut également être produit au cours de la même feature
- Les différents README de la solution peuvent faire référence aux ADR afin d'éclairer sur les choixs d'architecture
- Les ADR passées et devenue obsolète peuvent être marquées avec un statut : déprécié ou remplacé

## Ressources

[https://blog.octo.com/architecture-decision-record](https://blog.octo.com/architecture-decision-record)

[https://martinfowler.com/articles/scaling-architecture-conversationally.html](https://martinfowler.com/articles/scaling-architecture-conversationally.html>)

[https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
