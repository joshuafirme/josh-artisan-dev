<template>
    <div :class="['retro-system', isDark ? 'dark-theme' : '']">
        <nav class="navbar navbar-expand-lg fixed-top shadow-sm"
            :class="isDark ? 'navbar-dark bg-retro-dark' : 'navbar-light bg-retro-light'">
            <div class="container">
                <a class="navbar-brand fw-bold chunky-text" href="#">JOSH_DEV_SYSTEM_V1</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav ms-auto align-items-center">
                        <li class="nav-item"><a class="nav-link chunky-text" href="#about">BIOGRAPHY</a></li>
                        <li class="nav-item"><a class="nav-link chunky-text" href="#skills">ARSENAL</a></li>
                        <li class="nav-item"><a class="nav-link chunky-text" href="#projects">MISSIONS</a></li>
                        <li class="nav-item ms-3">
                            <button @click="toggleTheme" class="btn btn-outline-retro theme-toggle">
                                <i :class="isDark ? 'bi bi-controller text-warning' : 'bi bi-controller'"></i>
                                *</button>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>

        <section id="hero" class="min-vh-100 d-flex align-items-center position-relative retro-hero-terminal">

            <div class="crt-overlay"></div>

            <div class="container text-center text-md-start position-relative z-3">
                <div class="row align-items-center">
                    <div class="col-lg-8 terminal-content">

                        <span class="text-secondary fw-bold tracking-wide chunky-text">
                            <span v-if="showCursor1" class="cursor-blink">&gt;</span> {{ typedText1 }}
                        </span>

                        <h1 class="display-3 fw-bolder mt-3 mb-4 chunky-text terminal-glow text-secondary">
                            {{ typedText2 }} <span class="text-primary">{{ typedText3 }}</span><span v-if="showCursor2"
                                class="cursor-blink">_</span>
                        </h1>

                        <p class="lead mb-4 opacity-75 chunky-text text-retro-white">
                            {{ typedText4 }}<span v-if="showCursor3" class="cursor-blink">_</span>
                        </p>

                        <div class="vibe-code-block p-3 mb-5 fade-in" v-if="showButtons">
                            <code>
            <span class="text-muted">// DAILY_ROUTINE.JS</span><br>
            <span class="text-secondary">if</span> (josh.coffeeLevel &lt; <span class="text-secondary">1</span>) {<br>
            &nbsp;&nbsp;josh.brain.<span class="text-primary">throwException</span>();<br>
            &nbsp;&nbsp;ai_copilot.<span class="text-primary">takeTheWheel</span>();<br>
            } <span class="text-secondary">else</span> {<br>
            &nbsp;&nbsp;josh.<span class="text-primary">deployAwesomeFeatures</span>();<br>
            }
        </code>
                        </div>

                        <div class="d-flex gap-3 justify-content-center justify-content-md-start fade-in"
                            v-if="showButtons">
                            <a href="#projects" class="btn btn-primary btn-lg chunky-text px-4">START GAME</a>
                            <a href="#about" class="btn btn-outline-retro btn-lg chunky-text px-4">OPTIONS</a>
                        </div>

                    </div>

                    <div class="col-lg-4 text-center mt-5 mt-lg-0 fade-in" v-if="showAvatar">
                        <div class="pixel-art-avatar terminal-glow">

                            <img src="@/assets/images/profile.jpg" alt="Josh Profile" class="retro-profile-img mb-3">

                            <p class="chunky-text mt-2 text-retro-white">PLAYER_1 (JOSH)</p>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <section id="about" class="py-5 bg-retro-panel">
            <div class="container py-5">
                <div class="row align-items-center gap-5">
                    <div class="col-lg-12" data-aos="fade-left" data-aos-duration="1000">
                        <div class="retro-dialogue-box p-4 rounded-4 shadow">
                            <h2 class="fw-bold mb-4 chunky-text text-retro-white">BIOGRAPHY_LOG</h2>
                            <p class="fs-5 opacity-75 chunky-text text-retro-white">
                                &gt; DEV_JOSH BASED IN NASUGBU, CALABARZON, PHILIPPINES. PASSIONATE ABOUT SOLVING
                                COMPLEX CODE_PUZZLES. EXCELS IN BRIDGING BACKEND POWER AND FRONTEND INTUITION. ALSO
                                ENJOYS 3D MODELING AUTOMOTIVE CONCEPTS IN ZBRUSH_
                            </p>
                            <p class="fs-5 opacity-75 chunky-text text-retro-white">
                                &gt; FOCUS: WRITE CLEAN, MAINTAINABLE CODE. CONTINUOUS LEARNING & SKILL BOOSTING.
                                EXPLORING AI INTEGRATIONS_
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills" class="py-5" :class="isDark ? 'bg-darker' : 'bg-light'">
            <div class="container py-5">
                <div class="text-center mb-5" data-aos="fade-up">
                    <h2 class="fw-bold chunky-text">ARSENAL</h2>
                    <p class="opacity-75 chunky-text">TECHNOLOGIES JOSH HAS MASTERED OR EXPLORED_</p>
                </div>

                <div class="row g-4">
                    <div class="col-md-6" data-aos="fade-up" data-aos-delay="100">
                        <div class="card h-100 border-retro shadow-sm custom-retro-card">
                            <div class="card-body p-4">
                                <h4 class="card-title fw-bold mb-4 text-primary chunky-text">
                                    <i class="bi bi-star-fill me-2 pixelated-icon"></i> PROFICIENT
                                </h4>
                                <div class="d-flex flex-wrap gap-2">
                                    <span class="badge bg-primary px-3 py-2 chunky-text text-retro-white"
                                        v-for="skill in proficientSkills" :key="skill">
                                        {{ skill }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-md-6" data-aos="fade-up" data-aos-delay="200">
                        <div class="card h-100 border-retro shadow-sm custom-retro-card">
                            <div class="card-body p-4">
                                <h4 class="card-title fw-bold mb-4 text-info chunky-text">
                                    <i class="bi bi-book-half me-2 pixelated-icon"></i> KNOWLEDGEABLE
                                </h4>
                                <div class="d-flex flex-wrap gap-2">
                                    <span class="badge bg-secondary px-3 py-2 chunky-text text-retro-white"
                                        v-for="skill in knowledgeSkills" :key="skill">
                                        {{ skill }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Missions / Projects Section -->
        <section id="projects" class="py-5 bg-retro-missions">
            <div class="container py-5">
                <div class="text-center mb-5" data-aos="fade-up">
                    <h2 class="fw-bold chunky-text text-retro-white">MISSIONS</h2>
                    <p class="opacity-75 chunky-text text-retro-white">COMPLETED & DEPLOYED_PROJECTS_</p>
                </div>

                <div class="row g-4 justify-content-center">
                    <div class="col-lg-4 col-md-6" v-for="(project, index) in projects" :key="index" data-aos="zoom-in"
                        :data-aos-delay="index * 100">
                        <div
                            class="card h-100 border-retro shadow-sm custom-retro-card mission-card d-flex flex-column">
                            <div class="card-body p-4 flex-grow-1">
                                <div class="mb-3 d-flex justify-content-between align-items-center">
                                    <span class="mission-level chunky-text text-primary">MISSION_0{{ index + 1 }}</span>
                                    <i :class="project.icon + ' display-5 text-primary pixelated-icon'"></i>
                                </div>
                                <h5 class="card-title fw-bold chunky-text text-retro-white">{{ project.title }}</h5>

                                <div class="dummy-score chunky-text text-secondary mt-2 mb-3">
                                    <i class="bi bi-clock-history me-1"></i> {{ project.date }}
                                </div>

                                <p class="card-text opacity-75 mt-3 chunky-text text-retro-white"
                                    style="font-size: 0.55rem;">{{ project.description }}</p>
                            </div>

                            <div class="card-footer bg-transparent border-0 p-4 pt-0">
                                <div class="d-flex flex-wrap gap-1 mb-4">
                                    <span class="badge border border-retro text-body chunky-text text-retro-white"
                                        v-for="tech in project.stack" :key="tech">{{ tech }}</span>
                                </div>

                                <!-- Contextual Button Action -->
                                <button v-if="project.isInternal" @click="openScreenshotModal(project.screenshots)"
                                    class="btn btn-outline-retro w-100 chunky-text d-flex justify-content-center align-items-center gap-2">
                                    <span>VIEW_SCREENSHOTS</span> <i class="bi bi-eye"></i>
                                </button>

                                <a v-else :href="project.url" target="_blank"
                                    class="btn btn-outline-retro w-100 chunky-text d-flex justify-content-center align-items-center gap-2">
                                    <span>ACCESS_SYSTEM</span> <i class="bi bi-box-arrow-up-right"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <footer class="py-4 text-center bg-retro-footer" :class="isDark ? 'bg-darker' : 'bg-light'">
            <div class="container">
                <p class="mb-0 opacity-75 chunky-text text-retro-white">© {{ new Date().getFullYear() }}
                    JOSH_DEV_SYSTEM_V1 | BUILT_WITH_PHP_LARAVEL_VUEJS_BOOSTSTRAP5. &gt;&gt; POWER_ON_</p>
            </div>
        </footer>
    </div>

    <!-- Retro Screenshot Modal Container -->
    <div class="modal fade" id="screenshotModal" tabindex="-1" aria-hidden="true" data-bs-theme="dark">
        <div class="modal-dialog modal-xl modal-dialog-centered">
            <div class="modal-content retro-dialogue-box border-retro">
                <div class="modal-header border-bottom border-primary p-3">
                    <h5 class="modal-title chunky-text text-primary">SECURE_IMAGE_VIEWER.EXE</h5>
                    <button type="button" class="btn-close bg-primary" data-bs-dismiss="modal"
                        aria-label="Close"></button>
                </div>
                <div class="modal-body p-4 bg-dark">
                    <div class="d-flex flex-column gap-4">
                        <div v-for="(img, idx) in activeScreenshots" :key="idx" class="text-center">
                            <div class="text-start text-secondary small mb-2 chunky-text">// PANEL_DUMP_0{{ idx + 1 }}
                            </div>
                            <img :src="img" alt="Internal System Screenshot"
                                class="img-fluid border border-primary shadow-sm" style="image-rendering: pixelated;">
                        </div>
                    </div>
                </div>
                <div class="modal-footer border-top border-primary p-3">
                    <button type="button" class="btn btn-primary chunky-text"
                        data-bs-dismiss="modal">CLOSE_VIEWER</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

// --- THEME STATE ---
const isDark = ref(false);

// --- TYPEWRITER STATE ---
const typedText1 = ref('');
const typedText2 = ref('');
const typedText3 = ref('');
const typedText4 = ref('');

const showCursor1 = ref(true);
const showCursor2 = ref(false);
const showCursor3 = ref(false);

const showButtons = ref(false);
const showAvatar = ref(false);

// Target Strings to type out
const str1 = "SYS_INIT: OK. PRESS START.";
const str2 = "JOSH // UPTIME: 4 YEARS //";
const str3 = "SOFTWARE DEVELOPER";
const str4 = "LEVEL 1: BUILDING ROBUST APPLICATIONS. ARCHITECTING LARAVEL BACKENDS, DESIGNING VUE.JS FRONTS, AI SOLUTIONS & MORE. CLEAN, MAINTAINABLE CODE.";

// --- DATA ---
const proficientSkills = [
    'PHP', 'Laravel', 'JavaScript', 'jQuery', 'Node.js',
    'Vue.js', 'MySQL', 'Flutter', 'Firebase', 'REST APIs',
    'AI Integration', 'Git', 'HTML & CSS', 'Bootstrap 5'
];

const knowledgeSkills = [
    'React', 'Express JS', 'MongoDB', 'Tailwind', 'Java', 'C#', 'MSSQL'
];

import sosImg from '../assets/images/screenshots/sos.png';
import sos1Img from '../assets/images/screenshots/sos1.png';

const projects = [
    {
        title: 'PledgeSync and AutoBill Engine',
        date: 'MAY 2026 — PRESENT',
        description: 'A scalable Laravel and MySQL application that automates monthly payment collections via Paynamics. Features include anti-duplicate (idempotency) protections, background batch processing for thousands of records, automated retry logic, and Excel data synchronization.',
        icon: 'bi bi-shield-lock',
        isInternal: true,
        screenshots: [sosImg, sos1Img],
        stack: ['Laravel', 'MySQL', 'REST APIs', 'Paynamics']
    },
    {
        title: 'GV_FLORIDA_BUS_SYS',
        date: 'JUN 2025 — MAR 2026',
        description: 'FULL-STACK BOOKING & MANAGEMENT. WEB AND KIOSK RESERVATIONS, DYNAMIC SEAT ALLOCATION, PAYNAMICS INTEGRATION.',
        icon: 'bi bi-bus-front',
        url: 'https://www.gvfloridatransportinc.com/',
        stack: ['Laravel', 'Android', 'MySQL', 'REST APIs', 'JS', 'CSS']
    },
    {
        title: 'MAKI_SERVICES',
        date: 'OCT 2024 — FEB 2025',
        description: 'ALL-IN-ONE HOUSEHOLD SERVICE PLATFORM. CLEAING, REPAIRS, AND MAINTENANCE BOOKING WITH PAYMONGO INTEGRATION.',
        icon: 'bi bi-wrench-adjustable',
        url: 'https://makiservices.app/',
        stack: ['Laravel', 'Vue.js', 'MySQL', 'REST APIs', 'JS']
    },
    {
        title: 'DARTEK_POWER_TOOLS',
        date: 'OCT 2023 — FEB 2024',
        description: 'COMPREHENSIVE STORE & TOOL LOCATOR. INTEGRATED WITH A PREVENTIVE MAINTENANCE SCHEDULING (PMS) RECORDING SYSTEM.',
        icon: 'bi bi-lightning-charge',
        url: 'https://dartek.app/',
        stack: ['Laravel', 'Flutter', 'Vue.js', 'MySQL', 'JS']
    },
];

const activeScreenshots = ref([]);
const openScreenshotModal = (images) => {
  activeScreenshots.value = images;
  if (modalInstance) {
    modalInstance.show();
  }
};

// --- METHODS ---
const toggleTheme = () => {
    isDark.value = !isDark.value;
    updateThemeAttr();
    localStorage.setItem('portfolio-theme', isDark.value ? 'dark' : 'light');
};

const updateThemeAttr = () => {
    document.documentElement.setAttribute('data-bs-theme', isDark.value ? 'dark' : 'light');
};

// Reusable Typewriter Function
const typeString = (targetString, reactiveVar, speed, callback) => {
    let i = 0;
    const interval = setInterval(() => {
        if (i < targetString.length) {
            reactiveVar.value += targetString.charAt(i);
            i++;
        } else {
            clearInterval(interval);
            if (callback) callback();
        }
    }, speed);
};

// Orchestrates the Boot-up animation
const startBootSequence = () => {
    // 1. Type system init
    typeString(str1, typedText1, 50, () => {
        showCursor1.value = false;
        showCursor2.value = true;

        // 2. Wait a beat, type "JOSH IS NOW A"
        setTimeout(() => {
            typeString(str2, typedText2, 50, () => {

                // 3. Type "SOFTWARE DEVELOPER"
                typeString(str3, typedText3, 50, () => {
                    showCursor2.value = false;
                    showCursor3.value = true;

                    // 4. Wait a beat, type the paragraph (faster)
                    setTimeout(() => {
                        typeString(str4, typedText4, 15, () => {

                            // 5. Sequence complete, show UI
                            showButtons.value = true;
                            showAvatar.value = true;
                        });
                    }, 300);
                });
            });
        }, 300);
    });
};

let modalInstance = null;

// --- LIFECYCLE ---
onMounted(() => {
    if (typeof AOS !== 'undefined') {
        AOS.init({ once: true, offset: 50 });
    }

    const savedTheme = localStorage.getItem('portfolio-theme');
    if (savedTheme === 'dark') {
        isDark.value = true;
    } else if (!savedTheme && window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
        isDark.value = true;
    }

    updateThemeAttr();

    // Kick off the animation when component mounts
    startBootSequence();

    const modalEl = document.getElementById('screenshotModal');
    if (modalEl && typeof bootstrap !== 'undefined') {
        modalInstance = new bootstrap.Modal(modalEl);
    }
});

</script>