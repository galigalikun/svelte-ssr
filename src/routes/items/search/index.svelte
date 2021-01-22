<script context="module" lang="ts">
	export async function preload() {
		const res = await this.fetch(`todo`);
		const data = await res.json() as {
			total:number;
			items: {
				_source: {
					item_id: string;
					title: string;
				}
			}[];
		};
		return { items: data.items };
	}
</script>

<script lang="ts">
	export let items: {
				_source: {
					item_id: string;
					title: string;
				}
			}[];
</script>

<svelte:head>
	<title>商品検索!!!</title>
</svelte:head>

<h1>About this site</h1>

<ul>
	{#each items as item}
		<!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
		<li><a rel="prefetch" href="items/item/{item._source.item_id}">{item._source.title}</a></li>
	{/each}
</ul>
