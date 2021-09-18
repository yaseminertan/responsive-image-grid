<template>
    <div class="card-container">
        <a :href="imageUrl" class="image-container">
            <img v-lazy="url"/>
        </a>

        <div class="user-name">
            <a :href="userProfileLink"><span class="text-photo-by">photo by: </span>{{userName}}</a>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'ImageCard',
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
