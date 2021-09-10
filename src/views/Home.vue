<template>
  <div class="home">
    <Header>My Memos</Header>
    <ul v-for="memo in newest" :key="memo.id">
      <li><router-link :to="{name: 'Edit', params: {id: memo.id}}">{{ memo.body }}</router-link></li>
    </ul>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";

export default {
  name: 'home',
  components: {
    Header
  },
  computed: {
    newest() {
      return this.$store.state.memos.slice().reverse();
    }
  }
}
</script>

<style>
    textarea {
        width: 100%;
        height: 10em;
    }
    button {
        border: 1px solid #333;
        background: #333;
        color: #fff;
        padding: 10px 20px;
        margin-top: 10px;
    }
</style>
