<template>
    <div class="left-box" id='account-info'>
        <div>
            <h2>User Info</h2>
        </div>
        <section class="form" action="">
            <input type="text" placeholder="Firstname" v-model="form.firstname">
            <input type="text" placeholder="Lastname" v-model="form.lastname">
            <input type="text" placeholder="E-mail">
            <input type="text" placeholder="Age">
            <input type="text" placeholder="Role">
            <div>
                <input v-model="task" type="text" placeholder="Skills">
                <button @click="submitTask" class="plus">+</button>
            </div>
            <div class="skills" v-for="(task, index) in tasks" :key="index">
                <p class="vue-descri">{{ task.name }}</p>
                <img class="svg" src="../assets/trash-filled.svg" alt="" @click="deleteTask(index)">
            </div>
            <input type="text" placeholder="Experience Title">
            <input class="title-descri" type="text" placeholder="Title Description">
            <input type="text" placeholder="Experience Date">
            <div class="add">
                <button class="plus">+</button>
            </div>
        </section>
        <div>
            <button class="btn-submit">Add User Info</button>
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
            form: {
                firstname: '',
                lastname: '',
                email: '',
                role: '',
                age: '',
                skills: ''
            },
            task:'',
            tasks: [{ 
                name: "",
            },
            {
                name: "",
            }
        ]
        }
    },
    methods: {
        async submit() {
            this.$emit('submit', this.form)
        },
        submitTask() {
            this.tasks.push(this.task)

            this.task ="";
        },
        deleteTask(index){
            this.tasks.splice(index, 1);
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
}

.vue-descri {
    width: 85%;
}
</style>