<script lang="ts">
type Todo = {
	id: number;
	name: string;
	deleted: boolean;
	createdAt: string;
	updatedAt: string;
	completed: boolean;
};

let todos: Todo[] = $state([]);
let form_state = $state({name: ''})

function onsubmit(e: Event) {
	e.preventDefault();
}
</script>


<form method="POST" {onsubmit}>
<label for="name">Todo:</label>
<input type="text" name="name" bind:value={form_state.name} />
<button type="submit">+ Add</button>
</form>

<ul>
	{#each todos as todo }
		<li>
			{todo}
		</li>
	{/each}
</ul>