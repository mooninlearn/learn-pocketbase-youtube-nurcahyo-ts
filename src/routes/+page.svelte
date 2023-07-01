<script >
  import PocketBase from 'pocketbase';

  const pb = new PocketBase('http://127.0.0.1:8090');
  // (optional) send an email verification request
  let state ={
    email:"",
    password:""
  }

  let status = false

  async function sendlogin() {
    console.log('sendlogin');
    const data = {
      email: state.email,
      password: state.password,
      passwordConfirm: state.password,
    }
    console.log("data", data);

    const user = await pb.collection('users').create(data);

    console.log("user", user);
    // sendemail();
    if (user) {
      sendemail();
      // console.log("sendemail", state.email);
    }
  }

  async function sendemail(){
    await pb.collection('users').requestVerification(state.email);
    console.log("sendemail", state.email);
  }

  //FOR LOGIN NOW
  async function btnlogin(){
    const authData = await pb.collection('users').authWithPassword(state.email, state.password);
    if(authData){
      console.log("success Login")
      status = true
    }
  }

</script>

<div>
  <h1>Register</h1>
  <!-- <form> -->
  email: <input type="text" bind:value={state.email}>
  <br/>
  password: <input type="password" bind:value={state.password}>
  <br/>
  <button
  on:click={sendlogin}
  >Register now</button>
  <!-- </form> -->
  <hr/>


  <h1>Login</h1>
  <!-- <form> -->
  email: <input type="text" bind:value={state.email}>
  <br/>
  password: <input type="password" bind:value={state.password}>
  <br/>
  <button
  on:click={btnlogin}
  >login now</button>
  <!-- </form> -->

  <hr/>
  {#if status == true}
  <h1>You SUCCESS Login</h1>
  {/if}
  {#if status == false}
  <h1>You NOT LOGIN</h1>
  {/if}

</div>