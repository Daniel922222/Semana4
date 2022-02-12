<template>
    <div class="container pt-3">
    <div class="row">
    <div class="col-lg-12">
        
  <div class="form-group">
    <label for="cantidad">Ingrese catidad</label>
    <input type="number" class="form-control from-control-lg"
            v-model="cantidad"
            v-on:keyup=" convertir"
             id="cantidad"  placeholder="Ingrese cantidad">
    
  </div>
    </div>
    </div>
    <div class="row">
    <div class="col-lg-6">
    <div class="form-group">
    <label for="tengo">Tengo</label>
    <select class="form-control  from-control-lg" id="tengo" v-model="tengo" 
            v-on:change=" convertir">
      <option  v-for ="(almac,index) in alma" v-bind:key="index">
       {{almac}}
      </option>
    </select>
  </div> 
    </div>
    <div class="col-lg-6">
      <div class="form-group">
    <label for="quiero">Quiero</label>
    <select class="form-control  from-control-lg" id="quiero" v-model="quiero"
              v-on:change=" convertir">
      <option  v-for ="(almac,index) in alma" v-bind:key="index">
       {{almac}}
      </option>
      
    </select>
  </div>

    </div>

    </div>

     <div class="text-center pt-3">
      <h5>
         <span class="badge  badge-success"> {{cantidad}} {{tengo}} </span>
          <span class="badge  badge-dark">SON  </span>
           <span class="badge  badge-sucess">{{total}} {{quiero}}</span>

      </h5>
    </div>


    </div>



</template>
<script>
    export default{
        data() {
            return {
                alma:['Kilobytes','Megabytes','Gigabytes'],
                cantidad:0,
                tengo:'Kilobytes',
                quiero:'Megabytes',
                total:0
            }
        },
        
        methods:{
            convertir(){
            
                switch(this.tengo) {
  case 'Kilobytes':
      if(this.quiero ==='Kilobytes'){
          this.total=this.cantidad 
      }
       if(this.quiero ==='Megabytes'){
          this.total=this.cantidad /1000;
      }
       if(this.quiero ==='Gigabytes'){
          this.total=this.cantidad /1000000;
      }
    // code block
    break;
  case 'Megabytes':
       if(this.quiero ==='Kilobytes'){
          this.total=this.cantidad * 1000;
      }
       if(this.quiero ==='Megabytes'){
          this.total=this.cantidad 
      }
       if(this.quiero ==='Gigabytes'){
          this.total=this.cantidad /1000;
      }
    // code block
    break;
    case 'Gigabytes':
         if(this.quiero ==='Kilobytes'){
          this.total=this.cantidad * 1000000;
      }
       if(this.quiero ==='Megabytes'){
          this.total=this.cantidad * 1000;
      }
       if(this.quiero ==='Gigabytes'){
          this.total=this.cantidad 
      }
    // code block
    break;
  default:
    // code block
}
            

            
            }
        }
    }
    
</script>

<style scoped>
label {
font-weight: 700;
font-size:120%;
}
.badge{
margin: 2px;
font-size: 150%;
}
</style>
