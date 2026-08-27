<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import {
    ArrowUpRight,
    Briefcase,
    Building2,
    Calculator,
    Check,
    CheckCircle2,
    ChevronRight,
    Clock,
    Code2,
    Cpu,
    Database,
    ExternalLink,
    FileCode2,
    GitBranch,
    Globe,
    GraduationCap,
    HeartHandshake,
    Layers,
    Linkedin,
    Mail,
    MapPin,
    Moon,
    Phone,
    Rocket,
    Server,
    ShieldCheck,
    Sparkles,
    Sun,
    Terminal,
    UserCheck,
    Zap,
} from 'lucide-vue-next';
import { onMounted, ref } from 'vue';

// Dark mode state
const isDark = ref(false);

const toggleDarkMode = () => {
    isDark.value = !isDark.value;
    if (isDark.value) {
        document.documentElement.classList.add('dark');
        localStorage.setItem('theme', 'dark');
    } else {
        document.documentElement.classList.remove('dark');
        localStorage.setItem('theme', 'light');
    }
};

onMounted(() => {
    const savedTheme = localStorage.getItem('theme');
    const systemDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
    if (savedTheme === 'dark' || (!savedTheme && systemDark)) {
        isDark.value = true;
        document.documentElement.classList.add('dark');
    } else {
        isDark.value = false;
        document.documentElement.classList.remove('dark');
    }
});

// Personal Info
const profile = {
    name: 'Kashif Abbas',
    title: 'Senior Full-Stack Web Developer',
    experienceYears: '7+',
    location: 'Multan, Pakistan',
    timezone: 'UTC+5 · Overlapping with UK, EU & US East Hours',
    availability: 'Available for Full-Time Remote Roles & International Contracts',
    email: 'kashifgabol512@gmail.com',
    phone: '+923027772202',
    linkedin: 'https://www.linkedin.com/in/kashifgabol/',
    website: 'https://autometasoft.com',
    image: '/images/kashif.jpg',
    education: 'BSCS (Bachelor of Science in Computer Science)',
    languages: [
        { name: 'English', level: 'Fluent / Professional Working' },
        { name: 'Urdu', level: 'Native' },
        { name: 'Arabic', level: 'Conversational' },
    ],
};

const summary =
    'Senior Full-Stack Software Engineer with 7+ years of expertise architecting high-traffic enterprise web applications, SaaS platforms, and distributed systems. Specialist in Laravel (PHP 8+), Vue.js 3, Inertia.js, and complex relational databases. Proven track record engineering mission-critical Hospital Management Systems (HMS), Multi-Branch ERPs, POS platforms, Fintech Calculators, and Custom Client Portals for international companies across the UK, UAE, Saudi Arabia, and Pakistan.';

// Developer Skills organized by domain
const skillDomains = [
    {
        title: 'Backend Engineering',
        icon: Server,
        skills: [
            { name: 'Laravel (10 & 11) & PHP 8.2+', level: 96 },
            { name: 'RESTful API Design & Architecture', level: 94 },
            { name: 'Authentication & RBAC Security', level: 92 },
            { name: 'Queues, Jobs & Background Workers', level: 88 },
            { name: 'PHPUnit & Automated Testing', level: 85 },
        ],
    },
    {
        title: 'Frontend & UI Architecture',
        icon: Code2,
        skills: [
            { name: 'Vue.js 3 (Composition API)', level: 94 },
            { name: 'Inertia.js SPA Architecture', level: 92 },
            { name: 'Tailwind CSS & Modern Design Systems', level: 95 },
            { name: 'TypeScript & Modern JavaScript (ES6+)', level: 89 },
            { name: 'Vite, State Management & Tooling', level: 88 },
        ],
    },
    {
        title: 'Database & DevOps',
        icon: Database,
        skills: [
            { name: 'MySQL & PostgreSQL Schema Design', level: 92 },
            { name: 'Query Optimization & Indexing', level: 90 },
            { name: 'Git, GitHub Actions & CI/CD', level: 91 },
            { name: 'Linux Server Setup & Nginx Config', level: 85 },
            { name: 'Third-Party API Integrations', level: 93 },
        ],
    },
];

// Work Experiences
const experiences = [
    {
        id: 'exp-1',
        role: 'Lead Full-Stack Web Developer',
        company: 'AutoMeta Software Solutions',
        location: 'Multan, Pakistan (Serving International Clients)',
        period: 'March 2020 – Present',
        description:
            'Architecting, deploying, and maintaining business-critical enterprise applications, automated accounting platforms, and custom ERP systems for global and domestic enterprises.',
        bullets: [
            'Architected and delivered multi-tenant Hospital Management Systems (HMS) handling thousands of real-time clinical, billing, and pharmaceutical transactions.',
            'Engineered custom ERP & inventory platforms with real-time stock sync across multiple regional branches.',
            'Developed high-precision customs tax computation application (PTA Duty Calculator) processing dynamic foreign exchange rates and customs brackets.',
            'Optimized complex database queries in MySQL/PostgreSQL, reducing API response times by up to 45%.',
            'Implemented robust CI/CD and PHPUnit testing pipelines ensuring 99.9% production availability.',
        ],
        tags: ['Laravel', 'Vue.js 3', 'Inertia.js', 'REST APIs', 'MySQL', 'Tailwind CSS', 'PHPUnit', 'Docker'],
    },
    {
        id: 'exp-2',
        role: 'Full-Stack Web Developer',
        company: 'Sharjah Web & Advertising Projects',
        location: 'Sharjah, United Arab Emirates (Remote / Contract)',
        period: '2016 – 2020',
        description:
            'Engineered custom corporate portals, client portals, and bespoke web platforms for prominent enterprises across the UAE, UK, and Saudi Arabia.',
        bullets: [
            'Engineered responsive web applications for international corporate clients including Lead Craft Advertising (Dubai), Al Shan Business Group (Sharjah), and Awafi Pharma (KSA).',
            'Integrated secure customer inquiry gateways, quote calculation tools, and administrative dashboards.',
            'Maintained and refactored legacy PHP codebases into modular, maintainable MVC architectures.',
        ],
        tags: ['PHP', 'JavaScript', 'Bootstrap', 'MySQL', 'Web Portals', 'REST APIs'],
    },
];

// Featured Projects with updated accurate URLs
const projects = [
    {
        id: 'proj-1',
        title: 'Hospital Management System (HMS)',
        subtitle: 'Enterprise SaaS Healthcare Platform',
        badge: 'Enterprise SaaS',
        category: 'Full-Stack Web Application',
        description:
            'Mission-critical healthcare platform managing patient electronic medical records (EMR), doctor appointment schedules, OP/IP billing workflows, pharmacy stock management, and pathology lab reporting.',
        tech: ['Laravel', 'Vue.js 3', 'Inertia.js', 'MySQL', 'Tailwind CSS'],
        links: [
            { label: 'National Hospital Portal', url: 'https://hms.autometasoft.com' },
            { label: 'Qasim Hospital Portal', url: 'https://hms.autometasoft.com' },
        ],
        metrics: 'Used daily by 200+ healthcare staff with real-time lab & billing sync',
    },
    {
        id: 'proj-2',
        title: 'Business Management & Inventory ERP',
        subtitle: 'Enterprise Resource Planning & Multi-Store Inventory',
        badge: 'Live Production ERP',
        category: 'Full-Stack ERP System',
        description:
            'Custom enterprise resource planning platform engineered for manufacturing, import/export, and distribution companies to streamline sales orders, multi-warehouse inventory, customer invoicing, and financial balance sheets.',
        tech: ['Laravel', 'Vue.js', 'Tailwind CSS', 'MySQL', 'REST APIs'],
        links: [
            { label: 'UK Salts Inventory', url: 'https://uksaltsinventory.com/' },
            { label: 'AR Company Portal', url: 'https://arapp.autometasoft.com' },
        ],
        metrics: 'Automates thousands of monthly SKU movements and sales ledger entries',
    },
    {
        id: 'proj-3',
        title: 'PTA Mobile Duty & Tax Calculator',
        subtitle: 'Fintech Customs Tariff & Regulatory Tax Engine',
        badge: 'Fintech Tax Engine',
        category: 'Regulatory Calculation App',
        description:
            'High-precision tax computing application that calculates Pakistan Telecommunication Authority (PTA) and customs import duties on mobile devices with live C&F USD brackets, CNIC vs Passport status differentials, and real-time forex conversions.',
        tech: ['Laravel', 'Vue.js 3', 'REST APIs', 'Tailwind CSS', 'MySQL'],
        links: [
            { label: 'Live PTA Calculator', url: 'https://ptatax.autometasoft.com' },
        ],
        metrics: 'Processes instant tariff lookups with multi-tier regulatory logic',
    },
    {
        id: 'proj-4',
        title: 'Multi-Store ERP & POS Systems',
        subtitle: 'Retail & Distribution Point-of-Sale Applications',
        badge: 'Retail POS Platform',
        category: 'Full-Stack Retail System',
        description:
            'Fast, barcode-enabled Point of Sale and inventory control systems powering multi-location retail stores and distributors with offline resilience, daily cash drawer reconciliations, and instant receipt generation.',
        tech: ['Laravel', 'Vue.js', 'Inertia.js', 'Tailwind', 'PHPUnit'],
        highlights: ['VapeAuro (Lahore)', 'Raza General Store (Alipur)', 'Vape Land (Multan)', 'Task Management App'],
        metrics: 'Engineered for sub-100ms checkout latency and barcode accuracy',
    },
    {
        id: 'proj-5',
        title: 'Corporate Web Applications & Client Portals',
        subtitle: 'Bespoke Enterprise Web Platforms & Portals',
        badge: 'Corporate Portals',
        category: 'Enterprise Web Development',
        description:
            'Scalable corporate web applications and customer self-service portals engineered for multinational service providers, software enterprises, and industrial manufacturing groups.',
        tech: ['PHP', 'Vue.js', 'JavaScript', 'HTML5/CSS3', 'Bootstrap'],
        links: [
            { label: 'UK Salts Official', url: 'https://www.uksalts.net' },
            { label: 'JSoft Hub', url: 'https://www.jsofthub.com' },
            { label: 'Al Hadi Services', url: 'https://www.alhadi-services.com' },
            { label: 'MKG', url: 'https://mkg.com.pk' },
            { label: 'Ruposh Group', url: 'https://ruposh.group' },
        ],
        metrics: 'High-availability corporate platforms serving international audiences',
    },
];

// Services built for international clients
const devServices = [
    {
        title: 'Custom SaaS & Web Application Development',
        description: 'End-to-end full-lifecycle software engineering from relational database design to intuitive frontend interfaces using modern Laravel & Vue.js 3 / Inertia.js architecture.',
        features: [
            'Clean MVC, Repository Pattern & Service Architecture',
            'Secure Role-Based Access Control (RBAC) & Multi-Tenancy',
            'Blazing Fast SPA experience with Inertia.js & Vue 3',
            'Production-ready, testable & maintainable codebase',
        ],
        icon: Code2,
        badge: 'Full-Stack Architecture',
    },
    {
        title: 'Enterprise ERP, HMS & POS Solutions',
        description: 'Bespoke enterprise-grade systems designed to handle complex workflows, multi-branch operations, real-time inventory tracking, and financial ledgers with zero data loss.',
        features: [
            'Hospital Management Systems (HMS) & EMR Modules',
            'Multi-Warehouse Inventory & Supply Chain Tracking',
            'Automated Invoicing, Financial Reports & Ledgers',
            'Custom POS with Barcode & Thermal Receipt Engine',
        ],
        icon: Building2,
        badge: 'Enterprise Software',
    },
    {
        title: 'RESTful API Design & Third-Party Integrations',
        description: 'Building secure, scalable, and fully documented RESTful APIs that connect mobile apps, frontends, and external third-party platforms with high concurrency support.',
        features: [
            'Stateless JSON REST APIs with Sanctum/Passport auth',
            'Payment Gateway Integrations (Stripe, PayPal, Local)',
            'Webhook Listeners, Queued Jobs & Redis Caching',
            'Comprehensive Postman / OpenAPI Documentation',
        ],
        icon: Server,
        badge: 'API & Integration',
    },
    {
        title: 'Database Architecture & Query Optimization',
        description: 'Designing optimized relational database schemas, identifying performance bottlenecks, and rewriting sluggish queries to handle massive datasets effortlessly.',
        features: [
            'Advanced MySQL & PostgreSQL Schema Design',
            'Query Profiling, Index Optimization & Caching',
            'Safe Data Migrations, Seeding & Backup Pipelines',
            'Reduced server load and sub-second query response',
        ],
        icon: Database,
        badge: 'Database Optimization',
    },
];

// Engineering Pillars for international clients
const engineeringPillars = [
    {
        icon: ShieldCheck,
        title: 'Enterprise Reliability',
        description: 'Writing strictly typed, secure, and test-covered PHP/TypeScript code following PSR standards and security best practices.',
    },
    {
        icon: Zap,
        title: 'Performance Obsessed',
        description: 'Optimizing database queries, caching strategies, and frontend bundle sizes for instant page loads and fluid user interactions.',
    },
    {
        icon: Clock,
        title: 'Global Timezone Flexibility',
        description: 'Comfortable collaborating with distributed international engineering teams across UK, European, Middle Eastern, and US Eastern hours.',
    },
    {
        icon: HeartHandshake,
        title: 'Clear Asynchronous Communication',
        description: 'Providing proactive daily updates, structured Git commits, well-documented code, and transparent milestones.',
    },
];

// Tech stack badges
const techStack = [
    { name: 'Laravel 10/11', platform: 'Backend PHP Framework' },
    { name: 'Vue.js 3', platform: 'Progressive Frontend' },
    { name: 'Inertia.js', platform: 'Modern Monolith SPA' },
    { name: 'PHP 8.2+', platform: 'Modern Typed Backend' },
    { name: 'MySQL / Postgres', platform: 'Relational Database' },
    { name: 'Tailwind CSS', platform: 'Design System & UI' },
    { name: 'TypeScript', platform: 'Type-Safe Frontend' },
    { name: 'REST APIs', platform: 'Microservices & Endpoints' },
    { name: 'PHPUnit', platform: 'Automated Testing' },
    { name: 'Git & GitHub', platform: 'Version Control & CI/CD' },
    { name: 'Linux / Nginx', platform: 'Server Deployment' },
    { name: 'Vite', platform: 'Next-Gen Asset Bundler' },
];

// Contact state
const contactCopied = ref(false);
const copyEmail = () => {
    navigator.clipboard.writeText(profile.email);
    contactCopied.value = true;
    setTimeout(() => {
        contactCopied.value = false;
    }, 2500);
};
</script>

<template>
    <Head title="Kashif Abbas | Senior Full-Stack Software Engineer">
        <link rel="icon" type="image/png" href="/icon.png" />
        <link rel="apple-touch-icon" href="/icon.png" />
        <link rel="preconnect" href="https://fonts.googleapis.com" />
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
        <link
            href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap"
            rel="stylesheet"
        />
    </Head>

    <div
        class="min-h-screen bg-slate-50 text-slate-900 transition-colors duration-300 dark:bg-[#070b12] dark:text-slate-100 font-['Plus_Jakarta_Sans',sans-serif] selection:bg-indigo-500 selection:text-white"
    >
        <!-- Top Sticky Header -->
        <header
            class="sticky top-0 z-50 backdrop-blur-xl bg-white/85 dark:bg-[#070b12]/85 border-b border-slate-200/80 dark:border-slate-800/80 transition-colors"
        >
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between gap-4">
                <!-- Brand / Logo -->
                <a href="#" class="flex items-center gap-3 group">
                    <div class="relative">
                        <img
                            :src="profile.image"
                            alt="Kashif Abbas"
                            class="w-11 h-11 rounded-full object-cover ring-2 ring-indigo-500/80 shadow-md group-hover:scale-105 transition-transform"
                        />
                        <span
                            class="absolute bottom-0 right-0 w-3.5 h-3.5 bg-emerald-500 border-2 border-white dark:border-[#070b12] rounded-full animate-pulse"
                        ></span>
                    </div>
                    <div>
                        <div class="flex items-center gap-2">
                            <h1 class="text-base sm:text-lg font-extrabold tracking-tight text-slate-900 dark:text-white leading-tight">
                                Kashif Abbas
                            </h1>
                            <span class="hidden sm:inline-flex px-2 py-0.5 text-[10px] font-bold rounded-full bg-indigo-50 text-indigo-700 dark:bg-indigo-950/70 dark:text-indigo-300 border border-indigo-200 dark:border-indigo-800">
                                Senior Eng
                            </span>
                        </div>
                        <p class="text-xs font-medium text-slate-500 dark:text-slate-400">
                            Full-Stack Web Architect · Laravel & Vue.js
                        </p>
                    </div>
                </a>

                <!-- Nav Links -->
                <nav class="hidden md:flex items-center gap-1 bg-slate-100/70 dark:bg-slate-900/60 p-1.5 rounded-full border border-slate-200/70 dark:border-slate-800/70">
                    <a
                        href="#experience"
                        class="px-4 py-1.5 text-xs font-semibold rounded-full text-slate-600 hover:text-slate-900 hover:bg-white dark:text-slate-400 dark:hover:text-white dark:hover:bg-slate-800 shadow-sm transition-all"
                        >Experience</a
                    >
                    <a
                        href="#projects"
                        class="px-4 py-1.5 text-xs font-semibold rounded-full text-slate-600 hover:text-slate-900 hover:bg-white dark:text-slate-400 dark:hover:text-white dark:hover:bg-slate-800 shadow-sm transition-all"
                        >Projects</a
                    >
                    <a
                        href="#skills"
                        class="px-4 py-1.5 text-xs font-semibold rounded-full text-slate-600 hover:text-slate-900 hover:bg-white dark:text-slate-400 dark:hover:text-white dark:hover:bg-slate-800 shadow-sm transition-all"
                        >Skills</a
                    >
                    <a
                        href="#services"
                        class="px-4 py-1.5 text-xs font-semibold rounded-full text-slate-600 hover:text-slate-900 hover:bg-white dark:text-slate-400 dark:hover:text-white dark:hover:bg-slate-800 shadow-sm transition-all"
                        >Services</a
                    >
                    <a
                        href="#contact"
                        class="px-4 py-1.5 text-xs font-semibold rounded-full text-slate-600 hover:text-slate-900 hover:bg-white dark:text-slate-400 dark:hover:text-white dark:hover:bg-slate-800 shadow-sm transition-all"
                        >Contact</a
                    >
                </nav>

                <!-- Right Actions -->
                <div class="flex items-center gap-3">
                    <a
                        :href="profile.linkedin"
                        target="_blank"
                        class="hidden sm:inline-flex items-center gap-1.5 px-3.5 py-2 text-xs font-semibold rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 dark:bg-slate-800/80 dark:hover:bg-slate-800 dark:text-slate-200 transition-colors"
                    >
                        <Linkedin class="w-3.5 h-3.5 text-blue-600" />
                        <span>LinkedIn</span>
                    </a>

                    <a
                        :href="`mailto:${profile.email}`"
                        class="inline-flex items-center gap-2 px-4 py-2 text-xs font-bold rounded-xl bg-indigo-600 text-white hover:bg-indigo-500 shadow-md shadow-indigo-600/30 transition-all hover:scale-[1.02]"
                    >
                        <Mail class="w-3.5 h-3.5" />
                        <span>Hire Me</span>
                    </a>

                    <!-- Dark Mode Toggle -->
                    <button
                        @click="toggleDarkMode"
                        aria-label="Toggle Theme"
                        class="p-2.5 rounded-xl bg-slate-100 hover:bg-slate-200 text-slate-700 dark:bg-slate-800/80 dark:hover:bg-slate-800 dark:text-slate-200 transition-colors"
                    >
                        <Sun v-if="isDark" class="w-4 h-4 text-amber-400" />
                        <Moon v-else class="w-4 h-4 text-slate-700" />
                    </button>
                </div>
            </div>
        </header>

        <!-- Hero Section -->
        <section class="relative overflow-hidden pt-12 pb-20 lg:pt-20 lg:pb-28">
            <!-- Background Gradients & Grid Pattern -->
            <div
                class="absolute inset-0 bg-[radial-gradient(#6366f1_1px,transparent_1px)] [background-size:24px_24px] opacity-25 dark:opacity-15 pointer-events-none"
            ></div>
            <div
                class="absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[650px] h-[650px] bg-gradient-to-tr from-indigo-500/15 via-violet-500/10 to-emerald-500/10 rounded-full blur-3xl pointer-events-none"
            ></div>

            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="grid lg:grid-cols-12 gap-12 items-center">
                    <!-- Left Hero Text -->
                    <div class="lg:col-span-7 space-y-6">
                        <!-- Availability Badge -->
                        <div class="flex flex-wrap items-center gap-2">
                            <div
                                class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-700 dark:text-emerald-300 text-xs font-semibold shadow-sm"
                            >
                                <span class="w-2 h-2 rounded-full bg-emerald-500 animate-ping"></span>
                                <span>{{ profile.availability }}</span>
                            </div>

                            <div
                                class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-slate-200/70 dark:bg-slate-800/80 border border-slate-300/50 dark:border-slate-700/50 text-xs font-medium text-slate-700 dark:text-slate-300"
                            >
                                <Clock class="w-3.5 h-3.5 text-indigo-500" />
                                <span>{{ profile.timezone }}</span>
                            </div>
                        </div>

                        <!-- Main Heading -->
                        <div class="space-y-3">
                            <h2 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-slate-900 dark:text-white leading-[1.12]">
                                Engineering scalable web platforms with
                                <span class="bg-gradient-to-r from-indigo-600 via-violet-600 to-emerald-500 bg-clip-text text-transparent">
                                    Laravel & Vue.js
                                </span>
                            </h2>
                            <p class="text-lg sm:text-xl font-bold text-slate-700 dark:text-slate-300 flex items-center gap-2">
                                <Code2 class="w-5 h-5 text-indigo-500" />
                                <span>Kashif Abbas · Senior Full-Stack Software Engineer</span>
                            </p>
                        </div>

                        <!-- Summary Paragraph -->
                        <p class="text-base sm:text-lg text-slate-600 dark:text-slate-300 leading-relaxed font-normal">
                            {{ summary }}
                        </p>

                        <!-- Key Performance Stats -->
                        <div class="grid grid-cols-2 sm:grid-cols-4 gap-3.5 py-2">
                            <div class="p-4 rounded-2xl bg-white dark:bg-slate-900/80 border border-slate-200 dark:border-slate-800/80 shadow-sm backdrop-blur-sm">
                                <div class="text-2xl sm:text-3xl font-extrabold text-indigo-600 dark:text-indigo-400">7+</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-0.5">Years Experience</div>
                            </div>
                            <div class="p-4 rounded-2xl bg-white dark:bg-slate-900/80 border border-slate-200 dark:border-slate-800/80 shadow-sm backdrop-blur-sm">
                                <div class="text-2xl sm:text-3xl font-extrabold text-violet-600 dark:text-violet-400">15+</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-0.5">Enterprise Systems</div>
                            </div>
                            <div class="p-4 rounded-2xl bg-white dark:bg-slate-900/80 border border-slate-200 dark:border-slate-800/80 shadow-sm backdrop-blur-sm">
                                <div class="text-2xl sm:text-3xl font-extrabold text-emerald-600 dark:text-emerald-400">30+</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-0.5">Global Clients</div>
                            </div>
                            <div class="p-4 rounded-2xl bg-white dark:bg-slate-900/80 border border-slate-200 dark:border-slate-800/80 shadow-sm backdrop-blur-sm">
                                <div class="text-2xl sm:text-3xl font-extrabold text-amber-500">BSCS</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-0.5">Computer Science</div>
                            </div>
                        </div>

                        <!-- CTA Actions -->
                        <div class="flex flex-wrap items-center gap-4 pt-2">
                            <a
                                href="#projects"
                                class="inline-flex items-center gap-2 px-6 py-3.5 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-white font-bold text-sm shadow-lg shadow-indigo-600/30 transition-all hover:scale-[1.02]"
                            >
                                <Briefcase class="w-4 h-4" />
                                Explore Production Work
                            </a>
                            <a
                                href="#contact"
                                class="inline-flex items-center gap-2 px-6 py-3.5 rounded-xl bg-white hover:bg-slate-100 text-slate-900 border border-slate-300 dark:bg-slate-900 dark:hover:bg-slate-800 dark:text-white dark:border-slate-800 font-bold text-sm shadow-sm transition-all"
                            >
                                <Mail class="w-4 h-4 text-indigo-500" />
                                Get In Touch
                            </a>
                            <a
                                :href="profile.linkedin"
                                target="_blank"
                                class="inline-flex items-center gap-2 px-4 py-3.5 rounded-xl bg-blue-50 hover:bg-blue-100 text-blue-700 dark:bg-blue-950/50 dark:hover:bg-blue-900/50 dark:text-blue-300 font-semibold text-sm transition-all"
                            >
                                <Linkedin class="w-4 h-4 text-blue-600 dark:text-blue-400" />
                                LinkedIn
                            </a>
                        </div>
                    </div>

                    <!-- Right Profile Showcase Card -->
                    <div class="lg:col-span-5 flex justify-center">
                        <div class="relative w-full max-w-md">
                            <!-- Glowing Aura -->
                            <div
                                class="absolute -inset-1.5 bg-gradient-to-r from-indigo-500 via-violet-500 to-emerald-500 rounded-3xl blur opacity-30 dark:opacity-40"
                            ></div>

                            <div
                                class="relative bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 rounded-3xl p-6 shadow-2xl space-y-6"
                            >
                                <!-- Photo with Info Overlay -->
                                <div class="relative overflow-hidden rounded-2xl aspect-[4/5] shadow-lg group">
                                    <img
                                        :src="profile.image"
                                        alt="Kashif Abbas"
                                        class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-700"
                                    />
                                    <div
                                        class="absolute inset-0 bg-gradient-to-t from-slate-950/90 via-slate-950/30 to-transparent"
                                    ></div>
                                    <div class="absolute bottom-4 left-4 right-4 text-white space-y-1">
                                        <div class="flex items-center justify-between">
                                            <h3 class="text-xl font-bold">Kashif Abbas</h3>
                                            <span class="px-2 py-0.5 text-[10px] font-extrabold uppercase rounded bg-emerald-500 text-white">
                                                Available
                                            </span>
                                        </div>
                                        <p class="text-xs text-slate-300 font-medium flex items-center gap-1.5">
                                            <GraduationCap class="w-4 h-4 text-amber-400" />
                                            {{ profile.education }}
                                        </p>
                                    </div>
                                </div>

                                <!-- Contact Matrix -->
                                <div class="space-y-2 text-xs text-slate-600 dark:text-slate-300 font-mono">
                                    <div class="flex items-center justify-between p-2.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-100 dark:border-slate-800">
                                        <span class="flex items-center gap-2 font-medium font-sans">
                                            <Mail class="w-4 h-4 text-indigo-500" />
                                            Email
                                        </span>
                                        <a
                                            :href="`mailto:${profile.email}`"
                                            class="text-indigo-600 dark:text-indigo-400 font-semibold hover:underline font-sans"
                                        >
                                            {{ profile.email }}
                                        </a>
                                    </div>

                                    <div class="flex items-center justify-between p-2.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-100 dark:border-slate-800">
                                        <span class="flex items-center gap-2 font-medium font-sans">
                                            <Phone class="w-4 h-4 text-violet-500" />
                                            Phone / WhatsApp
                                        </span>
                                        <a :href="`tel:${profile.phone}`" class="text-slate-900 dark:text-white font-semibold font-sans">
                                            {{ profile.phone }}
                                        </a>
                                    </div>

                                    <div class="flex items-center justify-between p-2.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-100 dark:border-slate-800">
                                        <span class="flex items-center gap-2 font-medium font-sans">
                                            <Globe class="w-4 h-4 text-emerald-500" />
                                            Company Domain
                                        </span>
                                        <a
                                            :href="profile.website"
                                            target="_blank"
                                            class="text-emerald-600 dark:text-emerald-400 font-semibold hover:underline flex items-center gap-1 font-sans"
                                        >
                                            autometasoft.com
                                            <ExternalLink class="w-3 h-3" />
                                        </a>
                                    </div>

                                    <div class="flex items-center justify-between p-2.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-100 dark:border-slate-800">
                                        <span class="flex items-center gap-2 font-medium font-sans">
                                            <Linkedin class="w-4 h-4 text-blue-600" />
                                            LinkedIn
                                        </span>
                                        <a
                                            :href="profile.linkedin"
                                            target="_blank"
                                            class="text-blue-600 dark:text-blue-400 font-semibold hover:underline flex items-center gap-1 font-sans"
                                        >
                                            kashifgabol
                                            <ExternalLink class="w-3 h-3" />
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Engineering Standards / Value Proposition (Why Hire Me) -->
        <section class="py-16 bg-slate-100/80 dark:bg-slate-900/50 border-y border-slate-200 dark:border-slate-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-8">
                <div class="text-center space-y-2">
                    <span class="text-xs font-extrabold uppercase tracking-widest text-indigo-600 dark:text-indigo-400">
                        Engineering Philosophy
                    </span>
                    <h3 class="text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">
                        Built for Scalability, Security & International Standards
                    </h3>
                </div>

                <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div
                        v-for="p in engineeringPillars"
                        :key="p.title"
                        class="p-6 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-sm space-y-3"
                    >
                        <div class="w-10 h-10 rounded-xl bg-indigo-50 dark:bg-indigo-950/60 text-indigo-600 dark:text-indigo-400 flex items-center justify-center">
                            <component :is="p.icon" class="w-5 h-5" />
                        </div>
                        <h4 class="font-bold text-base text-slate-900 dark:text-white">
                            {{ p.title }}
                        </h4>
                        <p class="text-xs text-slate-600 dark:text-slate-400 leading-relaxed font-normal">
                            {{ p.description }}
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Featured Projects Section -->
        <section id="projects" class="py-20 lg:py-28">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Section Header -->
                <div class="flex flex-col md:flex-row md:items-end justify-between gap-6">
                    <div class="space-y-3">
                        <span
                            class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-violet-100 text-violet-700 dark:bg-violet-950/70 dark:text-violet-300 text-xs font-bold uppercase tracking-wider"
                        >
                            <Layers class="w-3.5 h-3.5" /> Production Portfolio
                        </span>
                        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                            Featured Enterprise Applications & Systems
                        </h2>
                        <p class="text-slate-600 dark:text-slate-400 max-w-2xl text-sm sm:text-base">
                            Real-world business systems, regulatory fintech platforms, and scalable SaaS solutions in active production.
                        </p>
                    </div>
                </div>

                <!-- Projects Grid -->
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div
                        v-for="proj in projects"
                        :key="proj.id"
                        class="group flex flex-col bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 rounded-3xl overflow-hidden shadow-md hover:shadow-2xl hover:border-indigo-500/50 transition-all duration-300 hover:-translate-y-1"
                    >
                        <!-- Card Header Banner -->
                        <div class="p-6 bg-gradient-to-br from-slate-900 via-indigo-950 to-slate-900 text-white relative space-y-2">
                            <div class="flex items-center justify-between gap-2">
                                <span class="px-2.5 py-0.5 rounded-full text-[10px] font-extrabold uppercase tracking-wider bg-white/20 text-white backdrop-blur-md">
                                    {{ proj.badge }}
                                </span>
                                <Code2 class="w-4 h-4 text-indigo-400" />
                            </div>
                            <h3 class="text-xl font-extrabold leading-snug group-hover:text-indigo-300 transition-colors">
                                {{ proj.title }}
                            </h3>
                            <p class="text-xs text-slate-300 font-medium">
                                {{ proj.subtitle }}
                            </p>
                        </div>

                        <!-- Card Body -->
                        <div class="p-6 flex-1 flex flex-col justify-between space-y-6">
                            <div class="space-y-4">
                                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 leading-relaxed font-normal">
                                    {{ proj.description }}
                                </p>

                                <!-- Performance / Metric Note -->
                                <div v-if="proj.metrics" class="p-3 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-100 dark:border-slate-800 text-xs font-medium text-slate-700 dark:text-slate-300 flex items-start gap-2">
                                    <Zap class="w-4 h-4 text-amber-500 shrink-0 mt-0.5" />
                                    <span>{{ proj.metrics }}</span>
                                </div>

                                <!-- Implementation Highlights -->
                                <div v-if="proj.highlights" class="space-y-1.5 bg-slate-50 dark:bg-slate-800/60 p-3 rounded-xl text-xs">
                                    <span class="font-bold text-slate-700 dark:text-slate-300 block mb-1">Key Implementations:</span>
                                    <div v-for="h in proj.highlights" :key="h" class="flex items-center gap-1.5 text-slate-600 dark:text-slate-300">
                                        <Check class="w-3.5 h-3.5 text-indigo-500 shrink-0" />
                                        <span>{{ h }}</span>
                                    </div>
                                </div>
                            </div>

                            <!-- Live Project Links & Tech Stack -->
                            <div class="space-y-4 pt-3 border-t border-slate-100 dark:border-slate-800">
                                <div v-if="proj.links && proj.links.length" class="space-y-2">
                                    <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wider block">Live Platform Links:</span>
                                    <div class="flex flex-wrap gap-2">
                                        <a
                                            v-for="l in proj.links"
                                            :key="l.url"
                                            :href="l.url"
                                            target="_blank"
                                            class="inline-flex items-center gap-1.5 px-3 py-1.5 rounded-lg bg-indigo-50 hover:bg-indigo-100 text-indigo-700 dark:bg-indigo-950/70 dark:hover:bg-indigo-900/70 dark:text-indigo-300 text-xs font-bold transition-colors"
                                        >
                                            {{ l.label }}
                                            <ArrowUpRight class="w-3 h-3" />
                                        </a>
                                    </div>
                                </div>

                                <!-- Tech Stack Pills -->
                                <div class="flex flex-wrap gap-1.5">
                                    <span
                                        v-for="t in proj.tech"
                                        :key="t"
                                        class="px-2.5 py-0.5 rounded-md bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-300 text-[11px] font-medium"
                                    >
                                        {{ t }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Professional Work Experience Section -->
        <section id="experience" class="py-20 lg:py-28 bg-slate-100/70 dark:bg-slate-900/40 border-t border-slate-200 dark:border-slate-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Header -->
                <div class="text-center space-y-3">
                    <span
                        class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-indigo-100 text-indigo-700 dark:bg-indigo-950/70 dark:text-indigo-300 text-xs font-bold uppercase tracking-wider"
                    >
                        <Briefcase class="w-3.5 h-3.5" /> Career Record
                    </span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                        Professional Work Experience
                    </h2>
                    <p class="text-slate-600 dark:text-slate-400 max-w-2xl mx-auto text-sm sm:text-base">
                        7+ years architecting enterprise software solutions for clients across the UK, UAE, Saudi Arabia, and Pakistan.
                    </p>
                </div>

                <!-- Timeline -->
                <div
                    class="space-y-8 relative before:absolute before:inset-0 before:left-4 sm:before:left-1/2 before:-translate-x-px before:w-0.5 before:bg-slate-200 dark:before:bg-slate-800"
                >
                    <div
                        v-for="(exp, idx) in experiences"
                        :key="exp.id"
                        class="relative flex flex-col sm:flex-row items-start group"
                    >
                        <!-- Timeline Node -->
                        <div
                            class="absolute left-4 sm:left-1/2 -translate-x-1/2 w-7 h-7 sm:w-8 sm:h-8 rounded-full bg-white dark:bg-slate-900 border-4 border-indigo-600 dark:border-indigo-500 shadow-md z-10 flex items-center justify-center"
                        >
                            <span class="w-2 h-2 rounded-full bg-indigo-600 dark:bg-indigo-400"></span>
                        </div>

                        <!-- Content Box -->
                        <div
                            :class="[
                                'w-[calc(100%-2.5rem)] sm:w-[calc(50%-2.5rem)] ml-10 sm:ml-0 p-6 sm:p-8 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200/90 dark:border-slate-800/90 shadow-lg hover:shadow-xl transition-all duration-300 space-y-4',
                                idx % 2 === 0 ? 'sm:mr-auto' : 'sm:ml-auto',
                            ]"
                        >
                            <div class="flex flex-wrap items-center justify-between gap-2 border-b border-slate-100 dark:border-slate-800 pb-3">
                                <div>
                                    <span
                                        class="inline-block px-2.5 py-0.5 rounded text-[11px] font-bold uppercase tracking-wider mb-1 bg-indigo-100 text-indigo-700 dark:bg-indigo-950 dark:text-indigo-300"
                                    >
                                        Software Engineering
                                    </span>
                                    <h3 class="text-xl font-bold text-slate-900 dark:text-white">
                                        {{ exp.role }}
                                    </h3>
                                    <p class="text-sm font-semibold text-indigo-600 dark:text-indigo-400 flex items-center gap-1.5">
                                        <Building2 class="w-4 h-4" />
                                        {{ exp.company }}
                                    </p>
                                </div>
                                <div class="text-right">
                                    <span
                                        class="inline-block px-3 py-1 rounded-full bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-300 text-xs font-semibold"
                                    >
                                        {{ exp.period }}
                                    </span>
                                    <p class="text-xs text-slate-500 dark:text-slate-400 mt-1 flex items-center gap-1 justify-end">
                                        <MapPin class="w-3 h-3" /> {{ exp.location }}
                                    </p>
                                </div>
                            </div>

                            <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 leading-relaxed font-normal">
                                {{ exp.description }}
                            </p>

                            <ul class="space-y-2 text-xs sm:text-sm text-slate-700 dark:text-slate-300">
                                <li v-for="(b, bIdx) in exp.bullets" :key="bIdx" class="flex items-start gap-2">
                                    <CheckCircle2 class="w-4 h-4 text-emerald-500 shrink-0 mt-0.5" />
                                    <span>{{ b }}</span>
                                </li>
                            </ul>

                            <div class="flex flex-wrap gap-1.5 pt-2">
                                <span
                                    v-for="t in exp.tags"
                                    :key="t"
                                    class="px-2.5 py-1 rounded-md bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-300 text-xs font-medium"
                                >
                                    #{{ t }}
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Technical Domain & Skills Matrix -->
        <section id="skills" class="py-20 lg:py-28">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Header -->
                <div class="text-center space-y-3">
                    <span
                        class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-emerald-100 text-emerald-700 dark:bg-emerald-950/70 dark:text-emerald-300 text-xs font-bold uppercase tracking-wider"
                    >
                        <Cpu class="w-3.5 h-3.5" /> Technical Matrix
                    </span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                        Full-Stack Capabilities & Technical Mastery
                    </h2>
                    <p class="text-slate-600 dark:text-slate-400 max-w-xl mx-auto text-sm sm:text-base">
                        Deep engineering capabilities across backend frameworks, reactive frontends, database tuning, and CI/CD pipelines.
                    </p>
                </div>

                <!-- Domain-Based Skills Grid -->
                <div class="grid md:grid-cols-3 gap-8">
                    <div
                        v-for="domain in skillDomains"
                        :key="domain.title"
                        class="p-6 sm:p-8 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md space-y-6 flex flex-col justify-between"
                    >
                        <div class="space-y-6">
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-xl bg-indigo-50 dark:bg-indigo-950/60 text-indigo-600 dark:text-indigo-400 flex items-center justify-center">
                                    <component :is="domain.icon" class="w-5 h-5" />
                                </div>
                                <h3 class="font-extrabold text-lg text-slate-900 dark:text-white">
                                    {{ domain.title }}
                                </h3>
                            </div>

                            <div class="space-y-4">
                                <div v-for="sk in domain.skills" :key="sk.name" class="space-y-1.5">
                                    <div class="flex items-center justify-between text-xs font-bold">
                                        <span class="text-slate-800 dark:text-slate-200">{{ sk.name }}</span>
                                        <span class="text-indigo-600 dark:text-indigo-400 font-mono">{{ sk.level }}%</span>
                                    </div>
                                    <div class="w-full bg-slate-100 dark:bg-slate-800 h-2 rounded-full overflow-hidden">
                                        <div
                                            class="bg-gradient-to-r from-indigo-500 to-emerald-500 h-full rounded-full transition-all duration-700"
                                            :style="{ width: `${sk.level}%` }"
                                        ></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section id="services" class="py-20 lg:py-28 bg-slate-900 text-white relative overflow-hidden">
            <!-- Background Glows -->
            <div class="absolute top-0 right-0 w-96 h-96 bg-indigo-600/10 rounded-full blur-3xl pointer-events-none"></div>
            <div class="absolute bottom-0 left-0 w-80 h-80 bg-violet-600/10 rounded-full blur-3xl pointer-events-none"></div>

            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-16 relative z-10">
                <!-- Header -->
                <div class="text-center space-y-3">
                    <span
                        class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-indigo-500/20 text-indigo-300 text-xs font-bold uppercase tracking-wider border border-indigo-500/30"
                    >
                        <Sparkles class="w-3.5 h-3.5" /> What I Deliver
                    </span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold">
                        Full-Stack Development Services for Global Clients
                    </h2>
                    <p class="text-slate-400 max-w-2xl mx-auto text-sm sm:text-base">
                        From custom enterprise SaaS solutions to high-throughput RESTful APIs — built with precision and scale in mind.
                    </p>
                </div>

                <!-- Services Grid -->
                <div class="grid md:grid-cols-2 gap-8">
                    <div
                        v-for="srv in devServices"
                        :key="srv.title"
                        class="p-8 rounded-3xl bg-slate-800/80 border border-slate-700/80 shadow-xl space-y-6 hover:border-indigo-500/50 transition-all duration-300 flex flex-col justify-between"
                    >
                        <div class="space-y-4">
                            <div class="flex items-center justify-between">
                                <span
                                    class="px-3 py-1 rounded-full bg-indigo-500/20 text-indigo-400 text-xs font-bold uppercase border border-indigo-500/30"
                                >
                                    {{ srv.badge }}
                                </span>
                                <component :is="srv.icon" class="w-5 h-5 text-indigo-400" />
                            </div>
                            <h3 class="text-xl font-extrabold text-white">{{ srv.title }}</h3>
                            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">{{ srv.description }}</p>
                        </div>
                        <div class="space-y-2 pt-4 border-t border-slate-700/60">
                            <div v-for="f in srv.features" :key="f" class="flex items-center gap-2 text-xs font-medium text-slate-200">
                                <CheckCircle2 class="w-4 h-4 text-emerald-400 shrink-0" />
                                <span>{{ f }}</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Tech Stack Badges -->
                <div class="space-y-6 text-center pt-8 border-t border-slate-800">
                    <h4 class="text-xs font-extrabold uppercase tracking-widest text-slate-400">Core Technology Stack</h4>
                    <div class="flex flex-wrap justify-center gap-3">
                        <div
                            v-for="t in techStack"
                            :key="t.name"
                            class="px-4 py-2 rounded-xl bg-slate-800 border border-slate-700/70 text-xs font-bold text-slate-200 hover:border-indigo-500/40 hover:text-white transition-colors"
                        >
                            <span class="text-white">{{ t.name }}</span>
                            <span class="text-[10px] text-slate-400 block font-normal">{{ t.platform }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Education, Languages & Certifications -->
        <section class="py-16 bg-slate-100/70 dark:bg-slate-900/40 border-t border-slate-200 dark:border-slate-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid md:grid-cols-2 gap-8">
                    <!-- Education -->
                    <div
                        class="p-8 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-lg space-y-4"
                    >
                        <div class="inline-flex p-3 rounded-2xl bg-indigo-50 dark:bg-indigo-950/60 text-indigo-600 dark:text-indigo-400">
                            <GraduationCap class="w-6 h-6" />
                        </div>
                        <h3 class="text-xl font-bold text-slate-900 dark:text-white">Academic Foundation</h3>
                        <div class="border-l-2 border-indigo-500 pl-4 space-y-1">
                            <h4 class="font-bold text-slate-900 dark:text-white">
                                Bachelor of Science in Computer Science (BSCS)
                            </h4>
                            <p class="text-xs text-slate-500 dark:text-slate-400">
                                4-Year Professional Degree · Software Engineering & Algorithms
                            </p>
                        </div>
                    </div>

                    <!-- Languages -->
                    <div
                        class="p-8 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-lg space-y-4"
                    >
                        <div class="inline-flex p-3 rounded-2xl bg-emerald-50 dark:bg-emerald-950/60 text-emerald-600 dark:text-emerald-400">
                            <Globe class="w-6 h-6" />
                        </div>
                        <h3 class="text-xl font-bold text-slate-900 dark:text-white">Language Proficiency</h3>
                        <div class="grid grid-cols-3 gap-3">
                            <div
                                v-for="lang in profile.languages"
                                :key="lang.name"
                                class="p-3 rounded-xl bg-slate-50 dark:bg-slate-800 text-center"
                            >
                                <div class="font-bold text-sm text-slate-900 dark:text-white">{{ lang.name }}</div>
                                <div class="text-[11px] font-semibold text-emerald-600 dark:text-emerald-400">{{ lang.level }}</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="py-20 lg:py-28 relative">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Header -->
                <div class="text-center space-y-3">
                    <span
                        class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-amber-100 text-amber-700 dark:bg-amber-950/70 dark:text-amber-300 text-xs font-bold uppercase tracking-wider"
                    >
                        <Mail class="w-3.5 h-3.5" /> Start a Conversation
                    </span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                        Let's Build Something Extraordinary Together
                    </h2>
                    <p class="text-slate-600 dark:text-slate-400 max-w-xl mx-auto text-sm sm:text-base">
                        Open for full-time remote software engineering roles, international contracts, and high-impact enterprise projects.
                    </p>
                </div>

                <!-- Contact Cards -->
                <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6 max-w-5xl mx-auto">
                    <!-- Email -->
                    <div
                        class="p-6 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3 flex flex-col justify-between"
                    >
                        <div class="space-y-3">
                            <div
                                class="w-12 h-12 rounded-2xl bg-indigo-50 dark:bg-indigo-950/60 text-indigo-600 dark:text-indigo-400 flex items-center justify-center mx-auto"
                            >
                                <Mail class="w-6 h-6" />
                            </div>
                            <h3 class="font-bold text-slate-900 dark:text-white">Email Address</h3>
                            <p class="text-xs text-slate-500 dark:text-slate-400 break-all">{{ profile.email }}</p>
                        </div>
                        <button
                            @click="copyEmail"
                            class="w-full py-2.5 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-white text-xs font-bold shadow-md transition-all inline-flex items-center justify-center gap-1.5"
                        >
                            <Check v-if="contactCopied" class="w-3.5 h-3.5" />
                            <span>{{ contactCopied ? 'Copied to Clipboard!' : 'Copy Email' }}</span>
                        </button>
                    </div>

                    <!-- Phone / WhatsApp -->
                    <div
                        class="p-6 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3 flex flex-col justify-between"
                    >
                        <div class="space-y-3">
                            <div
                                class="w-12 h-12 rounded-2xl bg-violet-50 dark:bg-violet-950/60 text-violet-600 dark:text-violet-400 flex items-center justify-center mx-auto"
                            >
                                <Phone class="w-6 h-6" />
                            </div>
                            <h3 class="font-bold text-slate-900 dark:text-white">Phone / WhatsApp</h3>
                            <p class="text-xs text-slate-500 dark:text-slate-400">{{ profile.phone }}</p>
                        </div>
                        <a
                            :href="`tel:${profile.phone}`"
                            class="w-full py-2.5 rounded-xl bg-violet-600 hover:bg-violet-500 text-white text-xs font-bold shadow-md transition-all inline-flex items-center justify-center gap-1.5"
                        >
                            <Phone class="w-3.5 h-3.5" />
                            <span>Call / WhatsApp</span>
                        </a>
                    </div>

                    <!-- Website -->
                    <div
                        class="p-6 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3 flex flex-col justify-between"
                    >
                        <div class="space-y-3">
                            <div
                                class="w-12 h-12 rounded-2xl bg-emerald-50 dark:bg-emerald-950/60 text-emerald-600 dark:text-emerald-400 flex items-center justify-center mx-auto"
                            >
                                <Globe class="w-6 h-6" />
                            </div>
                            <h3 class="font-bold text-slate-900 dark:text-white">Company Domain</h3>
                            <p class="text-xs text-slate-500 dark:text-slate-400">autometasoft.com</p>
                        </div>
                        <a
                            :href="profile.website"
                            target="_blank"
                            class="w-full py-2.5 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white text-xs font-bold shadow-md transition-all inline-flex items-center justify-center gap-1.5"
                        >
                            <ExternalLink class="w-3.5 h-3.5" />
                            <span>Visit Domain</span>
                        </a>
                    </div>

                    <!-- LinkedIn -->
                    <div
                        class="p-6 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3 flex flex-col justify-between"
                    >
                        <div class="space-y-3">
                            <div
                                class="w-12 h-12 rounded-2xl bg-blue-50 dark:bg-blue-950/60 text-blue-600 dark:text-blue-400 flex items-center justify-center mx-auto"
                            >
                                <Linkedin class="w-6 h-6" />
                            </div>
                            <h3 class="font-bold text-slate-900 dark:text-white">LinkedIn Profile</h3>
                            <p class="text-xs text-slate-500 dark:text-slate-400">in/kashifgabol</p>
                        </div>
                        <a
                            :href="profile.linkedin"
                            target="_blank"
                            class="w-full py-2.5 rounded-xl bg-blue-600 hover:bg-blue-500 text-white text-xs font-bold shadow-md transition-all inline-flex items-center justify-center gap-1.5"
                        >
                            <Linkedin class="w-3.5 h-3.5" />
                            <span>Connect on LinkedIn</span>
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer
            class="py-8 bg-white dark:bg-[#070b12] border-t border-slate-200 dark:border-slate-800 text-center text-xs text-slate-500 dark:text-slate-400 transition-colors"
        >
            <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-4">
                <div class="flex items-center gap-2">
                    <span class="font-bold text-slate-900 dark:text-white">Kashif Abbas</span>
                    <span>·</span>
                    <span>Senior Full-Stack Web Developer</span>
                </div>
                <div class="flex items-center gap-4">
                    <a
                        :href="profile.linkedin"
                        target="_blank"
                        class="inline-flex items-center gap-1.5 text-blue-600 dark:text-blue-400 font-semibold hover:underline"
                    >
                        <Linkedin class="w-3.5 h-3.5" />
                        LinkedIn
                    </a>
                    <span>·</span>
                    <a
                        :href="profile.website"
                        target="_blank"
                        class="inline-flex items-center gap-1.5 text-emerald-600 dark:text-emerald-400 font-semibold hover:underline"
                    >
                        <Globe class="w-3.5 h-3.5" />
                        AutoMeta Soft
                    </a>
                </div>
                <div>© {{ new Date().getFullYear() }} Kashif Abbas. All rights reserved.</div>
            </div>
        </footer>
    </div>
</template>
