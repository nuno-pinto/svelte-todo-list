<script lang="ts">
	import Form from './Form.svelte';
	import Tasks from './Tasks.svelte';

	let tasks = ['build a compiler', 'finish this project', 'learn how to dunk', 'another task'];

	function updateTasks(data: string[]) {
		tasks = data;
	}
</script>

<h1>To-do List</h1>

<Form {tasks} {updateTasks} />

<Tasks {tasks} {updateTasks} />
