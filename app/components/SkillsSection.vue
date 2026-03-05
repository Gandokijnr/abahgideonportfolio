<template>
  <section id="skills" class="py-8 sm:py-10 md:py-18 bg-card/30">
    <div class="container mx-auto px-4 sm:px-6">
      <div class="text-center mb-10 sm:mb-14 md:mb-16">
        <p
          class="text-primary font-medium tracking-widest uppercase text-sm mb-3"
        >
          Expertise
        </p>
        <h2 class="text-3xl sm:text-4xl md:text-5xl font-display font-bold">
          Skills & <span class="text-gradient">Technologies</span>
        </h2>
      </div>

      <div class="grid md:grid-cols-2 gap-10 md:gap-12 max-w-4xl mx-auto">
        <div>
          <h3
            class="font-display font-semibold text-lg sm:text-xl mb-5 sm:mb-6 flex items-center gap-2"
          >
            <span class="w-2 h-2 rounded-full bg-primary" />
            Development
          </h3>
          <div class="flex flex-wrap gap-2 sm:gap-3">
            <span
              v-for="(skill, i) in devSkills"
              :key="skill"
              class="px-3 sm:px-4 py-2 rounded-lg glass text-xs sm:text-sm font-medium hover:border-primary/50 transition-colors cursor-default"
            >
              {{ skill }}
            </span>
          </div>
        </div>

        <div>
          <h3
            class="font-display font-semibold text-lg sm:text-xl mb-5 sm:mb-6 flex items-center gap-2"
          >
            <span class="w-2 h-2 rounded-full bg-primary" />
            Digital Marketing
          </h3>
          <div class="flex flex-wrap gap-2 sm:gap-3">
            <span
              v-for="(skill, i) in marketingSkills"
              :key="skill"
              class="px-3 sm:px-4 py-2 rounded-lg glass text-xs sm:text-sm font-medium hover:border-primary/50 transition-colors cursor-default"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const devSkills = [
  "Vue.js",
  "Nuxt.js",
  "JavaScript",
  "HTML",
  "CSS",
  "React",
  "TypeScript",
  "Python",
  "PostgreSQL",
  "Next.js",
  "Tailwind CSS",
];

const marketingSkills = [
  "SEO / SEM",
  "Google Ads",
  "Meta Ads",
  "Content Strategy",
  "Email Marketing",
  "Analytics",
  "CRO",
  "Social Media",
  "Copywriting",
  "A/B Testing",
];
</script>
