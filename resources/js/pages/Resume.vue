<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import { Download, ExternalLink, Mail, MapPin, Phone } from 'lucide-vue-next';

const profile = {
    name: 'Kashif Abbas',
    role: 'Senior Full-Stack Developer',
    location: 'Multan, Pakistan',
    email: 'kashifgabol512@gmail.com',
    phone: '+92 302 7772202',
    linkedin: 'linkedin.com/in/kashifgabol',
    portfolio: 'kashif.autometasoft.com',
};

const experience = [
    {
        role: 'Lead Full-Stack Developer',
        company: 'AutoMeta Software Solutions',
        period: 'Mar 2020 - Present',
        summary: 'Lead delivery of business-critical SaaS, ERP, hospital management, and financial systems for clients across Pakistan, the UK, UAE, and Saudi Arabia.',
        achievements: [
            'Led a team of 5+ developers through architecture, delivery, and production support.',
            'Built multi-tenant HMS, multi-branch ERP, POS, inventory, and tax calculation platforms.',
            'Reduced API response times by up to 45% through query optimization and caching.',
            'Introduced CI/CD and automated PHPUnit coverage to support 99.9% production availability.',
        ],
    },
    {
        role: 'Full-Stack Web Developer',
        company: 'Freelance Full-Stack Developer',
        period: '2016 - 2020',
        summary: 'Delivered custom corporate websites, client portals, quote tools, and administrative dashboards for international businesses as an independent developer.',
        achievements: [
            'Delivered 15+ projects on time and within budget for clients across the UAE, UK, and Saudi Arabia.',
            'Modernized legacy PHP applications into modular MVC architectures and integrated secure APIs.',
        ],
    },
];

const projects = [
    { name: 'Hospital Management System', detail: 'EMR, appointments, billing, pharmacy, and pathology workflows used by 200+ healthcare staff.', url: 'https://hms.autometasoft.com' },
    { name: 'Business Management ERP', detail: 'Multi-warehouse inventory, invoicing, sales orders, and financial reporting for distribution businesses.', url: 'https://www.autometasoft.com/login' },
    { name: 'PTA Duty & Tax Calculator', detail: 'Live customs tariff and foreign exchange calculation engine with multi-tier regulatory logic.', url: 'https://ptatax.autometasoft.com' },
    { name: 'AR Company Portal', detail: 'Operations portal for business workflows, customer records, and reporting.', url: 'https://arapp.autometasoft.com' },
    { name: 'UKSalts Corporate Website', detail: 'International product and business website for a UK-based client.', url: 'https://www.uksalts.net' },
    { name: 'UKSalts Mobile App', detail: 'Laravel-based mobile app published on Google Play with 10,000+ active users.', url: 'https://play.google.com/store/apps/details?id=com.uksalts.app' },
];

const skills = [
    'Laravel',
    'PHP',
    'Vue.js',
    'Inertia.js',
    'TypeScript',
    'REST APIs',
    'MySQL',
    'Tailwind CSS',
    'PHPUnit',
    'Git / CI/CD',
    'Linux / Nginx',
    'Mobile App Publishing',
];

const printResume = () => window.print();
</script>

<template>
    <Head title="Resume | Kashif Abbas">
        <link rel="preconnect" href="https://fonts.googleapis.com" />
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
        <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet" />
    </Head>

    <main class="resume-shell min-h-screen bg-[#e9e6df] px-4 py-8 font-['DM_Sans',sans-serif] text-[#202522] sm:px-8 lg:py-12">
        <div class="mx-auto max-w-[960px]">
            <div class="mb-4 flex justify-end print:hidden">
                <button
                    type="button"
                    @click="printResume"
                    class="inline-flex items-center gap-2 rounded-md bg-[#202522] px-4 py-2.5 text-sm font-semibold text-white transition hover:bg-[#39453e]"
                >
                    <Download class="h-4 w-4" />
                    Download Resume
                </button>
            </div>

            <article class="resume-paper overflow-hidden bg-[#fffdf8] shadow-[0_18px_60px_rgba(32,37,34,0.14)] print:shadow-none">
                <header class="border-b-[6px] border-[#c7e86b] bg-[#202522] px-7 py-8 text-white sm:px-12 sm:py-10">
                    <div class="flex flex-col justify-between gap-7 sm:flex-row sm:items-end">
                        <div>
                            <p class="mb-3 font-['Space_Mono',monospace] text-xs font-bold uppercase tracking-[0.22em] text-[#c7e86b]">Resume / 2026</p>
                            <h1 class="text-4xl font-bold tracking-[-0.04em] sm:text-6xl">{{ profile.name }}</h1>
                            <p class="mt-3 text-lg font-medium text-[#d7ddd8]">{{ profile.role }}</p>
                        </div>
                        <div class="grid gap-2 text-sm text-[#d7ddd8] sm:text-right">
                            <a :href="`mailto:${profile.email}`" class="inline-flex items-center gap-2 sm:justify-end hover:text-[#c7e86b]">
                                <Mail class="h-4 w-4 text-[#c7e86b]" /> {{ profile.email }}
                            </a>
                            <a :href="`tel:${profile.phone.replaceAll(' ', '')}`" class="inline-flex items-center gap-2 sm:justify-end hover:text-[#c7e86b]">
                                <Phone class="h-4 w-4 text-[#c7e86b]" /> {{ profile.phone }}
                            </a>
                            <span class="inline-flex items-center gap-2 sm:justify-end"><MapPin class="h-4 w-4 text-[#c7e86b]" /> {{ profile.location }}</span>
                        </div>
                    </div>
                    <div class="mt-7 flex flex-wrap gap-x-5 gap-y-2 border-t border-white/15 pt-4 font-['Space_Mono',monospace] text-xs text-[#c8d0ca]">
                        <a :href="`https://${profile.linkedin}`" target="_blank" class="inline-flex items-center gap-1.5 hover:text-[#c7e86b]"><ExternalLink class="h-3.5 w-3.5" /> {{ profile.linkedin }}</a>
                        <a :href="`https://${profile.portfolio}`" target="_blank" class="inline-flex items-center gap-1.5 hover:text-[#c7e86b]"><ExternalLink class="h-3.5 w-3.5" /> Portfolio: {{ profile.portfolio }}</a>
                    </div>
                </header>

                <div class="resume-content grid gap-9 px-7 py-8 sm:px-12 sm:py-10 lg:grid-cols-[1fr_260px]">
                    <div class="space-y-9">
                        <section>
                            <p class="section-label">Profile</p>
                            <p class="max-w-2xl text-[15px] leading-7 text-[#4c5750]">
                                Senior Full-Stack Developer with 7+ years of experience architecting high-traffic enterprise web applications, SaaS platforms, and distributed systems. Specializes in Laravel, Vue.js, Inertia.js, and relational database design, with a track record of turning complex business workflows into reliable software.
                            </p>
                        </section>

                        <section>
                            <p class="section-label">Experience</p>
                            <div class="space-y-7">
                                <div v-for="job in experience" :key="`${job.company}-${job.role}`" class="relative border-l-2 border-[#c7e86b] pl-5">
                                    <div class="absolute -left-[7px] top-1 h-3 w-3 rounded-full bg-[#202522] ring-4 ring-[#fffdf8]"></div>
                                    <div class="flex flex-col justify-between gap-1 sm:flex-row sm:items-baseline">
                                        <div>
                                            <h2 class="text-lg font-bold text-[#202522]">{{ job.role }}</h2>
                                            <p class="font-semibold text-[#61713e]">{{ job.company }}</p>
                                        </div>
                                        <p class="font-['Space_Mono',monospace] text-xs font-bold text-[#7c867e]">{{ job.period }}</p>
                                    </div>
                                    <p class="mt-3 text-sm leading-6 text-[#4c5750]">{{ job.summary }}</p>
                                    <ul class="mt-3 space-y-2 text-sm leading-6 text-[#4c5750]">
                                        <li v-for="achievement in job.achievements" :key="achievement" class="flex gap-2"><span class="mt-2 h-1.5 w-1.5 shrink-0 rounded-full bg-[#93ae48]"></span><span>{{ achievement }}</span></li>
                                    </ul>
                                </div>
                            </div>
                        </section>

                    </div>

                    <aside class="space-y-8 border-t border-[#d9ddd4] pt-7 lg:border-l lg:border-t-0 lg:pl-7 lg:pt-0">
                        <section>
                            <p class="section-label">Core Skills</p>
                            <div class="flex flex-wrap gap-2">
                                <span v-for="skill in skills" :key="skill" class="rounded bg-[#eef2e8] px-2.5 py-1.5 text-xs font-semibold text-[#3f5130]">{{ skill }}</span>
                            </div>
                        </section>

                        <section>
                            <p class="section-label">Education</p>
                            <h2 class="font-bold">Bachelor of Science in Computer Science</h2>
                            <p class="mt-1 text-sm leading-5 text-[#69736c]">Software engineering, algorithms, and application development</p>
                        </section>

                        <section>
                            <p class="section-label">Languages</p>
                            <div class="space-y-2 text-sm">
                                <p class="flex justify-between"><span>English</span><span class="text-[#69736c]">Professional</span></p>
                                <p class="flex justify-between"><span>Urdu</span><span class="text-[#69736c]">Native</span></p>
                                <p class="flex justify-between"><span>Arabic</span><span class="text-[#69736c]">Conversational</span></p>
                            </div>
                        </section>

                        <section class="border-t-2 border-[#c7e86b] pt-5">
                            <p class="section-label">Availability</p>
                            <p class="text-sm leading-6 text-[#4c5750]">Open to full-time remote roles, international contracts, and high-impact enterprise projects.</p>
                        </section>
                    </aside>
                </div>

                <section class="selected-work border-t border-[#d9ddd4] bg-[#fffdf8] px-7 py-8 sm:px-12 sm:py-10">
                    <p class="section-label">Selected Work</p>
                    <div class="grid gap-x-5 gap-y-6 sm:grid-cols-2">
                        <div v-for="project in projects" :key="project.name" class="border-t-2 border-[#202522] pt-3">
                            <a :href="project.url" target="_blank" class="group inline-flex items-start gap-1 text-sm font-bold leading-5 hover:text-[#61713e]">
                                <span>{{ project.name }}</span>
                                <ExternalLink class="mt-0.5 h-3.5 w-3.5 shrink-0 opacity-60 transition group-hover:opacity-100" />
                            </a>
                            <p class="mt-2 text-xs leading-5 text-[#69736c]">{{ project.detail }}</p>
                            <a :href="project.url" target="_blank" class="mt-1 block truncate font-['Space_Mono',monospace] text-[10px] text-[#7c867e] hover:text-[#61713e]">{{ project.url.replace('https://', '') }}</a>
                        </div>
                    </div>
                </section>

                <footer class="resume-footer flex flex-col gap-2 border-t border-[#d9ddd4] bg-[#fffdf8] px-7 py-5 text-center text-xs text-[#7c867e] sm:px-12">
                    <p class="font-semibold text-[#202522]">Kashif Abbas <span class="px-1 text-[#93ae48]">&middot;</span> Senior Full-Stack Web Developer</p>
                    <p>
                        <a href="https://www.linkedin.com/in/kashifgabol/" target="_blank" class="hover:text-[#61713e]">LinkedIn</a>
                        <span class="px-1 text-[#93ae48]">&middot;</span>
                        <a href="https://autometasoft.com/" target="_blank" class="hover:text-[#61713e]">AutoMeta Soft</a>
                    </p>
                    <p class="text-[11px]">&copy; 2026 Kashif Abbas. All rights reserved.</p>
                </footer>
            </article>
        </div>
    </main>
</template>

<style>
.section-label {
    margin-bottom: 1rem;
    color: #61713e;
    font-family: 'Space Mono', monospace;
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
}

@media print {
    @page {
        margin: 0;
        size: A4;
    }

    html,
    body {
        background: #fffdf8;
    }

    .resume-shell {
        min-height: 0;
        padding: 0;
    }

    .resume-paper {
        min-height: 100vh;
        box-shadow: none;
        -webkit-print-color-adjust: exact;
        print-color-adjust: exact;
    }

    .resume-content {
        display: grid !important;
        grid-template-columns: minmax(0, 1fr) 260px;
        gap: 1.5rem;
        align-items: start;
        padding-top: 1.75rem !important;
        padding-bottom: 1.75rem !important;
    }

    .resume-paper > header {
        padding-top: 2rem !important;
        padding-bottom: 2rem !important;
    }

    .resume-paper > header h1 {
        font-size: 3.25rem !important;
    }

    .resume-content .space-y-9 > :not([hidden]) ~ :not([hidden]) {
        margin-top: 1.5rem !important;
    }

    .resume-content .space-y-7 > :not([hidden]) ~ :not([hidden]) {
        margin-top: 1rem !important;
    }

    .resume-content p,
    .resume-content li {
        font-size: 0.8rem !important;
        line-height: 1.45 !important;
    }

    .resume-content h2 {
        font-size: 1rem !important;
        line-height: 1.3 !important;
    }

    .resume-content .section-label {
        margin-bottom: 0.65rem;
    }

    .selected-work {
        break-before: page;
        page-break-before: always;
        break-inside: avoid;
        page-break-inside: avoid;
        min-height: calc(100vh - 7rem);
        background: #fffdf8;
    }

    .resume-footer {
        background: #fffdf8;
        -webkit-print-color-adjust: exact;
        print-color-adjust: exact;
    }

    a {
        color: inherit;
        text-decoration: none;
    }
}
</style>
