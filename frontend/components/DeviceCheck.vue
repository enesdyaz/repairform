<template>
  <div>
    <v-simple-table light style='width: 766px;' dense height="800px">
        <template v-slot:default>
            <thead >
                <tr>
                <th class="subtitle-2 font-weight-bold text-center">Problems</th>
                <th class="subtitle-2 font-weight-bold text-center">Status</th>
                <th class="subtitle-2 font-weight-bold text-center">Details</th>
               
                </tr>
            </thead>
  
            <tbody >
            <tr v-for="(item, index) in items" :key="item.id">
            <td class="caption text-left" >{{ item.problem }}</td>
            <td><v-chip x-small @click="onClick(index)">{{item.status}}</v-chip></td>                                  
            
            
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
          {id: 1,
            problem: 'Screen',
            status: 'work',
            issue: {
                reason: ['light broken','heavy borken','no screen']
            }
          },
            {id: 2,
            problem: 'Battery',
            status: 'work',
          },
          {id: 3,
            problem: 'Dock Connector',
            status: 'work',
          },
          {id: 4,
            problem: 'Earphone',
            status: 'work',
          },
          {id: 5,
            problem: 'Microphone',
            status: 'work',
          },
          {id: 6,
            problem: 'Wifi/GPS',
            status: 'work',
          },
          {id: 7,
            problem: 'Volume issue',
            status: 'work',
          },
          {id: 8,
            problem: 'Front Camera',
            status: 'work',
          },
          {id: 9,
            problem: 'Rear Camera',
            status: 'work',
          },
          {id: 10,
            problem: 'Rear Side',
            status: 'work',
          },
          {id: 11,
            problem: 'Seonsor',
            status: 'work',
          },
          {id: 12,
            problem: 'Water Damage',
            status: 'work',
          },
        ]
      }
  },
  computed: {
      status() {
          
          for (var i=0;i<this.items.length;i++){
              
              if(this.items[i].status === 'true'){
                
                this.detailList.push(this.items[i].issue.reason)
              }
          }
          console.log(this.detailList)
          
        }
    },

    methods:{
      onClick(index){
      //  console.log(this.items.problem)
        if(this.items[index].status==='work'){
            this.items[index].status = 'no work'
        } else {
          this.items[index].status = 'work'
        }
      }
    }
    
};

</script>

<style>

</style>