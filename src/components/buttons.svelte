<button
        on:click={ e => clicked(index) } >
    { buttonText }
</button>


<script lang="ts">
    import { createEventDispatcher } from 'svelte' ;
    const dispatcher = createEventDispatcher() ;
    export let buttonText: string = '' ;
    export let selection: number ;
    export let index: number ;
    function clicked(index: number) {
        dispatcher('selection', index) ;
    }
</script>

