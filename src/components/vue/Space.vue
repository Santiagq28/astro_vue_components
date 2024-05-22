<script setup>
    import { ref } from 'vue';
    import { defineProps } from 'vue';

    let props = defineProps({
        vehicule: String,
        estado: String,
        price: Number
    })

    let estado = ref('Disponible');
    let libre = ref(true);
    function Parquear(){
        if(estado.value == 'Disponible'){
            estado.value = 'Ocupado';
            libre.value = false;
        }else{
            estado.value = 'Disponible';
            libre.value = true;
        }
        

    }

</script>

<template>
    <button @click="Parquear" 
    
    class="p-4  text-white font-bold font-serif rounded w-[120px] text-center"
    :class="{'bg-red-600 hover:bg-red-400': estado === 'Ocupado',
        'bg-green-500 hover:bg-green-700': estado === 'Disponible'
    }"
    >
        {{ vehicule }}
        {{ estado }}
        ${{ price }}
    </button>
</template>