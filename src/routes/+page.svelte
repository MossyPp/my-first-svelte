<script lang="ts">
    import Calculator from "$lib/components/Calculator.svelte";
	import Counter from "$lib/components/Counter.svelte";
    import Sidebar from "$lib/components/Sidebar.svelte";
	import value from "$lib/components/Counter.svelte"

	let onDoorCounters:any = [
		{Name:"Non-Member", isBounded:false},
		{Name:"Member", isBounded:false},
		{Name:"Free", isBounded:false},
		{Name:"Society", isBounded:true, upperBound:4},




	]

	let preBoughtCounters:any = [
		{Name:"Non-Member", isBounded:true, upperBound:22},
		{Name:"Member", isBounded:true, upperBound:22},
		{Name:"Free", isBounded:true, upperBound:22},
	]

</script>

	<button on:click={ () => {console.log(value)}}>Click</button>
	<div class="pt-2 flex flex-nowrap gap-2 justify-between">
	<div class="flex flex-wrap gap-2 justify-between">
		<div class="border rounded-lg p-2 border-red-600">
		<p class="text-white">On the Door Sales</p>
		<div class="flex flex-wrap gap-2 justify-between">
		{#each onDoorCounters as {Name, isBounded, upperBound }}
		{#if isBounded == true}
		<Counter isBounded={true} {upperBound}>{Name}</Counter>
		{:else}
		<Counter>{Name}</Counter>
		{/if}
		{/each}
		</div>
		</div>
		<div class="border rounded-lg p-2 border-green-600">
		<p class="text-white">Online Sales</p>
		<div class="flex flex-wrap gap-2 justify-between">
		{#each preBoughtCounters as {Name, isBounded, upperBound }}
		{#if isBounded == true}
		<Counter isBounded={true} {upperBound}>{Name}</Counter>
		{:else}
		<Counter>{Name}</Counter>
		{/if}
		{/each}
		</div>
		</div>
	</div>
	<div class="gap-2">
		<Sidebar/>
	</div>
	</div>
