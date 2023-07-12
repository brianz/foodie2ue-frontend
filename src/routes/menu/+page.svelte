<script lang="ts">
	import { TabGroup, Tab, TabAnchor } from '@skeletonlabs/skeleton';
	
	let tabSet: number = 0;

	type Category = {
		id: number;
		name: string;
		menuItems: MenuItem[];
	}
	type AddOn = {
		id: number;
		name: string;
		price: string;
		description: string;
	};

	type MenuItem = {
		created: string;
		description: string;
		id: number;
		name: string;
		slug: string;
		price: string;
		thumbnail: string;
		addons: AddOn[];
		updated: string;
	};


	const burgerMenuItems: MenuItem[] = [
		{
			created: '2023-07-07T19:17:10.278101',
			description: 'Delicious hamburger with one all-American beef patty',
			id: 1,
			name: 'Hamburger',
			slug: 'hamburger',
			price: '8.99',
			thumbnail: 'https://placehold.co/600x400',
			addons: [
				{
					description: 'Add extra cheddar cheese',
					id: 1,
					name: 'Extra cheese',
					price: '0.99'
				},
				{
					description: 'An extra 1/3 lb all-beef patty',
					id: 2,
					name: 'Extra patty',
					price: '2.99'
				},
				{
					description: '',
					id: 3,
					name: 'Extra pickles',
					price: '0.49'
				},
				{
					description: '',
					id: 4,
					name: 'Extra lettuce',
					price: '0.99'
				},
				{
					description: 'Slather on some extra mayonaise goodness',
					id: 5,
					name: 'Extra mayo',
					price: '0.99'
				},
				{
					description: 'Add extra ketchup',
					id: 6,
					name: 'Extra ketchup',
					price: '0.99'
				},
				{
					description: 'Add extra tomatoes',
					id: 7,
					name: 'Extra tomatoes',
					price: '0.99'
				}
			],
			updated: '2023-07-07T19:17:10.278101'
		},
		{
			created: '2023-07-07T19:17:10.309122',
			description: 'Delicious hamburger with one all-American beef patty with cheese',
			id: 2,
			name: 'Cheeseburger',
			slug: 'cheeseburger',
			price: '9.99',
			thumbnail: 'https://placehold.co/600x400',
			addons: [
				{
					description: 'Add extra cheddar cheese',
					id: 1,
					name: 'Extra cheese',
					price: '0.99'
				},
				{
					description: 'An extra 1/3 lb all-beef patty',
					id: 2,
					name: 'Extra patty',
					price: '2.99'
				},
				{
					description: '',
					id: 3,
					name: 'Extra pickles',
					price: '0.49'
				},
				{
					description: '',
					id: 4,
					name: 'Extra lettuce',
					price: '0.99'
				},
				{
					description: 'Slather on some extra mayonaise goodness',
					id: 5,
					name: 'Extra mayo',
					price: '0.99'
				},
				{
					description: 'Add extra ketchup',
					id: 6,
					name: 'Extra ketchup',
					price: '0.99'
				},
				{
					description: 'Add extra tomatoes',
					id: 7,
					name: 'Extra tomatoes',
					price: '0.99'
				}
			],
			updated: '2023-07-07T19:17:10.309122'
		},
		{
			created: '2023-07-07T19:17:10.328264',
			description: 'Delicious hamburger with one all-American beef patty, cheese and bacon',
			id: 3,
			name: 'Bacon cheeseburger',
			slug: 'bacon-cheeseburger',
			price: '11.99',
			thumbnail: 'https://placehold.co/600x400',
			addons: [
				{
					description: 'Add extra cheddar cheese',
					id: 1,
					name: 'Extra cheese',
					price: '0.99'
				},
				{
					description: 'An extra 1/3 lb all-beef patty',
					id: 2,
					name: 'Extra patty',
					price: '2.99'
				},
				{
					description: '',
					id: 3,
					name: 'Extra pickles',
					price: '0.49'
				},
				{
					description: '',
					id: 4,
					name: 'Extra lettuce',
					price: '0.99'
				},
				{
					description: 'Slather on some extra mayonaise goodness',
					id: 5,
					name: 'Extra mayo',
					price: '0.99'
				},
				{
					description: 'Add extra ketchup',
					id: 6,
					name: 'Extra ketchup',
					price: '0.99'
				},
				{
					description: 'Add extra tomatoes',
					id: 7,
					name: 'Extra tomatoes',
					price: '0.99'
				}
			],
			updated: '2023-07-07T19:17:10.328264'
		}
	]

	const sandwichMenuItems: MenuItem[] = [
		{
			created: '2023-07-07T19:17:10.348026',
			description: 'A grilled cheese sandwich with cheddar cheese',
			id: 4,
			name: 'Grilled cheese',
			slug: 'grilled-cheese',
			price: '7.99',
			thumbnail: 'https://placehold.co/600x400',
			addons: [
				{
					description: 'Add extra cheddar cheese',
					id: 1,
					name: 'Extra cheese',
					price: '0.99'
				}
			],
			updated: '2023-07-07T19:17:10.348026'
		}
	]

	const fryMenuItems: MenuItem[] = [
		{
			addons: [],
			created: '2023-07-07T19:17:10.369814',
			description: 'Yummy freedom/french fries',
			id: 5,
			name: 'Small - French fries',
			slug: 'small-french-fries',
			thumbnail: 'https://placehold.co/600x400',
			updated: '2023-07-07T19:17:10.369814',
			price: '0.99'
		},
		{
			addons: [],
			created: '2023-07-07T19:17:10.369814',
			description: 'Yummy freedom/french fries',
			id: 5,
			name: 'Medium - French fries',
			slug: 'medium-french-fries',
			thumbnail: 'https://placehold.co/600x400',
			updated: '2023-07-07T19:17:10.369814',
			price: '1.29'
		},
		{
			addons: [],
			created: '2023-07-07T19:17:10.369814',
			description: 'Yummy freedom/french fries',
			id: 5,
			name: 'Large - French fries',
			slug: 'large-french-fries',
			thumbnail: 'https://placehold.co/600x400',
			updated: '2023-07-07T19:17:10.369814',
			price: '1.49'
		}
		
	]

	const categories: Category[] = [
		{
			id: 1,
			name: 'Burgers',
			menuItems: burgerMenuItems
		},
		{
			id: 2,
			name: 'Sandwich',
			menuItems: sandwichMenuItems
		},
		{
			id: 2,
			name: 'Fries',
			menuItems: fryMenuItems
		}
	]
</script>


<TabGroup>
	<Tab bind:group={tabSet} name="burgers" value={0}>
		<svelte:fragment slot="lead">burgers</svelte:fragment>
	</Tab>
	<Tab bind:group={tabSet} name="sandwiches" value={1}>sandwiches</Tab>
	<Tab bind:group={tabSet} name="fries" value={2}>fries</Tab>
	<!-- Tab Panels --->
	<svelte:fragment slot="panel">
		{#if tabSet === 0}
			<!-- Burger Menu Items -->
				<div class="flex flex-col place-items-center">
					{#each burgerMenuItems as item}
						<div class="card variant-glass-primary w-96 mb-4 first:mt-4">
							<header class="card-header text-2xl font-bold">{item.name}</header>
							<section class="p-4 text-center">
								<img src={item.thumbnail} alt={item.name} />
								{item.description}
							</section>
							<footer class="card-footer justify-right">
								{#if item.sizes}
									{#each item.sizes as size}
										<button type="button" class="btn variant-filled">
											<span
												><svg
													xmlns="http://www.w3.org/2000/svg"
													viewBox="0 0 24 24"
													fill="currentColor"
													class="w-6 h-6"
												>
													<path
														fill-rule="evenodd"
														d="M7.5 6v.75H5.513c-.96 0-1.764.724-1.865 1.679l-1.263 12A1.875 1.875 0 004.25 22.5h15.5a1.875 1.875 0 001.865-2.071l-1.263-12a1.875 1.875 0 00-1.865-1.679H16.5V6a4.5 4.5 0 10-9 0zM12 3a3 3 0 00-3 3v.75h6V6a3 3 0 00-3-3zm-3 8.25a3 3 0 106 0v-.75a.75.75 0 011.5 0v.75a4.5 4.5 0 11-9 0v-.75a.75.75 0 011.5 0v.75z"
														clip-rule="evenodd"
													/>
												</svg>
											</span>
											{size.name} - ${size.price}
										</button>
									{/each}
								{:else}
									<button type="button" class="btn variant-filled">
										<span
											><svg
												xmlns="http://www.w3.org/2000/svg"
												viewBox="0 0 24 24"
												fill="currentColor"
												class="w-6 h-6"
											>
												<path
													fill-rule="evenodd"
													d="M7.5 6v.75H5.513c-.96 0-1.764.724-1.865 1.679l-1.263 12A1.875 1.875 0 004.25 22.5h15.5a1.875 1.875 0 001.865-2.071l-1.263-12a1.875 1.875 0 00-1.865-1.679H16.5V6a4.5 4.5 0 10-9 0zM12 3a3 3 0 00-3 3v.75h6V6a3 3 0 00-3-3zm-3 8.25a3 3 0 106 0v-.75a.75.75 0 011.5 0v.75a4.5 4.5 0 11-9 0v-.75a.75.75 0 011.5 0v.75z"
													clip-rule="evenodd"
												/>
											</svg>
										</span>
										${item.price}
									</button>
								{/if}
							</footer>
						</div>
					{/each}
				</div>
		{:else if tabSet === 1}
			<!-- Sandwich Menu Items -->
			<div class="flex flex-col place-items-center">
				{#each sandwichMenuItems as item}
					<div class="card variant-glass-primary w-96 mb-4 first:mt-4">
						<header class="card-header text-2xl font-bold">{item.name}</header>
						<section class="p-4 text-center">
							<img src={item.thumbnail} alt={item.name} />
							{item.description}
						</section>
						<footer class="card-footer justify-right">
							{#if item.sizes}
								{#each item.sizes as size}
									<button type="button" class="btn variant-filled">
										<span
											><svg
												xmlns="http://www.w3.org/2000/svg"
												viewBox="0 0 24 24"
												fill="currentColor"
												class="w-6 h-6"
											>
												<path
													fill-rule="evenodd"
													d="M7.5 6v.75H5.513c-.96 0-1.764.724-1.865 1.679l-1.263 12A1.875 1.875 0 004.25 22.5h15.5a1.875 1.875 0 001.865-2.071l-1.263-12a1.875 1.875 0 00-1.865-1.679H16.5V6a4.5 4.5 0 10-9 0zM12 3a3 3 0 00-3 3v.75h6V6a3 3 0 00-3-3zm-3 8.25a3 3 0 106 0v-.75a.75.75 0 011.5 0v.75a4.5 4.5 0 11-9 0v-.75a.75.75 0 011.5 0v.75z"
													clip-rule="evenodd"
												/>
											</svg>
										</span>
										{size.name} - ${size.price}
									</button>
								{/each}
							{:else}
								<button type="button" class="btn variant-filled">
									<span
										><svg
											xmlns="http://www.w3.org/2000/svg"
											viewBox="0 0 24 24"
											fill="currentColor"
											class="w-6 h-6"
										>
											<path
												fill-rule="evenodd"
												d="M7.5 6v.75H5.513c-.96 0-1.764.724-1.865 1.679l-1.263 12A1.875 1.875 0 004.25 22.5h15.5a1.875 1.875 0 001.865-2.071l-1.263-12a1.875 1.875 0 00-1.865-1.679H16.5V6a4.5 4.5 0 10-9 0zM12 3a3 3 0 00-3 3v.75h6V6a3 3 0 00-3-3zm-3 8.25a3 3 0 106 0v-.75a.75.75 0 011.5 0v.75a4.5 4.5 0 11-9 0v-.75a.75.75 0 011.5 0v.75z"
												clip-rule="evenodd"
											/>
										</svg>
									</span>
									${item.price}
								</button>
							{/if}
						</footer>
					</div>
				{/each}
			</div>
		{:else if tabSet === 2}
			<!-- Fry Menu Items -->
			<div class="flex flex-col place-items-center">
				{#each fryMenuItems as item}
					<div class="card variant-glass-primary w-96 mb-4 first:mt-4">
						<header class="card-header text-2xl font-bold">{item.name}</header>
						<section class="p-4 text-center">
							<img src={item.thumbnail} alt={item.name} />
							{item.description}
						</section>
						<footer class="card-footer justify-right">
							{#if item.sizes}
								{#each item.sizes as size}
									<button type="button" class="btn variant-filled">
										<span
											><svg
												xmlns="http://www.w3.org/2000/svg"
												viewBox="0 0 24 24"
												fill="currentColor"
												class="w-6 h-6"
											>
												<path
													fill-rule="evenodd"
													d="M7.5 6v.75H5.513c-.96 0-1.764.724-1.865 1.679l-1.263 12A1.875 1.875 0 004.25 22.5h15.5a1.875 1.875 0 001.865-2.071l-1.263-12a1.875 1.875 0 00-1.865-1.679H16.5V6a4.5 4.5 0 10-9 0zM12 3a3 3 0 00-3 3v.75h6V6a3 3 0 00-3-3zm-3 8.25a3 3 0 106 0v-.75a.75.75 0 011.5 0v.75a4.5 4.5 0 11-9 0v-.75a.75.75 0 011.5 0v.75z"
													clip-rule="evenodd"
												/>
											</svg>
										</span>
										{size.name} - ${size.price}
									</button>
								{/each}
							{:else}
								<button type="button" class="btn variant-filled">
									<span
										><svg
											xmlns="http://www.w3.org/2000/svg"
											viewBox="0 0 24 24"
											fill="currentColor"
											class="w-6 h-6"
										>
											<path
												fill-rule="evenodd"
												d="M7.5 6v.75H5.513c-.96 0-1.764.724-1.865 1.679l-1.263 12A1.875 1.875 0 004.25 22.5h15.5a1.875 1.875 0 001.865-2.071l-1.263-12a1.875 1.875 0 00-1.865-1.679H16.5V6a4.5 4.5 0 10-9 0zM12 3a3 3 0 00-3 3v.75h6V6a3 3 0 00-3-3zm-3 8.25a3 3 0 106 0v-.75a.75.75 0 011.5 0v.75a4.5 4.5 0 11-9 0v-.75a.75.75 0 011.5 0v.75z"
												clip-rule="evenodd"
											/>
										</svg>
									</span>
									${item.price}
								</button>
							{/if}
						</footer>
					</div>
				{/each}
			</div>
		{/if}
	</svelte:fragment>
</TabGroup>
			

<dl class="list-dl">
	<!-- <div> -->
	<!-- 	<span class="badge bg-primary-500">💀</span> -->
	<!-- 	<span class="flex-auto"> -->
	<!-- 		<dt>{item.name}</dt> -->
	<!-- 		<dd>{item.description}</dd> -->
	<!-- 		{#if item.size} -->
	<!-- 			<dd>{item.size}</dd> -->
	<!-- 		{/if} -->
	<!-- 		<span>${item.price}</span> -->
	<!-- 	</span> -->
	<!-- </div> -->
	<!--  -->
</dl>
