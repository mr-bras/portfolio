<script>
    export default {
        data() {
            return {
                // текст
                title: 'КотИКо',

                // цвет текста
                fontColor: '#52ff66',
                // цвет фона текста
                bgColor: '#000000',
                // размер текста
                fontSize: 50,
                fontFamily: 'Times New Roman',
                isUpperCase: false 
            }
        }
    }
</script>

<template>
    <div class="text-editor">

        <div class="card">
            <div class="card-body">
                <input type="text" class="form-control mt-3 text-center" v-model="title">
                <input v-model="fontSize" type="range" class="form-control mt-3" min="20" max="100">
                <div class="d-flex">
                    <input v-model="fontColor" type="color" class="form-control mt-3">
                    <input v-model="bgColor" type="color" class="form-control mt-3">
                </div>
                <select v-model="fontFamily" class="form-select mt-3" name="" id="">
                    <option value="Arial">Arial</option>
                    <option value="Times New Roman">Times New Roman</option>
                    <option value="Courier New">Courier New</option>
                </select>
                <div class="form-check mt-3">
                    <input v-model="isUpperCase" type="checkbox" class="form-check-input" id="uppercase">
                    <label for="uppercase">Капслок</label>
                </div>
            </div>
        </div>


        <div class="result-container">
            <p 
            class="result" 
            :class="{
                'uppercase': isUpperCase
            }"
            :style="{
                'font-size': fontSize + 'px',
                'background-color': bgColor,
                'color': fontColor,
                'font-family': fontFamily
            }">
                <span>
                    {{ title }}
                </span>
            </p>
        </div>

    </div>
</template>

<style>
    .text-editor .result {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .text-editor .uppercase {
        text-transform: uppercase;
    }
</style>