<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
<div class="bg-gray-800 h-screen w-screen">


  <RouterView />

<div  class="fixed bottom-0 w-full">
<bottomNav></bottomNav>

</div>


</div>
 



</template>

<script>
import bottomNav from "./components/bottomnav.vue"

export default {
components:{

bottomNav

}


}

</script>