<template>
  <section id="about" class="py-8 sm:py-10 md:py-18">
    <div class="container mx-auto px-4 sm:px-6">
      <div class="grid md:grid-cols-2 gap-10 md:gap-16 items-center">
        <div>
          <p
            class="text-primary font-medium tracking-widest uppercase text-sm mb-3"
          >
            About Me
          </p>
          <h2
            class="text-3xl sm:text-4xl md:text-5xl font-display font-bold mb-5 sm:mb-6"
          >
            Building the web,
            <br />
            <span class="text-gradient">growing brands.</span>
          </h2>
          <p
            class="text-muted-foreground leading-relaxed text-base sm:text-[1.05rem] mb-4"
          >
            I build digital systems that help businesses scale, automate, and
            generate measurable revenue.
          </p>
          <p
            class="text-muted-foreground leading-relaxed text-base sm:text-[1.05rem]"
          >
            As the Founder of Strativa Web Services, I partner with startups,
            growing brands, and entrepreneurs to design high-performing
            websites, scalable software solutions, and growth-driven marketing
            systems focused on real business impact.
          </p>
          <p
            class="text-muted-foreground leading-relaxed text-base sm:text-[1.05rem] mt-4"
          >
            With a background in frontend engineering and product-focused
            development, I build clean, conversion-optimized experiences using
            Vue.js, Nuxt, WordPress, and backend tools like Supabase. I also
            create custom dashboards, internal tools, and workflows that help
            teams operate smarter and make data-driven decisions.
          </p>
          <ul
            class="mt-6 space-y-2 text-muted-foreground text-base sm:text-[1.05rem]"
          >
            <li>Web Development (Vue.js, Nuxt, WordPress)</li>
            <li>Custom Software &amp; Admin Dashboards</li>
            <li>SEO &amp; Conversion Optimization</li>
            <li>Digital Growth &amp; Automation Systems</li>
            <li>Performance &amp; Scalability Optimization</li>
          </ul>
          <p
            class="text-muted-foreground leading-relaxed text-base sm:text-[1.05rem] mt-6"
          >
            If you're building something bold and need a technical partner who
            understands product and growth, let's connect.
          </p>
        </div>

        <div class="grid gap-4 sm:gap-6">
          <div
            v-for="(highlight, i) in highlights"
            :key="highlight.label"
            class="glass rounded-xl p-5 sm:p-6 flex items-center gap-4 sm:gap-5 hover:border-primary/50 transition-colors"
          >
            <div
              class="w-11 h-11 sm:w-12 sm:h-12 rounded-lg bg-primary/10 flex items-center justify-center shrink-0"
            >
              <component :is="highlight.icon" class="text-primary" :size="22" />
            </div>
            <div>
              <h3 class="font-display font-semibold text-base sm:text-lg">
                {{ highlight.label }}
              </h3>
              <p class="text-muted-foreground text-sm">{{ highlight.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Code2, TrendingUp, Zap } from "lucide-vue-next";

const highlights = [
  { icon: Code2, label: "5+ Years Dev", desc: "Full-stack expertise" },
  { icon: TrendingUp, label: "Growth Focused", desc: "Data-driven marketing" },
  { icon: Zap, label: "Fast Delivery", desc: "Agile development" },
];
</script>
