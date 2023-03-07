<template>
    <div id="container">
        <ion-item>
            <ion-label>Escribe un nombre</ion-label>
            <input v-model="nombrePersona" />
            <ion-button expand="full" @click="getSex">Enviar</ion-button>
        </ion-item>

        <div class="card">
                <div class="container">
                    <h4>
                        <b>{{nombrePersona}}</b>
                    </h4>
                    <p id="color" v-if="sexo" :style="{ color: color}">{{sexo}}</p>


                </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    
    data(){
        return{
            nombrePersona :'',
            sexo: '',
            color:'',
        }
    },
    methods:{

        async getSex(){
            // eslint-disable-next-line no-undef
            console.log(this.nombrePersona)
            await axios
                    // eslint-disable-next-line no-undef
                    .get(`https://api.genderize.io/?name=${this.nombrePersona}`)
                    .then((data) => this.sexo = data.data.gender);

            if(this.sexo === 'male'){
                setTimeout(() => document.getElementById('color').focus(), 50)
                this.color='blue'
            } else if(this.sexo === 'female'){
                this.color = 'pink'
                setTimeout(() => document.getElementById('color').focus(), 50)
            }
        },
    }
    
}
</script>

<style>

#square {
  height: 50px;
  width: 0 50px;
  background-color:white;
}


#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>