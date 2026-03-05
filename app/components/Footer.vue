<template>
  <footer class="py-10 border-t border-border">
    <div
      class="container mx-auto px-4 sm:px-6 flex flex-col md:flex-row items-center justify-between gap-4"
    >
      <p class="text-sm text-muted-foreground">
        © 2026 Dev. All rights reserved.
      </p>
      <div class="flex gap-5">
        <a
          v-for="(icon, i) in socialIcons"
          :key="i"
          href="#"
          class="text-muted-foreground hover:text-primary transition-colors p-2"
        >
          <component :is="icon" :size="18" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { Github, Linkedin, Twitter } from "lucide-vue-next";

const socialIcons = [Github, Linkedin, Twitter];
</script>
