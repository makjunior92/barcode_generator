/* eslint-disable */

<template>
  <div id="app">

      <div class="container">
        <div class="row">
          
          
        <div class="col-md-8 offset-md-3 mt-5">

         <div class="card">
          
          <div class="card-body">
            <h5 class="card-title">Barcode Generator</h5>
            

            <!-- code -->
           
             <div class="form-group mt-5">
              <label for="usr">Enter the code:</label>
              <input type="text" class="form-control" v-model="code">
            </div>
          

            <h6 class="card-subtitle mb-2 text-muted mt-5">Bar code settings</h6>

           <div class="row">
              <!-- width -->

            <div class="col-md-4">
              
              <div class="input-group mb-3">
                    <div class="input-group-prepend">
                      <label class="input-group-text" >Width</label>
                    </div>
                    <select class="custom-select" v-model="width" name="" id="">
                      <option value="1">1</option>
                      <option value="1.5">1.5</option>
                      <option value="2">2</option>
                      <option value="3">3</option>
                      <option value="4">4</option>
                    </select>
                  </div>
              
            </div>


            <!-- height -->


             <div class="col-md-4">
              
              <div class="input-group mb-3">
                    <div class="input-group-prepend">
                      <label class="input-group-text" for="inputGroupSelect01">Height</label>
                    </div>
                    <select class="custom-select" v-model="height">
                       <option value="50">50</option>
                        <option value="100">100</option>
                    </select>
                  </div>
              
            </div>


            <!-- font size -->

            <div class="col-md-4">
              
              <div class="input-group mb-3">
                    <div class="input-group-prepend">
                      <label class="input-group-text" for="inputGroupSelect01">Font Size</label>
                    </div>
                    <select class="custom-select" v-model="font_size">
                        <option value="10">10</option>
                        <option value="15">15</option>
                        <option value="20">20</option>
                        <option value="40">40</option>
                    </select>
                  </div>
              
            </div>

           </div>

           
            
            <button type="button" class="btn btn-primary" @click="printSection">Print</button>
          
          </div>
        
        </div>



        <div v-if="code!=''" class="card mt-5">
          <div class="card-body text-center">
            
            <barcode
              id="printSection"
              v-model="code"
              v-bind:fontSize="font_size"
              v-bind:height="height"
              v-bind:text="code"
              v-bind:width="width"
            ></barcode>
          
          </div>
        </div>
        
        </div>
        
        
        
        </div>
      </div>


    
  </div>
</template>

<script>
import VueBarcode from "vue-barcode";

export default {
  // import {  } from "module";
  components: {
    barcode: VueBarcode,
  },
  data() {
    return {
      code: "",
      height: 50,
      font_size: 20,
      width : 1,
      text : "WellMax Value"
    };
  },
  methods: {

      printSection() {
        this.$htmlToPaper("printSection");
      }
    },


};
</script>

<style scoped></style>

/* eslint-disable */
