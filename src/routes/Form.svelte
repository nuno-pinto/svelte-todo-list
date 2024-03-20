<script lang="ts">
	export let tasks = ['clean the kitchen'];
	export let updateTasks = (data: string[]) => {};

	let task = '';

	function validateTask(task: string) {
		if (task === '') {
			alert('Task cannot be empty');
			return false;
		}

		if (tasks.includes(task)) {
			alert('Task already exists');
			return false;
		}

		return true;
	}

	function addTask(task: string) {
		if (!validateTask(task)) {
			return;
		}

		tasks = [...tasks, task];

		updateTasks(tasks);
	}
</script>

<form>
	<input bind:value={task} type="text" placeholder="Add a task" />
	<button on:click={() => addTask(task)}>Add task</button>
</form>
