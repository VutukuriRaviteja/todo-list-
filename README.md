# todo-list-
<!DOCTYPE html>
<html>
<head>
	<title>Todo List</title>
	<style>
		/* Add some basic styles for the list */
		ul {
			list-style-type: none;
			padding: 0;
		}
		li {
			padding: 5px;
			margin: 5px 0;
			border: 1px solid black;
			background-color: #eee;
			display: flex;
			align-items: center;
			justify-content: space-between;
		}
		li button {
			background-color: red;
			color: white;
			border: none;
			padding: 5px;
			border-radius: 3px;
			cursor: pointer;
		}
	</style>
</head>
<body>
	<h1>Todo List</h1>
	<input type="text" id="taskInput" placeholder="Add new task">
	<button onclick="addTask()">Add</button>
	<ul id="taskList"></ul>

	<script>
		// Define a function to add a new task to the list
		function addTask() {
			// Get the input field and its value
			var inputField = document.getElementById("taskInput");
			var task = inputField.value;

			// Clear the input field
			inputField.value = "";

			// Create a new list item and its delete button
			var listItem = document.createElement("li");
			var taskText = document.createTextNode(task);
			var deleteButton = document.createElement("button");
			var buttonText = document.createTextNode("Delete");

			// Add the task text and delete button to the list item
			listItem.appendChild(taskText);
			deleteButton.appendChild(buttonText);
			listItem.appendChild(deleteButton);

			// Add an event listener to the delete button to remove the task when clicked
			deleteButton.addEventListener("click", function() {
				listItem.parentNode.removeChild(listItem);
			});

			// Add the new list item to the task list
			var taskList = document.getElementById("taskList");
			taskList.appendChild(listItem);
		}
	</script>
</body>
</html>
