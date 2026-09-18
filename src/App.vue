<script setup lang="ts">
import { ref } from 'vue'
import About from './components/About.vue'
import ExperienceList from './components/ExperienceList.vue'
import EducationList from './components/EducationList.vue'
import ProjectList from './components/ProjectList.vue'
import Contact from './components/Contact.vue'

const sections = [
    { id: 'about', label: 'À propos' },
    { id: 'experience', label: 'Expérience' },
    { id: 'education', label: 'Formation' },
    { id: 'projects', label: 'Projets' },
    { id: 'contact', label: 'Contact' },
]

const activeSection = ref('about')
</script>

<template>
    <div class="main">
        <aside class="sidebar">
            <div class="identity">
                <img class="photo" src="/avatar2.jpg" alt="Julien Miens" />
                <h1>Julien Miens</h1>
                <p class="title">Développeur</p>
            </div>
            <nav class="nav">
                <button
                    v-for="section in sections"
                    :key="section.id"
                    type="button"
                    class="nav-item"
                    :class="{ active: activeSection === section.id }"
                    @click="activeSection = section.id"
                >
                    {{ section.label }}
                </button>
            </nav>
        </aside>

        <main class="content">
            <section v-if="activeSection === 'about'">
                <About />
            </section>
            <section v-else-if="activeSection === 'experience'">
                <ExperienceList />
            </section>
            <section v-else-if="activeSection === 'education'">
                <EducationList />
            </section>
            <section v-else-if="activeSection === 'projects'">
                <ProjectList />
            </section>
            <section v-else-if="activeSection === 'contact'">
                <Contact />
            </section>
        </main>
    </div>
</template>

<style scoped>

.main {
    background-color: black;
    color: white;
    min-height: 100vh;
    display: flex;
}

.sidebar {
    flex: 0 0 260px;
    position: sticky;
    top: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    gap: 3rem;
    padding: 2rem 1.5rem;
    box-sizing: border-box;
    border-right: 1px solid #222;
}

.identity {
    text-align: center;
}

.photo {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    margin: 0 auto 1rem;
}

.identity h1 {
    font-size: 1.3rem;
    margin: 0 0 0.25rem;
}

.title {
    margin: 0;
    color: #aaa;
    font-size: 0.9rem;
}

.nav {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}

.nav-item {
    background: none;
    border: none;
    font: inherit;
    text-align: left;
    color: #ccc;
    font-size: 1.15rem;
    cursor: pointer;
    border-left: 3px solid transparent;
    padding: 0.4rem 0 0.4rem 1rem;
    transition: color 0.15s, border-color 0.15s;
}

.nav-item:hover {
    color: white;
}

.nav-item.active {
    color: var(--accent);
    border-left-color: var(--accent);
    font-weight: 600;
}

.content {
    flex: 1;
    padding: 2rem 3rem;
    box-sizing: border-box;
}

</style>
