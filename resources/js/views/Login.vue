<template>
  <div>
    <br><br>
    <div class="container">
      <div class="row">
        <div class="col-md-4 mx-auto">
          <div class="card shadow rounded">
            <div class="card-body">
              <h5 class="card-title">Acceso</h5>
              <br>
              <p class="alert alert-warning" v-if="error">{{error}}</p>
              <form autocomplete="off" @submit.prevent="login" method="post">
                <input type="email" class="form-control" placeholder="usuario" v-model="email" />
                <br>
                <input type="password" class="form-control" placeholder="clave" v-model="password" />
                <br>
                <button type="submit" class="btn btn-dark">Entrar</button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: null,
      password: null,
      error: null
    };
  },
  methods: {
    login() {
      this.$store
        .dispatch("retrieveToken", {
          email: this.email,
          password: this.password
        })
        .then(response => {
          this.$router.push({ name: "dashboard" });
        })
        .catch(error => {
          this.error = error.response.data;
          this.error = "Credenciales incorrectas"; 
        });
    }
  }
};
</script>

<style>
.col-center{
  float: none;
  margin: auto;
}

body{
  background-color: beige;
}
</style>