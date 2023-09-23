<template>
  <div class="container">
    <nav class="navbar navbar-light bg-light">
      <form class="form-inline">
        <input class="form-control" type="text" placeholder="Search" v-model="dataShared.searchText"
        />
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        <button type="button" class="btn btn-danger">RESET</button>
      </form>
    </nav>
    
  </div>
</template>

<script>
import dataShared from "../../shared/dataShared"

export default {
  name: "SearchArea",
  data() {
    return {
      dataShared
      // Da qui passo i dati all'observable dataShared che utilizzo come posto condiviso per immagazzinare le info dell'oggetto
      //(avrei anche potutti salvarli in una variabile qui. Ma in qesto modo e' piu' semplice prendere i dati anche da altri componenti senza il problema delle parentele)
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../../assets/style/mixins.scss";

.container {
  width: 100%;
  display: flex;
  @include flex_center;

  margin: 30px;

  input {
    width: 200px;
    display: inline;
    margin-right: 30px;
  }

  button {
    margin: 5px;
  }
}
</style>