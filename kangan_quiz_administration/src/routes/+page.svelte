<script>
  import Login from "./Login.svelte";
  import QuizManager from "./QuizManager.svelte";
  let login = false;

  function setLogin(event) {
    console.log(event.detail);
    login = event.detail.login;
  }

</script>

<div>
  {#if !login}
   <Login on:loginEvent={setLogin} />

  {:else}

    <QuizManager />
  {/if}
</div>

  