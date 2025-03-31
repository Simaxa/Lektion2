<script>
    import { goto } from '$app/navigation';
    import Input from '$lib/Input.svelte';
    import Button from '$lib/Button.svelte';
  
    let username = '';
    let password = '';
    let error = '';
  
    function login() {
      if (username === 'admin' && password === '1234') {
        goto('/home');
      } else {
        error = 'Brugernavn eller password er forkert';
      }
    }
  </script>
  
  <Input bind:value={username} placeholder="Brugernavn" />
  <Input bind:value={password} placeholder="Password" />
  <Button onclick={login}>Login</Button>
  
  {#if error}
    <p class="text-red-500 m-2">{error}</p>
  {/if}
  