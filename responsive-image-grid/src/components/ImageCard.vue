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
