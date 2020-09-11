# Responsive Svelte + Tailwind Pagination component

Simple pagination component built with svelte and tailwindcss 

## Installation
```bash
    $npm i @fouita/pagination -D
```

## Simple usage

![fouita pagination](https://cdn.fouita.com/assets/pics/template/pagination/pagination-simple.png)

```html
<script>
    import Pagination from '@fouita/pagination'
    let current =1
    let num_items=30
    let per_page=3
</script>

<Pagination bind:current={current} {num_items} {per_page} />
```

## Style rounded

![fouita pagination rounded](https://cdn.fouita.com/assets/pics/template/pagination/pagination-rounded.png)

```html
<Pagination rounded bind:current={current} {num_items} {per_page} />
```


## Change Size to small

![fouita pagination small](https://cdn.fouita.com/assets/pics/template/pagination/pagination-small.png)

```html
<Pagination small rounded bind:current={current} {num_items} {per_page} />
```

## Change Color

You can use a color from tailwindcss list `(gray, red, blue, indigo, pink, purple, teal, orange, yellow)`

![fouita pagination small](https://cdn.fouita.com/assets/pics/template/pagination/pagination-color.png)

```html
<Pagination small rounded color="pink" bind:current={current} {num_items} {per_page} />
```


## Per page selection

You can add

![fouita pagination selection](https://cdn.fouita.com/assets/pics/template/pagination/pagination_per_page.png)

```html
<script>
	import Pagination from '@fouita/pagination'

	let current =1
	let num_items=30
	let per_page=3	
</script>
	
<div class="flex justify-between items-center">
	<div class="flex items-center">
		Per page:
		<select class="border px-2 rounded ml-2" bind:value={per_page}>
			<option>3</option>
			<option>5</option>
			<option>10</option>
		</select>
	</div>
	<Pagination small  bind:current={current} {num_items} per_page={per_page} />
</div>			  
```

## Navigate Action

if you like to perform some actions or API requests when navigating through pages, you can do so by calling `on:navigate` event.

```html
<script>
	import Pagination from '@fouita/pagination'

	let current =1
	let num_items=30
	let per_page=3	
	
	// let list_fetch = ... your init data
	async function changePage(evt){
		current = evt.detail
		// list_fetched = ... FETCH DATA HERE
	}
</script>

<Pagination small {current} {num_items} per_page={per_page} on:navigate={changePage} />
```


## About

[Fouita : UI framework for svelte + tailwind components](https://fouita.com)
