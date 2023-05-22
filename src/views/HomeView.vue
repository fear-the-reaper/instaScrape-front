<script setup>
  import { ref } from 'vue';
  import { RouterLink } from "vue-router"
  import card from '../components/card.vue';
  import loading from "../components/loader.vue"
  const results = ref(null);

  const is_loading = ref(false);

  const scrape_url = ref("")
  const onSubmit = async (event) => {
    is_loading.value = true;
    console.log(`The URL is ${scrape_url.value}`);
    const URL = "http://localhost:8000/scrape"
    const data_to_send = {
      "url": scrape_url.value
    }
    const res = await fetch(URL, {
      method: 'POST',
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(data_to_send),
    });

    const data = await res.json();

    console.log(data);

    if (data) {
      results.value = data;
      is_loading.value = false;
    }


  }
</script>

<template>
  <main class="p-6">
    <div class="has-text-centered is-size-2">
      InstaScraper
    </div>
    <form @submit.prevent="onSubmit($event)">
      <div class="m-4 columns is-centered">
        <div class="column is-one-third">
          <div class="field is-grouped">
            <p class="control is-expanded">
              <input v-model="scrape_url" class="input" type="text" placeholder="Enter the post url">
            </p>
            <p class="control">
              <a class="button is-info">
                Scrape
              </a>
            </p>
          </div>
        </div>
      </div>
    </form>
    <div v-if="results && !is_loading" class="is-flex is-flex-wrap-wrap is-justify-content-center">
      <RouterLink id="handler" v-for="(comment, index) in results.comments" :to="{ name: 'details', params: {id: index+1, comment: JSON.stringify(comment)}}">
        <card :comment-number=index+1 :comment="comment.comment" :username="comment.username"></card>
      </RouterLink>
    </div>
    <div v-else-if="!results && !is_loading" class="has-text-centered has-text-weight-bold">
      Nothing to scrape...
    </div>
    <div v-if="is_loading">
      <loading></loading>
    </div>
  </main>
</template>


<style scoped>
  #handler {
    display: contents;
  }
</style>