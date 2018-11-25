<template>
  <div id="input-setoran">

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
        <button class="button is-link" @click="submitSetoran">Submit</button>
      </div>
    </div>

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
      keterangan: ''
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
