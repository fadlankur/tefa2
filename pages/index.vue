
<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6">
                <nuxt-link to="/pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5 mb-4">
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
            <h2 class="mt-5">STATISTIK</h2>
            <div class="container-fluid">
                <div class="row my-5">
                    <div class="col-lg-6">
                        <div class="card bg-p rounded-5 mb-4">
                            <div class="p">
                                <div class="card-body">
                                    <h1 style="font-size: 110px;">7</h1>
                                    <h2>Pengunjung</h2>
                                </div>    
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-6">
                        <div class="card bg-b rounded-5">
                            <div class="b">
                                <div class="card-body">
                                    <h1 style="font-size: 110px">77</h1>
                                    <h2>Buku</h2>
                                </div>
                            </div>
                        </div>
                    </div>                   
                </div>                
            </div>
        </div>  
        <div>
            <Chart/>
        </div>      
    </div>
</template>


<style scoped>
.card {
    height: 250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
    background-image: url('../assets/img/kunjungan.jpeg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover ;
    color: black;
}
.card.bg-buku {
    background: url('../assets/img/caribuku.jpg') no-repeat center center;
    background-size: cover;
    color: black;
}
.card.bg-p  {
    background-color: #FDB702;
    background-position: center center;
}
.card.bg-b {
    background-color: #C8FF52;
    background-position: center center;
}
</style>