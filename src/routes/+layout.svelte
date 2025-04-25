<script lang="ts">
  import '../app.css';        // relative path up to project-root/app.css
  let { children } = $props();
</script>

{@render children()}

