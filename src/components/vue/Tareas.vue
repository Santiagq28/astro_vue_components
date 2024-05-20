<script setup>
    import { ref } from 'vue';

    let tareas = ref([]);

    let add_tarea;

    let mostrar = ref(false);

    let eliminar = ref(-1);

    function Agregar_tarea(){
        tareas.value.push(add_tarea);
        mostrar.value = true;
    }
    function Borrar(index){
        console.log(index);
        tareas.value.splice(index,1);
        
    }
</script>

<template>
    <div class="grid bg-slate-100 w-80">
        <div>
            <input type="text" v-model="add_tarea" class="p-2 bg-zinc-800 text-white">
            <button @click="Agregar_tarea" class="p-2 rounded">Agregar</button>
        </div>
        
        <div>
            <ul v-show="mostrar">
                <li  v-for="(tarea,index) in tareas" 
                :key="index"
                class="bg-zinc-400 py-2 px-4 flex justify-between text-white font-bold text-lg m-2"
                >   
                    <p>{{ tarea }}</p>
                    
                    <button @click="Borrar(index)" class="bg-red-500 text-white font-bold px-4 py-1 rounded m-2">X</button>
                </li>
                
            </ul>
        </div>
    </div>
</template>