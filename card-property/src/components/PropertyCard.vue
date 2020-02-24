<template>
  <div class="bg-white border rounded-lg overflow-hidden">
    <img :src="property.imageUrl" :alt="property.imageAlt" />
    <div class="p-6">
      <div class="flex items-baseline">
        <span class="inline-block bg-teal-200 text-teal-800 text-xs px-2 rounded-full uppercase font-semibold tracking-wide">New</span>
        <div
          class="text-gray-600 text-xs uppercase font-semibold tracking-wide ml-2"
        >{{ property.beds }} beds &bull; {{ property.baths }} baths</div>
      </div>

      <h4 class="mt-1 font-semibold text-lg leading-tight truncate">{{ property.title }}</h4>
      <div class="mt-1">
        {{ property.formattedPrice }}
        <span class="text-gray-600 text-sm">/ wk</span>
      </div>
      <div class="mt-2 flex items-center">
        <svg
          v-for="i in 5"
          :key="i"
          :class="i <= property.rating ? 'text-teal-500' : 'text-gray-400'"
          class="h-4 w-4 mr-1 fill-current"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 49.94 49.94"
        >
          <path
            d="M48.856 22.73a3.56 3.56 0 00.906-3.671 3.56 3.56 0 00-2.892-2.438l-12.092-1.757a1.58 1.58 0 01-1.19-.865L28.182 3.043a3.56 3.56 0 00-3.212-1.996 3.56 3.56 0 00-3.211 1.996L16.352 14c-.23.467-.676.79-1.191.865L3.069 16.622A3.56 3.56 0 00.177 19.06a3.56 3.56 0 00.906 3.671l8.749 8.528c.373.364.544.888.456 1.4L8.224 44.701a3.506 3.506 0 00.781 2.904c1.066 1.267 2.927 1.653 4.415.871l10.814-5.686a1.619 1.619 0 011.472 0l10.815 5.686a3.544 3.544 0 001.666.417c1.057 0 2.059-.47 2.748-1.288a3.505 3.505 0 00.781-2.904l-2.065-12.042a1.582 1.582 0 01.456-1.4l8.749-8.529z"
          />
        </svg>
        <span class="ml-2 text-gray-600 text-sm">{{ property.reviewCount }} reviews</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["property"]
};
</script>
