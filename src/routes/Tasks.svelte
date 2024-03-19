<script lang="ts">
	export let tasks = ['clean the kitchen'];
	export let updateTasks = (data: string[]) => {};

	function deleteTask(index: number) {
		tasks.splice(index, 1);
		tasks = tasks;
		updateTasks(tasks);
		console.log('called');
	}
</script>

<ul>
	{#each tasks as task, index (task)}
		<li>
			{index + 1}: {task}
			<button on:click={() => deleteTask(index)}>delete</button>
		</li>
	{/each}
</ul>
