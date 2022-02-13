<template>
  <q-page class='flex flex-center' padding>
    <div class="register">
      <h4 class="text-center q-my-xs">Sing Up</h4>
      <form action class="form" @submit.prevent="register">
        <label class="form-label" for="#n_completo">Nombre Completo:</label>
        <input
          v-model="n_completo"
          class="form-input"
          type="n_completo"
          id="n_completo"
          required
          placeholder="Nombre Completo"
        />
        <label class="form-label" for="#dni">DNI:</label>
        <input
          v-model="dni"
          class="form-input"
          type="dni"
          id="dni"
          required
          placeholder="DNI"
        />
        <label class="form-label" for="#user_name">Usuario:</label>
        <input
          v-model="user_name"
          class="form-input"
          type="user_name"
          id="user_name"
          required
          placeholder="Usuario"
        />
        <label class="form-label" for="#contraseña"
          >Contraeña:</label
        >
        <input
          v-model="contraseña"
          class="form-input"
          type="contraseña"
          id="contraseña"
          placeholder="Contraseña"
        />
        <input class="form-submit" type="submit" value="Sign Up" />
      </form>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'Register',
  data: () => ({
    n_completo: '',
    dni: '',
    user_name: '',
    contraeña: ''
  }),
  methods: {
    register () {
      console.log(this.n_completo)
      console.log(this.dni)
      console.log(this.user_name)
      console.log(this.contraeña)
    }
  }
}
</script>

<style lang="scss" scoped>
.register {
  padding: 2rem;
}
.title {
  text-align: center;
}
.form {
  margin: 3rem auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 20%;
  min-width: 350px;
  max-width: 100%;
  background: rgba(19, 35, 47, 0.9);
  border-radius: 5px;
  padding: 40px;
  box-shadow: 0 4px 10px 4px rgba(0, 0, 0, 0.3);
}
.form-label {
  margin-top: 2rem;
  color: white;
  margin-bottom: 0.5rem;
  &:first-of-type {
    margin-top: 0rem;
  }
}
.form-input {
  padding: 10px 15px;
  background: none;
  background-image: none;
  border: 1px solid white;
  color: white;
  &:focus {
    outline: 0;
    border-color: #1ab188;
  }
}
.form-submit {
  background: #1ab188;
  border: none;
  color: white;
  margin-top: 3rem;
  padding: 1rem 0;
  cursor: pointer;
  &:hover {
    background: #0b9185;
  }
}
.error {
  margin: 1rem 0 0;
  color: #ff4a96;
}
</style>
