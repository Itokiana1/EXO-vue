<template>
  <div class="flex">
    <AddFormulaire @submit="handleInputData"/>
    <UserInfo :users="users" @openDrawer="handleOpen" />
    <DrawerCard v-if="isVisible"/>
  </div>
</template>

<script>
import UserInfo from "./components/UserInfo.vue";
import AddFormulaire from "./components/AddFormulaire.vue"
import DrawerCard from "./components/DrawerCard.vue";


export default {
  name: 'App',
  components: {
    UserInfo, AddFormulaire, DrawerCard,
  },
  data() {
    return {
      formData: {
        firstname: "",
        lastname: '',
        age: '',
        role: '',
        email: '',
        skills: '',
        experience: '',
        descri: '',
        date: '',
      },
      users: [],
      isVisible: false,
    }
  },
  methods: {
    handleInputData(formData) {
      // this.formData = formData;
      this.users.push(formData)
    },
    hideForm() {
      this.formData = !this.formData
    },
    handleOpen() {
      this.isVisible = !this.isVisible
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
