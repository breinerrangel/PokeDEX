<template>
    <cargra v-if="login" />


    <div class="box" v-else>




        <h1 class="titulo">
            PokeDEx
        </h1>
        <div class="buscador">
            <form action="" @submit.prevent="buscar">

                <input type="text" placeholder="buscar pokemon" v-model="encontrar">
            </form>

        </div>
        <div class="padre">
            <div class="card2" v-for="item in lista">

                <card :nombre="item.name" :key="item.name" :url="item.sprites.other.dream_world.front_default" />

            </div>
        </div>
        <div class="buton">
            <button v-if="resta" @click="restarr">
                antras</button>

            <button @click="sumar">adelante</button>

        </div>




    </div>
</template>
<script>

export default {
    name: "pokemon",
    data() {
        return {
            lista: [],

            /*  {
                 nombre:"hola",
                 url:"sadasdsa"
             }
             ,{
                 nombre:"sadsad",
                 url:"ddad"
             } */


            encontrar: "",
            login: true,
            contador: 1,
            resta: false,







        }





    },
    mounted() {
        this.getIfo()
        this.buscar()




    },
    methods: {
        async getIfo() {
            console.log(this.contador)
            try {
                if (this.contador == 1) {
                    this.resta = false
                    this.lista = []
                    for (let i = 1; i < 20; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)
                        console.log(this.lista)


                    }

                }








                else if (this.contador == 2) {

                    this.lista = []
                    this.resta = true
                    for (let i = 20; i < 40; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)

                    }


                }
                else if (this.contador == 3) {
                    this.lista = []
                    this.resta = true
                    for (let i = 40; i < 60; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)

                    }


                }
                else if (this.contador == 4) {

                    this.lista = []
                    this.resta = true
                    for (let i = 60; i < 80; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)

                    }


                }
                else if (this.contador == 5) {

                    this.lista = []
                    this.resta = true
                    for (let i = 80; i < 100; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)

                    }


                }
                else if (this.contador == 6) {

                    this.lista = []
                    this.resta = true
                    for (let i = 100; i < 120; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)

                    }


                }
                else if (this.contador == 7) {

                    this.lista = []
                    this.resta = true
                    for (let i = 120; i < 150; i++) {
                        const { data } = await this.$axios.get(`pokemon/${i}`)
                        this.lista.push(data)

                    }


                }





                this.login = false





            } catch (error) {


            }

        },
        sumar() {
            this.contador++
            this.getIfo()

        },
        restarr() {
            this.contador--
            this.getIfo()
        },
        buscar() {
            for (let i = 0; i < this.lista.length; i++) {
                if (this.lista[i].name == this.encontrar) {
                    this.$router.push(`/${this.encontrar}`)
                }
            }

        },










    }

}


</script>
<style>
.titulo {

    width: 95%;
    background-color: white;
    font-size: 50px;
    font-weight: bold;
    text-align: center;
    margin: auto;
    height: 90px;

}

.buscador {

    width: 250px;
    height: 30px;
    margin-top: 10px;
    margin-left: 10px;


}

.box {


    height: auto;
    width: 100%;



}

.card {
    background-color: darkmagenta;
    width: 300px;
    height: 350px;
    margin-left: 10px;
    display: flex;
    flex-direction: column;
    cursor: pointer;
    animation: pokemon 2s linear infinite;
    border: 5px solid;
    border-color: floralwhite;

}

@keyframes pokemon {
    0% {
        background-color: blueviolet;
    }

    50% {
        background-color: chartreuse;
    }

    75% {
        background-color: darkorange;
    }

    100% {
        background-color: blueviolet;
    }

}

.card h3 {

    height: 30px;
    width: 100%;
    text-align: center;

}

.card div {

    width: 100%;
    height: 85%;

}

.card div img {

    height: 270px;
    width: 100%;
}

.card p {


    color: white;
    height: 15%;
    width: 100%;
    text-align: center;
    font-size: 24px;


}

.padre {
    display: flex;

    gap: 10px;
    flex-wrap: wrap;

}

.card2 {
    display: flex;
    margin-left: 30px;



}

@media all and (max-width: 1360px) {
    .padre {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;

    }


}

.buton {
    display: flex;
    justify-content: center;
    align-items: center;
    justify-content: space-around;
    gap: 100px;
    margin-top: 10px;

}

.buton button {
    padding: 12px;
    background-color: black;
    color: white;
    border-radius: 15px;

}
</style>