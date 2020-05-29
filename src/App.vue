<template>
<div id="app">
<h3>{{title}}</h3>
<router-view></router-view>
<router-link class="link" to="/data/people">Meet the Characters</router-link> |
<router-link class="link" to="/data/planets">Explore the Planets</router-link>

</div>

</template>
<script>
import Character from './Components/Character.vue'
export default {
    name:"app",
    data() {
        return {
            title:"Generate Your Team",
           initial_ids:[1,13,14]
        }
    },
    // components:{
    //     Character

    // }

}
</script>>
//
