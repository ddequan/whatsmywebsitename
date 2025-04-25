<script lang="ts">
    import { currentUser, pb } from "$lib/pocketbase";
    import { onMount } from "svelte";
    import { goto } from "$app/navigation";

    onMount(() => {
        pb.authStore.clear();
        goto("/login");
    });
</script>
