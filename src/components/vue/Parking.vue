<script setup>
    import { ref } from 'vue';
    import Space from '../vue/Space.vue';
    let total = ref(0);

    let parqueadero = ref([0,0,0,0,0,0]);

    function Parquear(precio, pos){
        if(parqueadero.value[pos] == 0){
            total.value += precio;
            console.log(total.value);
            parqueadero.value[pos] = 1;
        }
        else{
            parqueadero.value[pos] = 0;
        }
    }

</script>

<template>
    <div class="grid text-center justify-center">
        <div class="flex gap-10">
            <Space @click="Parquear(1000,0)" vehicule="Carro" :price="1000"/>
            <Space @click="Parquear(1000,1)" vehicule="Carro" :price="1000" />
            <Space @click="Parquear(1000,2)" vehicule="Carro" :price="1000" />
        </div>
        <div class="flex gap-10 mt-5">
            <Space @click="Parquear(500,3)" vehicule="Moto" :price="500" />
            <Space @click="Parquear(500,4)" vehicule="Moto" :price="500" />
            <Space @click="Parquear(500,5)" vehicule="Moto" :price="500" />
        </div>
        <div class="text-center p-4 bg-zinc-500 rounded mt-4 text-white font-bold"><h6>{{ total }}</h6></div>
    </div>
    
</template>