<template>
    <div class="user-info">
        <div class="info" v-for="(user, index) in users" :key="index">
            <div class="ellipse-background">
                <div class="ellipse"></div>
                <div class="parent-descri">
                    <div class="first-lastname">
                        <p>{{ user.firstname }}</p>
                        <p>{{ user.lastname }}</p>
                    </div>
                    <p>{{ user.email }}</p>
                </div>
            </div>
            <div class="role">
                <img v-if="showFrame" class="frame" src="../assets/Frame.png" alt="">
                <p>{{ user.role }}</p>
            </div>
            <div class="age">
                <img v-if="showFrame" class="frame" src="../assets/Frame(1).png" alt="">
                <p>{{ user.age }}</p>
            </div>
            <div class="skills">
                <img v-if="showFrame" class="frame" src="../assets/Frame(2).png" alt="">
                <p>{{ user.skills }}</p>
            </div>
            <button @click="handleClick">More</button>
        </div>
    </div>
</template>
<script>

export default {
    name: 'UserInfo',
    props: ['users'],
    data() {
        return {
            showFrame: false,
        }
    },
    mounted() {
        this.showFrame = true;
    },
    methods: {
        toggleFrame() {
            this.showFrame = !this.showFrame;
        },
        handleClick() {
            this.$emit("openDrawer")
        }
    }
}
</script>
<style>
.user-info {
    display: flex;
    flex-wrap: wrap;
    width: 600px;
}

.ellipse {
    width: 45px;
    height: 45px;
    border-radius: 50%;
    background: #D9D9D9;
}

.ellipse-background {
    display: flex;
    gap: 18px;
    height: 45px;
    align-items: center;
}

.parent-descri {
    display: flex;
    flex-direction: column;
    line-height: 0;
}

.first-lastname {
    display: flex;
}

.role {
    display: flex;
    margin-top: 15px;
    align-items: center;
}

.age {
    display: flex;
    align-items: center;
}

.frame {
    width: 24px;
    height: 24px;
    margin-right: 10px;
}

.info {
    position: relative;
    width: 300px;
    height: 200px;
}

.link {
    position: absolute;
    bottom: 0;
    right: 0;
}
</style>



