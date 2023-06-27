<script setup>
  import BasicLayout from "../Layouts/BasicLayout.vue";
  import { Link } from "@inertiajs/inertia-vue3";

  defineProps({
    articles: Object,
  });
</script>

<template>
  <BasicLayout>
    <section class="space-y-5 border-b-2 pb-10">
      <h2 class="text-2xl font-bold py-10">Read our latest articles</h2>
      <article v-for="article in articles" :key="article.id">
        <img src="/images/kinsta-logo.png" alt="Article thumbnail" />

        <div class="flex flex-col text-left justify-between pl-3 space-y-5">
          <h3 class="text-xl font-semibold text-red-500 hover:text-indigo-800">
            <Link :href="route('article.show', article.id)" preserve-scroll>
              {{ article.title }}
            </Link>
          </h3>
        <p>{{ article.excerpt }}</p>
        </div>
      </article>
    </section>
  </BasicLayout>
</template>