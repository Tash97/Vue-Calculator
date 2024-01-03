<template>
    <nav class="flex justify-center items-center h-[15vh] bg-gradient-to-b from-purple-500 to-purple-800 text-3xl">
        <h1>The Calculator</h1>
    </nav>
    <div class="bg-gradient-to-br from-blue-400 to-red-400 w-full h-[85vh] flex justify-center items-center">
        
        <Calculator />

    </div>
</template>

<script setup>
    import Calculator from './components/Calculator.vue'
</script>