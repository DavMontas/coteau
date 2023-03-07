<template>
    <div id="container">
        <ion-item>
            <ion-label>Escribe el nombre un pais</ion-label>
            <input v-model="country" />
            <ion-button expand="full" @click="getUni">Enviar</ion-button>
        </ion-item>

                    <table>
                        <tr>
                            <th>
                                Nombre
                            </th>
                            <th>Dominio</th>
                            <th>Pagina web</th>

                        </tr>
                        <tr v-for="item in universidades" :key="item">
                            <td >{{ item.name }}</td>
                            <td>{{ item.domains }}</td>
                            <td>{{ item.web_pages }}</td>

                        </tr>

                    </table>
    </div>
</template>

<script>
import axios from 'axios'
export default {

    data(){
        return{
            country :'',
            universidades: [],
        }
    },
    methods:{

        async getUni(){
            // eslint-disable-next-line no-undef
            console.log(this.country)
            await axios
                    // eslint-disable-next-line no-undef
                    .get(`http://universities.hipolabs.com/search?country=${this.country}`)
                    .then((data) => {
                        data.data.forEach( item => {
                            console.log(item);
                            this.universidades.push(item)
                        })
                    });

           console.log(this.universidades);
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

table {
    margin: 0 auto;
}

table, th, td {
  border: 1px solid;
  padding: 10px;
}
</style>