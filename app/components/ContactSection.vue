<template>
  <section id="contact" class="py-8 sm:py-10 md:py-18 bg-card/30">
    <div class="container mx-auto px-4 sm:px-6">
      <div class="text-center mb-10 sm:mb-14 md:mb-16">
        <p
          class="text-primary font-medium tracking-widest uppercase text-sm mb-3"
        >
          Contact
        </p>
        <h2 class="text-3xl sm:text-4xl md:text-5xl font-display font-bold">
          Let's <span class="text-gradient">Connect</span>
        </h2>

        <div class="mt-6">
          <a
            :href="whatsAppUrl"
            target="_blank"
            rel="noopener noreferrer"
            class="w-full sm:w-auto inline-flex items-center justify-center gap-2 px-8 py-3 rounded-xl bg-primary text-primary-foreground font-semibold hover:opacity-90 transition-opacity glow-gold"
          >
            <MessageCircle :size="18" />
            Chat on WhatsApp
          </a>
        </div>
      </div>

      <div class="max-w-2xl mx-auto">
        <div
          class="flex flex-col sm:flex-row flex-wrap gap-4 sm:gap-6 justify-center mb-10 sm:mb-12"
        >
          <div class="flex items-center gap-3 text-muted-foreground">
            <Mail :size="18" class="text-primary" />
            <span class="text-sm">abahgideon111@gmail.com</span>
          </div>
          <div class="flex items-center gap-3 text-muted-foreground">
            <MapPin :size="18" class="text-primary" />
            <span class="text-sm">Available Worldwide</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Mail, MapPin, MessageCircle } from "lucide-vue-next";

const whatsAppPhone = "2347019727419";

const buildWhatsAppUrl = (text) => {
  const encodedText = encodeURIComponent(text);
  return `https://wa.me/${whatsAppPhone}?text=${encodedText}`;
};

const whatsAppUrl = buildWhatsAppUrl(
  "Hi Gideon, I found your portfolio and I'd like to connect about a project.",
);
</script>
