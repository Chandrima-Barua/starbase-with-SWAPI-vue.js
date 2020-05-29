<template>
<div class="col-md-12">
<Item v-for="(passedItem,index) in items" :key="index" :passedItem="passedItem" :type="type">
</Item>
</div>
</template>
<script>
import Item from './Item.vue'
export default {
    
    data() {
        return {
            type:this.$route.params.type,
            items:[] 
        }
       
    },
    watch:{
        '$route': 'fetchItems'
    },
    methods:{
        
        fetchItems() {
            
            this.items = []
            this.type = this.$route.params.type
            let datainitial_ids = [1,13,14]
            for(let i in datainitial_ids){
                let id = datainitial_ids[i]
                
                 fetch(`https://swapi.dev/api/${this.type}/${id}`,{
                method:'GET'
            }).then(response => response.json()).then(json => this.items.push(json))
            }
        },
         switchCharacter(){
            let random_id = Math.floor(Math.random() * 83) + 1
             this.fetchCharacter(random_id)

        }
    },
    created() {
     this.fetchItems()
               },
    components:{
        Item
    }
   
    
}
</script>>