<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-md-6">
                <nuxt-link to="/dataKas/tambah">
                <div class="card bg-dataKas rounded-5 m-3">
                    <div class="card-body">
                        <h2>Bayar Uang Kas</h2>
                    </div>
                </div>
                </nuxt-link>
            </div>
        
            <div class="col-md-6">
                <nuxt-link to="/keperluan/tambah">
                <div class="card bg-riwayat rounded-5 m-3">
                    <div class="card-body">
                        <h2>Keperluan Uang Kas</h2>
                    </div>
                </div>
                </nuxt-link>
            </div>

            <div class="col-md-6 jarak">
                <nuxt-link to="/dataKas">
                <div class="card bg-KasKeluar rounded-5 m-3">
                    <div class="card-body">
                        <h2>Riwayat Uang Kas</h2>
                    </div>
                </div>
                </nuxt-link>
            </div>

        </div>
    </div>
</template>

<style scoped>
.card {
    height:250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-dataKas {
    background: url('../assets/wangg1.png');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    margin-bottom: 30px;
}
.card.bg-riwayat {
    background: url('../assets/wangg1.png') no-repeat center center;
    background-size: cover;
}

.card.bg-KasKeluar {
    background: url('../assets/wangg2.png');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    margin-bottom: 30px;
}

.jeep{
    height: 200px;
    box-shadow: 1px 1px 10px;
    border-radius: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #E1B4F1;
}

.raccing1{
    height: 200px;
    box-shadow: 1px 1px 10px;
    border-radius: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #C1F5E9;
}

.jarak {
    margin-inline-start: 300px;
}
</style>