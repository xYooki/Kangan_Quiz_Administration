<script>
  import Login from "./Login.svelte";
  import QuizManager from "./QuizManager.svelte";
  let login = false;
  let nav = "quizManager";

  function setLogin(event) {
    console.log(event.detail);
    login = event.detail.login;
  }

  function loginMessageHandler(event) {
    if(event.detail.result) {
      nav = 'quizManager';
      console.log(nav);
      return;
    }

    nav = 'login';

  }

</script>

<div>
  {#if nav == 'login'}
   <Login on:loginEvent={setLogin} on:loginMessage={loginMessageHandler} />
  {:else if nav == 'quizManager'}
    <QuizManager />
  {/if}
</div>

  