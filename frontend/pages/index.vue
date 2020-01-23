<template>
  <div class="book">
    <div class="page">


      <div class='d-flex ' style='width: 770px; border:1px solid lightgrey'>
        <div><repair-order-form></repair-order-form></div>
        <div style='margin-left: 50px;'><phone-model></phone-model></div>
      </div>

      <div class='d-flex mt-5' style='width: 770px; border:1px solid lightgrey'>
        <div><device-check></device-check></div>
      </div>


     </div>
  </div>
</template>

<script>

import PhoneModel from '../components/PhoneModel.vue'
import RepairOrderForm from '../components/RepairOrderForm.vue'
import DeviceCheck from '../components/DeviceCheck.vue'
export default {
  components:{
    PhoneModel,
    RepairOrderForm,
    DeviceCheck
  }
}
</script>

<style>
  body {
        
        width: 100%;
        height: 100%;
        margin: 0;
        padding: 0;
        background-color: #FAFAFA;
        font: 12pt "Tahoma";
    }
    * {
        box-sizing: border-box;
        -moz-box-sizing: border-box;
    }
    .page {
        width: 210mm;
        min-height: 297mm;
        padding: 2mm;
        margin: 12mm auto;
        border: 1px whitesmoke solid;
        border-radius: 5px;
        background: whitesmoke;
        box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    }
    .subpage {
        padding: 1cm;
        border: 1px lightgray solid;
        height: 257mm;
        outline: 1cm #FFEAEA solid;
    }
    
    @page {
        size: A4;
        margin: 0;
    }


    @media print {
        
        html, body {
            visibility: visible;
            position: absolute;
            left: 0;
            top: 0;
            width: 210mm;
            height: 297mm;        
        }
        .page {

            margin: 0;
            border: initial;
            border-radius: initial;
            width: initial;
            min-height: initial;
            box-shadow: initial;
            background: initial;
            page-break-after: always;
        }
    }
/*   */
  
</style>