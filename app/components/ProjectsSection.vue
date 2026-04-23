<template>
  <section id="projects" class="py-16 sm:py-20 md:py-32">
    <div class="container mx-auto px-4 sm:px-6">
      <div class="text-center mb-10 sm:mb-14 md:mb-16">
        <p
          class="text-primary font-medium tracking-widest uppercase text-sm mb-3"
        >
          Portfolio
        </p>
        <h2 class="text-3xl sm:text-4xl md:text-5xl font-display font-bold">
          Featured <span class="text-gradient">Projects</span>
        </h2>
      </div>

      <div
        class="grid md:grid-cols-2 gap-5 sm:gap-6 md:gap-8 max-w-5xl mx-auto"
      >
        <div
          v-for="(project, i) in features"
          :key="project.title"
          class="glass rounded-2xl overflow-hidden group hover:border-primary/40 transition-all duration-300"
        >
          <div class="h-2 bg-gradient-to-r from-primary/20 to-primary/5" />
          <div class="p-5 sm:p-7">
            <div class="flex items-start gap-4">
              <div
                v-if="project.icon"
                class="text-primary shrink-0 mt-1"
                v-html="project.icon"
              />
              <div class="min-w-0">
                <div class="flex flex-wrap items-center gap-x-3 gap-y-1 mb-2">
                  <h3
                    class="font-display font-bold text-lg sm:text-xl group-hover:text-primary transition-colors"
                  >
                    {{ project.title }}
                  </h3>
                  <span
                    v-if="project.year"
                    class="text-xs px-2 py-1 rounded-full bg-secondary text-secondary-foreground"
                  >
                    {{ project.year }}
                  </span>
                  <span
                    v-if="project.category"
                    class="text-xs text-muted-foreground"
                  >
                    {{ project.category }}
                  </span>
                </div>

                <p
                  v-if="project.meta"
                  class="text-sm text-muted-foreground mb-3"
                >
                  {{ project.meta }}
                </p>
              </div>
            </div>

            <h3
              v-if="project.subtitle"
              class="font-display font-semibold text-sm sm:text-base text-muted-foreground mt-4"
            >
              {{ project.subtitle }}
            </h3>
            <p class="text-muted-foreground text-sm leading-relaxed mt-3 mb-5">
              {{ project.description }}
            </p>
            <div class="flex flex-wrap gap-2 mb-5">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="text-xs px-3 py-1 rounded-full bg-secondary text-secondary-foreground"
              >
                {{ tag }}
              </span>
            </div>
            <div class="flex gap-4">
              <a
                v-if="project.liveUrl"
                :href="project.liveUrl"
                target="_blank"
                rel="noopener noreferrer"
                class="text-muted-foreground hover:text-primary transition-colors"
              >
                <ExternalLink :size="18" />
              </a>
              <a
                v-if="project.codeUrl"
                :href="project.codeUrl"
                target="_blank"
                rel="noopener noreferrer"
                class="text-muted-foreground hover:text-primary transition-colors"
              >
                <Github :size="18" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ExternalLink, Github } from "lucide-vue-next";

const features = [
  {
    title: "HomeAffairs",
    year: "2026",
    category: "E-commerce",
    tags: ["Nuxt 4", "Vue 3", "Supabase", "Paystack", "PWA"],
    meta: "Multi-branch grocery commerce • SSR • PWA",
    description:
      "A multi-branch grocery commerce platform with delivery and pickup flows, Paystack payments, pay-on-delivery controls, and dedicated admin + driver workflows.",
    liveUrl: "https://homeaffairs.vercel.app",
    problem:
      "Grocery operations across multiple branches break down without a unified system for inventory-aware shopping, fulfillment coordination, and real-time dispatch.",
    who: "Customers ordering groceries, store staff processing orders, branch managers overseeing operations, and drivers fulfilling deliveries.",
    impact:
      "Combines a modern shopping experience with operational tooling (verification, dispatch, inventory) and realtime driver assignment to reduce fulfillment delays and errors.",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="9" cy="21" r="1"/><circle cx="20" cy="21" r="1"/><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"/></svg>',
  },
  {
    title: "MediCore",
    year: "2026",
    category: "SaaS",
    tags: ["Nuxt", "Vue 3", "TypeScript", "Supabase", "Tailwind"],
    meta: "Hospital management system • Multi-tenant • RBAC",
    description:
      "A hospital management system for patient records, billing, staff roles, dashboards, and real-time notifications with tenant isolation and role-based access control.",
    liveUrl: "https://medicoree.vercel.app",
    problem:
      "Hospitals often rely on fragmented tools for records, billing, and staff coordination, making reporting and daily workflows slow and error-prone.",
    who: "Hospitals and clinics with admins, doctors, nurses, and accountants who need a single system of record for operations.",
    impact:
      "Centralizes patients, medical records, billing, and notifications with secure tenant boundaries and streamlined workflows for faster day-to-day operations.",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 3h18v18H3z"/><path d="M12 7v10"/><path d="M7 12h10"/></svg>',
  },
  {
    title: "Selify",
    subtitle: "Jiji.ng Alternative",
    year: "2023",
    category: "E-commerce",
    tags: ["Vue.js", "Node.js", "MongoDB"],
    description:
      "A modern classifieds marketplace where users can quickly list items like phones, cars, electronics, and services with smart pricing suggestions and verified listings.",
    liveUrl: "https://www.selify.ng",
    codeUrl: "https://github.com/Gandokijnr",
    problem:
      "Informal, fragmented marketplaces make it hard for everyday buyers and sellers to discover trustworthy listings and complete secure transactions.",
    who: "Individual sellers and small merchants in Nigeria looking to buy and sell products safely online.",
    impact:
      "A modern, user-centric marketplace platform designed to make buying and selling simple, safe, and rewarding for everyone.",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h7l7 7-7 7-7-7z"/><circle cx="9" cy="7" r="1"/></svg>',
  },
  {
    title: "VisionGardens Hotels",
    year: "2025",
    category: "Web Apps",
    tags: ["Nuxt", "TypeScript", "Stripe"],
    description:
      "A luxury booking platform that transforms outdated hotel websites into a real-time, high-converting reservation experience.",
    problem:
      "Premium hotels struggle to present their value online and handle bookings smoothly due to clunky websites.",
    who: "Boutique and luxury hotel owners who want to attract high-value guests through a modern digital experience.",
    impact:
      "Combines elegant room showcases, real-time availability, and seamless reservations to increase direct bookings.",
    liveUrl: "https://visiongardenshotel.com/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 10h18v8H3z"/><path d="M7 10V7a3 3 0 0 1 3-3h4a3 3 0 0 1 3 3v3"/></svg>',
  },
  {
    title: "Roomio",
    year: "2025",
    category: "SaaS",
    tags: ["Vue", "Python", "PostgreSQL"],
    description:
      "Transform hotel operations with effortless bookings, automated housekeeping, profit-driven revenue tools, and actionable analytics—all in one platform.",
    problem:
      "Hotels struggle with fragmented systems leading to errors, delays, staff stress, and lost revenue opportunities.",
    who: "Hotels, boutique stays, resorts, and serviced apartments looking to streamline operations and scale efficiently.",
    impact:
      "Centralizes availability, payments, and reservations to reduce admin overhead by 40% and deliver smoother guest experiences.",
    liveUrl: "https://roommio.netlify.app/landing",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="4" y="4" width="9" height="14" rx="1"/><path d="M7 7h3M7 11h3M7 15h3"/><circle cx="18" cy="13" r="3"/></svg>',
  },
  {
    title: "Winebay",
    year: "2025",
    category: "E-commerce",
    tags: ["React", "Commerce.js", "Tailwind"],
    description:
      "A modern e-commerce experience for discovering and purchasing curated wines, combining rich product storytelling with smooth checkout.",
    problem:
      "Wine lovers and boutique brands struggle with fragmented shopping experiences that lack discovery tools and trust-building content.",
    who: "Wine enthusiasts, collectors, and boutique wine brands seeking better online shopping experiences.",
    impact:
      "Makes it easier to discover the right bottle and purchase with confidence through a polished, conversion-focused experience.",
    liveUrl: "https://winebay.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 3h2v5a2 2 0 0 1-2 2v7"/><path d="M15 3h2v5a3 3 0 0 1-3 3h0a3 3 0 0 1-3-3V3h2"/></svg>',
  },
  {
    title: "My UniCamp",
    year: "2025",
    category: "Web Apps",
    tags: ["Vue", "Algolia", "Firebase"],
    description:
      "A course discovery platform that transforms scattered university information into a clear, searchable catalog of programs worldwide.",
    problem:
      "Prospective students are overwhelmed by scattered information and struggle to compare programs across schools.",
    who: "High school graduates, career switchers, and lifelong learners researching degree or certificate programs.",
    impact:
      "Simplifies program discovery, helping users quickly find relevant courses and make confident education decisions.",
    liveUrl: "https://myunicamp.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 7l9-4 9 4-9 4-9-4z"/><path d="M7 10v5a5 5 0 0 0 10 0v-5"/></svg>',
  },
  {
    title: "Farmxic",
    year: "2024",
    category: "Web Apps",
    tags: ["Nuxt", "Node.js", "MongoDB"],
    description:
      "An agricultural platform connecting isolated farming efforts into an ecosystem of modern tools, knowledge, and market opportunities.",
    problem:
      "Small and mid-scale farmers lack access to modern techniques, reliable markets, and relevant agricultural information.",
    who: "Farmers and agricultural cooperatives seeking better tools, knowledge, and market connections.",
    impact:
      "Connects farmers to resources and market access, helping improve yields, income, and resilience.",
    liveUrl: "https://www.farmxic.com/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 20c4-6 8-8 16-8-2.5 3-6 5-10 6.5"/><path d="M10 20c0-6 2-10 6-13"/></svg>',
  },
  {
    title: "SurePicks",
    year: "2025",
    category: "Web Apps",
    tags: ["React", "Python", "Redis"],
    description:
      "A sports prediction platform replacing gut-feel betting with data-driven insights and real-time odds analysis.",
    problem:
      "Sports bettors rely on guesswork or low-quality tips, resulting in uninformed bets and inconsistent outcomes.",
    who: "Recreational and semi-professional sports bettors seeking a data-backed edge.",
    impact:
      "Uses analytics, odds, and expert insights to help users make informed betting decisions and manage risk intelligently.",
    liveUrl: "https://surepicks.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 19V9"/><path d="M9 19V5"/><path d="M14 19v-7"/><path d="M17 8l2 2 3-3"/></svg>',
  },
  {
    title: "Real Estate Showcase",
    year: "2024",
    category: "Landing Pages",
    tags: ["HTML", "CSS", "JavaScript"],
    description:
      "A modern listings interface transforming static property catalogs into a responsive, searchable home-hunting experience.",
    problem:
      "Homebuyers struggle to find relevant properties when listings are poorly presented or hard to search.",
    who: "Real estate agencies and property developers needing a modern online presence.",
    impact:
      "Makes properties easier to browse and filter, driving more qualified leads and higher engagement.",
    liveUrl: "https://gidiestate.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 11l9-7 9 7v9a1 1 0 0 1-1 1h-5v-6H9v6H4a1 1 0 0 1-1-1z"/></svg>',
  },
  {
    title: "Agency Aggregator",
    year: "2025",
    category: "SaaS",
    tags: ["Vue", "Laravel", "MySQL"],
    description:
      "A management platform replacing scattered agency spreadsheets with a secure, all-in-one dashboard for teams, clients, and data.",
    problem:
      "Agencies manage clients and projects across disconnected tools, creating data silos and operational blind spots.",
    who: "Agency owners and operations managers at digital, creative, or marketing agencies.",
    impact:
      "Centralizes data with role-based access and dashboards, improving control, visibility, and efficiency.",
    liveUrl: "https://agencyaggregator.netlify.app/auth/login",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16v4H4zM4 10h10v4H4zM4 16h7v4H4z"/></svg>',
  },
  {
    title: "Fx Trading Academy",
    year: "2024",
    category: "Web Apps",
    tags: ["Nuxt", "Node.js", "Chart.js"],
    description:
      "An educational platform transforming scattered forex knowledge into structured, actionable learning modules.",
    problem:
      "Aspiring traders face steep learning curves and fragmented resources, leading to costly mistakes in live markets.",
    who: "Beginner and intermediate forex traders seeking structured, practical learning.",
    impact:
      "Provides guided modules, analysis tools, and trading guides to reduce confusion and improve decision-making.",
    liveUrl: "https://gandokigroup.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 20V10m4 10V6m4 14V8m4 12V4"/></svg>',
  },
  {
    title: "Job Navigator",
    year: "2023",
    category: "Web Apps",
    tags: ["React", "Express", "MongoDB"],
    description:
      "A job search platform transforming scattered applications into a single, trackable job-hunting workspace.",
    problem:
      "Job seekers waste time jumping between platforms and struggle to track applications effectively.",
    who: "Early- and mid-career professionals actively searching for new opportunities.",
    impact:
      "Consolidates listings, filters, and application tracking for a more focused, organized job search.",
    liveUrl: "https://jobnavigator.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16v4H4zM4 10h12v4H4zM4 16h8v4H4z"/></svg>',
  },
  {
    title: "Trade Ventures",
    year: "2023",
    category: "E-commerce",
    tags: ["Vue", "Stripe", "PostgreSQL"],
    description:
      "A full-featured online store replacing basic catalogs with carts, payments, inventory control, and admin dashboards.",
    problem:
      "Product-based businesses lack robust storefronts with inventory management, payments, and admin tooling.",
    who: "Small and medium retailers looking to launch or upgrade their online sales channel.",
    impact:
      "Provides a complete buying experience and back-office tools, increasing sales while simplifying operations.",
    liveUrl: "https://tradeventures.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 6h15l-1.5 9h-12z"/><circle cx="9" cy="19" r="1.5"/><circle cx="18" cy="19" r="1.5"/></svg>',
  },
  {
    title: "Smart Calculator",
    year: "2023",
    category: "Web Apps",
    tags: ["JavaScript", "CSS", "HTML"],
    description:
      "A modern browser-based calculator with advanced functions and history tracking for fast, traceable calculations.",
    problem:
      "Users rely on basic tools that lack advanced functions or history, making it easy to repeat work or make errors.",
    who: "Students, analysts, and professionals doing frequent ad-hoc calculations.",
    impact:
      "Advanced functions and history tracking speed up calculations and reduce mistakes.",
    liveUrl: "https://caluculatingapp.netlify.app/",
    codeUrl: "https://github.com/Gandokijnr",
    icon: '<svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="4" y="3" width="16" height="18" rx="2"/><path d="M8 8h8M8 12h2m4 0h2M8 16h2m4 0h2"/></svg>',
  },
];
</script>
