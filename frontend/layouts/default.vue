<template>
  <v-app>
  <div id="logo" class="grey darken-3" style='height:180px;'>
    <div align='right'>
    <v-btn class='white--text' style='margin-top: 10px' outlined  small>SIGN IN</v-btn>
    <v-btn class='white--text' style='margin-top: 10px;margin-right: 10px;' outlined  small>SIGN UP</v-btn>
    </div>
    <v-img src='/logo.png' style='margin: 0px auto;width:300px;'></v-img>
  </div>
  <div>
    <nuxt/>
  </div>
</v-app>

</template>

<script>
export default {

}
</script>

<style>
@media print {
        
        #logo{
          display: none;
        }
        html, body {
            visibility: hidden;
            position: absolute;
            left: 0;
            top: 0;
            width: 210mm;
            height: 297mm;        
        }
}
</style>