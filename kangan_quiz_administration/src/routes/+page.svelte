<script>
  import Login from "./Login.svelte";
  import QuizManager from "./QuizManager.svelte";
  let login = false;
  let nav = "login";
  let username ="";

  function handleLogout() {
    // username = null;
    nav = 'login';
  }

  function setLogin(event) {
    console.log(event.detail);
    login = event.detail.login;
  }

  function loginMessageHandler(event) {
    if(event.detail.result) {
      nav = 'quizManager';
      username = event.detail.user;
      console.log(nav);
      return;
    }

    nav = 'login';

  }

</script>

<style>
/*LOG OUT BUTTON*/
.logout-button {
    font-family: 'Roboto', sans-serif;
    background-color: #ffca1b;  
    color: #333;
    padding: 2px 10px;
    cursor: pointer;
    border: none;
    width: 100%; 
    height: 100%;
  }
</style>

<div>
  {#if nav == 'login'}
   <Login on:loginEvent={setLogin} on:loginMessage={loginMessageHandler} />
  {:else if nav == 'quizManager'}
  <button class="logout-button" on:click={handleLogout}>LOG OUT</button>
  <QuizManager username = {username}/>
  {/if}
</div>

  