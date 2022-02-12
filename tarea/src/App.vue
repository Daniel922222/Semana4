<template>
    <div class="fondo"> 
     <Navbar />
      <longitu/>
     <Convertidor />
     <masa/>
     <tiempo/>
     <almacenamiento/>
     
    </div>
    
     
  
    

</template>

<script>
import Navbar from './components/Navbar';
import Convertidor from './components/Convertidor';
import longitu from './components/longitu';
import masa from './components/masa.vue';
import tiempo from './components/tiempo.vue';
import almacenamiento from './components/almacenamiento.vue'


export default {
  name: 'App',
  components: {
    Navbar,
    Convertidor,
    longitu,
    masa,
    tiempo,
    almacenamiento
    
   
    
  
  
 
  }
}
</script>

<style>
 .fondo{
  background-image:url('./assets/fon2.jpg') ;

  background-size:cover ;


 }

</style>
