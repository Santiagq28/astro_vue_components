<script setup>
    import { ref } from 'vue';
    let numeros = ref([1,2,3,4,5,6,7,8,9,10]);
    let divisor;
    let newnumber;
    let mostrar = ref(false);
    function Agregar(){
        numeros.value.push(newnumber);
    }
    function Par() {
        if(mostrar.value == false || divisor == 0){
            mostrar.value = false;
            divisor = 1;
            mostrar.value = true;
        }else{
            mostrar.value = false;
        }

        
    }
    function Impar(){
        if(mostrar.value == false || divisor == 1){
            mostrar.value = false;
            divisor = 0;
            mostrar.value = true;
        }else{
            mostrar.value = false;
        }
        
    }
</script>


<template>
    <div class="bg-zinc-600 justify-center my-10 text-center">
        <input type="number" v-model="newnumber">
        <button class="bg-white m-2 p-2" @click="Agregar">Agregar</button>
        <button class="bg-green-600 p-2 text-white" @click="Par">Par</button>
        <button class="bg-red-600 p-2 text-white" @click="Impar">Impar</button>
        <div>
            <ul class="justify-center mx-auto">
                <li v-show="mostrar" v-for="(numero, index) in numeros" 
                :key="index"
                :class="{'hidden': numero%2 === divisor}"
                class="text-white bg-black mt-2 p-5 w-16 text-center mx-auto">
                    {{ numero }}
                </li>
            </ul>
        </div>
    </div>

</template>