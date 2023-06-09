<script>

</script>

<template>
    <nav class="navbar">
        <div class="container">
            <a class="logo" href="#">
                <img id="logo" src="../assets/logo.png" alt="" srcset="">
                Портфолие на Vue
            </a>
            <div class="text">
                Андреев Алексей
            </div>
        </div>
    </nav>
</template>

<style scoped>
    .navbar {
        background-color: lightgray;
    }
    .navbar #logo {
        width: 30px;
    }

    .navbar .logo {
        display: flex;
        gap: 10px;
        align-items: center;
    }
</style>
