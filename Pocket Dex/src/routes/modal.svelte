<script>

	/**
	 * @type {{ name: any; types: any; number: any; sprite: any; moves: any; baseExperience: any; }}
	 */
	export let pokemon;
	export let showModal = false;

	function close() {
		showModal = false;
	}

	// @ts-ignore
	function getTypeColor(type) {
		const typeColors = {
			normal: '#A8A77A',
			fire: '#EE8130',
			water: '#6390F0',
			electric: '#F7D02C',
			grass: '#7AC74C',
			ice: '#96D9D6',
			fighting: '#C22E28',
			poison: '#A33EA1',
			ground: '#E2BF65',
			flying: '#A98FF3',
			psychic: '#F95587',
			bug: '#A6B91A',
			rock: '#B6A136',
			ghost: '#735797',
			dark: '#705746',
			steel: '#B7B7CE',
			fairy: '#D685AD'
		};

		// @ts-ignore
		return typeColors[type] || '#CCCCCC';
	}
</script>

{#if showModal}
	<div class="fixed inset-0 overflow-y-auto">
		<div class="flex items-center justify-center min-h-screen">
			<div class="fixed inset-0 transition-opacity">
				<div class="absolute inset-0 bg-gray-500 opacity-75"></div>
			</div>
			<div
				class="relative bg-white rounded-lg p-4 border border-2 border-red-500 max-h-[80vh] overflow-y-auto"
			>
				<button class="absolute top-0 right-0 p-2 text-xl text-gray-500" on:click={close}
					>&times;</button
				>
				<div class="grid grid-cols-2 gap-4">
					<div class="col-span-1">
						<img
							src={pokemon.sprite}
							alt={pokemon.name}
							class="w-full h-full object-cover border border-2 border-red-500 rounded-lg"
						/>
					</div>
					<div class="col-span-1">
						<h2 class="text-3xl font-bold mb-2">{pokemon.name.toUpperCase()}</h2>
						<p class="text-xl mb-4">Order on the pokédex: {pokemon.number}</p>
						<div class="flex">
							{#each pokemon.types as type}
								<span
									style={`background-color: ${getTypeColor(type)};`}
									class="rounded-full px-4 py-2 mx-1 text-white text-md"
								>
									{type}
								</span>
							{/each}
						</div>
					</div>
					<div class="col-span-1">
						<p class="ml-2 text-sm">Pokémon's base experience: {pokemon.baseExperience}</p>
					</div>
				</div>
				<div class="grid grid-cols-2 gap-4 bg-slate-200 p-2 rounded-md">
                    <p class="text-xl col-span-2 mb-4">Pokémon's moves:</p>
                    {#each pokemon.moves.sort((/** @type {{ level: number; }} */ a, /** @type {{ level: number; }} */ b) => a.level - b.level) as move}
                        <div class="col-span-1 mb-4 bg-white p-2 rounded-md">
                            <p class="text-lg font-bold">{move.name}</p>
                            <p>Method: {move.method.name}</p>
                            <p>Level: {move.level}</p>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>
{/if}
