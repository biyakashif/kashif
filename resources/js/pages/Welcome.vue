<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import {
    ArrowUpRight,
    BarChart3,
    Briefcase,
    Building2,
    Check,
    CheckCircle2,
    ChevronRight,
    Code,
    Cpu,
    Database,
    Download,
    ExternalLink,
    FileText,
    Globe,
    GraduationCap,
    Layers,
    Mail,
    MapPin,
    Megaphone,
    Moon,
    Palette,
    Phone,
    Server,
    Share2,
    Sparkles,
    Sun,
    Target,
    User,
} from 'lucide-vue-next';
import { computed, onMounted, ref } from 'vue';

// Mode selection: 'developer' | 'marketing' | 'all'
type Mode = 'developer' | 'marketing' | 'all';
const activeMode = ref<Mode>('developer');

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
    location: 'Multan, Pakistan',
    locationNote: 'Available for Full-Time & Remote Opportunities',
    email: 'kashifgabol512@gmail.com',
    phone: '+923027772202',
    website: 'https://autometasoft.com',
    image: '/images/kashif.jpg',
    education: 'BSCS (Bachelor of Science in Computer Science)',
    languages: [
        { name: 'English', level: 'Fluent' },
        { name: 'Urdu', level: 'Native' },
        { name: 'Arabic', level: 'Basic' },
    ],
};

// Summaries per mode
const summaries = {
    developer:
        'Senior Full-Stack Web Developer with 7+ years of hands-on experience designing, building, and maintaining scalable web applications using Laravel, Vue.js, Inertia.js, and RESTful APIs. Proven track record delivering business-critical enterprise solutions including Hospital Management Systems (HMS), ERP, POS, Inventory, Task Management, and Business Management platforms across multiple industries. Skilled in database architecture, secure authentication, query optimization, and writing clean, testable code.',
    marketing:
        'Versatile Digital Media Marketing Manager and Creative Strategist with over 7 years of expertise driving brand visibility, social media engagement, and high-ROAS marketing campaigns. Experienced in orchestrating end-to-end paid ad strategies for European e-commerce brands and international clients across Facebook, Instagram, LinkedIn, Pinterest, TikTok, and Google Ads. Combined with advanced graphic design skills (Photoshop, Illustrator, Canva, Figma) to deliver impactful digital assets.',
    all:
        'Dual-Threat Professional bringing 7+ years of combined mastery as a Senior Full-Stack Web Developer and Digital Media Marketing Manager. Adept at creating high-performance web applications with Laravel, Vue.js, and Inertia.js while simultaneously driving growth, brand strategy, content creation, and multi-channel paid ad campaigns for international e-commerce and enterprise clients.',
};

// Skill Categories
const developerSkills = [
    { name: 'Laravel & PHP 8+', level: 95, category: 'Backend' },
    { name: 'Vue.js 3 & Inertia.js', level: 92, category: 'Frontend' },
    { name: 'RESTful API Design', level: 90, category: 'Backend' },
    { name: 'MySQL & PostgreSQL', level: 88, category: 'Database' },
    { name: 'Tailwind CSS & Responsive UI', level: 94, category: 'Frontend' },
    { name: 'TypeScript & JavaScript', level: 88, category: 'Frontend' },
    { name: 'Vite, Node.js & Tooling', level: 85, category: 'Tools' },
    { name: 'PHPUnit & Automated Testing', level: 82, category: 'Testing' },
    { name: 'Git & Version Control', level: 90, category: 'Tools' },
];

const marketingSkills = [
    { name: 'Paid Ad Campaigns (Meta & Google)', level: 92, category: 'Marketing' },
    { name: 'Social Media Strategy & Management', level: 95, category: 'Marketing' },
    { name: 'Content Strategy & Copywriting', level: 88, category: 'Content' },
    { name: 'Adobe Photoshop & Illustrator', level: 90, category: 'Design' },
    { name: 'Canva & Ad Creatives', level: 96, category: 'Design' },
    { name: 'Figma & UI/UX Prototyping', level: 86, category: 'Design' },
    { name: 'ROAS & Conversion Optimization', level: 89, category: 'Analytics' },
    { name: 'E-Commerce Growth Strategy', level: 90, category: 'Marketing' },
];

const displayedSkills = computed(() => {
    if (activeMode.value === 'developer') return developerSkills;
    if (activeMode.value === 'marketing') return marketingSkills;
    return [...developerSkills, ...marketingSkills];
});

// Experiences
const experiences = [
    {
        id: 'exp-1',
        mode: 'developer',
        role: 'Full-Stack Web Developer',
        company: 'AutoMeta Software Solutions',
        location: 'Multan, Pakistan',
        period: 'March 2020 – Present',
        description:
            'Architecting, developing, and maintaining scalable enterprise web applications and business management systems using Laravel, Vue.js, Inertia.js, and RESTful APIs.',
        bullets: [
            'Architected and deployed production-ready Hospital Management Systems (HMS), ERPs, and POS platforms.',
            'Designed and implemented secure RESTful APIs for business-critical operations.',
            'Optimized database queries in MySQL/PostgreSQL, cutting page load times by over 40%.',
            'Wrote automated feature and unit tests with PHPUnit to maintain code reliability.',
            'Collaborated with cross-functional teams to deliver custom web solutions for regional and international clients.',
        ],
        tags: ['Laravel', 'Vue.js', 'Inertia.js', 'REST APIs', 'MySQL', 'Tailwind CSS', 'PHPUnit'],
    },
    {
        id: 'exp-2',
        mode: 'marketing',
        role: 'Freelance Graphic Designer & Social Media Manager',
        company: 'International & Local Clients',
        location: 'Remote & Global Clients',
        period: 'October 2023 – Present',
        description:
            'Crafting digital branding, ad creative assets, and managing digital marketing strategies for e-commerce, healthcare, and technical service providers.',
        bullets: [
            'Serving as primary graphic designer for international clients, delivering digital marketing collateral.',
            'Managing social media presence and engagement strategies across Meta, Instagram, LinkedIn, and TikTok.',
            'Creating high-converting ad visuals and branding kits for clients including Laiba Beauty Parlor, UK Salts, AutoMeta Soft, Al Hadi Technical Services, and Zain Herbal Products.',
            'Optimized brand reach and customer acquisition through tailored organic and paid campaigns.',
        ],
        tags: ['Graphic Design', 'Social Media Strategy', 'Photoshop', 'Illustrator', 'Paid Ads', 'Branding'],
    },
    {
        id: 'exp-3',
        mode: 'marketing',
        role: 'Digital Marketing & Social Media Manager',
        company: 'NASK Soft',
        location: 'Lahore, Pakistan',
        period: 'May 2022 – October 2023',
        description:
            'Led digital marketing campaigns, content creation, and paid advertising strategies for European e-commerce fashion brands and tech portals.',
        bullets: [
            'Managed end-to-end paid advertising campaigns across Facebook, Instagram, Pinterest, TikTok, and LinkedIn.',
            'Boosted brand visibility and engagement for major e-commerce platforms like lovemyfashions.com, europafashions.co.uk, and wholesaleshopping.co.uk.',
            'Designed ad copy, visual assets, and promotional banners that significantly increased online sales traffic.',
            'Analyzed campaign metrics and audience insights to continuously optimize ad spend and ROAS.',
        ],
        tags: ['Digital Marketing', 'Paid Campaigns', 'Social Media', 'Meta Ads', 'E-Commerce Growth', 'Analytics'],
    },
    {
        id: 'exp-4',
        mode: 'both',
        role: 'Web Developer & Graphic Designer',
        company: 'Sharjah Web & Advertising Projects',
        location: 'Sharjah, UAE',
        period: '2016 – 2020',
        description:
            'Delivered custom web development solutions and graphic design assets for prominent corporate clients in the UAE, UK, and Saudi Arabia.',
        bullets: [
            'Developed responsive websites using HTML, CSS, JavaScript, Bootstrap, and PHP.',
            'Collaborated with top companies including Lead Craft Advertising (Dubai), Al Shan Business Group (Sharjah), UK Salts (London), and Awafi Pharma (KSA).',
            'Designed product catalogs, corporate branding kits, web banners, and marketing materials with Photoshop, Illustrator, and Canva.',
        ],
        tags: ['Web Development', 'Graphic Design', 'Bootstrap', 'JavaScript', 'Photoshop', 'Canva', 'Branding'],
    },
];

const filteredExperiences = computed(() => {
    if (activeMode.value === 'all') return experiences;
    return experiences.filter((e) => e.mode === activeMode.value || e.mode === 'both');
});

// Projects / Portfolio Items
const projects = [
    {
        id: 'proj-1',
        mode: 'developer',
        title: 'Hospital Management System (HMS)',
        subtitle: 'Healthcare Enterprise SaaS Solution',
        category: 'Full-Stack Web App',
        description:
            'Comprehensive Hospital Management System featuring patient records, doctor scheduling, billing, pharmacy inventory, and lab reporting.',
        image: '/images/kashif.jpg',
        tech: ['Laravel', 'Vue.js', 'Inertia.js', 'REST APIs', 'MySQL'],
        links: [
            { label: 'National Hospital Alipur', url: 'https://hms.autometasoft.com' },
            { label: 'Qasim Hospital Alipur', url: 'https://hms.autometasoft.com' },
        ],
    },
    {
        id: 'proj-2',
        mode: 'developer',
        title: 'Business Management System',
        subtitle: 'Enterprise Resource & Accounting Platform',
        category: 'Full-Stack Web App',
        description:
            'Custom business management system designed for manufacturing and distribution enterprises to manage inventory, sales orders, and client accounts.',
        image: '/images/kashif.jpg',
        tech: ['Laravel', 'Vue.js', 'Tailwind CSS', 'MySQL'],
        links: [
            { label: 'UK Salts Portal', url: 'https://www.uksalts.net' },
            { label: 'AR Company Portal', url: 'https://ar.autometasoft.com' },
        ],
    },
    {
        id: 'proj-3',
        mode: 'developer',
        title: 'ERP & POS Inventory Applications',
        subtitle: 'Multi-Store Point of Sale & ERP Systems',
        category: 'Full-Stack Enterprise',
        description:
            'Point of Sale and ERP applications powering retail stores and distribution businesses, including VapeAuro (Lahore), Raza General Store (Alipur), and Vape Land (Multan).',
        image: '/images/kashif.jpg',
        tech: ['Laravel', 'Vue.js', 'Inertia.js', 'Tailwind', 'PHPUnit'],
        highlights: ['VapeAuro (Lahore)', 'Raza General Store (Alipur)', 'Vape Land (Multan)', 'Task Management App'],
    },
    {
        id: 'proj-4',
        mode: 'developer',
        title: 'Corporate Web Applications & Client Portals',
        subtitle: 'Responsive Custom Web Platforms',
        category: 'Web Development',
        description:
            'High-performance responsive websites and web portals built for international services, industrial salts, and software providers.',
        image: '/images/kashif.jpg',
        tech: ['PHP', 'Vue.js', 'JavaScript', 'HTML5/CSS3', 'Bootstrap'],
        links: [
            { label: 'UK Salts', url: 'https://www.uksalts.com' },
            { label: 'JSoft Hub', url: 'https://www.jsofthub.com' },
            { label: 'Al Hadi Services', url: 'https://www.alhadi-services.com' },
            { label: 'MKG', url: 'https://mkg.com.pk' },
            { label: 'Ruposh Group', url: 'https://ruposh.group' },
        ],
    },
    {
        id: 'proj-5',
        mode: 'marketing',
        title: 'European E-Commerce Marketing Campaigns',
        subtitle: 'Multi-Channel Paid Ads & Social Strategy',
        category: 'Digital Marketing',
        description:
            'End-to-end social media strategies and paid ad campaigns for European fashion e-commerce brands, driving traffic, brand authority, and ROAS.',
        image: '/images/kashif.jpg',
        tech: ['Meta Ads', 'Instagram', 'Pinterest Ads', 'TikTok Ads', 'Content Strategy'],
        links: [
            { label: 'Love My Fashions', url: 'https://lovemyfashions.com' },
            { label: 'Europa Fashions', url: 'https://europafashions.co.uk' },
            { label: 'Wholesale Shopping', url: 'https://wholesaleshopping.co.uk' },
            { label: 'Studio Hub', url: 'https://www.studio-hub.co.uk' },
            { label: 'NASK Soft', url: 'https://www.nasksoft.com' },
        ],
    },
    {
        id: 'proj-6',
        mode: 'marketing',
        title: 'Brand Identity & Digital Assets Suite',
        subtitle: 'Graphic Design & Local Business Growth',
        category: 'Graphic Design & Marketing',
        description:
            'Custom branding kits, social media visual assets, product catalogs, and promotional media for international clients and local businesses.',
        image: '/images/kashif.jpg',
        tech: ['Photoshop', 'Illustrator', 'Canva', 'Figma', 'Brand Identity'],
        highlights: [
            'International Client Branding',
            'Laiba Beauty Parlor Campaign',
            'UK Salts Branding',
            'AutoMeta Soft Assets',
            'Zain Herbal Products Strategy',
        ],
    },
];

const filteredProjects = computed(() => {
    if (activeMode.value === 'all') return projects;
    return projects.filter((p) => p.mode === activeMode.value);
});

// Contact modal / form state
const contactCopied = ref(false);
const copyEmail = () => {
    navigator.clipboard.writeText(profile.email);
    contactCopied.value = true;
    setTimeout(() => {
        contactCopied.value = false;
    }, 2500);
};


// Core Growth Marketing Services
const marketingServices = [
    {
        title: 'Paid Acquisition & Campaign Scaling',
        description: 'Data-driven paid advertising strategies across Meta (Facebook & Instagram), Google Ads, and TikTok with audience targeting, retargeting & lookalike scaling.',
        features: ['Meta Ads & Pixel CAPI Tracking', 'Google Search & Display Ads', 'Retargeting & Custom Audiences', 'A/B Testing & ROAS Optimization'],
        badge: 'Paid Ads Strategy',
    },
    {
        title: 'Social Media Management & Branding',
        description: 'Complete brand identity management, monthly content strategy, graphic asset creation, and community engagement.',
        features: ['Photoshop & Illustrator Banners', 'Canva Ad Creatives & Reels', 'Brand Identity Kits & Catalogs', 'Organic Social Reach Strategy'],
        badge: 'Social & Creative',
    },
    {
        title: 'E-Commerce CRO & Funnel Strategy',
        description: 'Maximizing store sales with high-converting ad copy, landing page structure optimization, and promotional offer hooks.',
        features: ['High-Converting Ad Copywriting', 'E-Commerce Store Layout Audits', 'Offer Hook & Carousel Planning', 'Cart Abandonment Strategies'],
        badge: 'Conversion CRO',
    },
    {
        title: 'Analytics & Multi-Channel Tracking',
        description: 'Comprehensive performance dashboards, custom conversion tracking, GA4 setup, and weekly client reporting.',
        features: ['Google Analytics 4 (GA4)', 'Meta Pixel & Conversion API', 'Custom Conversion Events', 'ROI & ROAS Audit Dashboards'],
        badge: 'Data & Analytics',
    },
];

// Marketing Toolstack Badges
const marketingToolstack = [
    { name: 'Meta Ads Manager', platform: 'Facebook & Instagram' },
    { name: 'Google Ads', platform: 'Search & Display' },
    { name: 'TikTok Ads Manager', platform: 'Video Campaigns' },
    { name: 'Pinterest Business', platform: 'E-Commerce Shopping' },
    { name: 'Google Analytics 4', platform: 'Web Traffic Analytics' },
    { name: 'Meta Pixel & CAPI', platform: 'Server-Side Conversions' },
    { name: 'Adobe Photoshop', platform: 'Graphic Retouching' },
    { name: 'Adobe Illustrator', platform: 'Vector Logos & Branding' },
    { name: 'Canva Pro', platform: 'Rapid Social Creatives' },
    { name: 'Figma', platform: 'Landing Page Prototypes' },
];

</script>

<template>
    <Head title="Kashif Abbas | Full-Stack Developer & Digital Marketing Manager">
        <link rel="icon" type="image/png" href="/icon.png" />
        <link rel="apple-touch-icon" href="/icon.png" />
        <link rel="preconnect" href="https://fonts.googleapis.com" />
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
        <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet" />
    </Head>

    <div class="min-h-screen bg-slate-50 text-slate-900 transition-colors duration-300 dark:bg-[#0b0f17] dark:text-slate-100 font-['Plus_Jakarta_Sans',sans-serif]">
        <!-- Top Sticky Header Navigation -->
        <header class="sticky top-0 z-50 backdrop-blur-md bg-white/80 border-b border-slate-200/80 dark:bg-[#0b0f17]/80 dark:border-slate-800/80">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between gap-4">
                <!-- Brand / Logo -->
                <div class="flex items-center gap-3">
                    <div class="relative group">
                        <img
                            :src="profile.image"
                            alt="Kashif Abbas"
                            class="w-11 h-11 rounded-full object-cover ring-2 ring-indigo-500/80 shadow-md group-hover:scale-105 transition-transform"
                        />
                        <span class="absolute bottom-0 right-0 w-3.5 h-3.5 bg-emerald-500 border-2 border-white dark:border-[#0b0f17] rounded-full"></span>
                    </div>
                    <div>
                        <h1 class="text-lg font-bold tracking-tight text-slate-900 dark:text-white leading-tight">
                            Kashif Abbas
                        </h1>
                        <p class="text-xs font-medium text-indigo-600 dark:text-indigo-400">
                            BSCS (Bachelor in Computer Science)
                        </p>
                    </div>
                </div>

                <!-- Center Mode Selector (Main Profession Switcher) -->
                <nav class="hidden md:flex items-center p-1 bg-slate-100 dark:bg-slate-900/90 rounded-full border border-slate-200 dark:border-slate-800 shadow-inner">
                    <button
                        @click="activeMode = 'developer'"
                        :class="[
                            'flex items-center gap-2 px-4 py-2 text-xs font-semibold rounded-full transition-all duration-200',
                            activeMode === 'developer'
                                ? 'bg-indigo-600 text-white shadow-md shadow-indigo-600/30'
                                : 'text-slate-600 hover:text-slate-900 dark:text-slate-400 dark:hover:text-white',
                        ]"
                    >
                        <Code class="w-4 h-4" />
                        Full-Stack Developer
                    </button>
                    <button
                        @click="activeMode = 'marketing'"
                        :class="[
                            'flex items-center gap-2 px-4 py-2 text-xs font-semibold rounded-full transition-all duration-200',
                            activeMode === 'marketing'
                                ? 'bg-rose-600 text-white shadow-md shadow-rose-600/30'
                                : 'text-slate-600 hover:text-slate-900 dark:text-slate-400 dark:hover:text-white',
                        ]"
                    >
                        <Megaphone class="w-4 h-4" />
                        Digital Marketing Manager
                    </button>
                    <button
                        @click="activeMode = 'all'"
                        :class="[
                            'flex items-center gap-2 px-4 py-2 text-xs font-semibold rounded-full transition-all duration-200',
                            activeMode === 'all'
                                ? 'bg-slate-900 text-white dark:bg-slate-100 dark:text-slate-900 shadow-md'
                                : 'text-slate-600 hover:text-slate-900 dark:text-slate-400 dark:hover:text-white',
                        ]"
                    >
                        <Sparkles class="w-4 h-4 text-amber-400" />
                        All Skills
                    </button>
                </nav>

                <!-- Right Actions & Theme Switcher -->
                <div class="flex items-center gap-3">
                    <a
                        :href="`mailto:${profile.email}`"
                        class="hidden sm:inline-flex items-center gap-2 px-4 py-2 text-xs font-semibold rounded-lg bg-indigo-50 text-indigo-600 hover:bg-indigo-100 dark:bg-indigo-950/50 dark:text-indigo-300 dark:hover:bg-indigo-900/50 transition-colors"
                    >
                        <Mail class="w-3.5 h-3.5" />
                        Contact Me
                    </a>

                    <!-- Dark Mode Toggle Button -->
                    <button
                        @click="toggleDarkMode"
                        aria-label="Toggle Theme"
                        class="p-2.5 rounded-full bg-slate-100 hover:bg-slate-200 text-slate-700 dark:bg-slate-800/80 dark:hover:bg-slate-800 dark:text-slate-200 transition-colors"
                    >
                        <Sun v-if="isDark" class="w-4 h-4 text-amber-400" />
                        <Moon v-else class="w-4 h-4 text-slate-700" />
                    </button>
                </div>
            </div>

            <!-- Mobile View Mode Switcher Bar -->
            <div class="md:hidden flex items-center justify-around p-2 bg-slate-100/90 dark:bg-slate-900/90 border-t border-slate-200 dark:border-slate-800 gap-1.5 text-xs overflow-x-auto">
                <button
                    @click="activeMode = 'developer'"
                    :class="[
                        'flex items-center gap-1.5 px-3.5 py-1.5 rounded-full font-bold whitespace-nowrap transition-all duration-200',
                        activeMode === 'developer' ? 'bg-indigo-600 text-white shadow-sm' : 'text-slate-600 dark:text-slate-400 hover:text-slate-900 dark:hover:text-white',
                    ]"
                >
                    <Code class="w-3.5 h-3.5" />
                    Developer
                </button>
                <button
                    @click="activeMode = 'marketing'"
                    :class="[
                        'flex items-center gap-1.5 px-3.5 py-1.5 rounded-full font-bold whitespace-nowrap transition-all duration-200',
                        activeMode === 'marketing' ? 'bg-rose-600 text-white shadow-sm' : 'text-slate-600 dark:text-slate-400 hover:text-slate-900 dark:hover:text-white',
                    ]"
                >
                    <Megaphone class="w-3.5 h-3.5" />
                    Marketing
                </button>
                <button
                    @click="activeMode = 'all'"
                    :class="[
                        'flex items-center gap-1.5 px-3.5 py-1.5 rounded-full font-bold whitespace-nowrap transition-all duration-200',
                        activeMode === 'all' ? 'bg-slate-900 text-white dark:bg-slate-100 dark:text-slate-900 shadow-sm' : 'text-slate-600 dark:text-slate-400 hover:text-slate-900 dark:hover:text-white',
                    ]"
                >
                    <Sparkles class="w-3.5 h-3.5 text-amber-400" />
                    All Skills
                </button>
            </div>
        </header>

        <!-- Hero Section -->
        <section class="relative overflow-hidden py-16 lg:py-24">
            <!-- Background Glow Decor -->
            <div class="absolute top-1/4 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-gradient-to-tr from-indigo-500/10 via-rose-500/10 to-emerald-500/10 rounded-full blur-3xl pointer-events-none"></div>

            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="grid lg:grid-cols-12 gap-12 items-center">
                    <!-- Left Hero Text & Mode Intro -->
                    <div class="lg:col-span-7 space-y-6">
                        <!-- Location & Status Badge -->
                        <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-slate-200/70 dark:bg-slate-800/80 border border-slate-300/50 dark:border-slate-700/50 text-xs font-medium text-slate-700 dark:text-slate-300 shadow-sm">
                            <MapPin class="w-3.5 h-3.5 text-indigo-500" />
                            <span>{{ profile.location }}</span>
                            <span class="w-1 h-1 rounded-full bg-slate-400"></span>
                            <span class="text-indigo-600 dark:text-indigo-400 font-semibold">{{ profile.locationNote }}</span>
                        </div>

                        <!-- Dynamic Role Heading -->
                        <div class="space-y-2">
                            <h2 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-slate-900 dark:text-white leading-[1.15]">
                                Hi, I'm <span class="bg-gradient-to-r from-indigo-600 via-rose-500 to-amber-500 bg-clip-text text-transparent">Kashif Abbas</span>
                            </h2>
                            <p class="text-xl sm:text-2xl font-bold text-slate-700 dark:text-slate-200 flex items-center gap-2">
                                <span v-if="activeMode === 'developer'" class="text-indigo-600 dark:text-indigo-400 flex items-center gap-2">
                                    <Code class="w-6 h-6" /> Senior Full-Stack Web Developer
                                </span>
                                <span v-else-if="activeMode === 'marketing'" class="text-rose-600 dark:text-rose-400 flex items-center gap-2">
                                    <Megaphone class="w-6 h-6" /> Digital Media Marketing Manager
                                </span>
                                <span v-else class="text-amber-600 dark:text-amber-400 flex items-center gap-2">
                                    <Sparkles class="w-6 h-6" /> Full-Stack Developer & Marketing Manager
                                </span>
                            </p>
                        </div>

                        <!-- Summary Paragraph -->
                        <p class="text-base sm:text-lg text-slate-600 dark:text-slate-300 leading-relaxed font-normal">
                            {{ summaries[activeMode] }}
                        </p>

                        <!-- Key Quick Stats -->
                        <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 py-4">
                            <div class="p-3.5 rounded-xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-sm">
                                <div class="text-2xl font-extrabold text-indigo-600 dark:text-indigo-400">7+</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400">Years Experience</div>
                            </div>
                            <div class="p-3.5 rounded-xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-sm">
                                <div class="text-2xl font-extrabold text-rose-600 dark:text-rose-400">15+</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400">Enterprise Apps</div>
                            </div>
                            <div class="p-3.5 rounded-xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-sm">
                                <div class="text-2xl font-extrabold text-emerald-600 dark:text-emerald-400">20+</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400">Paid Campaigns</div>
                            </div>
                            <div class="p-3.5 rounded-xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-sm">
                                <div class="text-2xl font-extrabold text-amber-500">BSCS</div>
                                <div class="text-xs font-medium text-slate-500 dark:text-slate-400">Computer Science</div>
                            </div>
                        </div>

                        <!-- CTA Buttons -->
                        <div class="flex flex-wrap items-center gap-4 pt-2">
                            <a
                                href="#projects"
                                class="inline-flex items-center gap-2 px-6 py-3 rounded-xl bg-indigo-600 hover:bg-indigo-700 text-white font-semibold text-sm shadow-lg shadow-indigo-600/30 transition-all hover:scale-[1.02]"
                            >
                                <Briefcase class="w-4 h-4" />
                                View Featured Projects
                            </a>
                            <a
                                href="#contact"
                                class="inline-flex items-center gap-2 px-6 py-3 rounded-xl bg-white hover:bg-slate-100 text-slate-900 border border-slate-300 dark:bg-slate-900 dark:hover:bg-slate-800 dark:text-white dark:border-slate-800 font-semibold text-sm shadow-sm transition-all"
                            >
                                <Mail class="w-4 h-4 text-indigo-500" />
                                Get In Touch
                            </a>
                        </div>
                    </div>

                    <!-- Right Hero Profile Card -->
                    <div class="lg:col-span-5 flex justify-center">
                        <div class="relative w-full max-w-md">
                            <!-- Card Glow Aura -->
                            <div class="absolute -inset-1.5 bg-gradient-to-r from-indigo-500 via-rose-500 to-amber-500 rounded-3xl blur opacity-30 dark:opacity-40"></div>

                            <div class="relative bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 rounded-3xl p-6 shadow-2xl space-y-6">
                                <!-- Profile Photo -->
                                <div class="relative overflow-hidden rounded-2xl aspect-[4/5] shadow-lg group">
                                    <img
                                        :src="profile.image"
                                        alt="Kashif Abbas"
                                        class="w-full h-full object-cover object-top group-hover:scale-105 transition-transform duration-500"
                                    />
                                    <div class="absolute inset-0 bg-gradient-to-t from-slate-950/80 via-transparent to-transparent"></div>
                                    <div class="absolute bottom-4 left-4 right-4 text-white">
                                        <h3 class="text-xl font-bold">Kashif Abbas</h3>
                                        <p class="text-xs text-slate-300 font-medium flex items-center gap-1.5">
                                            <GraduationCap class="w-4 h-4 text-amber-400" />
                                            {{ profile.education }}
                                        </p>
                                    </div>
                                </div>

                                <!-- Contact Quick Links -->
                                <div class="space-y-2.5 text-xs text-slate-600 dark:text-slate-300">
                                    <div class="flex items-center justify-between p-2.5 rounded-lg bg-slate-50 dark:bg-slate-800/50">
                                        <span class="flex items-center gap-2 font-medium">
                                            <Mail class="w-4 h-4 text-indigo-500" />
                                            Email
                                        </span>
                                        <a :href="`mailto:${profile.email}`" class="text-indigo-600 dark:text-indigo-400 font-semibold hover:underline">
                                            {{ profile.email }}
                                        </a>
                                    </div>
                                    <div class="flex items-center justify-between p-2.5 rounded-lg bg-slate-50 dark:bg-slate-800/50">
                                        <span class="flex items-center gap-2 font-medium">
                                            <Phone class="w-4 h-4 text-rose-500" />
                                            Phone / WhatsApp
                                        </span>
                                        <a :href="`tel:${profile.phone}`" class="text-slate-900 dark:text-white font-semibold">
                                            {{ profile.phone }}
                                        </a>
                                    </div>
                                    <div class="flex items-center justify-between p-2.5 rounded-lg bg-slate-50 dark:bg-slate-800/50">
                                        <span class="flex items-center gap-2 font-medium">
                                            <Globe class="w-4 h-4 text-emerald-500" />
                                            Official Domain
                                        </span>
                                        <a :href="profile.website" target="_blank" class="text-emerald-600 dark:text-emerald-400 font-semibold hover:underline flex items-center gap-1">
                                            autometasoft.com
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

        <!-- Interactive Profession Selector Banner -->
        <section class="py-6 bg-slate-100/80 dark:bg-slate-900/50 border-y border-slate-200 dark:border-slate-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-4">
                <p class="text-xs font-bold tracking-wider uppercase text-slate-500 dark:text-slate-400">
                    Switch Portfolio Perspective Below
                </p>
                <div class="inline-flex flex-wrap justify-center items-center p-1.5 bg-white dark:bg-slate-900 rounded-2xl border border-slate-200 dark:border-slate-800 shadow-md gap-2 w-full sm:w-auto max-w-full overflow-x-auto">
                    <button
                        @click="activeMode = 'developer'"
                        :class="[
                            'flex items-center gap-2 px-6 py-3 rounded-xl font-bold text-sm transition-all duration-200',
                            activeMode === 'developer'
                                ? 'bg-indigo-600 text-white shadow-lg shadow-indigo-600/30 scale-[1.02]'
                                : 'text-slate-700 hover:text-slate-900 dark:text-slate-300 dark:hover:text-white hover:bg-slate-100 dark:hover:bg-slate-800',
                        ]"
                    >
                        <Code class="w-5 h-5 text-indigo-200" />
                        Full-Stack Developer Mode
                    </button>

                    <button
                        @click="activeMode = 'marketing'"
                        :class="[
                            'flex items-center gap-2 px-6 py-3 rounded-xl font-bold text-sm transition-all duration-200',
                            activeMode === 'marketing'
                                ? 'bg-rose-600 text-white shadow-lg shadow-rose-600/30 scale-[1.02]'
                                : 'text-slate-700 hover:text-slate-900 dark:text-slate-300 dark:hover:text-white hover:bg-slate-100 dark:hover:bg-slate-800',
                        ]"
                    >
                        <Megaphone class="w-5 h-5 text-rose-200" />
                        Digital Marketing Manager Mode
                    </button>

                    <button
                        @click="activeMode = 'all'"
                        :class="[
                            'flex items-center gap-2 px-6 py-3 rounded-xl font-bold text-sm transition-all duration-200',
                            activeMode === 'all'
                                ? 'bg-slate-900 text-white dark:bg-white dark:text-slate-900 shadow-lg scale-[1.02]'
                                : 'text-slate-700 hover:text-slate-900 dark:text-slate-300 dark:hover:text-white hover:bg-slate-100 dark:hover:bg-slate-800',
                        ]"
                    >
                        <Sparkles class="w-5 h-5 text-amber-400" />
                        Combined Overview
                    </button>
                </div>
            </div>
        </section>


        <!-- Work Experience Section -->
        <section id="experience" class="py-20 lg:py-28">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Section Header -->
                <div class="text-center space-y-3">
                    <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-indigo-100 text-indigo-700 dark:bg-indigo-950/70 dark:text-indigo-300 text-xs font-bold uppercase tracking-wider">
                        <Briefcase class="w-3.5 h-3.5" /> Career History
                    </span>
                    <h3 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                        Professional Work Experience
                    </h3>
                    <p class="text-slate-600 dark:text-slate-400 max-w-2xl mx-auto text-sm sm:text-base">
                        Proven track record delivering scalable enterprise software and managing high-performance digital marketing campaigns.
                    </p>
                </div>

                <!-- Experience Cards Timeline -->
                <div class="space-y-8 relative before:absolute before:inset-0 before:left-4 sm:before:left-1/2 before:-translate-x-px before:w-0.5 before:bg-slate-200 dark:before:bg-slate-800">
                    <div
                        v-for="(exp, idx) in filteredExperiences"
                        :key="exp.id"
                        class="relative flex flex-col sm:flex-row items-start group"
                    >
                        <!-- Timeline Node Dot -->
                        <div class="absolute left-4 sm:left-1/2 -translate-x-1/2 w-7 h-7 sm:w-8 sm:h-8 rounded-full bg-white dark:bg-slate-900 border-4 border-indigo-600 dark:border-indigo-500 shadow-md z-10 flex items-center justify-center">
                            <span class="w-2 h-2 rounded-full bg-indigo-600 dark:bg-indigo-400"></span>
                        </div>

                        <!-- Content Box -->
                        <div
                            :class="[
                                'w-[calc(100%-2.5rem)] sm:w-[calc(50%-2.5rem)] ml-10 sm:ml-0 p-5 sm:p-8 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200/90 dark:border-slate-800/90 shadow-lg hover:shadow-xl transition-all duration-300 space-y-4',
                                idx % 2 === 0 ? 'sm:mr-auto' : 'sm:ml-auto',
                            ]"
                        >
                            <div class="flex flex-wrap items-center justify-between gap-2 border-b border-slate-100 dark:border-slate-800 pb-3">
                                <div>
                                    <span
                                        :class="[
                                            'inline-block px-2.5 py-0.5 rounded text-[11px] font-bold uppercase tracking-wider mb-1',
                                            exp.mode === 'developer'
                                                ? 'bg-indigo-100 text-indigo-700 dark:bg-indigo-950 dark:text-indigo-300'
                                                : exp.mode === 'marketing'
                                                ? 'bg-rose-100 text-rose-700 dark:bg-rose-950 dark:text-rose-300'
                                                : 'bg-amber-100 text-amber-700 dark:bg-amber-950 dark:text-amber-300',
                                        ]"
                                    >
                                        {{ exp.mode === 'developer' ? 'Software Engineering' : exp.mode === 'marketing' ? 'Digital Marketing' : 'Hybrid Role' }}
                                    </span>
                                    <h4 class="text-xl font-bold text-slate-900 dark:text-white">
                                        {{ exp.role }}
                                    </h4>
                                    <p class="text-sm font-semibold text-indigo-600 dark:text-indigo-400 flex items-center gap-1.5">
                                        <Building2 class="w-4 h-4" />
                                        {{ exp.company }}
                                    </p>
                                </div>
                                <div class="text-right">
                                    <span class="inline-block px-3 py-1 rounded-full bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-300 text-xs font-semibold">
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

                            <!-- Bullet Points -->
                            <ul class="space-y-2 text-xs sm:text-sm text-slate-700 dark:text-slate-300">
                                <li v-for="(b, bIdx) in exp.bullets" :key="bIdx" class="flex items-start gap-2">
                                    <CheckCircle2 class="w-4 h-4 text-emerald-500 shrink-0 mt-0.5" />
                                    <span>{{ b }}</span>
                                </li>
                            </ul>

                            <!-- Skill Tags -->
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

        <!-- Featured Projects & Key Systems Showcase -->
        <section id="projects" class="py-20 lg:py-28 bg-slate-100/70 dark:bg-slate-900/40 border-t border-slate-200 dark:border-slate-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Section Header -->
                <div class="flex flex-col md:flex-row md:items-end justify-between gap-6">
                    <div class="space-y-3">
                        <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-rose-100 text-rose-700 dark:bg-rose-950/70 dark:text-rose-300 text-xs font-bold uppercase tracking-wider">
                            <Layers class="w-3.5 h-3.5" /> Portfolio Portfolio Showcase
                        </span>
                        <h3 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                            Featured Projects & Marketing Campaigns
                        </h3>
                        <p class="text-slate-600 dark:text-slate-400 text-sm sm:text-base max-w-xl">
                            Enterprise software solutions, hospital systems, e-commerce stores, and high-impact digital marketing campaigns.
                        </p>
                    </div>

                    <!-- Filter Pill Selector -->
                    <div class="flex items-center p-1 bg-white dark:bg-slate-900 rounded-xl border border-slate-200 dark:border-slate-800 shadow-sm self-start max-w-full overflow-x-auto">
                        <button
                            @click="activeMode = 'developer'"
                            :class="[
                                'px-4 py-2 text-xs font-bold rounded-lg transition-colors',
                                activeMode === 'developer' ? 'bg-indigo-600 text-white' : 'text-slate-600 dark:text-slate-400',
                            ]"
                        >
                            Web Apps (Full-Stack)
                        </button>
                        <button
                            @click="activeMode = 'marketing'"
                            :class="[
                                'px-4 py-2 text-xs font-bold rounded-lg transition-colors',
                                activeMode === 'marketing' ? 'bg-rose-600 text-white' : 'text-slate-600 dark:text-slate-400',
                            ]"
                        >
                            Marketing Campaigns
                        </button>
                        <button
                            @click="activeMode = 'all'"
                            :class="[
                                'px-4 py-2 text-xs font-bold rounded-lg transition-colors',
                                activeMode === 'all' ? 'bg-slate-800 text-white dark:bg-slate-200 dark:text-slate-900' : 'text-slate-600 dark:text-slate-400',
                            ]"
                        >
                            All Projects
                        </button>
                    </div>
                </div>

                <!-- Projects Grid -->
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <div
                        v-for="proj in filteredProjects"
                        :key="proj.id"
                        class="group flex flex-col bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 rounded-2xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300 hover:-translate-y-1"
                    >
                        <!-- Card Banner Header -->
                        <div class="p-6 bg-gradient-to-br from-slate-900 via-slate-800 to-indigo-950 text-white relative">
                            <div class="flex items-center justify-between gap-2 mb-2">
                                <span class="px-2.5 py-0.5 rounded text-[10px] font-extrabold uppercase tracking-wider bg-white/20 text-white backdrop-blur-md">
                                    {{ proj.category }}
                                </span>
                                <Code v-if="proj.mode === 'developer'" class="w-4 h-4 text-indigo-400" />
                                <Megaphone v-else class="w-4 h-4 text-rose-400" />
                            </div>
                            <h4 class="text-xl font-extrabold leading-snug group-hover:text-indigo-300 transition-colors">
                                {{ proj.title }}
                            </h4>
                            <p class="text-xs text-slate-300 mt-1 font-medium">
                                {{ proj.subtitle }}
                            </p>
                        </div>

                        <!-- Card Body -->
                        <div class="p-6 flex-1 flex flex-col justify-between space-y-6">
                            <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 leading-relaxed font-normal">
                                {{ proj.description }}
                            </p>

                            <!-- Highlights list if present -->
                            <div v-if="proj.highlights" class="space-y-1.5 bg-slate-50 dark:bg-slate-800/60 p-3 rounded-xl text-xs">
                                <span class="font-bold text-slate-700 dark:text-slate-300 block mb-1">Featured Implementation:</span>
                                <div v-for="h in proj.highlights" :key="h" class="flex items-center gap-1.5 text-slate-600 dark:text-slate-300">
                                    <Check class="w-3.5 h-3.5 text-indigo-500 shrink-0" />
                                    <span>{{ h }}</span>
                                </div>
                            </div>

                            <!-- Live Project / Client Links -->
                            <div v-if="proj.links && proj.links.length" class="space-y-2 pt-2 border-t border-slate-100 dark:border-slate-800">
                                <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wider block">Live Links / Platforms:</span>
                                <div class="flex flex-wrap gap-2">
                                    <a
                                        v-for="l in proj.links"
                                        :key="l.url"
                                        :href="l.url"
                                        target="_blank"
                                        class="inline-flex items-center gap-1 px-3 py-1.5 rounded-lg bg-indigo-50 hover:bg-indigo-100 text-indigo-700 dark:bg-indigo-950/60 dark:hover:bg-indigo-900/60 dark:text-indigo-300 text-xs font-semibold transition-colors"
                                    >
                                        {{ l.label }}
                                        <ArrowUpRight class="w-3 h-3" />
                                    </a>
                                </div>
                            </div>

                            <!-- Tech Stack Pills -->
                            <div class="flex flex-wrap gap-1.5 pt-2">
                                <span
                                    v-for="t in proj.tech"
                                    :key="t"
                                    class="px-2 py-0.5 rounded bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-300 text-[11px] font-medium"
                                >
                                    {{ t }}
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Technical & Marketing Skills Matrix -->
        <section id="skills" class="py-20 lg:py-28">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Section Header -->
                <div class="text-center space-y-3">
                    <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-emerald-100 text-emerald-700 dark:bg-emerald-950/70 dark:text-emerald-300 text-xs font-bold uppercase tracking-wider">
                        <Cpu class="w-3.5 h-3.5" /> Capabilities
                    </span>
                    <h3 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                        Core Competencies & Toolsets
                    </h3>
                    <p class="text-slate-600 dark:text-slate-400 max-w-xl mx-auto text-sm sm:text-base">
                        Comprehensive skill matrix spanning web development, database architecture, ad campaign management, and creative design.
                    </p>
                </div>

                <!-- Skills Grid -->
                <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div
                        v-for="sk in displayedSkills"
                        :key="sk.name"
                        class="p-5 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md space-y-3"
                    >
                        <div class="flex items-center justify-between">
                            <h4 class="font-bold text-sm text-slate-900 dark:text-white">
                                {{ sk.name }}
                            </h4>
                            <span class="px-2 py-0.5 rounded text-[10px] font-bold uppercase bg-slate-100 dark:bg-slate-800 text-indigo-600 dark:text-indigo-400">
                                {{ sk.category }}
                            </span>
                        </div>
                        <div class="w-full bg-slate-100 dark:bg-slate-800 h-2.5 rounded-full overflow-hidden">
                            <div
                                class="bg-gradient-to-r from-indigo-500 via-rose-500 to-amber-500 h-full rounded-full transition-all duration-500"
                                :style="{ width: `${sk.level}%` }"
                            ></div>
                        </div>
                        <div class="text-right text-xs font-semibold text-slate-500 dark:text-slate-400">
                            {{ sk.level }}% Proficiency
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Education & Languages Section -->
        <section class="py-16 bg-slate-100/70 dark:bg-slate-900/40 border-t border-slate-200 dark:border-slate-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid md:grid-cols-2 gap-8">
                    <!-- Education Card -->
                    <div class="p-8 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-lg space-y-4">
                        <div class="inline-flex p-3 rounded-2xl bg-indigo-50 dark:bg-indigo-950/60 text-indigo-600 dark:text-indigo-400">
                            <GraduationCap class="w-6 h-6" />
                        </div>
                        <h4 class="text-xl font-bold text-slate-900 dark:text-white">Academic Education</h4>
                        <div class="border-l-2 border-indigo-500 pl-4 space-y-1">
                            <h5 class="font-bold text-slate-900 dark:text-white">Bachelor of Science in Computer Science (BSCS)</h5>
                            <p class="text-xs text-slate-500 dark:text-slate-400">Bachelor's Degree · Computer Science & Software Engineering</p>
                        </div>
                    </div>

                    <!-- Languages Card -->
                    <div class="p-8 rounded-3xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-lg space-y-4">
                        <div class="inline-flex p-3 rounded-2xl bg-emerald-50 dark:bg-emerald-950/60 text-emerald-600 dark:text-emerald-400">
                            <Globe class="w-6 h-6" />
                        </div>
                        <h4 class="text-xl font-bold text-slate-900 dark:text-white">Languages</h4>
                        <div class="grid grid-cols-3 gap-3">
                            <div v-for="lang in profile.languages" :key="lang.name" class="p-3 rounded-xl bg-slate-50 dark:bg-slate-800 text-center">
                                <div class="font-bold text-sm text-slate-900 dark:text-white">{{ lang.name }}</div>
                                <div class="text-xs font-semibold text-emerald-600 dark:text-emerald-400">{{ lang.level }}</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Core Growth Marketing Services & Platforms (Visible when Marketing or All mode active) -->
        <section v-if="activeMode === 'marketing' || activeMode === 'all'" id="marketing-services" class="py-20 lg:py-28 bg-slate-900 text-white relative overflow-hidden">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-16 relative z-10">
                <!-- Section Header -->
                <div class="text-center space-y-3">
                    <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-rose-500/20 text-rose-300 text-xs font-bold uppercase tracking-wider border border-rose-500/30">
                        <Megaphone class="w-3.5 h-3.5" /> Core Offerings
                    </span>
                    <h3 class="text-3xl sm:text-4xl font-extrabold">
                        Growth Marketing & Branding Services
                    </h3>
                    <p class="text-slate-400 max-w-2xl mx-auto text-sm sm:text-base">
                        End-to-end paid advertising, high-converting graphic design, e-commerce CRO, and social media management.
                    </p>
                </div>

                <!-- Services Grid -->
                <div class="grid md:grid-cols-2 gap-8">
                    <div
                        v-for="srv in marketingServices"
                        :key="srv.title"
                        class="p-8 rounded-3xl bg-slate-800/80 border border-slate-700/80 shadow-xl space-y-6 hover:border-rose-500/50 transition-all duration-300 flex flex-col justify-between"
                    >
                        <div class="space-y-4">
                            <div class="flex items-center justify-between">
                                <span class="px-3 py-1 rounded-full bg-rose-500/20 text-rose-400 text-xs font-bold uppercase border border-rose-500/30">
                                    {{ srv.badge }}
                                </span>
                                <Megaphone class="w-5 h-5 text-rose-400" />
                            </div>
                            <h4 class="text-xl font-extrabold text-white">{{ srv.title }}</h4>
                            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">{{ srv.description }}</p>
                        </div>

                        <!-- Features List -->
                        <div class="space-y-2 pt-4 border-t border-slate-700/60">
                            <div v-for="f in srv.features" :key="f" class="flex items-center gap-2 text-xs font-medium text-slate-200">
                                <CheckCircle2 class="w-4 h-4 text-emerald-400 shrink-0" />
                                <span>{{ f }}</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Marketing Platforms & Toolstack Badges -->
                <div class="space-y-6 text-center pt-8 border-t border-slate-800">
                    <h4 class="text-xs font-extrabold uppercase tracking-widest text-slate-400">Marketing & Design Toolset</h4>
                    <div class="flex flex-wrap justify-center gap-3">
                        <div
                            v-for="t in marketingToolstack"
                            :key="t.name"
                            class="px-4 py-2 rounded-xl bg-slate-800 border border-slate-700/70 text-xs font-bold text-slate-200 hover:border-rose-500/40 hover:text-white transition-colors"
                        >
                            <span class="text-white">{{ t.name }}</span>
                            <span class="text-[10px] text-slate-400 block font-normal">{{ t.platform }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>


        <!-- Contact Section -->
        <section id="contact" class="py-20 lg:py-28 relative">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <!-- Section Header -->
                <div class="text-center space-y-3">
                    <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-amber-100 text-amber-700 dark:bg-amber-950/70 dark:text-amber-300 text-xs font-bold uppercase tracking-wider">
                        <Mail class="w-3.5 h-3.5" /> Get In Touch
                    </span>
                    <h3 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
                        Let's Connect & Collaborate
                    </h3>
                    <p class="text-slate-600 dark:text-slate-400 max-w-xl mx-auto text-sm sm:text-base">
                        Available for full-time roles, remote contracts, enterprise web development, and growth marketing strategies.
                    </p>
                </div>

                <!-- Contact Cards Container -->
                <div class="grid md:grid-cols-3 gap-6 max-w-4xl mx-auto">
                    <!-- Email Card -->
                    <div class="p-6 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3">
                        <div class="w-12 h-12 rounded-full bg-indigo-50 dark:bg-indigo-950/60 text-indigo-600 dark:text-indigo-400 flex items-center justify-center mx-auto">
                            <Mail class="w-6 h-6" />
                        </div>
                        <h4 class="font-bold text-slate-900 dark:text-white">Email Address</h4>
                        <p class="text-xs text-slate-500 dark:text-slate-400">{{ profile.email }}</p>
                        <button
                            @click="copyEmail"
                            class="px-4 py-2 rounded-lg bg-indigo-600 hover:bg-indigo-700 text-white text-xs font-semibold shadow-md transition-colors inline-flex items-center gap-1.5"
                        >
                            <Check v-if="contactCopied" class="w-3.5 h-3.5" />
                            <span>{{ contactCopied ? 'Email Copied!' : 'Copy Email' }}</span>
                        </button>
                    </div>

                    <!-- Phone Card -->
                    <div class="p-6 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3">
                        <div class="w-12 h-12 rounded-full bg-rose-50 dark:bg-rose-950/60 text-rose-600 dark:text-rose-400 flex items-center justify-center mx-auto">
                            <Phone class="w-6 h-6" />
                        </div>
                        <h4 class="font-bold text-slate-900 dark:text-white">Phone / WhatsApp</h4>
                        <p class="text-xs text-slate-500 dark:text-slate-400">{{ profile.phone }}</p>
                        <a
                            :href="`tel:${profile.phone}`"
                            class="px-4 py-2 rounded-lg bg-rose-600 hover:bg-rose-700 text-white text-xs font-semibold shadow-md transition-colors inline-flex items-center gap-1.5"
                        >
                            <Phone class="w-3.5 h-3.5" />
                            <span>Call Directly</span>
                        </a>
                    </div>

                    <!-- Official Domain Card -->
                    <div class="p-6 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md text-center space-y-3">
                        <div class="w-12 h-12 rounded-full bg-emerald-50 dark:bg-emerald-950/60 text-emerald-600 dark:text-emerald-400 flex items-center justify-center mx-auto">
                            <Globe class="w-6 h-6" />
                        </div>
                        <h4 class="font-bold text-slate-900 dark:text-white">Official Domain</h4>
                        <p class="text-xs text-slate-500 dark:text-slate-400">autometasoft.com</p>
                        <a
                            :href="profile.website"
                            target="_blank"
                            class="px-4 py-2 rounded-lg bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-semibold shadow-md transition-colors inline-flex items-center gap-1.5"
                        >
                            <ExternalLink class="w-3.5 h-3.5" />
                            <span>Visit Website</span>
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="py-8 bg-white dark:bg-slate-950 border-t border-slate-200 dark:border-slate-800 text-center text-xs text-slate-500 dark:text-slate-400">
            <div class="max-w-7xl mx-auto px-4 flex flex-col sm:flex-row items-center justify-between gap-4">
                <div class="flex items-center gap-2">
                    <span class="font-bold text-slate-900 dark:text-white">Kashif Abbas</span>
                    <span>·</span>
                    <span>Full-Stack Web Developer & Digital Media Marketing Manager</span>
                </div>
                <div>
                    © {{ new Date().getFullYear() }} autometasoft.com. All rights reserved.
                </div>
            </div>
        </footer>
    </div>
</template>
