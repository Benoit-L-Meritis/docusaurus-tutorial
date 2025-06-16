---
sidebar_position: 5
---

# 5. Améliorer l'expérience de rédaction de la documentation

Pour améliorer l'expérience, vous pouvez faireajouter les configurations suivantes

## Prise en charge de la coloration syntaxique pour les blocs de code

Dans le fichier de configuration `docusaurus.config.ts` dans la section `themeConfig` >> `prism`
ajouter les langages à colorer.

```typescript
const config: Config = {
  // ... autres configurations
  themeConfig: {
    prism: {
      theme: lightCodeTheme,
      darkTheme: darkCodeTheme,
      additionalLanguages: [
        'csharp',
        'gherkin',
        'powershell',
        'json',
        'yaml',
        'docker',
        'sql',
        'php',
        'ruby',
        'go',
        'rust',
        // Ajoutez tous les langages dont vous avez besoin
      ],
    },
  },
};
```

## Prise en charge des diagramme au format Mermaid

**Mermaid** permet d'intégrer des visualisations dans la documentation.

https://mermaid.js.org/

Il s'intègre naturellement dans les fichiers Markdown (GitHub, GitLab, Docusaurus, etc.) pour enrichir la documentation
avec des éléments visuels maintenables en code, évitant les images statiques difficiles à mettre à jour.

Dans le fichier de configuration `docusaurus.config.ts` ajouter les éléments suivants :

A la racine de la configuration ajouter

```typescript
    themes: ['@docusaurus/theme-mermaid'],
    markdown: {
        mermaid: true,
    },
```

Dans la section `themeConfig`, ajouter une entrée pour Mermaid

```typescript
    mermaid: {
      theme: { light: 'neutral', dark: 'dark' },
    },
```

Vous pouvez, si vous le souhaitez, ajouter des options de style pour les rendus des diagrammes.
```typescript
themeConfig: {
  mermaid: {
    theme: {
      light: 'neutral',
      dark: 'dark'
    },
    options: {
      fontFamily: 'Arial',
      fontSize: 16,
      primaryColor: '#ff6b6b',
    },
  },
},
```

## Recommendations d'extensions VS Code

Pour une meilleure expérience de développement, les extensions suivantes sont intéressantes à ajouter à votre projet.

TODO
extension VS CODE