<!--passing data parent component to child component, some time you might also want to communicate from child component back to  the parent component this is where custome events -->
<!--use of $emit. events validation (similar to validating props passed into a child component it is also possible to validate custome events that are emitted from the child component )-->
<!-- to allow components to send 
and receive events outside beyond the parent-child relationship, producing a result known as the event bus. -->
<template>
  <div id="event">
    <h2 id="pop">This is a Popup</h2> <!--1-->
    <button id="close" @click="$emit('close','tom')">Close Popup</button>  <!--click event we use event binding-->
   </div>
</template>
 
<script>
export default {
  name: 'PopUp',
  emits: ['close']          //that component can emit the parent component(app component) //last step
    
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

<!--to summarize custom events, specify the emits option in the child component and emit an event using the dollar emit instance property 
  bind to the custome event using eventbinding in the parent component,
  any data you want to send from child to the parent  can be included as the second argument to dollar emit -->
