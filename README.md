# To-do-list-project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            margin: 50px;
        }
        .container {
            max-width: 400px;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin: auto;
        }
        input {
            width: 70%;
            padding: 8px;
            margin: 10px 0;
        }
        button {
            padding: 8px 15px;
            background-color: #28a745;
            color: white;
            border: none;
            cursor: pointer;
        }
        ul {
            list-style: none;
            padding: 0;
        }
        li {
            padding: 8px;
            background: #ddd;
            margin: 5px 0;
            display: flex;
            justify-content: space-between;
        }
        .delete {
            background: red;
            color: white;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>To-Do List</h2>
        <input type="text" id="task" placeholder="Add a new task...">
        <button onclick="addTask()">Add</button>
        <ul id="taskList"></ul>
    </div>

    <script>
        function addTask() {
            let taskInput = document.getElementById("task");
            let taskValue = taskInput.value.trim();
            if (taskValue === "") return;
            
            let li = document.createElement("li");
            li.innerHTML = `${taskValue} <button class='delete' onclick='removeTask(this)'>X</button>`;
            document.getElementById("taskList").appendChild(li);
            
            taskInput.value = "";
        }
        
        function removeTask(button) {
            button.parentElement.remove();
        }
    </script>
</body>
</html>
