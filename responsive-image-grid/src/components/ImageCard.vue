<template>
    <div class="card-container">
        <div>
            <a :href="imageUrl">
                <img :src="url"/>
            </a>
        </div>
        <div class="user-name">
            <a :href="userProfileLink">{{userName}}</a>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        url: {
            type: String,
        },
        imageUrl: {
            type: String,
        },
        userProfileLink:{
            type: String,
        },
        userName:{
            type: String,
        },
    },
}
</script>
<style lang="scss" scoped>
.card-container{
    position: relative;
    width: max-content;
    margin:10px auto;
    .user-name{
        position: absolute;
        bottom:0;
        width: 100%;
        height: 80px;
        background: rgba(128, 128, 128, 0.6);
        display: flex;
        align-items: center;
        justify-content: center;
        a{
            font-family: lato;
            font-weight: bold;
            font-size: 40px;
            color: #000;
            text-decoration: none;
            cursor: pointer;
            transition:all ease-in-out .2s;
            &:hover{font-size: 44px;}
        }
    }
}
</style>