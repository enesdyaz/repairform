<template>
  <div>
      
    <v-simple-table light style='width: 740px;' dense height="800px">
        <template v-slot:default>
            <thead >
                <tr>
                <th class="subtitle-2 font-weight-bold text-center">Problems</th>
                <th class="subtitle-2 font-weight-bold text-center">Status</th>
                <th class="subtitle-2 font-weight-bold text-center">Details</th>
               
                </tr>
            </thead>
  
            <tbody >
            <tr v-for="item in items" :key="item.name">
            <td class="caption text-left">{{ item.problem }}</td>
            <td class="caption text-left"><v-switch dense v-model='item.status' light :label="`${item.status.toString()}`" ></v-switch></td>                                  
            <td class="caption text-left">
                <div v-if='items.status === true'>
                    <div>
                    issue happend
                    </div>
                </div>
                </td>                                  
            </tr>
            </tbody>
         </template>
    </v-simple-table>
{{status}}


  </div>
</template>

<script>
  export default {
    data () {
      return {
        detailList: [],
        items: [
          {
            problem: 'Screen',
            status: false,
            issue: {
                reason: ['light broken','heavy borken','no screen']
            }
          },
            {
            problem: 'Battery',
            status: false,
          },
          {
            problem: 'Dock Connector',
            status: false,
          },
          {
            problem: 'Earphone',
            status: false,
          },
          {
            problem: 'Microphone',
            status: false,
          },
          {
            problem: 'Wifi/GPS',
            status: false,
          },
          {
            problem: 'Volume issue',
            status: false,
          },
          {
            problem: 'Front Camera',
            status: false,
          },
          {
            problem: 'Rear Camera',
            status: false,
          },
          {
            problem: 'Rear Side',
            status: false,
          },
          {
            problem: 'Seonsor',
            status: false,
          },
          {
            problem: 'Water Damage',
            status: false,
          },
        ]
      }
  },
  computed: {
      status() {
          
          for (var i=0;i<this.items.length;i++){
              console.log(this.items[i].problem)
              if(this.items[i].status === 'true'){
                
                this.detailList.push(this.items[i].issue.reason)
              }
          }
          console.log(this.detailList)
          
        }
    }
    
};

</script>

<style>

</style>