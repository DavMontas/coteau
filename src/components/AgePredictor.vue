<template>
  <div id="container">
          <ion-item>
            <ion-label>Escribe un nombre</ion-label>
            <input v-model="nombrePersona" />
            <ion-button expand="full" @click="getAge">Enviar</ion-button>
        </ion-item>

        <div class="card">
                <div class="container">
                    <h4>
                        <b>{{nombrePersona}}</b>
                    </h4>
                    <div v-if="age">
                    <p>{{age}}, es una persona {{ etapa }}</p>
                    <img :src="img" >
                    </div>


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
            age: '',
            etapa:'',
            img: '',
        }
    },
    methods:{

        async getAge(){
            // eslint-disable-next-line no-undef
            console.log(this.nombrePersona)
            await axios
                    // eslint-disable-next-line no-undef
                
                    .get(`https://api.agify.io/?name=${this.nombrePersona}`)
                    .then((data) => this.age = data.data.age);

            if(this.age <= 26 ){
                this.etapa='joven'
                this.img = 'https://www.ouinolanguages.com/thumb/Spanish/vocab/50/images/pic9.jpg'
            }
            else if(this.age > 26 && this.age < 60){
                this.etapa='adulta'
                this.img = 'https://terapygo.com/wp-content/uploads/2019/06/depresi%C3%B3ngeritatrica.jpg'
            } 
            else if(this.age >= 60){
                this.etapa='vieja'
                this.img = 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsr_tpkMrv6pZ_R95CEDg_BNhryhPPAgYFEw&usqp=CAU'
            } 

        },
    }

}
</script>

<style>
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