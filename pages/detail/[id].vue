<template>
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-1">
          <a href="/" class="btn btn-grey mt-3"><-</a>
        </div>
        <div class="col-sm-10">
          <h2 class="text-center mb-5 mt-5 fw-bold">DETAIL PESANAN</h2>
      </div>
      <hr>
      <div class="col-md-3">
        <img :src="detail.cover" class="cover" alt="cover" style="height: 400px;">
      </div>
    
        <ul class="list-group list-grup-flush">
          <li class="list-group-item"> {{ detail.judul }}</li>
          <li class="list-group-item"> Deskripsi : </li>
          <li class="list-group-item"> {{ detail.deskripsi }}</li>
          <li class="list-group-item"> {{ detail.deskripsi2 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi3 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi4 }}</li>
        </ul>
      

        <!-- <div class="flex-container">
          <div class="col-lg-2">
            <span v-if="loading">Sedang memuat gambar...</span>
            <span v-else><img :src="detail.cover" alt="cover" class="cover" /></span>
          </div>
          <div v-if="loading">Sedang memuat data...</div>
          <div v-else>
            <h1>{{ detail.deskripsi }}</h1>
            <button type="button" class="btn btn-secondary" disabled>order </button>
          </div>
        </div> -->
      </div>
    </div>
    <div class="footer">
              <p>Copyright © 2024 i, Inc. All rights reserved.</p>
          </div>
  </template>


<script setup>
definePageMeta({
  layout: 'homepage'
})

const supabase = useSupabaseClient()

const route = useRoute()
const detail = ref([])

const getDetailById = async () => {
    const { data, error } = await supabase.from('detail').select(`*`)
    .eq('id', route.params.id)
    if(data) detail.value = data[0]
}
onMounted(() => {
    getDetailById()
})
definePageMeta ({
    layout: 'homepage'
})
</script>

<style scoped>
.cover {
    height: 430px;
    width: 340px;
}
.card.mb-8 {
    margin-top: 50px;
    height: 340px;
    width: 235px;
}
ul {
  width: 50%;
}
.footer {
    text-align: center;
    background-color:#D9D9D9;
    height: 4em;
}
</style>
