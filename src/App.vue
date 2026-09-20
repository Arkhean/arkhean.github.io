<script setup lang="ts">
import { computed, ref, type Component } from 'vue'
import About from './components/About.vue'
import ExperienceList from './components/ExperienceList.vue'
import EducationList from './components/EducationList.vue'
import ProjectList from './components/ProjectList.vue'
import Contact from './components/Contact.vue'

const sections: { id: string; label: string; component: Component }[] = [
    { id: 'about', label: 'À propos', component: About },
    { id: 'experience', label: 'Expérience', component: ExperienceList },
    { id: 'education', label: 'Formation', component: EducationList },
    { id: 'projects', label: 'Projets', component: ProjectList },
    { id: 'contact', label: 'Contact', component: Contact },
]

const activeSection = ref('about')
const activeComponent = computed(() => sections.find((s) => s.id === activeSection.value)?.component)
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
            <section>
                <component :is="activeComponent" />
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
    min-width: 0;
    padding: 2rem 3rem;
    box-sizing: border-box;
}

@media (max-width: 768px) {
    .main {
        flex-direction: column;
    }

    .sidebar {
        flex: none;
        position: static;
        height: auto;
        gap: 1.5rem;
        padding: 1.5rem 1rem;
        border-right: none;
        border-bottom: 1px solid #222;
    }

    .photo {
        width: 96px;
        height: 96px;
    }

    .nav {
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        gap: 0.25rem 1rem;
    }

    .nav-item {
        font-size: 1rem;
        border-left: none;
        border-bottom: 3px solid transparent;
        padding: 0.4rem 0.25rem;
    }

    .nav-item.active {
        border-bottom-color: var(--accent);
    }

    .content {
        padding: 1.5rem 1rem;
    }
}

</style>
