<template>
  <div class="flex">
    <AddFormulaire />
    <UserInfo />
  </div>
</template>

<script>
import UserInfo from "./components/UserInfo.vue";
import AddFormulaire from "./components/AddFormulaire.vue"

export default {
  name: 'App',
  components: {
    UserInfo, AddFormulaire
  },
  data() {
    return {

    }
  },
  methods: {

  }
}
</script>

<style scoped>
.flex {
  display: flex;
  gap: 50px;
}
</style>
