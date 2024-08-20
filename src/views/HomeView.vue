
<template>
  <Skip />
  <HeaderView />
    <main id="main" role="main">
        <Intro />
        <Skill />
        <Site />
        <Contact />
    </main>
  <FooterView />
</template>

<script setup>
import Contact from '@/components/Contact.vue';
import HeaderView from '@/components/HeaderView.vue';
import FooterView from '@/components/FooterView.vue';
import Skip from '@/components/Skip.vue';
import Intro from '@/components/Intro.vue';
import Skill from '@/components/Skill.vue';
import Site from '@/components/Site.vue';
</script>
