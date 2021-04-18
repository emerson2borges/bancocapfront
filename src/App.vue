<template>
  <div class="" id="app"></div>
    <div class='container grid-xs py-2'>
      <img class="img-responsive img-logo" src="@/assets/banco.png" alt="imagem banco">
      <form @submit.prevent="sacar(asacar)">
        <div class="input-group">
          <input type="number" v-model="asacar" class="form-input" placeholder="Valor a sacar">
          <button class="btn- btn-primary input-group-btn">SACAR</button>
        </div>
      </form>
      <br />
      <form @submit.prevent="depositar(adepositar)">
        <div class="input-group flex-centered">
          <input type="number" v-model="adepositar" class="form-input" placeholder="Valor a depositar">
          <button class="btn- btn-primary input-group-btn">DEPOSITAR</button>
        </div>
      </form>
      <div>
        <br />
        <p>
          <label>Seu saldo é de: R$ </label><label>{{ saldo }}</label>
        </p>
      </div>
    </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return { saldo: 200, asacar: 0, adepositar: 0 }
  },
  methods: {
    depositar(valor) {
      this.saldo = this.saldo + parseInt(valor);
      this.adepositar.valueOf='0';
    },
    sacar(valor) {
      if(this.saldo > parseInt(valor)) {
        this.saldo -= parseInt(valor);
      } else {
        alert('Saque não realizado.')
      }
    }
  }
}
</script>

<style scoped>
.img.logo {
  max-width: 200px;
  margin: 0 auto;
  align-content: center;
}
</style>

