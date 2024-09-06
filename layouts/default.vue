<template>
    <div class="container-fluid">
         <Header /> <!-- custom component -->
         <slot />  <!-- page akan mengisi pada bagian ini -->
    </div>
</template>
<style>
.container-fluid{
    background-color:#FFFF ;
}
</style>
