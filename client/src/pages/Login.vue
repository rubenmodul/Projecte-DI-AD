<template>
  <q-page class='flex flex-center' padding>
    <div class="login">
      <h5 class="text-center q-my-xs">Login in the page</h5>
      <form action class="q-my-xs form">
        <label class="form-label" for="#username">Username:</label>
        <input
          class="form-input"
          type="username"
          id="username"
          required
          placeholder="username"
        />
        <label class="form-label" for="#password">Password:</label>
        <input
          class="form-input"
          type="password"
          id="password"
          placeholder="Password"
        />
        <input class="form-submit" type="submit" value="Login" />
        <p class="msg"> Crear cuenta
          <a href="http://localhost:8080/#/register">Registrate</a>
        </p>
      </form>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'Login'
}
</script>

<style lang="scss" scoped>
.login {
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
  box-shadow: 0 4px 10px 4px rgba(255, 255, 255, 0.3);
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
    border-color: #ffffff;
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
</style>
