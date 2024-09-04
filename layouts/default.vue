<template>
    <div class="container-fluid">
         <Header v-if="!isHomePage" /> <!-- custom component -->
         <slot />  <!-- page akan mengisi pada bagian ini -->
    </div>
</template>
<style>
.container-fluid{
    background-color:#FFFF ;
}
</style>

<script>
export default {
    computed: {
        isHomePage() {
            return this.$route.name === "detail";
        }
    }
}
</script>