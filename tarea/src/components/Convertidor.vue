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
      <option  v-for ="(moneda,index) in monedas" v-bind:key="index">
       {{moneda}}
      </option>
    </select>
  </div> 
    </div>
    <div class="col-lg-6">
      <div class="form-group">
    <label for="quiero">Quiero</label>
    <select class="form-control  from-control-lg" id="quiero" v-model="quiero"
              v-on:change=" convertir">
      <option  v-for ="(moneda,index) in monedas" v-bind:key="index">
       {{moneda}}
      </option>
      
    </select>
  </div>

    </div>

    </div>

     <div class="text-center pt-3">
      <h5>
         <span class="badge  badge-success"> {{cantidad}} {{tengo}} </span>
          <span class="badge  badge-dark">SON  </span>
           <span class="badge  badge-sucess">{{getTotal(total)}} {{quiero}}</span>

      </h5>
    </div>


    </div>



</template>
<script>
    export default{
        data() {
            return {
                monedas:['USD','EUR','LIBRA'],
                cantidad:0,
                tengo:'USD',
                quiero:'EUR',
                total:0
            }
        },
        
        methods:{
            convertir(){
            
                switch(this.tengo) {
  case 'USD':
      if(this.quiero ==='USD'){
          this.total=this.cantidad 
      }
       if(this.quiero ==='EUR'){
          this.total=this.cantidad * 0.88;
      }
       if(this.quiero ==='LIBRA'){
          this.total=this.cantidad * 0.75
      }
    // code block
    break;
  case 'EUR':
       if(this.quiero ==='USD'){
          this.total=this.cantidad *1.19;
      }
       if(this.quiero ==='EUR'){
          this.total=this.cantidad 
      }
       if(this.quiero ==='LIBRA'){
          this.total=this.cantidad * 0.89
      }
    // code block
    break;
    case 'LIBRA':
         if(this.quiero ==='USD'){
          this.total=this.cantidad *1.33;
      }
       if(this.quiero ==='EUR'){
          this.total=this.cantidad  *1.12;
      }
       if(this.quiero ==='LIBRA'){
          this.total=this.cantidad 
      }
    // code block
    break;
  default:
    // code block
}
            

            },
            getTotal(valor){
                return Math.round(valor)
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
