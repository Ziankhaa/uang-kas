<template> 
    <div class="container-fluid"> 
      <div class="row"> 
        <div class="col-lg-12"> 
          <h2 class="text-center my-4">Keperluan Kas PPLG 4</h2>
          <form @submit.prevent="kirimData">
            <div class="row d-flex justify-content-center">
            <div class="mb-3 col-lg-6"> 
                  <select v-model="form.nama" class="form-control form-control-lg form-select rounded-3 mb-2"> 
                    <option value="">Nama...</option>
                  </select> 
                </div>
              </div>
              <div class="row d-flex justify-content-center">
                <div class="mb-3 col-lg-6 ">
                  <input type="date" class="form-control form-control-lg form-select rounded-3 mb-2" placeholder="Tanggal">
                </div>
              </div>
              <div class="row d-flex justify-content-center">
                <div class="mb-3 col-lg-6">
                  <input type="text" class="form-control form-control-lg form-select rounded-3 mb-2" placeholder="Keperluan...">
                </div>
                </div>
              <div class="row d-flex justify-content-center">
                <div class="mb-3 col-lg-6">
                  <input type="text" class="form-control form-control-lg form-select rounded-3 mb-2" placeholder="Nominal Bayar...">
                </div>
                </div>
          </form>
        </div>
      </div>
      <nuxt-link to="/keperluan">
      <button type="submit" class="btn btn-success btn-lg rounded-3 px-3"> Kirim </button>
      </nuxt-link>
    </div>
    </template>
  
    
    <style scoped>
    
    .btn-success{
      background-color: #000000;
    }
    input{
      background: #D9D9D9;
    }
    select{
      background: #D9D9D9;
    }
    </style>
    
    <script setup>
    const supabase = useSupabaseClient()
    
    const members = ref([])
    
    const objectives = ref([])
    
    const form = ref ({
    nama: "",
    Waktu: "",
    Keperluan: "",
    })
    
    </script>