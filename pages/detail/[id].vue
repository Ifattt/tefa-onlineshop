<template>
  <div>
    <div class="row">
      <div class="col-lg-1">
        <a href="/" class="btn btn-grey mt-3">
          <button style="background-color: transparent; border: none; ">
            <img src="~/assets/img/kembali.png" alt="kembali" style="width: 30px; height: 30px;">
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
      <div class="col-4">
        <img :src="detail.cover" class="cover img-fluid" alt="cover">
      </div>
      <div class="col">
        <ul class="">
          <li class="list-group-item"> {{ detail.judul }}</li>
          <li class="list-group-item"> Deskripsi : </li>
          <li class="list-group-item deskripsi"> {{ detail.deskripsi }}</li>
          <!-- <li class="list-group-item"> {{ detail.deskripsi2 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi3 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi4 }}</li>
          <li class="list-group-item"> {{ detail.deskripsi5 }}</li> -->
        </ul>
        <NuxtLink class="btn bg-abu btn-lg rounded-5"
          to="https://wa.me/6285724948649?text=Halo%20saya%20ingin%20pesan%20bouquet" target="_blank">
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
 white-space: pre-line ;
}
.cover {
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

/* .container-fluid {
  height: 90vh;
} */

.btn-order {
  position: relative;
}

.btn-order .btn-float {
  position: absolute;
  right: 0;
  bottom: 0;
}

.list-group-item {
  font-size: 1.5rem !important;
  width: 100%;
}

.list-group {
  width: 100% !important;
}

@media only screen and (max-width: 768px) {
  .list-group-item {
  font-size: 10px !important;
}

.row {
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.col {
  display: flex;
  justify-content: center;
  flex-direction: column;

}

}
</style>