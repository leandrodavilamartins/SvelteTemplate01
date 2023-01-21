<script>
  import "carbon-components-svelte/css/g100.css";
  import { db } from "./main";
  import Router from "../node_modules/svelte-spa-router";
  import About from "./About.svelte";
  import Help from "./Help.svelte";
  import AddForm from "./AddForm.svelte";
  import Tabela from "./Tabela.svelte";
  export let name;

  console.log(db);
</script>

<main>
  <h1>Hello {name}!</h1>
  <nav>
    <a href="/#/about">About</a>
    <a href="/#/help">Help</a>
    <a href="/#/tabela">Tabela</a>
    <a href="/#/addForm">Adicionar</a>
  </nav>
  <Router
    routes={{
      "/about": About,
      "/help": Help,
      "/tabela": Tabela,
      "/addForm": AddForm,
    }}
  />
  <br />
  <div id="form">
    <slot />
    <!--Here enter the components -->
  </div>
</main>

<style>
  #form {
    display: flex;
    justify-content: left;
    margin-left: 10%;
  }
</style>
