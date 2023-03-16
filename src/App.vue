<template>
  <div class="flex">
    <AddFormulaire @submit="handleInputData" />
    <UserInfo v-if="!isShow" :formData="formData" />
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
      formData: {
        firstname: localStorage.getItem("firstname") || "",
        lastname: '',
        age: '',
        role: '',
        email: '',
        experience: '',
        descri: '',
        date: '',
      },
      isShow: false,
    }
  },
  watch: {
    firstname(newValue) {
      localStorage.setItem("firstname", newValue);
    }},
    methods: {
      handleInputData(formData) {
        this.formData = formData;
      },
      hideForm() {
        this.formData = !this.formData
      }
    }
  }
</script>

<style scoped>
.flex {
  display: flex;
  gap: 50px;
}
</style>
