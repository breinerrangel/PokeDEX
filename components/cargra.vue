<template>
    


        <div class="loading first">
            <div class="loading second">
                <div class="loading third"></div>
            </div>
        </div>
    
</template>
<style>
*,
*::before,
*::after {
    box-sizing: border-box;
}

body {
    margin: 0;
    background-color: #fafafa;
    background-image: url("https://images6.alphacoders.com/114/1140114.jpg");
    background-position: center;
    background-attachment: fixed;
    background-size: cover;
    background-repeat: no-repeat;

}

@keyframes loading {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(360deg);
    }
}

.loading {
    position: absolute;
    top: 50%;
    left: 50%;
    border: 5px solid #fff;
    border-radius: 100%;


}

.first {
    margin: -30px 0 0 -30px;
    height: 60px;
    width: 60px;
    border-top-color: #fbe9ea;
    animation: loading 3s infinite linear;

}

.second {
    margin: -20px 0 0 -20px;
    height: 40px;
    width: 40px;
    border-top-color: #e16971;
    animation: loading 2s infinite linear;
}

.third {
    margin: -10px 0 0 -10px;
    height: 20px;
    width: 20px;
    border-top-color: #941e25;
    animation: loading 1s infinite linear;
}
</style>