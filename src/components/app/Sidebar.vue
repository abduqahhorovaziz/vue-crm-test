<template>
  <ul class="sidenav app-sidenav" :class="{ open: modelValue }">
    <router-link
      v-for="link in links"
      :key="link.url"
      :to="link.url"
      v-slot="{ href, navigate, isActive }"
      :exact="link.exact"
    >
      <li :class="{ active: isActive }">
        <a :href="href" @click="navigate" class="waves-effect">
          {{ link.title }}
        </a>
      </li>
    </router-link>
  </ul>
</template>

<script>
export default {
  props: ["modelValue"],
  data: () => ({
    links: [
      { title: "Счет", url: "/", exact: true },
      { title: "История", url: "/history" },
      { title: "Планирование", url: "/planning" },
      { title: "Новая запись", url: "/record" },
      { title: "Категории", url: "/categories" },
    ],
  }),
};
</script>
