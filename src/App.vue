<template>
  <div id="app">
    <div id="contatos">
      <ul>
        <li v-for="contato in contatos">{{contato.nome}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      contatos: []
    }
  },
  mounted: function () {
    var lista = [];
    this.$http.get('http://localhost:3412/contatos').then((response)=>
    {
      this.contatos = response.data
    }, (response) => {
      console.log('error', response)
    }
  );
  }
}
</script>

<style>

</style>
