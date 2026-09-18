<script setup lang="ts">
import ProjectItem from './ProjectItem.vue'
import TypeText from './TypeText.vue'

interface Project {
    title: string
    year: number
    description: string
    stack: string[]
    url: string
}

const projects: Project[] = [
    {
        title: 'Site de Chat via Websocket',
        year: 2026,
        description: 'Projet ayant pour but d\'apprendre le Rust et aussi le fonctionnement des Websockets. J\'ai utilisé l\'IA pour m\'aider à comprendre le Rust en la faisant générer de petites fonctions et en m\'expliquant au fur et à mesure ce qui sert à quoi. La partie HTML est 100% générée par IA sans relecture car hors scope de mon étude. Le serveur a été conteneurisé, la taille de l\'image Docker est minuscule c\'est impressionnant. En vrai le Rust est un langage pas difficile mais très différent dans son approche, il est très intéressant.',
        stack: ['Rust', 'HTML', 'Docker'],
        url: 'https://github.com/Arkhean/rust-websocket-chat',
  },
  {
      title: 'Application mobile de Gestion de Bibliothèque',
      year: 2020,
      description: 'Projet développé pendant le confinement. Le but est de pouvoir enregistrer ses livres dans une bibliothèque virtuelle. Les codes-barres des livres peuvent être scannés avec la caméra pour auto-remplir certaines données. Le but du projet était aussi d\'apprendre le React Native permettant de développer un même code déployable sur Android et iOS. L\'avantage aussi c\'est que le React s\'utilise aussi pour le frontend de site web plus classique.',
      stack: ['React Native', 'Android'],
      url: 'https://github.com/Arkhean/ReadingBook',
  },
  {
      title: 'Pathfinding sur grille hexagonale',
      year: 2019,
      description: 'Affichage d\'une grille hexagonale. Implémentation de l\'algorithme A* pour le calcul du plus court chemin entre 2 cases. On peut rendre des cases interdites en cliquant dessus pour le forcer à recalculer un autre chemin. Le code est assez ancien et absolument pas bien organisé, mais c\'est marrant de jouer avec.',
      stack: ['C'],
      url: 'https://github.com/Arkhean/Hexagonal_Pathfinding',
  },
  {
      title: 'Pyfit, bibliothèque d\'outils de Machine Learning et Deep Learning',
      year: 2020,
      description: 'Projet scolaire, implémenté pour comprendre le fonctionnement et les subtilités sous-jacentes aux réseaux de neurones et autres algorithmes utilisés en intelligence artificielle.',
      stack: ['Python', 'Jupyter'],
      url: 'https://github.com/Arkhean/pyfit-ultime',
  },
  {
      title: 'Mon CV sous forme de site WEB',
      year: 2026,
      description: 'Mon CV codé en VueJS, sympa non ? Le but est d\'apprendre le Vue afin de pourquoi pas devenir Fullstack.',
      stack: ['VueJS'],
      url: 'https://github.com/Arkhean/arkhean.github.io',
  },
]
</script>

<template>
    <h2><TypeText text="Projets personnels" /></h2>
    <p>Surtout un ensemble de curiosités car je suis un peu touche-à-tout, c'est pour ça qu'il n'y a pas que du Python.</p>
    <div class="project-list">
        <ProjectItem
            v-for="project in projects"
            :key="project.url"
            v-bind="project"
        />
    </div>
</template>

<style scoped>

h2 {
    color: var(--accent);
}

.project-list {
    margin-top: 1.5rem;
    margin-right: 20%;
}

</style>
