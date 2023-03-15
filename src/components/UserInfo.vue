<template>
    <div class="user-info">
        <div class="info">
            <div class="ellipse-background">
                <div class="ellipse"></div>
                <div class="parent-descri">
                    <div class="first-lastname">
                        <p>Firstname</p>
                        <p>Lastname</p>
                    </div>
                    <p>hfhfhf@gmail.com</p>
                </div>
            </div>
            <div class="role">
                <img src="" alt="">
                <p>admin</p>
            </div>
            <div class="age">
                <img src="" alt="">
                <p>24</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'UserInfo',
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
}

.age {
    display: flex;
}
</style>