<template> 
  <div class="container-fluid"> 
    <div class="row"> 
      <div class="col-lg-12"> 
        <h2 class="text-center my-4">Bayar Uang Kas Digital PPLG 4</h2>
        <form @submit.prevent="kirimData">
          <div class="row d-flex justify-content-center">
            <div class="mb-3 col-lg-6"> 
              <select v-model="form.nama" class="form-control form-control-lg form-select rounded-3 mb-2"> 
                <option value="">Nama...</option>
                <option v-for="(member, i) in members" :key="i" :value="member.nama">{{ member.nama }}</option>
              </select> 
            </div>
          </div>

          <div class="row d-flex justify-content-center">
            <div class="mb-3 col-lg-6">
              <input v-model="form.tanggal" type="date" class="form-control form-control-lg form-select rounded-3 mb-2" placeholder="Tanggal">
            </div>
          </div>

          <div class="row d-flex justify-content-center">
            <div class="mb-3 col-lg-6">
              <input v-model="form.nominal" type="text" class="form-control form-control-lg form-select rounded-3 mb-2" placeholder="Nominal Bayar:">
            </div>
          </div>

          <div class="row d-flex justify-content-center">
            <div class="col-lg-6">
              <button type="submit" class="btn btn-success btn-lg rounded-3 px-3"> Kirim </button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.btn-success {
  background-color: #000000;
}

input {
  background: #D9D9D9;
}

select {
  background: #D9D9D9;
}
</style>

<script setup>
import {ref, onMounted} from 'vue'

const supabase = useSupabaseClient()

const members = ref([])

const form = ref({
  nama: "",
  tanggal: "",
  nominal: ""
})

const kirimData = async () => {
  const { data, error } = await supabase
  .from('riwayat')
  .insert([{
    nama: form.value.nama,
    tanggal: form.value.tanggal,
    nominal: form.value.nominal
  }])
  if (!error) navigateTo('/dataKas/')
}

const getNama = async () => {
  const { data, error } = await supabase.from('siswa').select('id, nama')
  if (error) {
    console.error('Gagal mengambil nama')
    return
  }
  members.value = data
}

onMounted(getNama)
</script>
