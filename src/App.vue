<template>
  <div id="eve">
    <button @click="showPopup = true">show Popup</button><!--set the showpopup value true-->
    <PopUp v-show="showPopup" @close="closePopup"/> <!--conditionally render it-->
  
  </div>
</template>

<script>
import PopUp from './components/PopUp.vue'

export default {
  name: 'App',
  components: {
    PopUp,
   
  },
  data() {
    return {            //add data property to conditionally render it
      showPopup: false  // show popup initialized to false the popup is hidden on page load 
    }
    
  },
  methods: {                               //now send the data to the parent with our custom event //now the close event handler to method 
    closePopup(name) {
      this.showPopup = false
      console.log('name', name)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
