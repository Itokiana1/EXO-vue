<template>
    <div class="left-box" id='account-info'>
        <div>
            <h2>User Info</h2>
        </div>
        <section class="form" action="">
            <input type="text" placeholder="Firstname" v-model="formData.firstname">
            <input type="text" placeholder="Lastname" v-model="formData.lastname">
            <input type="text" placeholder="E-mail" v-model="formData.email">
            <input type="text" placeholder="Age" v-model="formData.age">
            <input type="text" placeholder="Role" v-model="formData.role">
            <div>
                <input v-model="task" type="text" placeholder="Skills">
                <button @click="submitTask" class="plus">+</button>
            </div>
            <div class="skills" v-for="(task, index) in tasks" :key="index">
                <p class="vue-descri">{{ task }}</p>
                <img class="svg" src="../assets/Frame.svg" alt="" @click="deleteTask(index)">
            </div>
            <input type="text" placeholder="Experience Title" v-model="formData.experience">
            <input class="title-descri" type="text" placeholder="Title Description" v-model="formData.descri">
            <input type="text" placeholder="Experience Date" v-model="formData.date">
            <div class="add">
                <button class="plus">+</button>
            </div>
        </section>
        <div>
            <button class="btn-submit" @click.prevent="handleSubmit">Add User Info</button>
        </div>
    </div>
</template>
<script>

export default {
    name: 'AddFormulaire',
    components: {

    },
    data() {
        return {
            formData: {
                firstname: localStorage.getItem("firstname") || "",
                lastname: '',
                email: '',
                role: '',
                age: '',
                skills: '',
                experience: '',
                descri: '',
                date: '',
            },
            task: '',
            tasks: [],

        }
    },
    watch: {
        firstname(newValue) {
            localStorage.setItem("firstname", newValue);
        },
    },
    methods: {
        submitTask() {
            this.tasks.push(this.task)
        },
        deleteTask(index) {
            this.tasks.splice(index, 1);
        },
        handleSubmit() {
            this.$emit('submit', this.formData);
            //  console.log("submited");
        }
    }
}
</script>
<style scoped>
.left-box {
    padding-left: 15px;
}

.form {
    display: flex;
    flex-direction: column;
    position: relative;
    gap: 15px;
}

input {
    height: 45px;
    padding-left: 10px;
    position: relative;
    font-size: 14px;
    color: #000000;
}

.plus {
    position: absolute;
    width: 50px;
    height: 50px;
    right: 0;
    background: #2444B5;
    color: white;
}

.add {
    height: 45px;
}

.btn-submit {
    background: #2444B5;
    position: relative;
    width: 183px;
    height: 45px;
    color: white;
    font-weight: 400;
    margin: 25px;
}

.title-descri {
    height: 105px;
}

.skills {
    display: flex;
    align-items: center;
    gap: 10px;
}

.vue-descri {
    width: 73%;
    background: #DDE3EB;
    padding: 5px;
    margin-left: 10px;
}
</style>