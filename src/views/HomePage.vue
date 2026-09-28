<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

const profile = ref({
  name: 'Victor Cuellar',
  slogan: 'Full Stack Developer and Student',
  avatar:
    'https://api.dicebear.com/9.x/avataaars/svg?seed=Jack&accessories=sunglasses&accessoriesColor=25557c&accessoriesProbability=90&clothesColor=25557c&clothing=hoodie&clothingGraphic=pizza&eyebrows=defaultNatural&eyes=default&facialHair[]&facialHairColor[]&facialHairProbability=0&hairColor=4a312c&hatColor[]&mouth=twinkle&skinColor=edb98a&top=shortFlat&backgroundColor=c0aede',

  links: [
    {
      id: 1,
      title: 'GitHub',
      url: 'https://github.com/vcuell13',
      icon: 'code',
      description: 'Check out my projects',
    },
    {
      id: 2,
      title: 'LinkedIn',
      url: 'https://linkedin.com/in/vcuellar',
      icon: 'briefcase',
      description: 'Connect with me professionally',
    },
  ],
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <div class="mb-8 flex flex-col items-center text-center">
      <div
        class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-cyan-500 shadow-lg shadow-cyan-600/30 sm:h-32 sm:w-32"
      >
        <img
          :src="profile.avatar"
          :alt="profile.name"
          class="h-full w-full object-cover"
        />
      </div>

      <h1 class="mb-2 font-display text-2xl font-bold text-cyan-300 sm:text-3xl">
        {{ profile.name }}
      </h1>

      <p class="max-w-xs text-teal-200 sm:text-lg">
        {{ profile.slogan }}
      </p>
    </div>

    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <RouterLink
      to="/info"
      class="mt-8 text-sm text-teal-300 underline-offset-4 transition-colors duration-200 hover:text-cyan-300 hover:underline"
    >
      About me →
    </RouterLink>
  </main>
</template>

