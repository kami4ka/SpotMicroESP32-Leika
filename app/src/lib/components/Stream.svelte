<script lang="ts">
    import { onDestroy } from 'svelte';
    import { location } from '$lib/stores';

    let source = $state(`${$location}/api/camera/stream`);

    onDestroy(() => (source = '#'));
</script>

<div class="w-full h-full">
    <img
        src={source}
        class="absolute object-cover blur-3xl w-full h-full -z-10"
        alt="Live stream is down"
    />
    <img src={source} class="object-contain w-full h-full" alt="Live stream is down" />
</div>
