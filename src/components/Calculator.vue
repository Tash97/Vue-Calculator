<template>
    <div class="bg-gradient-to-br from-purple-500 to-purple-800 rounded-lg flex flex-col w-[27%] h-[95%] border-black border-[1px]">
            <div class="flex items-center justify-center w-full h-[33%]">
                <div class="bg-blue-500 border-black border-[1px] w-[90%] h-[80%] flex flex-col justify-end items-end px-1.5 py-2 pt-4 text-5xl">
                    <div class="mb-auto text-5xl opacity-50">{{ answer }}</div>
                    <div>{{ screenValue }}</div>
                </div>
            </div>
            <div class="flex items-start justify-center w-full h-[67%] ">
                <div class=" flex flex-col w-[90%] h-[95%]">
                    <div class=" w-full h-[20%] flex justify-between items-center ">
                        <div @click="clear()" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-c"></i>
                        </div>
                        <div @click="clickToScreen('posneg')" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="font-semibold text-xl">+/-</i>
                        </div>
                        <div @click="theUltraRich()" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-percent"></i>
                        </div>
                        <div @click="addOperator('/')" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-divide"></i>
                        </div>
                    </div>
                    <div class=" w-full h-[20%] flex justify-between items-center ">
                        <div @click="clickToScreen(7)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-7"></i>
                        </div>
                        <div @click="clickToScreen(8)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-8"></i>
                        </div>
                        <div @click="clickToScreen(9)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-9"></i>
                        </div>
                        <div @click="addOperator('*')" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-xmark"></i>
                        </div>
                    </div>
                    <div class=" w-full h-[20%] flex justify-between items-center ">
                        <div @click="clickToScreen(4)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-4"></i>
                        </div>
                        <div @click="clickToScreen(5)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-5"></i>
                        </div>
                        <div @click="clickToScreen(6)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-6"></i>
                        </div>
                        <div @click="addOperator('-')" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-minus"></i>
                        </div>
                    </div>
                    <div class=" w-full h-[20%] flex justify-between items-center ">
                        <div @click="clickToScreen(1)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-1"></i>
                        </div>
                        <div @click="clickToScreen(2)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-2"></i>
                        </div>
                        <div @click="clickToScreen(3)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-3"></i>
                        </div>
                        <div @click="addOperator('+')" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-plus"></i>
                        </div>
                    </div>
                    <div class=" w-full h-[20%] flex justify-between items-center ">
                        <div @click="clickToScreen(0)" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-start ps-[2.05em] items-center w-[47.65%] h-[76%]">
                            <i class="fa-solid fa-0"></i>
                        </div>
                        <div @click="clickToScreen('.')" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="font-semibold text-xl">.</i>
                        </div>
                        <div @click="TGEqualizer()" class="bg-gradient-to-b from-purple-700 to-purple-800 border-black border-[1px] rounded-lg flex justify-center items-center w-[21%] h-[76%]">
                            <i class="fa-solid fa-equals"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>

<script setup>
import { ref } from 'vue';

const screenValue = ref(0)
const number = ref([])
const expressionArray = ref([])
const answer = ref(null)

const clickToScreen = (num) => {
    if(number.value.length < 14 && screenValue.value !== 'Too Big!'){      
        if(num === 'posneg' && number.value.length){
            screenValue.value = Number(screenValue.value) * -1
            number.value = screenValue.value.toString().split("")
        } else if (num !== 'posneg'){
            number.value.push(num)
            screenValue.value = number.value.join("")
        }
    }

}

const addOperator = (operator) => {
    if(screenValue.value && screenValue.value !== 'Too Big!'){
        expressionArray.value.push(screenValue.value)
        screenValue.value = null
        number.value = []
        if(expressionArray.value.length === 3 ){
            if(expressionArray.value[1] === "+"){
                answer.value = Number(expressionArray.value[0]) + Number(expressionArray.value[2])
                if(answer.value.toString().length > 14){
                    if(answer.value.toFixed(2).toString().length > 14){
                        screenValue.value = "Too Big!"
                        answer.value = "Too Big!"
                    } else{
                        answer.value = answer.value.toFixed(2)
                        expressionArray.value = [answer.value, operator]
                    }
                } else{
                    expressionArray.value = [answer.value, operator]
                }
            } else if(expressionArray.value[1] === "-"){
                answer.value = Number(expressionArray.value[0]) - Number(expressionArray.value[2])
                if(answer.value.toString().length > 14){
                    if(answer.value.toFixed(2).toString().length > 14){
                        screenValue.value = "Too Big!"
                        answer.value = "Too Big!"
                    } else{
                        answer.value = answer.value.toFixed(2)
                        expressionArray.value = [answer.value, operator]
                    }
                } else{
                    expressionArray.value = [answer.value, operator]
                }
            } else if(expressionArray.value[1] === "*"){
                answer.value = Number(expressionArray.value[0]) * Number(expressionArray.value[2])
                if(answer.value.toString().length > 14){
                    if(answer.value.toFixed(2).toString().length > 14){
                        screenValue.value = "Too Big!"
                        answer.value = "Too Big!"
                    } else{
                        answer.value = answer.value.toFixed(2)
                        expressionArray.value = [answer.value, operator]
                    }
                } else{
                    expressionArray.value = [answer.value, operator]
                }
            } else if(expressionArray.value[1] === "/"){
                answer.value = Number(expressionArray.value[0]) / Number(expressionArray.value[2])
                if(answer.value.toString().length > 14){
                    if(answer.value.toFixed(2).toString().length > 14){
                        screenValue.value = "Too Big!"
                        answer.value = "Too Big!"
                    } else{
                        answer.value = answer.value.toFixed(2)
                        expressionArray.value = [answer.value, operator]
                    }
                } else{
                    expressionArray.value = [answer.value, operator]
                }
            }
        } else{
            expressionArray.value.push(operator)

        }     
    }    
}

const TGEqualizer = () => {
    if(screenValue.value && expressionArray.value.length === 2 && screenValue.value !== 'Too Big!'){
        expressionArray.value.push(screenValue.value)
        screenValue.value = null
        number.value = []
        if(expressionArray.value[1] === "+"){
            answer.value = Number(expressionArray.value[0]) + Number(expressionArray.value[2])
            if(answer.value.toString().length > 14){
                if(answer.value.toFixed(2).toString().length > 14){
                    screenValue.value = 'Too Big!'
                    answer.value = 'Too Big!'
                } else{
                    answer.value = answer.value.toFixed(2)
                    screenValue.value = answer.value
                    number.value = answer.value.toString().split("")
                    expressionArray.value = []
                }
            } else{
                screenValue.value = answer.value
                number.value = answer.value.toString().split("")
                expressionArray.value = []
            }
        } else if(expressionArray.value[1] === "-"){
            answer.value = Number(expressionArray.value[0]) - Number(expressionArray.value[2])
            if(answer.value.toString().length > 14){
                if(answer.value.toFixed(2).toString().length > 14){
                    screenValue.value = 'Too Big!'
                    answer.value = 'Too Big!'
                } else{
                    answer.value = answer.value.toFixed(2)
                    screenValue.value = answer.value
                    number.value = answer.value.toString().split("")
                    expressionArray.value = []
                }
            } else{
                screenValue.value = answer.value
                number.value = answer.value.toString().split("")
                expressionArray.value = []
            }
        } else if(expressionArray.value[1] === "*"){
            answer.value = Number(expressionArray.value[0]) * Number(expressionArray.value[2])
            if(answer.value.toString().length > 14){
                if(answer.value.toFixed(2).toString().length > 14){
                    screenValue.value = 'Too Big!'
                    answer.value = 'Too Big!'
                } else{
                    answer.value = answer.value.toFixed(2)
                    screenValue.value = answer.value
                    number.value = answer.value.toString().split("")
                    expressionArray.value = []
                }
            } else{
                screenValue.value = answer.value
                number.value = answer.value.toString().split("")
                expressionArray.value = []
            }
        } else if(expressionArray.value[1] === "/"){
            answer.value = Number(expressionArray.value[0]) / Number(expressionArray.value[2])
            if(answer.value.toString().length > 14){
                if(answer.value.toFixed(2).toString().length > 14){
                    screenValue.value = 'Too Big!'
                    answer.value = 'Too Big!'
                } else{
                    answer.value = answer.value.toFixed(2)
                    screenValue.value = answer.value
                    number.value = answer.value.toString().split("")
                    expressionArray.value = []
                }
            } else{
                screenValue.value = answer.value
                number.value = answer.value.toString().split("")
                expressionArray.value = []
            }
        }
    }

}

const theUltraRich = () => {
    if(screenValue.value !== 'Too Big!'){
        screenValue.value = Number(screenValue.value) * .01 
        if(screenValue.value.toString().length > 14){
            screenValue.value = "Too Big!"
            answer.value = "Too Big!" 
        }
    }
}

const clear = () => {
    screenValue.value = 0
    number.value = []
    answer.value = null
    expressionArray.value = []
}
</script>