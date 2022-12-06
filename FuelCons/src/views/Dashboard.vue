<template>

<div class="">

<div class="w-full px-8 py-8">
<carListVue></carListVue>
<CarDetail></CarDetail>
</div>


</div>




</template>
<script>

import CarDetail from "../components/cars/carDetail.vue"
import carListVue from "../components/cars/carList.vue";
export default {
components:{
CarDetail,
carListVue


}


}

</script>