<script lang="ts">
    import { currentUser, pb } from "$lib/pocketbase";
</script>

{#if $currentUser}

<p>signed in as {$currentUser.name}</p>

{:else}

<form class= "flex flex-col items-center justify-center align-center h-screen text-xl gap-1"> 
    
    <input placeholder="Username" type="text" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white bg-blue-500" required minlength="5" maxlength="25"/>   

    <input placeholder="Password" type="password" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white" required minlength="8"/>

    <button class= "rounded-lg py-1.5 w-40 dark:bg-black/30 text-white transition delay-5 duration-300 ease-in-out hover:scale-105 hover:bg-blue-600/75" type="submit">Login</button> 

    <div class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white">
        <p class= "p-2 text-sm text-white"> Don't have an account?
            <a href="/register" class="text-lg text-indigo-400 font-medium hover:underline transition-all duration-150">Register now</a>
          </p>
        </div>
      
</form>

{/if}