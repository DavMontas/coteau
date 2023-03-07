<template>
  <div id="container">
    <p> <strong> {{ nombre }} </strong>  </p>
    <p> Puede contactarme a : 20211370@itla.edu.do</p>
    <img src="../img/foto.jpeg" alt="">
    
  </div>
</template>


<script>
    export default{
        data(){
            return{
                nombre: 'Davinci Montas',
            }

        },

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

img {
  height: 200px;
  width: 50%;
}
</style>