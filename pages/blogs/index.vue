<template>
	
  <div>
  <v-container class="" fluid>
    <v-row>
      <v-col v-for="n in query.length" :key="n" cols="12" md="4" class="mb-8">
        <v-card
            elevation="10"
            class="rounded-xl fill-height hover mx-2"
            @click="routeTo(`/${query[n - 1].slug}`)"
          >
          </v-card>
      </v-col>
    </v-row>
  </v-container>
</div>

</template>

<script setup>
const { path } = useRoute();
const router = useRouter();

const { data: query } = await useAsyncData("pages", () =>
queryContent("/")
  
  .find()
);
useHead({
title: 'ICJIA',
meta: [
  { name: 'description', content: 'Explore my latest blog posts!' },
  
],
});

</script>

<style lang="scss" scoped>

</style>