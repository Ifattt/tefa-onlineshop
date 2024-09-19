<template>
    <!-- <div class="container-fluid"> -->
         <Header /> <!-- custom component -->
         <slot />  <!-- page akan mengisi pada bagian ini -->
         <Footer />
<!-- </div> -->
</template>
<style>
.container-fluid{
    background-color:#FFFF ;
    width: 100vw;
}

a {
    color: #313131;
    text-decoration: none;
    font-weight: bold;
}
a:hover {
    color: inherit;
}
</style>
