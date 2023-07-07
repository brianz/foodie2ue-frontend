<script lang="ts">
	const menuItems = [
		{ id: 1, name: 'Hamburger' },
		{ id: 2, name: 'Cheeseburger' },
		{ id: 3, name: 'French Fries' },
		{ id: 4, name: 'Onion rings' }
	];
</script>

<h1>This is the Menu header</h1>

<dl class="list-dl">
	<dd>Description</dd>
	{#each menuItems as item}
		<div>
			<span class="badge bg-primary-500">💀</span>
			<span class="flex-auto">
				<dt>{item.name}</dt>
			</span>
		</div>
	{/each}
</dl>
