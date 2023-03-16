<template>
    <div class="user-info">
        <div class="info">
            <div class="ellipse-background">
                <div class="ellipse"></div>
                <div class="parent-descri">
                    <div class="first-lastname">
                        <p>{{ formData.firstname }}</p>
                        <p>{{ formData.lastname }}</p>
                    </div>
                    <p>{{ formData.email }}</p>
                </div>
            </div>
            <div class="role">
                <img class="frame" src="../assets/Frame.png" alt="">
                <p>{{ formData.role }}</p>
            </div>
            <div class="age">
                <img class="frame" src="../assets/Frame(1).png" alt="">
                <p>{{ formData.age }}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'UserInfo',
    props: ['formData'],
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
</style>



