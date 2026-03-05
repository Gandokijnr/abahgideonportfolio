<template>
  <nav class="fixed top-0 left-0 right-0 z-50 glass">
    <div
      class="container mx-auto flex items-center justify-between py-3 sm:py-4 px-4 sm:px-6"
    >
      <a href="#" class="text-xl font-display font-bold text-gradient">
        Dev.
      </a>
      <div class="hidden md:flex gap-8">
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          class="text-sm font-medium text-muted-foreground hover:text-primary transition-colors"
        >
          {{ link.label }}
        </a>
      </div>
      <button
        @click="toggleMenu"
        class="md:hidden text-foreground"
        :aria-expanded="isOpen"
        aria-label="Toggle menu"
      >
        <Menu v-if="!isOpen" :size="24" />
        <X v-else :size="24" />
      </button>
    </div>
    <div v-if="isOpen" class="md:hidden glass border-t border-border">
      <a
        v-for="link in links"
        :key="link.href"
        :href="link.href"
        @click="closeMenu"
        class="block px-4 sm:px-6 py-3 text-sm text-muted-foreground hover:text-primary transition-colors"
      >
        {{ link.label }}
      </a>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";
import { Menu, X } from "lucide-vue-next";

const links = [
  { label: "About", href: "#about" },
  { label: "Skills", href: "#skills" },
  { label: "Projects", href: "#projects" },
  { label: "Contact", href: "#contact" },
];

const isOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

const closeMenu = () => {
  isOpen.value = false;
};
</script>
