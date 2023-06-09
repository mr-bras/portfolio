
<script>
export default {
    data() {
        return {
            up: '',
            down: '',
            image: "src/assets/meme-default.jpg"
        }
    }
}

</script>


<template>
    <div class="mem-gen">
        <div class="meme">
            <p class="top-text">
                {{ up }}
            </p>
            <p class="bottom-text">
                {{ down }}
            </p>
            <img :src="image">
        </div>
        
        <hr>
        
        <div class="input-group mb-3">
            <span class="input-group-text">Верхняя надпись</span>
            <textarea v-model="up" class="form-control"></textarea>
        </div>

        <div class="input-group mb-3">
            <span class="input-group-text">Нижняя надпись</span>
            <textarea v-model="down" class="form-control"></textarea>
        </div>


        <div class="input-group mb-3">
            <span class="input-group-text">Изображение</span>
            <textarea v-model="image" class="form-control"></textarea>
        </div>
    </div>
</template>

<style>

.mem-gen img {
    max-width: 500px;
    width: 100%;
    height: auto;
}

.mem-gen .meme {
    position: relative;
    text-align: center;
}

.mem-gen span {
    width: 150px;
}

.top-text,
.bottom-text {
    position: absolute;
    width: 100%;
    text-align: center;
    color: #ffffff;
    font-family: 'Arial', sans-serif;
    font-size: 30px;
    font-weight: 700;
    margin: 0;
    text-shadow:
        0 -2px 0 #000000,
        0 2px 0 #000000,
        -2px -0 0 #000000,
        2px -0 0 #000000,
        -2px 0 0 #000000,
        2px 0 0 #000000,
        -1px -2px 0 #000000,
        1px -2px 0 #000000,
        -1px 2px 0 #000000,
        1px 2px 0 #000000,
        -2px -1px 0 #000000,
        2px -1px 0 #000000,
        -2px 1px 0 #000000,
        2px 1px 0 #000000,
        -2px -2px 0 #000000,
        2px -2px 0 #000000,
        -2px 2px 0 #000000,
        2px 2px 0 #000000;
}

.top-text {
    top: 20px;
}

.bottom-text {
    bottom: 20px;
}

hr {
    margin: 40px auto;
    width: 50%;
    height: 8px;
    background-color: #41b883;
    border: 0;
    border-top: 3px solid #35495e;
}
</style>