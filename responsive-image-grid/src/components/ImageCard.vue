<template>
    <div class="card-container">
        <a :href="imageUrl" class="image-container">
            <img :src="url"/>
        </a>

        <div class="user-name">
            <a :href="userProfileLink">{{userName}}</a>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'Images',
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
    .card-container {
        position: relative;
        margin:10px;
        &:hover {
            .user-name {
                height: 50px;
                a { font-size: 26px; }
            }
        }
        .image-container{
            img{
                object-fit: cover;
                width: 100%;
                height: auto;
            }
        }
        .user-name {
            position: absolute;
            bottom:0;
            width: 100%;
            height: 0;
            background: rgba(128, 128, 128, 0.6);
            transition:all ease-in-out .2s;
            display: flex;
            align-items: center;
            justify-content: center;
            a {
                font-family: lato;
                font-weight: bold;
                font-size: 0;
                color: #fff;
                text-decoration: none;
                cursor: pointer;
                transition:all ease-in-out .2s;
            }
        }
    }
</style>