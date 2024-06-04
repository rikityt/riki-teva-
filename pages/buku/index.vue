<template>
  <div class="container-fluid p-5">
      <div class="row">
          <div class="col-lg-12">
              <h2 class="text-center my-4">BUKU</h2>
              <div class="my-3">
                  <input type="search" class="form-control form-control-lg rounded-5" placeholder="mau baca apa hari ini">
                  <form @submit.prevent="getbooks">
                    <input v-model="keyword"  type="search">
                  </form>
              </div>
              <div class="my-3 text-muted">Menampilkan 3 dari 3</div>
              <div class="row">
                  <div v-for="(book,i) in books" :key="i" class="col-lg-2">
                    <div class="card mb-3">
                        <div class="card-body">
                            <img :src="book.cover" class="cover" alt="cover">
                        </div>
                    </div>
                  </div>
                  <div class="col-lg-2">
                      <div class="card mb-3">
                          <div class="card-body">
                              <img src="~/assets/img/jujutsu.jpg" class="Buku" alt="Buku2">
                          </div>
                      </div>
                  </div>
                  <div class="col-lg-2">
                      <div class="card mb-3">
                          <div class="card-body">
                              <img src="~/assets/img/naruto.jpg" class="Buku" alt="Buku3">
                          </div>
                      </div>
                  </div>
                  <nuxt-link to="http://localhost:3000/">
                      <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">KEMBALI</button>
                  </nuxt-link>
              </div>
          </div>
      </div>
  </div>

</template>

<style scoped>
.card-body {
  text-decoration: none;
  width: 100%;
  height: 20em;
  padding: 0;
}
.Buku {
  width: 100%;
  height: 100%;
  object-position: 0 30; 
}
</style>

<script setup>
const supabase = useSupabaseClient()
const books = ref([])
const getbooks = async () =>{
    const {data, error} = await supabase.form('buku').select('*,kategori(*)')
    if(data)books.value = data
}
onMounted(() =>{
getbooks()
})


</script>