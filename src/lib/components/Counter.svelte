<script lang="ts">
    import { writable } from 'svelte/store';
    export let isBounded:boolean = false;
    export let upperBound:number = 288
    let value = writable(0)
    function increment() {
        if ($value!=upperBound){
            $value +=1;}
    }   

    function decrement() {
        if ($value!=0){
            $value -=1;}
    }


</script>
    <div id="counter" class="bg-[rgb(2,2,6)] max-w-[300px] overflow-hidden rounded-[15px] gap-2">
        <div class="flex justify-center text-white bg-gray-700">
            <p class="gap-1 p-[25px] text-[2rem] text-white font-mono w-fit "> <slot/> </p>
        </div>

        <div id="keys" class="flex gap-2.5 p-[25px]">
            <button on:click={() => decrement()} class="text-[4rem] text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[160px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)];]">-</button>
        {#if isBounded == false}
            <input id="display" readonly value={$value} class="text-center w-full text-[4rem] text-center bg-[rgb(60,60,62)] text-[azure] p-5 border-[none] rounded-[50px]">
        {:else}
            <input id="display" readonly value="{$value} / {upperBound}" class="text-center w-full text-[2rem] text-left bg-[rgb(60,60,62)] text-[azure] p-5 border-[none] rounded-[50px]">
        {/if}
            <button on:click={() => increment()} class="text-[5rem] text-[azure] text-4xl font-mono font-[bold] bg-[hsl(148,63%,31%)] w-[100px] h-[160px] rounded-[50px] hover:bg-[hsl(148,63%,45%)] active:bg-[hsl(25,75%,75%)]">+</button>
        </div>
        
    </div>
