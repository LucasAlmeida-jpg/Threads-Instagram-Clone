<template>
  <MainLayout>
    <div id="IndexPage" class="w-full overflow-auto">
      <div class="mx-auto max-w-[500px] overflow-hidden">
      <div id="Posts" class="px-4 max-w-[600px] mx-auto">
        <div class="text-white" v-if="isPosts" v-for="post in posts" :key="post">
          {{ post }}
        </div>
      </div>
      </div>
    </div>
  </MainLayout>
</template>

<script setup>
import MainLayout from '../layouts/MainLayout.vue';
import {useUserStore} from '../stores/user';
const userStore = useUserStore();

let posts = ref([]); 
let isPosts = ref(true);
let isLoading = ref(true);

onBeforeMount(() => {
  posts.value =  [
    {
      name: 'Lucas',
      image: 'https://placehold.co/100',
      text: 'Este é o título do Lucas', 
      picture: 'https://placehod.co/500'
    }
  ]
})
</script>


