<template>
    <div class="super-box">
        <h1>
            {{ habilidades.name }}
        </h1>
        <div class="contenedor">
            <div class="img">
                <img :src="url" alt="" width="270px" style="margin-left: 80px;">
                
            </div>
            <div class="habilidades">
                <div class="se" >
                    <div class="habi">
                        <h2>abilities</h2>
                <p v-for="item in habilidades.abilities" :key="item.name"  >
                    {{ item.ability.name }}
                </p>
                    </div>
                    <div class=estadi>
                        <h2>stats</h2>
                <p v-for="item in habilidades.stats" :key="item.name"  >
                    {{ item.stat.name }}: {{ item.base_stat }}
                </p>
                    </div>
                
                
                </div>

            </div>
        </div>
        <div class="otras-v"   >
            <h2>picture</h2>
            <div class="imageness">
            <img :src="sprites.back_default" alt="" >
            <img :src="sprites.back_female" alt="">
            <img :src="sprites.back_shiny" alt="">
            <img :src="sprites.back_shiny_female" alt="">
            <img :src="sprites.front_default" alt="">
            <img :src="sprites.front_female" alt="">
            <img :src="sprites.front_shiny" alt="">
            <img :src="sprites.ront_shiny_female" alt="">
            </div>
            
           

        </div>
    </div>
</template>
<script>
export default{
    


    

    
    
    mounted() {
        console.log(this.$route)
    
        
        
        
    },
    data() {
        return {
            habilidades:[],
            sprites:[]
            
            
            
            
            

            
        }
    },
    mounted(){
        this.gethabi()
    },
    methods: {
        async gethabi(){
            const {data}= await this.$axios.get(`https://pokeapi.co/api/v2/pokemon/${this.$route.params.habi}`)
            this.habilidades=(data)
            this.url=this.habilidades.sprites.other.dream_world.front_default,
            this.sprites=this.habilidades.sprites
            
            console.log(this.habilidades) 
            console.log(this.sprites)

            },
            
           
        },
        
    
    
           
        
}
</script>
<style>
.super-box{
    height: auto;
    width: 100%;
    background-image: url("https://images4.alphacoders.com/941/941902.png");
    background-position: center;
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
}

.imageness{
    display: flex;
    justify-content: center;
    align-items: center;
}
.super-box h1{
    margin: auto;
    width: 70%;
    height: 90px;
    font-size: 45px;
    background-color: crimson;
    color: white;
    
    text-align: center;

}
.contenedor{
    width: 100%;
    height: 300px;
    display: flex;
    
    margin-top: 10px;
    

}
.img{
    width: 30%;
   
}
.habilidades{
    border: 5px;
    border-style:dotted;
    border-radius: 15px;
    width: 70%;
 
    padding-left: 30px;
  
    color: white;
    background-color: rgba(0, 0, 0, 0.356);
    
    

}
.habilidades p{
    font-size: 25px;
    color: azure;
    
   

}
.habilidades h2{
    font-size: 40px;
    color: red;
   
}
.img{
   
    width: 30%;
    height: 100%;
}
.se{
    display: flex;
    
}
.se p{
    
    
}
.otras-v h2{
    text-align: center;
    background-color: crimson;
    width: 60%;
    margin: auto;
    height: 90px;
    font-size: 50px;
}
.otras-v{
   
    width: 100%;
    height: 500px;
   
    display: flex;
    flex-direction: column;

    gap: 30px;

    
   
}
.otras-v img{
    height: 250px;

}
.habi{
  
    width: 30%;
}
.estadi{
    width: 70%;
    

}
.estadi p{
    color: white;
}
.estadi h2{
    font-size: 30px;
    color: red;
   
}


</style>