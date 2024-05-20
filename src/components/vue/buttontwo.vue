<script setup>
    import { ref } from 'vue';

    let options = ref(["option1", "option2", "option3"]);
    let mostrar = ref(true);
    function ocultar(){
        if(mostrar.value == false){
            mostrar.value = true;
        }
        else{
            mostrar.value = false;
        }
        
    }
</script>
<template>
    <div class="bg-zinc-300 flex py-4 px-2 mx-auto text-center justify-center">
        <div class="w-60">
            <ul>
                <li class="bg-black text-white py-2 px-1 mt-1 w-60">Options</li>
                <li class="bg-black text-white py-2 px-1 mt-1 w-60"
                v-show="mostrar"
                v-for="(option, index) in options" :key="index"
                
                >{{ option }}</li>
            </ul>
        </div>
        <button class="bg-white h-10"
        @click="ocultar">
            Mostrar
        </button>
    </div>
</template>