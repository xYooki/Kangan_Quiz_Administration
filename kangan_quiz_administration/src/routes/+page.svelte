<script>
  import Login from "./Login.svelte";
  import QuizManager from "./QuizManager.svelte";
  import AddQuestions from './addQuestions.svelte';
  let login = false;

  function setLogin(event) {
    console.log(event.detail);
    login = event.detail.login;
  }

</script>

<AddQuestions />

<div>
  {#if !login}
   <Login on:loginEvent={setLogin} />

  {:else}

    <QuizManager />
  {/if}
</div>

  