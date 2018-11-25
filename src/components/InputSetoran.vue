<template>
  <div id="input-setoran">

    <form action="">

      <div class="field">
        <label class="label">Nama</label>
        <div class="control">
          <input class="input" type="text" placeholder="Masukan Nama Anda" v-model="nama">
        </div>
      </div>
  
      <div class="field">
        <label class="label">Nominal</label>
        <div class="control">
          <input class="input" type="text" placeholder="Contoh: Rp200.000" v-model="nominal_setoran">
        </div>
      </div>
  
  
      
      <div class="field">
        <label class="label">Keterangan</label>
        <div class="control">
          <textarea class="textarea" placeholder="Textarea" v-model="keterangan"></textarea>
        </div>
      </div>
      
  
      <div class="field is-grouped">
        <div class="control">
          <button class="button is-link" @click.prevent="submitSetoran">Submit</button>
        </div>  
      </div>


    </form>


  </div>
</template>
    
<script>
import axios from 'axios'

export default {
  name: "outputSetoran",
  data () {
    return {
      nama: '',
      nominal_setoran: '',
      keterangan: '',
      currentTab: ''
    }
  },
  methods: {
    submitSetoran: function () {
      let dataSetoran = {
        nama: this.nama,
        nominal: this.nominal_setoran,
        keterangan: this.keterangan
      }

    axios({
      method: 'post',
      url: 'https://replikasi.herokuapp.com/data/masukkan',
      data: dataSetoran
    })
    .then(response => {
      console.log(response) /* eslint-disable-line no-console */
      location.reload()
    })
    .catch(err => {
      console.log(err) /* eslint-disable-line no-console */
    })


    }
  }
}
</script>

<style scoped>

</style>
