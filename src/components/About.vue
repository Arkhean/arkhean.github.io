<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'
</script>

<template>
    <SectionTitle text="À propos" />
    <div class="about-content">
        <p class="about-text">
            Activement à la recherche d'un nouveau poste à Lille ou Full Remote, je suis <strong>Développeur Python</strong>
            depuis plus de 5 ans dont 2 en tant que Technical Leader. <br/><br/>

            J'ai de l'expérience dans le
            développement de <strong>Backend</strong> (<strong>FastAPI</strong>, Docker, PostgreSQL) mais je suis aussi un peu touche-à-tout et curieux de nature.

            Ayant des notions dans d'autres technologies (Java, Rust, React), je sais utiliser l'IA (<strong>Claude Code</strong>)
            afin de booster ma productivité et monter en compétence plus rapidement sur de nouveaux domaines.
            Mais je sais aussi faire sans l'IA, car il est important de comprendre ce qu'on code quand même. <br/><br/>

            Proactif, rigoureux, et curieux d'apprendre, n'hésitez pas à me contacter.
        </p>
        <dl class="about-facts">
            <div class="fact">
                <dt>Localisation</dt>
                <dd>Lille, Nord (59)</dd>
            </div>
            <div class="fact">
                <dt>Disponibilité</dt>
                <dd>Immédiatement</dd>
            </div>
            <div class="fact">
                <dt>Langues</dt>
                <dd>Français, Anglais</dd>
            </div>
            <div class="fact">
                <dt>Stack</dt>
                <dd>Python, SQL</dd>
            </div>
        </dl>
    </div>
</template>

<style scoped>

.about-content {
    display: flex;
    gap: 3rem;
    margin-top: 1.5rem;
}

.about-text {
    flex: 1 1 60%;
    line-height: 1.6;
    color: #ddd;
}

.about-facts {
    flex: 1 1 35%;
    margin: 0;
}

.about-facts .fact {
    margin-bottom: 1rem;
}

.about-facts dt {
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: #888;
}

.about-facts dd {
    margin: 0.25rem 0 0;
    color: #eee;
}

@media (max-width: 768px) {
    .about-content {
        flex-direction: column;
        gap: 1.5rem;
    }
}

</style>
