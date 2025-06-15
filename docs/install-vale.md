---
sidebar_position: 2
---

# 2. Installation et configuration de Vale

Vale est un outil de vérification de style et de grammaire personnalisable. Cela signifie que vous pouvez le configurer pour réviser vos documents exactement comme vous le souhaitez.

Vale utilise le guide de style Vale lors de la révision pour repérer les erreurs et faire des suggestions. Mais vous pouvez y ajouter le guide de style de votre entreprise ou tout autre guide de style si vous le préférez. Il existe des guides de style publics que vous pouvez utiliser comme le guide de style Google, le guide de style Microsoft, et ainsi de suite. Pour ce tutoriel, nous utiliserons le guide de style Microsoft.


## Installation avec WinGet

`winget install errata-ai.Vale`

## Récupérer la définition des styles

Par exemple pour Microsoft : https://github.com/errata-ai/Microsoft/releases/download/v0.7.0/Microsoft.zip

Puis déziper le contenu dans

```text
- docusaurus-tutorial
  //other folders
  - styles
    - Microsoft
  //other folders
```

## Configurer le linter Vale

Créer un fichier `.vale.ini` à la racide de votre projet afin de  configurer le linter

Puis ajouter le code suivant dans le fichier

```
StylesPath = styles

MinAlertLevel = suggestion

[*.md]

BasedOnStyles = Vale, Microsoft
```

- `StylesPath` : Permet de savoir où sont installés les styles
- `MinAlertLevel` : Niveau d'alerte minimal (suggestion, warnings, errors)
- `[*.md]` : Parser uniquement les fichier Markdown
- `BasedOnStyles`: Liste des styles à utiliser

## Parser un fichier 

Executer la commande suivante dans le terminal

`vale intro.md`

Exemple de sortie 

```shell
docs\intro.md
 5:3    warning     Don't use end punctuation in    Microsoft.HeadingPunctuation
                    headings.
 5:14   error       Did you really mean             Vale.Spelling
                    'configurer'?
 6:30   error       Did you really mean 'un'?       Vale.Spelling
 6:43   error       Did you really mean 'moyen'?    Vale.Spelling
 6:52   error       Did you really mean 'publier'?  Vale.Spelling
 6:60   error       Did you really mean 'les'?      Vale.Spelling
 6:88   error       Did you really mean 'sur'?      Vale.Spelling
 6:92   error       Did you really mean 'votre'?    Vale.Spelling
 6:113  error       Did you really mean 'vers'?     Vale.Spelling
 6:118  error       Did you really mean 'votre'?    Vale.Spelling
 6:149  error       Did you really mean 'ligne'?    Vale.Spelling
 6:156  suggestion  Try to keep sentences short (<  Microsoft.SentenceLength
                    30 words).
```

## Inclure le lint dans le pipeline de CI

Ajouter une étape avant le déploiement du site

```yml
# Step 3: Run Vale lint checks.
- name: Vale Lint
  uses: errata-ai/vale-action@reviewdog
  with:
    files: .
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```