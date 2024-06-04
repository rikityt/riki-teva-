<template>
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
        <nuxt-link to="/pengunjung/tambah">
          <div class="card bg-pengunjung rounded-5">
            <div class="card-body">
              <h2>Pengunjung</h2>
            </div>
          </div>
        </nuxt-link>
      </div>

      <div class="col-lg-6">
        <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5">
            <div class="card-body">
              <h2>Cari Buku</h2>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
  
  <div class="container-fluid">
    <div class="row my-5">
      <div class="col-lg-6">
          <div class="card rounded-5 color1">
            <div class="card-body d-flex justify-content-around d-flex align-items-center">
              <h2><span class="no">30</span> pengunjung</h2>
              </div>
            </div>
        </div>
        <div class="col-lg-6">
          
            <div class="card rounded-5 color2">
              <div class="card-body d-flex justify-content-around d-flex align-items-center">
                <h2><span class="no">400</span> Buku</h2>
              </div>
            </div>         
        </div>
      </div>
       <div class="line">
              <statistik/>
       </div>   
  </div>

</template>


<style scoped>
.card {
  height: 250px;
  box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
  background-image: url('../assets/img/bg-home-kunjungan.jpeg');
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
.card.bg-buku {
  background: url(../assets/img/bg-home-cari-buku.jpg) no-repeat center center;
  background-size: cover;
}
.card{
  background-color: #e797a6;
}
</style>