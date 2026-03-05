<template>
  <section
    class="relative min-h-[calc(70svh-5rem)] md:min-h-screen flex items-center justify-center overflow-hidden py-10 md:py-0"
  >
    <div
      class="absolute inset-0 bg-cover bg-top opacity-50"
      style="background-image: url(&quot;/hero-bg.png&quot;)"
    />
    <div
      class="absolute inset-0 bg-gradient-to-b from-background/50 via-background/80 to-background"
    />

    <div class="relative z-10 container mx-auto px-4 sm:px-6 text-center">
      <p
        class="text-primary font-medium tracking-widest uppercase text-xs sm:text-sm mb-3 sm:mb-4"
      >
        Full Stack Developer & Digital Marketing Expert
      </p>

      <h1
        class="text-4xl sm:text-5xl md:text-7xl lg:text-8xl font-display font-bold leading-tight mb-5 sm:mb-6"
      >
        Crafting Digital
        <br />
        <span class="text-gradient">Experiences</span>
      </h1>

      <p
        class="text-muted-foreground text-base sm:text-lg md:text-xl max-w-2xl mx-auto mb-8 sm:mb-10"
      >
        Founder & Lead Strategist at Strativa Web Services| Building
        Revenue-Driven Digital Systems | Web, Software & Growth Marketing
      </p>

      <div class="flex flex-col sm:flex-row gap-3 sm:gap-4 justify-center">
        <a
          href="#projects"
          class="inline-flex items-center justify-center gap-2 px-7 sm:px-8 py-3 rounded-lg bg-primary text-primary-foreground font-semibold hover:opacity-90 transition-opacity glow-gold"
        >
          View Work
        </a>
        <a
          href="#contact"
          class="inline-flex items-center justify-center gap-2 px-7 sm:px-8 py-3 rounded-lg border border-border text-foreground hover:border-primary transition-colors"
        >
          Get in Touch
        </a>
      </div>

      <div class="absolute bottom-6 sm:bottom-10 left-1/2 -translate-x-1/2">
        <a
          href="#about"
          class="text-muted-foreground hover:text-primary transition-colors animate-bounce block"
        >
          <ArrowDown :size="24" />
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ArrowDown } from "lucide-vue-next";
</script>
