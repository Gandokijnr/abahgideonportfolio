<template>
  <div>
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ProjectsSection />
    <ContactSection />
  </div>
</template>

<script setup>
useHead({
  title: "Abah Gideon",
  link: [{ rel: "icon", type: "image/svg+xml", href: "/favicon.svg" }],
  meta: [
    {
      name: "description",
      content: "Full Stack Developer & Digital Marketing Expert",
    },
  ],
});
</script>
