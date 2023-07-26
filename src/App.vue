
<script setup>

// Variable reactiva
import { ref} from 'vue'

const registro = ref({
  nombre: '',
  apellido: '',
  genero: '',
  edad: '',
  email: '',
  password: '',
  opciones: [],
  administrador: false,
  observaciones: '',
  grupo: ''
})

const guardar = (e) => {
  e.preventDefault();
  console.log(registro.value);
  cambio.value=false
}

const restablecer = (e) =>{
  e.preventDefault();
  //Limpiar los campos
  nombre.value = '';
  apellido.value = '';
  genero.value = '';
  edad.value = '';
  email.value = '';
  password.value = '';
  opciones.value = [];
  administrador.value = false;
  observaciones.value = '';
  grupo.value = '';
}


let cambio = ref(true)
</script>

<template>
  <div v-if="cambio">
    
    <form >
  <h2>Registro</h2>
    <label for="nombre">
      Nombre:
      <input type="text" id="nombre" v-model="registro.nombre">
    </label>
    <br>
    <label for="apellido">
      Apellido:
      <input type="text" id="apellido" v-model="registro.apellido">
    </label>
    <br>
    <label>
      <strong>Género:</strong>
      <br>
      <label for="g-masculino">Masculino<input type="radio" id="g-masculino" name="genero" value="m" v-model="registro.genero"></label>
      <label for="g-femenino">Femenino<input type="radio" id="g-femenino" name="genero" value="f" v-model="registro.genero"></label>
    </label>
    <br>
    <label for="edad">
      Edad
      <input type="number" id="edad" max="100" min="16" v-model="registro.edad">
    </label>
    <br>
    <label for="email">
      Correo:
      <input type="email" id="email" v-model="registro.email">
    </label>
    <br>
    <label for="password">
      Contraseña:
      <input type="password" id="password" v-model="registro.password">
    </label>
    <br>
    <label>
      Conocimientos
    </label>
    <br>
    <label for="HTML">HTML <input type="checkbox" id="HTML" v-model="registro.opciones" value="HTML"></label>
    <label for="HTML">CSS <input type="checkbox" id="CSS" v-model="registro.opciones" value="CSS"></label>
    <label for="HTML">javascript <input type="checkbox" id="javascript" v-model="registro.opciones" value="javascript"></label>
    <br>
    <label for="administrador"></label>
    <input type="checkbox" v-model="registro.administrador">
    ¿Usuario administrador?
    <br>
    <label for="observaciones"><strong>Comentario:</strong></label>
    <br>
    <textarea name="observaciones" id="observaciones" cols="30" rows="10" v-model="registro.observaciones"></textarea>
    <br>
    <label for="grupo">
      grupo
      <select name="grupo" id="grupo" v-model="registro.grupo">
        <option value="0" selected>...</option>
        <optgroup label="seccion 1">
          <option value="1-1">1</option>
          <option value="1-2">2</option>
          <option value="1-3">3</option>
          <option value="1-4">4</option>
        </optgroup>
        <optgroup label="seccion 2">
          <option value="2-1">1</option>
          <option value="2-2">2</option>
          <option value="2-3">3</option>
          <option value="2-4">4</option>
        </optgroup>
      </select>
    </label>
    <br>
    <button @click="guardar" class="btnGuardar">Guardar</button>
    <button @click="restablecer" class="btnRestablecer">Restablecer</button>
    <br>
    <div class="divYa">
    <a href="" class="yaCuenta">Ya tengo cuenta</a>
  </div>
  </form>
  </div>

  <div v-else>
    <form >
      <h2>Log in</h2>
      <label for="email">
      Correo:
      <input type="email" id="email" v-model="registro.email">
    </label>
    <br>
    <label for="password">
      Contraseña:
      <input type="password" id="password" v-model="registro.password">
    </label>
    <br>
    <button @click="guardar" class="btnGuardar">Guardar</button>
    <button @click="restablecer" class="btnRestablecer">Restablecer</button>
    </form>
  </div>

  <div v-else>
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Exercitationem nisi, omnis voluptatum a eligendi eos ullam? Architecto quidem quo possimus? Soluta similique commodi ea voluptatem. Eius mollitia magni quisquam totam?</p>
  </div>
</template>

<style>

h2{
  padding-top: 20px;
  color: rgb(24, 59, 59);
}

div{
  margin: 30px;
  align-items: center;
  align-content: center;
}

label{
  padding: 10px;
}

input{
  border-radius: 10px;
}

button{
  margin: 10px;
}

form{
  text-align: center;
  background-color: antiquewhite;
  border-radius: 10px;
}

.btnGuardar{
  background-color: rgb(122, 57, 4);
  color: aliceblue;
  border: 0;  
  border-radius: 5px;
  height: 40px;
  width: 100px;
  text-align: center;

}

.btnRestablecer{
  background-color: rgb(236, 221, 14);
  color: black;
  border: 0;  
  border-radius: 5px;
  height: 40px;
  width: 100px;
  text-align: center;
}

.divYa{
  padding: 10px;
  padding-bottom: 30px;
}




</style>


