<template>
    <div class="container-fluid">
         <navbar/> <!-- custom component -->
         <slot />  <!-- page akan mengisi pada bagian ini -->
    </div>
</template>
<style>
.container-fluid{
    background-color:#EBC6C6 ;
}
</style>