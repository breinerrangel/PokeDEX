<template>
    <nuxt-link :to=nombre>
    
        <div class="card" >

            <div class="imagen">
                <img :src="url" alt="dsafdsfasdf">
            </div>
            <p class="name">{{ nombre }}</p>

        </div>
        
    </nuxt-link>
    
</template>
<script>

export default {


    props: {
        url: {

            type: String,
            require: true
        },
        nombre: {
            type: String,
            require: true

        }

    },
    
    
    
   
}


</script>