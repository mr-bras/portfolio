<script>
export default {
    data() {
        return {
            username: '',
            password: '',
            isError: false,
            isLoggedIn: false,
            image: 'src/assets/hide.png',
            index: 0,
            type: 'password'
        };
    },
    methods: {
        login() {
            if (this.username == 'admin' && this.password == '1234') {
                this.isLoggedIn = true;
                this.isError = false
            } else {
                this.isError = true
            }
        },
        switc() {
            if (this.type == 'password') {
                this.type = 'text';
                this.image = 'src/assets/show.png'
            }
            else if (this.type == 'text') {
                this.type = 'password';
                this.image = 'src/assets/hide.png'
            }
        }
    }
}
</script>

<template>
    <div class="login-form">
        <div class="card">
            <div class="card-body">
                <div v-if="!isLoggedIn">
                    <div class="mb-3">
                        <label for="username" class="form-label">Логин</label>
                        <input v-model="username" type="text" class="form-control" id="username" autocomplete="off">
                    </div>
                    <div class="mb-3 password-input">
                        <label for="password" class="form-label">Пароль</label>
                        <div class="input-group">
                        <input v-model="password" :type="type" class="form-control" id="password" autocomplete="off">
                        <button class="btn btn-outline-secondary" @click="switc">
                            <img :src="image">
                        </button>
                    </div>
                    </div>
                    <div class="mb-3">
                        <button @click="login" class="btn btn-primary">
                            Войти
                        </button>
                    </div>
                    <div v-if="isError" class="alert alert-danger" role="alert">
                        Неправильные данные, попробуйте ещё раз.
                    </div>
                </div>

                <div v-if="isLoggedIn" class="alert alert-success" role="alert">
                    Добро пожаловать, пользователь!
                </div>
            </div>
        </div>

    </div>
</template>
<style scoped>
.password-input img {
    height: 24px;
}
</style>
