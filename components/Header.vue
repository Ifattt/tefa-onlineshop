<template>
<div class="container-fluid p-0">
    <nav class="navbar bg-white navbar-expand-lg bg-body-tertiary">
        <a class="navbar-brand font-bold" href="#"><b>Tita Bouquet</b></a>
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
    position:fixed;
    top: 0; 
    width: 100%; 
    z-index: 1000;
  }

  .navigasi > a {
    color: #000000;
    text-decoration: none;
    margin-right: 40px;
  }
</style>
