<template>
  <div>
    <v-simple-table light style='width: 766px;' dense height="800px">
        <template v-slot:default>
            <thead>
                <tr>
                <th style='width: 300px' class="subtitle-2 font-weight-bold text-center">Problems</th>
                <th style='width: 90px' class="subtitle-2 font-weight-bold text-center">Status</th>
                <th class="subtitle-2 font-weight-bold text-center">Details</th>
               
                </tr>
            </thead>
  
            <tbody >
            <tr v-for="(item, index) in items" :key="item.id">

            <td style='padding: 8px; margin-left: 10px' class="caption text-left" >{{index+1}}. {{ item.problem }}</td>
            <td ><v-chip x-small @click="onClick(index)">{{item.status}}</v-chip></td>         
            <td class="caption text-left" v-if="items[index].status === 'no work'">  
              
            
                  <v-chip-group v-model="items[index].issueSelect" multiple column active-class="primary">              
                    <v-chip  v-for="i in item.issue" :key="i" x-small>{{i}}</v-chip>
                  </v-chip-group> 
            
           
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
            status: 'work',
            issue: ['light broken','heavy borken','no screen','half screen', 'smashed'],    
            issueSelect: [],
          },
            {
            problem: 'Battery',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],  
            issueSelect: [],
          },
          {
            problem: 'Dock Connector',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],   
          },
          {id: 4,
            problem: 'Earphone',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 5,
            problem: 'Microphone',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 6,
            problem: 'Wifi/GPS',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 7,
            problem: 'Volume issue',
            status: 'work', 
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 8,
            problem: 'Front Camera',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 9,
            problem: 'Rear Camera',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 10,
            problem: 'Rear Side',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 11,
            problem: 'Seonsor',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
          },
          {id: 12,
            problem: 'Water Damage',
            status: 'work',
            issue: ['light broken','heavy borken','no screen'],
            issueSelect: [],  
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