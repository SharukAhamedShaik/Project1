// script.js
// Adding event listeners and defining functions
document.getElementById('add-task').addEventListener('click', addTask);
function addTask() {
 const taskInput = document.getElementById('new-task');
 const taskText = taskInput.value.trim();
 if (taskText !== "") {
 const taskItem = document.createElement('li');
 taskItem.innerHTML = `<span>${taskText}</span>
 <button onclick="editTask(this)">Edit</button>
 <button onclick="deleteTask(this)">Delete</button>
 <button onclick="completeTask(this)">Complete</button>`;
 document.getElementById('task-list').appendChild(taskItem);
 taskInput.value = "";
 }
}
function completeTask(button) {
 const taskItem = button.parentElement;
 taskItem.classList.toggle('completed');
}
function editTask(button) {
 const taskItem = button.parentElement;
 const taskSpan = taskItem.querySelector('span');
 const newText = prompt("Edit your task:", taskSpan.innerText);
 if (newText) taskSpan.innerText = newText;
}
function deleteTask(button) {
 const taskItem = button.parentElement;
 taskItem.remove();
};