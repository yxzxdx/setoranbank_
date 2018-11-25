<template>
  <div id="app">
    <!-- <div class="columns">
      <nav v-for="tab in tabs" :key="tab" @click="currentTab = tab" >
        <button class="button">{{tab}}</button>
      </nav>

      <div class="column">
        <component :is="currentTabComponent" class="tab-content"></component>        
      </div>
    </div> -->

  <div class="card">
    <header class="card-header">
      <p class="card-header-title ">
        <span class="is-size-4 has-text-primary">Aplikasi Pencatatan Setoran</span>
      </p>
      <a href="#" class="card-header-icon" aria-label="more options">
        <span class="icon">
          <i class="fas fa-angle-down" aria-hidden="true"></i>
        </span>
      </a>
    </header>

    <div class="card-content">
      <div class="content">
        <component :is="currentTabComponent" class="tab-content"></component> 
      </div>
    </div>

    <footer class="card-footer" >
      <div v-for="tab in tabs" :key="tab" @click="currentTab = tab" class="nav-button">
        <button class="button is-primary">{{tab}}</button>
      </div>
    </footer>
  </div>




  </div>
</template>

<script>
import InputSetoran from './components/InputSetoran.vue'
import OutputSetoran from './components/OutputSetoran.vue'

export default {
  name: 'app',
  components: {
    "tab-input": InputSetoran,
    "tab-output": OutputSetoran
  },
  data () {
    return {
      tabs: ['Input', 'Output'],
      currentTab: 'input'
    }
  },
  computed: {
    currentTabComponent: function () {
      return "tab-" + this.currentTab.toLowerCase();
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.card {
}

.class-header-title {
  text-align: center;
}


.nav-button {
  width: 100%;
}

.nav-button button {
  width: 100%;
}

</style>
