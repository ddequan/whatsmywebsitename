<script lang="ts">
    import { currentUser, pb } from "$lib/pocketbase";
</script>

{#if $currentUser}

<p>signed in as {$currentUser.name}</p>

{:else}

<form class= "flex flex-col items-center justify-center align-center h-screen text-xl gap-1"> 
    
    <input placeholder="Email" type="email" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white bg-blue-500" required/>

    <input placeholder="Display Name" type="text" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white bg-blue-500" required minlength="3" maxlength="20"/>  
  
    <input placeholder="Username" type="text" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white bg-blue-500" required minlength="5" maxlength="25"/>
    
    <input placeholder="Password" type="password" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white" required minlength="8"/>

    <div class="flex flex-col items-center text-white">

        <!-- svelte-ignore a11y_label_has_associated_control -->

        <label class="text-lg">Birthday</label></div>
    <input placeholder="Birthday" type="date" class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white bg-blue-500" required/>

    <button class= "rounded-lg py-1.5 w-40 dark:bg-black/30 text-white transition delay-5 duration-300 ease-in-out hover:scale-105 hover:bg-blue-600/75" type="submit">Register</button
        >
    <div class="rounded-lg px-2 py-2 text-center w-55 dark:bg-black/30 text-white">
    <p class= "p-2 text-sm text-white"> Already have an account?
        <a href="/login" class="text-lg text-indigo-400 font-medium hover:underline transition-all duration-150">Login now</a>
      </p>
    </div>
        
    <label class="flex justify-between items-start p-2 text-sm text-white">
        <span>
          I have read and agree to EchoSpace's 
          <a href="/termsofservice" class="text-indigo-400 font-medium hover:underline transition-all duration-150">
            Terms of Service
          </a>.
        </span>
        <input type="checkbox" class="ml-2 mt-1 accent-indigo-500" required />
      </label>
      
</form>

{/if}