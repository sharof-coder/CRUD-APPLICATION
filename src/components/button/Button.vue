<template>
    <button type="submit" class="btn btn-outline-danger" @submit.prevent><slot></slot></button>
</template>
<script>
export default {
    
}
</script>
<style>
    button{
        padding: .5rem 2rem;
    }
</style>