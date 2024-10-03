<template>
  <div>
    <div class="row">
      <div class="col-lg-1">
        <a href="/" class="btn btn-grey mt-3">
          <button style="background-color: transparent; border: none; ">
            <img src="~/assets/img/kembali.png" alt="kembali" style="width: 30px; height: 30px; margin-top: 10px;">
          </button></a>
      </div>
    </div>
    <div class="row">
      <div class="col-sm-12 justify-content-center">
        <h2 class="text-center mb-5 mt-5 fw-bold">DETAIL PESANAN</h2>
      </div>
    </div>
    <hr>
    <div class="row">
      <div class="col-sm-3">
        <img :src="detail.cover" class="cover img-fluid" alt="cover">
      </div>
      <div class="col">
        <ul class="row">
          <li class="list-group-item"> {{ detail.judul }}</li>
          <li class="list-group-item"> Deskripsi : </li>
          <li class="list-group-item deskripsi"> {{ detail.deskripsi }}</li>
          <!-- <li class="list-group-item"> {{ detail.deskripsi2 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi3 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi4 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi5 }}</li> -->
        </ul>
        <NuxtLink class="btn bg-abu btn-lg rounded-5"
          :to="`https://wa.me/6285724948649?text=Halo saya ingin pesan bouquet: ${detail.judul}. https://onlinebouket.com/detail/${detail.id}`" target="_blank">
          <!-- <button style="background-color: transparent; border: none; "> -->
          <img src="~/assets/img/whatsapp.png" alt="whatsapp" style="width: 30px; height: 30px;">
          Order Disini
          <!-- </button> -->
        </NuxtLink>
      </div>
    </div>
  </div>
  <!-- <div class="d-grid gap-2 d-md-flex justify-content-md-end"> -->
  <div>
    <div>

    </div>
  </div>


</template>


<script setup>
definePageMeta({
  layout: 'homepage'
})

useHead({
  title: `Detail Bouquet`,
  meta: [
    {
      name: 'description',
      content: `jual bouket: ....`
    },
    {
      property: 'og:image',
      content: '.....'
    }
  ]
})

const supabase = useSupabaseClient()

const route = useRoute()
const detail = ref([])

const getDetailById = async () => {
  const { data, error } = await supabase.from('detail').select(`*`)
    .eq('id', route.params.id)
  if (data) detail.value = data[0]
}
onMounted(() => {
  getDetailById()
})
definePageMeta({
  layout: 'homepage'
})
</script>

<style scoped>
.deskripsi {
  white-space: pre-line;
  margin: 20px 10px;
  height: auto; 
  border-radius: 1rem;
}
.cover {
  width: 100%; 
  max-width: 340px;
  border-radius: 1rem;
  margin: 20px 0; 
}

.card.mb-8 {
  margin-top: 50px;
  height: auto; 
  width: 100%; 
}

ul {
  width: 100%;
}

.list-group-item {
  font-size: 1.2rem; 
  width: 100%;
  margin: 15px 0;
}

.list-group {
  width: 100%;
}


@media only screen and (max-width: 768px) {          
  .list-group-item {
    font-size: 1rem; 
  }
}
</style>
