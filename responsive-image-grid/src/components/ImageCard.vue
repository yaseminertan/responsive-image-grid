<template>
    <div class="card-container">
        <img :src="url"/>
    </div>
</template>
<script>
export default {
    props: {
        url: {
        type: String,
        },
    
    },
}
</script>