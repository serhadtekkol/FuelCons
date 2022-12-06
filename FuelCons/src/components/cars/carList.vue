<template>
    <div class="w-full">
    <div class="bg-gray-700 rounded-md shadow-md text-gray-200 px-4 py-4">

<h2>Car List</h2>
<div class="mt-4 bg-gray-500  rounded-md px-4 py-2">
<div class="flex ">
<div class="flex-auto">
    BMW IX4 
    
</div>
<div class="w-8 text-center">
<button @click="showhide('car88454')" class="bg-purple-600 px-2 py-1 rounded-md" > <i class="fal fa-circle-info"></i> </button>

</div>



</div>

</div>


</div>

    
    </div>


<div v-if="showmodal" class="z-50 mx-auto bg-gray-100/50 backdrop-blur-sm  fixed top-0 left-0 w-full  grid h-screen place-items-center">
<div class="w-3/4 bg-gray-800 text-gray-300 shadow-md rounded-lg px-3 py-3">
    <table class="w-full text-sm">
<thead >
<th>Title</th>
<th>Value</th>

</thead>
<tbody class="text-center">
<tr>
<td>KM</td>
<td>18999</td>
</tr>

<tr>
<td>Last Price</td>
<td>20.14</td>
</tr>

<tr>
<td>Total Amount</td>
<td>1864</td>
</tr>

<tr>
<td>Last Station</td>
<td><a :href='t'>Link</a> Opet</td>
</tr>
<tr>
<td>Liter</td>
<td>58,12</td>
</tr>


</tbody>

</table>
<div class="mt-4 text-center">
<button @click="showmodal=false" class=" bg-purple-600 text-white my-9 w-full rounded-md px-2 py-1.5">Close</button>





</div>



</div>

</div>


</template>

<script>
export default {
methods:{
showhide(idsi){
console.log(idsi)
this.showmodal=true;
this.getlocation();
},
getlocation(){
  
    if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(this.showPosition);
  } else {
   console.log( "Geolocation is not supported by this browser.");
  }

},
showPosition(position) {

this.t="https://www.google.com/maps/search/?api=1&query="+position.coords.latitude+","+position.coords.longitude;

 console.log( "Latitude: " + position.coords.latitude +
  "<br>Longitude: " + position.coords.longitude);
}


},
data(){


    return{

showmodal:false,
t:"",
    }
}


}








</script>

<style scoped>

  tr  td:nth-child(1){

text-align: left !important;


}


thead{

border-bottom: 1px gray solid;

}

</style>