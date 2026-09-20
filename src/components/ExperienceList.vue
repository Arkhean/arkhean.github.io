<script setup lang="ts">
import ExperienceItem from './ExperienceItem.vue'
import SectionList from './SectionList.vue'

interface Experience {
    title: string
    company: string
    period: string
    context: string
    achievements: string[]
    stack: string[]
}

const experiences: Experience[] = [
    {
        title: 'Team Leader R&D Backend WEB',
        company: 'TEHTRIS',
        period: 'septembre 2024 - juillet 2026',
        context: 'Gestion d\'une équipe de 4 développeurs backend fonctionnant en Agilité SCRUM et conception d\'une architecture logicielle durable, scalable et hautement disponible pour le cloud pour la refonte de la plateforme «XDR» (SaaS). Modernisation et sécurisation de l\'authentification et de l\'administration des utilisateurs de la nouvelle plateforme web.',
    achievements: [
      'Management technologique et direction technique d\'une équipe backend.',
      'Conception et développement de micro-services Python (**FastAPI**) durables avec **Docker** avec une base de données PostgreSQL et cache Redis et déploiement automatisé par **CI/CD** (GitLab).',
      'Intégration de solutions cloud avec les **services managés AWS** (Cognito et Lambda).',
      'Sécurisation des accès et implémentation de l\'**authentification forte** de la plateforme web (protocole **OpenID Connect**, **OAuth2**, TOTP).',
      'Pilotage des **revues de code** et application des bonnes pratiques d\'ingénierie logicielle. Accompagnement de développeurs juniors en pair programming, en binôme avec un autre développeur senior.',
      'Tests unitaires avec pytest (**TDD**).',
      'Planification et animation des rituels de développement au sein d\'une organisation agile.',
      'Travail en collaboration avec le **Product Owner** afin de participer au découpage et à l’estimation des tâches techniques.',
      'Utilisation de l’IA Claude Code de manière restreinte et sécurisée afin de générer quelques sous-parties spécifiques du code mais sans exposer l’intelligence métier.'],
        stack: ['Python', 'PostgreSQL', 'Redis', 'AWS', 'Pytest', 'Agilité SCRUM', 'Jira'],
  },
  {
    title: 'R&D Software Developer Backend WEB',
    company: 'TEHTRIS',
    period: 'septembre 2021 - août 2024',
    context: "Au sein d’une équipe de 4 développeurs, conception et développement de nouvelles briques applicatives pour la plateforme de cybersécurité «XDR», fournissant aux analystes en cybersécurité (SOC) des outils performants pour le traitement et la résolution d'incidents de sécurité complexes.",
    achievements: [
      "Modernisation de la base de code : réécriture de code **PHP vers Python**.",
      "Conception et développement d’un système intégré de gestion de tickets d'incidents.",
      "Développement de fonctionnalités web transverses pour enrichir l’expérience utilisateur de la plateforme «XDR».",
      "Conception et développement d’**API REST** sécurisées pour l'intégration de connecteurs avec des outils externes (ServiceNow).",
      "Participation active aux travaux d’équipe et au partage de compétences techniques.",
      "Tests unitaires avec pytest (**TDD**).",
    ],
      stack: ["Python", "API", "PostgreSQL", "Pytest"],
    }
]
</script>

<template>
    <SectionList title="Expérience">
        <ExperienceItem
            v-for="experience in experiences"
            :key="experience.title + experience.company"
            v-bind="experience"
        />
    </SectionList>
</template>
