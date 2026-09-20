<script setup lang="ts">
import EducationItem from './EducationItem.vue'
import SectionList from './SectionList.vue'

interface Education {
    degree: string
    school: string
    period: string
    description: string
}

const educations: Education[] = [
    {
        degree: 'Diplôme d\'Ingénieur en Informatique',
        school: 'ENSEIRB-MATMECA (Bordeaux, 33)',
        period: '2018 - 2021',
        description: 'Diplôme d\'ingénieur en Informatique avec spécialité Intelligence Artificielle en 3e année.',
  },
  {
      degree: 'Classe Préparatoire aux Grandes Écoles',
      school: 'Lycée Henri Wallon (Valenciennes, 59)',
      period: '2016 - 2018',
      description: 'MPSI/MP* (Mathématiques et Physique) avec option Informatique.',
  },
  {
      degree: 'Baccalauréat Scientifique, mention Très Bien',
      school: 'Lycée Ernest Couteaux (Saint-Amand-les-Eaux, 59)',
      period: '2013 - 2016',
      description: 'Option Sciences de l\'Ingénieur et Spé Mathématiques.',
  },
]
</script>

<template>
    <SectionList title="Formation">
        <EducationItem
            v-for="education in educations"
            :key="education.degree + education.school"
            v-bind="education"
        />
    </SectionList>
</template>
