<template>
<div class="container-fluid">
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="logo">
        <a class="navbar-brand font-bold" href="#"><b>Tita Bouquet</b></a>
      </div>
      <div class="navigasi">
        <a href="#produk">Produk Kami</a>
        <a href="#kategori">Kategori</a>
      </div>
    </nav>
</div>
</template>

<style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0; 
    width: 100%;
    background-color: #ffffff; 
    z-index: 1000;
  }

  .navigasi > a {
    color: #000000;
    text-decoration: none;
    margin-right: 40px;
  }
</style>
